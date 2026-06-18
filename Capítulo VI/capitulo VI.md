# Capítulo VI: Product Verification & Validation

## 6.1. Testing Suites & Validation

La verificación del backend de **Centralis** (`web-service`, Spring Boot 3.5.5 / Java 24) se organiza en cuatro suites complementarias, cada una con un propósito distinto dentro de la pirámide de pruebas. Todas las pruebas se ejecutan con `./mvnw.cmd test` y validan **únicamente comportamiento realmente implementado**, trazado a las User Stories (US) del backlog del proyecto.

| Suite | Nivel | Aísla | Tecnología | Pruebas |
|---|---|---|---|---|
| Unit Tests | Dominio puro | Sin Spring, sin BD | JUnit 5 + Mockito | 43 |
| Integration Tests | Aplicación + persistencia | Spring real + H2 | `@SpringBootTest` + JPA | 12 |
| Behavior-Driven Development | Especificación de negocio | — | Cucumber (Gherkin español) | 5 features / 14 escenarios |
| System Tests | Sistema completo | App en puerto real | JUnit Platform Suite + `TestRestTemplate` | 1 runner |

**Convenciones transversales (rúbrica de testing):**

- Cada prueba lleva un `@DisplayName` descriptivo en español y sigue el patrón **AAA** (Arrange / Act / Assert).
- Cada prueba documenta su justificación de negocio mediante un comentario `// Business / User Story Rational (USxx): ...`.
- **No se prueban validaciones de parámetros de DTO** (`@Valid`, bean-validation); el foco está en invariantes y reglas de negocio del dominio.
- Alcance: cinco contextos acotados principales — **announcement, event, chat, company, iam**. Los contextos `notification`, `dashboard` y `profile` quedan fuera del alcance de las suites.
- **Notificaciones / Firebase (FCM)** se mockean (`@MockBean FirebaseConfiguration`, `@MockBean FirebaseCloudMessagingService`) para que el contexto arranque de forma hermética sin credenciales y sin efectos externos.

---

### 6.1.1. Core Entities Unit Tests

Las pruebas unitarias verifican las **invariantes y el comportamiento de los agregados y value objects del dominio**, sin levantar el contexto de Spring ni acceder a base de datos. Cubren las ocho categorías de la rúbrica: *happy path*, límites superior/inferior, excepción por datos insuficientes, excepción por estado inválido, condicionales A/B e integridad de datos.

Ubicación: `src/test/java/synera/centralis/api/<contexto>/unit/<Contexto>UnitTest.java`.

**Announcement — `AnnouncementUnitTest` (10 pruebas, US10–US13)**

Prueba el agregado `Announcement` y el value object `Priority`.

| Categoría | Prueba | US |
|---|---|---|
| Happy | Publicar un anuncio válido queda registrado | US10 |
| Límite superior | Título de exactamente 200 caracteres es aceptado | US10 |
| Límite superior | Título de 201 caracteres es rechazado | US10 |
| Límite superior | Descripción de 5001 caracteres es rechazada | US10 |
| Datos insuficientes | Descripción nula impide crear el anuncio | US10 |
| Estado inválido | No se puede degradar la prioridad a nula | US11 |
| Condicional A | Un anuncio HIGH o URGENT se considera destacado | US11 |
| Condicional B | Solo URGENT dispara la urgencia | US11 |
| Integridad | Editar un anuncio actualiza y recorta sus campos | US12 |
| Integridad | `Priority` no admite nivel nulo | US11 |

**Evidencia de ejecución:** https://imgur.com/a/wGVawnE

![img_6.png](https://i.imgur.com/w7SLwCE.jpeg)

Nota: Se muestra la ejecución exitosa de la suite de pruebas del proyecto centralis, la cual valida la integridad y el comportamiento esperado de los agregados del dominio, incluyendo Announcement, Event y Chat.

**Event — `EventUnitTest` (8 pruebas, US18–US21)**

Prueba las invariantes del agregado `Event`.

| Categoría | Prueba | US |
|---|---|---|
| Happy | Crear un evento con un invitado queda registrado | US18 |
| Límite superior | Título de 200 caracteres es aceptado | US18 |
| Límite superior | Descripción de 1001 caracteres es rechazada | US18 |
| Límite inferior / datos insuficientes | Un evento sin invitados es inválido | US18 |
| Estado inválido | No se puede agregar un invitado nulo | US18 |
| Condicional A | Editar solo la fecha conserva el resto de datos | US20 |
| Condicional B | `isRecipient` distingue invitados de no invitados | US18 |
| Integridad | Agregar y quitar invitados ajusta el conteo | US20 |

**Evidencia de ejecución:** https://imgur.com/a/JRTadpa

![img_8.png](https://i.imgur.com/djhZ9ei.jpeg)

Nota: Se muestra la ejecución exitosa de la suite de pruebas del proyecto centralis, la cual valida la integridad y el comportamiento esperado de los agregados del dominio, incluyendo Announcement, Event y Chat.

**Chat — `ChatUnitTest` (9 pruebas, US23–US28)**

Prueba el agregado `Group`, incluida la conversación directa.

| Categoría | Prueba | US |
|---|---|---|
| Happy | Crear un grupo agrega al creador automáticamente | US23 |
| Límite superior | Nombre de 101 caracteres es rechazado | US23 |
| Límite inferior | No se puede quitar al último miembro | US24/US28 |
| Estado inválido | No se puede agregar un miembro duplicado | US23 |
| Estado inválido | No se puede quitar a un no miembro | US24 |
| Datos insuficientes | Conversación directa consigo mismo es inválida | US25 |
| Condicional A | Una conversación directa se marca como directa | US25 |
| Condicional B | Actualizar solo el nombre conserva la visibilidad | US23 |
| Integridad | Agregar un miembro nuevo incrementa el conteo | US23 |

**Evidencia de ejecución:** https://imgur.com/a/bJBJQyE

![img_7.png](https://i.imgur.com/No6oLI0.jpeg)

Nota: Se muestra la ejecución exitosa de la suite de pruebas del proyecto centralis, la cual valida la integridad y el comportamiento esperado de los agregados del dominio, incluyendo Announcement, Event y Chat.

**Landing Page & Mobile**

Para la elaboración de los principales tests de nuestra Landing Page (**Centralis**) y nuestra aplicación móvil, hemos tenido en cuenta las secciones más importantes que garantizan la correcta navegación y propuesta de valor para el usuario:

* **Features:** Verificación de la visibilidad de las funcionalidades clave para la alineación de equipos.
* **How it works:** Validación del flujo de información sobre el funcionamiento del hub centralizado.
* **Product / Help Center:** Comprobación de los accesos a la documentación y soporte.
* **Sign In / Get Started:** Test de interactividad de los botones de llamada a la acción (Call to Action).

Para la **Landing Page**, gracias a la herramienta de **Selenium IDE**, se han logrado realizar los tests funcionales que aseguran que cada elemento de la interfaz responda correctamente a las acciones del usuario. Por otro lado, para el entorno **Mobile**, se ha implementado **Patrol** como framework de pruebas E2E, permitiendo validar la interacción real y el comportamiento de la interfaz en dispositivos móviles.

![img_1.png](https://i.imgur.com/f9OSU7T.png)

---

### 6.1.2. Core Integration Tests

**Announcement Integration Tests**

| Contexto | Prueba | Verifica | US |
|---|---|---|---|
| Announcement | Publicar y consultar anuncio | Persistencia real + recuperación por listado | US10 |
| Announcement | Listado aislado por compañía | **Multi-tenant**: cada empresa solo ve lo suyo | US10 |

**Evidencia de ejecución:** https://imgur.com/a/9QHjfFb

![img_9.png](https://i.imgur.com/6538moV.png)

Esta sección documenta la validación de la capa de servicios de aplicación. El componente AnnouncementCommandServiceImpl (ver imagen abajo) gestiona las operaciones de comando para los anuncios, asegurando la integridad transaccional mediante @Transactional y la correcta inyección de repositorios.

La ejecución de las pruebas integradas confirma que la lógica de negocio, incluyendo la publicación de eventos (UrgentAnnouncementCreatedEvent) y la persistencia en base de datos H2, se comporta según lo definido en el dominio.

**Chat Integration Tests**

| Contexto | Prueba | Verifica | US |
|---|---|---|---|
| Chat | Crear y consultar grupo | Persistencia + creador como miembro | US23 |
| Chat | Grupo aislado por compañía | Inaccesible desde otro tenant | US23 |

**Evidencia de ejecución:** https://imgur.com/a/4xP59S1

![img_10.png](https://i.imgur.com/FYJk9yc.png)

La ejecución de la suite de pruebas integradas valida que la lógica de negocio para la creación de mensajes y la verificación de membresía en grupos se integra correctamente con la capa de persistencia y el sistema de eventos.

**Event Integration Tests**

| Contexto | Prueba | Verifica | US |
|---|---|---|---|
| Event | Crear y consultar evento | Persistencia con sus invitados | US18 |
| Event | Eventos aislados por compañía | Aislamiento por tenant | US18 |

**Evidencia de ejecución:** https://imgur.com/a/MOHCHsc

![img_11.png](https://i.imgur.com/B8iSVUZ.png)

La ejecución de las pruebas integradas valida que la lógica para registrar invitados y gestionar fechas se integra correctamente, asegurando que las restricciones de dominio (como la validación de invitados nulos) se cumplan durante la persistencia.

**Landing Page test**

Se realizó un test automatizado utilizando Selenium IDE para verificar el correcto funcionamiento de la landing page de Centralis. El objetivo del test fue asegurarse de que los elementos clave de la página, como el título principal, la navegación y los botones de acción ("Get Started", "Explore Features"), se cargaran correctamente y fueran interactivos, garantizando una experiencia de usuario óptima.

![img_2.png](https://i.imgur.com/i6lbpD6.png)

**Mobile test**

Se realizó un test automatizado utilizando Patrol para verificar el correcto funcionamiento de la interfaz móvil de la aplicación. El objetivo del test fue asegurar que los elementos clave de la página, el inicio de sesión y los botones de navegación interna se cargaran correctamente y fueran interactivos en dispositivos móviles, validando la experiencia de usuario y la respuesta de la interfaz bajo condiciones de uso real.

![img_3.png](https://i.imgur.com/yfNT8Dl.png)

**User CRUD (Consultants/Clients)**

Se realizó un test automatizado para verificar el funcionamiento del CRUD de los usuarios principales (Consultores y Clientes), asegurando que el proceso de crear, leer, actualizar y eliminar los registros se realice correctamente. El test abarcó la funcionalidad de un usuario que gestiona su perfil, edita su información de contacto y elimina entradas, todo esto con el objetivo de garantizar que la plataforma maneje los datos de manera eficiente y sin errores.

![img_4.png](https://i.imgur.com/2bxlkll.png)

**Appointment / Agenda CRUD**

Se realizó un test automatizado para validar el correcto funcionamiento del sistema de gestión de agendas y citas de Centralis, asegurando que los usuarios puedan registrar, visualizar, actualizar y eliminar sus compromisos o reuniones sin inconvenientes. Este test garantizó que los integrantes del equipo puedan interactuar con el calendario de forma fluida.

![img_5.png](https://i.imgur.com/O8rNdTX.png)

---

### 6.1.3. Core Behavior-Driven Development

El desarrollo guiado por comportamiento (BDD) expresa los criterios de aceptación de las User Stories como **especificaciones ejecutables en Gherkin español** (`# language: es`). Cada feature usa `Característica:`, escenarios `Dado/Cuando/Entonces/Y` y se vincula a su US en la cabecera.

Ubicación: `src/test/resources/synera/centralis/api/cucumber/`. Los archivos siguen el patrón `USxx-Titulo.feature`:

| Feature | US | Escenarios | Técnica destacada |
|---|---|---|---|
| `US10-Publicacion-basica-de-anuncios.feature` | US10, US11 | 1 + Esquema (3 ejemplos) | `Esquema del escenario` + `Ejemplos` con prioridades NORMAL/HIGH/URGENT |
| `US18-Creacion-basica-de-eventos.feature` | US18, US34 | 2 | `Data Table` de invitados + escenario de denegación por rol |
| `US23-Creacion-de-chats-grupales.feature` | US23 | 2 | `Data Table` de miembros (grupo público y privado) |
| `US41-Registro-de-nueva-compania.feature` | US41 | 1 + Esquema (3 ejemplos) | `Esquema del escenario` + `Ejemplos` con distintos RUC |
| `US34-Restringir-el-acceso-a-la-API.feature` | US34 | 2 | Acceso autenticado vs. solicitud sin token |

Cumplimiento de la rúbrica: ≥2 features con `Esquema del escenario` + `Ejemplos` (announcement, company), ≥2 features con `Data Table` (event, chat). Los decimales, cuando aplican, se manejan como `String` y no como `{double}`.

Ejemplo (`US10-Publicacion-basica-de-anuncios.feature`):

```gherkin
# language: es
Característica: Publicación de anuncios

  Esquema del escenario: Publicar anuncios con distintas prioridades
    Dado que el gerente ha iniciado sesión para publicar anuncios
    Cuando publica un anuncio con título "<titulo>" y prioridad "<prioridad>"
    Entonces el anuncio se guarda correctamente
    Y la prioridad registrada es "<prioridad>"

    Ejemplos:
      | titulo            | prioridad |
      | Aviso general     | NORMAL    |
      | Cambio de horario | HIGH      |
      | Evacuación        | URGENT    |
```

Las *step definitions* (`<Contexto>StepDefinitions`) usan anotaciones Cucumber en español (`@Dado`, `@Cuando`, `@Entonces`, `@Y`) y heredan de `AbstractCucumberSteps`, que centraliza la autenticación simulada y las llamadas HTTP.

Ejemplo (US18-Creacion-basica-de-eventos.feature):
```gherkin

# language: es
Característica: Creación básica de eventos

Esquema del escenario: Registrar eventos con distintas fechas
Dado que el gerente ha iniciado sesión para crear eventos
Cuando registra un evento con título "<titulo>" y fecha "<fecha>"
Entonces el evento se guarda correctamente
Y la fecha registrada es "<fecha>"

Ejemplos:
| titulo               | fecha      |
| Capacitación técnica | 2026-06-15 |
| Reunión directorio   | 2026-06-20 |
Ejemplo (US18-Creacion-basica-de-eventos.feature):

```
Nota: Las step definitions (EventStepDefinitions) usan anotaciones en español (@Dado, @Cuando, @Entonces, @Y) y heredan de AbstractCucumberSteps.

Ejemplo (US23-Creacion-de-chats-grupales.feature):
```gherkin

# language: es
Característica: Creación de chats grupales

Esquema del escenario: Crear grupos de chat según visibilidad
Dado que el empleado ha iniciado sesión para crear un grupo
Cuando crea un grupo con nombre "<nombre>" y visibilidad "<visibilidad>"
Entonces el grupo se registra correctamente
Y el estado del grupo es "<visibilidad>"

Ejemplos:
| nombre      | visibilidad |
| Equipo IT   | PUBLICO     |
| Gerencia    | PRIVADO     |
```
Nota: Las step definitions (ChatStepDefinitions) usan anotaciones en español (@Dado, @Cuando, @Entonces, @Y) y heredan de AbstractCucumberSteps.

Ejemplo (US34-Restringir-el-acceso-a-la-API.feature):
```gherkin
# language: es
Característica: Restringir el acceso a la API

Esquema del escenario: Validar intentos de acceso no autorizado
  Dado que existe una solicitud hacia un endpoint "<endpoint>"
  Cuando el usuario intenta acceder sin token válido
  Entonces el sistema deniega el acceso
  Y responde con estado "<codigo>"

Ejemplos:
| endpoint      | codigo |
| /api/v1/chat  | 403    |
| /api/v1/event | 403    |
```
Nota: Las step definitions (SecurityStepDefinitions) usan anotaciones en español (@Dado, @Cuando, @Entonces, @Y) y heredan de AbstractCucumberSteps.

Ejemplo (US41-Registro-de-nueva-compania.feature):
```gherkin
# language: es
Característica: Registro de nueva compañía

  Esquema del escenario: Registrar nueva empresa exitosamente
    Dado que un usuario desea registrar una nueva compañía
    Cuando ingresa el nombre "<nombre>" y sector "<sector>"
    Entonces la compañía se registra correctamente
    Y el sector registrado es "<sector>"

    Ejemplos:
      | nombre       | sector       |
      | TechSol S.A. | Tecnología   |
      | BioLife      | Salud        |
```
Nota: Las step definitions (CompanyStepDefinitions) usan anotaciones en español (@Dado, @Cuando, @Entonces, @Y) y heredan de AbstractCucumberSteps.

### 6.1.4. Core System Tests

En esta sección se detallan las pruebas de sistema realizadas para validar la integridad de la plataforma **Centralis** en su totalidad. Estas evaluaciones aseguran que la interacción entre la aplicación móvil y los servicios de backend operen correctamente bajo escenarios de uso real, cubriendo flujos completos de navegación y sincronización de datos.

**Escenarios de Prueba de Sistema (E2E)**

Se han ejecutado pruebas integrales que validan la respuesta del sistema en los siguientes escenarios críticos:

1. **Flujo de Comunicación Organizacional:**

    - **Escenario:** Un administrador publica un anuncio desde la plataforma web y un colaborador lo visualiza en la aplicación móvil nativa.
    - **Validación:** Se confirma la correcta interacción con la API RESTful en Render y la actualización inmediata de la interfaz en Flutter, asegurando que la latencia y el formato de los datos sean los esperados.



*Link del video:*  https://shorturl.at/0ugjH
Inicio 00:00 		Fin: 00:10

   <img src="https://i.imgur.com/hh2gAQI.png" alt="crear chat">



   <img src="https://i.imgur.com/bFIMTQe.png" alt="crear chat">



2. **Sincronización de Eventos y Calendario:**

    - **Escenario:** Registro de un evento corporativo y verificación de su disponibilidad para todos los usuarios pertenecientes al mismo `company_id`.
    - **Validación:** Se valida la navegación entre módulos y la persistencia de la información en la base de datos PostgreSQL, garantizando que no existan errores de sincronización entre el estado del servidor y la vista del cliente móvil.



*Link del video:*  https://shorturl.at/0ugjH
Inicio 00:10 		Fin: 00:34

<img src="https://i.imgur.com/dXVz6K5.png" alt="crear chat">



<img src="https://i.imgur.com/VIGAK7a.png" alt="crear chat">







## 6.2. Static testing & Verification

En esta sección se detallan las actividades de verificación estática aplicadas sobre la base de código de **Centralis**. A diferencia de las pruebas dinámicas, la verificación estática no requiere la ejecución de los componentes del sistema; en su lugar, se centra en la inspección, el análisis de la estructura del código y la revisión por pares (*code reviews*) para identificar de forma temprana inconsistencias de diseño, vulnerabilidades de seguridad y desviaciones de las convenciones de programación adoptadas.

### 6.2.1. Static Code Analysis
#### 6.2.1.1. Coding standard & Code conventions.

Para asegurar la legibilidad, uniformidad y mantenibilidad a largo plazo de la plataforma, el equipo ha adoptado estándares de codificación formales para cada ecosistema tecnológico:

- **Backend (Java / Spring Boot):** Se siguen estrictamente las **Java Coding Conventions** oficiales de Oracle y las guías de estilo de Google para Java. Esto incluye la nomenclatura CamelCase para clases y métodos, la correcta estructuración de paquetes según el diseño modular de la arquitectura, y la restricción en la longitud máxima de líneas de código para facilitar su lectura en revisiones conjuntas.
- **Frontend Móvil (Dart / Flutter):** Se aplican los principios de la guía oficial de estilo de Dart (*Effective Dart*). El formateador integrado de Flutter se ejecuta antes de cada confirmación de código para estandarizar el uso de comas finales, indentación de dos espacios y la organización semántica de los *widgets* dentro del árbol de la interfaz.

#### 6.2.1.2. Code Quality & Code Security.

La evaluación de la calidad y la seguridad del código se realiza con el soporte de linters automatizados y analizadores estáticos de vulnerabilidades:

- **Métricas de Calidad (Code Quality):** Se evalúa la complejidad ciclomática de las funciones para asegurar que las reglas de negocio de anuncios y eventos no contengan lógica anidada excesiva que dificulte su mantenimiento. Asimismo, se monitorea la duplicidad de código (*code duplication*) y se gestiona proactivamente la "deuda técnica", garantizando que los componentes de persistencia transaccional e interoperabilidad mantengan un índice de mantenibilidad óptimo.
- **Métricas de Seguridad (Code Security):** Se escanea la base de código para detectar malas prácticas críticas antes de consolidar el software en la rama `main`. Esto incluye la verificación de que no existan credenciales expuestas en texto plano (*hardcoded secrets*), la validación y sanitización de datos de entrada en las APIs para prevenir ataques de inyección SQL, y la auditoría de que las consultas respeten estrictamente las restricciones de seguridad del aislamiento *multi-tenancy* establecido en el modelo *SaaS*.

### 6.2.2. Reviews

Las revisiones de código se ejecutan bajo una metodología formal de revisión por pares (*Peer Reviews*) integrada directamente en la plataforma de gestión de Git.

- **Flujo de Pull Requests (PR):** Ningún desarrollador tiene autorización para realizar fusiones directas a las ramas estables `develop` o `main`. Cuando se finaliza una funcionalidad o una suite de pruebas en una rama `feature/*`, se genera un *Pull Request* formal en GitHub.
- **Proceso de Aprobación:** Cada *Pull Request* requiere la asignación obligatoria de al menos un revisor del equipo de ingeniería. El revisor analiza de manera crítica la lógica propuesta, comprueba que se cumplan las convenciones de diseño del proyecto y verifica que las pruebas asociadas den cobertura a las nuevas reglas de negocio.
- **Criterio de Cierre:** El código solo puede ser integrado al flujo principal una vez que ha recibido la aprobación formal del revisor (*Approved*) y el motor de Integración Continua (CI) certifica que la construcción no genera conflictos ni errores sintácticos en el entorno compartido. Esto asegura la transparencia, la responsabilidad profesional y la transferencia de conocimiento entre todos los miembros de la startup.



## 6.3. Validation Interviews

### 6.3.1. Diseño de Entrevistas

El proceso de validación de la plataforma se sustenta en una metodología de investigación cualitativa mediante sesiones de entrevistas, diseñadas con el propósito de contrastar la percepción del usuario frente a las soluciones tecnológicas desplegadas. Esta fase de auditoría interactiva busca evaluar tanto el impacto de la propuesta de valor comunicada en los canales digitales como la usabilidad y eficacia operativa de las interfaces dentro de los flujos de trabajo cotidianos de las organizaciones. Con este fin, se establece una agenda de evaluación dividida en componentes específicos que permiten recopilar métricas de satisfacción, detectar fricciones de navegación y validar la alineación de las funcionalidades con las necesidades reales de cada segmento objetivo:  

- **Evaluación de la Landing Page:** El usuario analizará la propuesta de valor, claridad de características y arquitectura descrita en el sitio web de Centralis por Fudi.  
- **Validación del User Flow del Empleado:** Flujos de comunicación horizontal (creación y visualización de anuncios globales, comentarios interactivos, inicio de chats individuales y revisión de eventos organizacionales).
- **Validación del User Flow del Gerente:** Flujos de gestión y auditoría (creación de anuncios y eventos corporativos, apertura de canales grupales de chat y el despliegue del módulo de analíticas de lectura por perfil de empleado).



**Segmento 1: Empleados **

**A. Fase de Exploración Inicial (Landing Page)**

- Una vez revisada la Landing Page, ¿cuál es su entendimiento inicial sobre el propósito de Centralis?  
- De las características observadas en la web (Anuncios, Eventos, Chat), ¿cuál considera que resolvería su mayor problema de comunicación actual en su empresa?  
- ¿Considera que el diseño visual y la información de la página le transmiten la seguridad y privacidad necesarias para confiar los datos de su entorno laboral?  

**B. Fase de Interacción y Tareas (App Móvil)**

- **Tarea 1: Publicación e Interacción de Anuncios.** *Escenario: "Su equipo ha completado un hito importante y desea comunicarlo a toda la empresa. Ingrese a la app, publique un anuncio global y verifique cómo dejar un comentario en una publicación existente."*
  - *Pregunta de validación:* ¿Qué tan intuitivo le resultó el proceso de redactar y publicar un anuncio global sin restricciones o filtros previos?
  - *Pregunta de validación:* Al interactuar con la sección de comentarios, ¿la interfaz le facilitó entablar una conversación fluida con otros colaboradores?
- **Tarea 2: Comunicación y Agenda.** *Escenario: "Necesita coordinar de manera urgente un pendiente con un compañero de otra área y revisar a qué eventos corporativos ha sido asignado esta semana."*
  - *Pregunta de validación:* ¿Fue fácil para usted iniciar un chat individual (uno a uno) de forma autónoma con un colega específico?
  - *Pregunta de validación:* ¿El calendario o sección de eventos le permitió confirmar su participación de manera clara y rápida?

**C. Fase de Cierre**

- Si su empresa implementara Centralis mañana mismo, ¿qué elemento de la aplicación móvil se convertiría en su herramienta diaria indispensable?  
- Dado que cualquier empleado puede publicar anuncios globales, ¿le preocuparía que la pantalla principal se sature de información o el diseño le ayuda a priorizar lo importante?
- ¿Qué mejoras o cambios drásticos le realizaría a la aplicación para que se adapte mejor a su rutina laboral?

**Segmento 2: Gerentes / Administradores**

**A. Fase de Exploración Inicial (Landing Page)**

- Como gerente, al leer que Centralis está diseñado para la "Cohesión Corporativa", ¿considera que la propuesta de valor justifica migrar la comunicación de su empresa de herramientas tradicionales (como WhatsApp) a esta plataforma dedicada?  
- Al revisar la sección de características, ¿le queda claro que el sistema opera bajo un entorno móvil unificado para gestionar a su personal?  

**B. Fase de Interacción y Tareas (App Móvil)**

- **Tarea 1: Gestión de Contenido y Grupos.** *Escenario: "Se acerca el cierre de trimestre y necesita emitir un comunicado oficial urgente para toda la organización, programar la reunión de balance general y abrir un grupo de chat enfocado en el equipo de finanzas."*
  - *Pregunta de validación:* ¿Cómo evalúa el flujo de creación de anuncios y eventos desde su dispositivo móvil en comparación con las herramientas web tradicionales?
  - *Pregunta de validación:* Al momento de estructurar un nuevo grupo de chat, ¿la asignación de miembros y la configuración del canal le resultaron ágiles?
- **Tarea 2: Auditoría y Analíticas de Lectura.** *Escenario: "Usted ha lanzado un comunicado de seguridad crítico. Desea verificar de manera estricta si un empleado en específico ya revisó la información y conocer su historial completo de lecturas para asegurar la alineación del equipo."*
  - *Pregunta de validación:* El ingreso al perfil del empleado para auditar los anuncios y eventos que ha visto, ¿le resultó accesible y claro de interpretar?
  - *Pregunta de validación:* Sabiendo que esta funcionalidad es indispensable para usted como administrador, ¿considera que la forma en que se presentan los datos en la pantalla móvil resguarda un ambiente de confianza laboral o se percibe invasiva?

**C. Fase de Cierre**

- ¿Considera que el control analítico por perfil de usuario le otorga el respaldo operativo necesario para garantizar que los comunicados importantes realmente se lean en la empresa?
- ¿Qué opinión tiene sobre que los empleados tengan la capacidad de publicar anuncios globales directamente en el mismo espacio que la gerencia? ¿Implementaría alguna restricción o prefiere mantener la comunicación abierta?
- ¿Qué funcionalidad adicional requeriría en la aplicación móvil de Centralis para automatizar por completo el seguimiento de la productividad y comunicación de sus colaboradores?

### 6.3.2. Registro de Entrevistas

***Segmento Objetivo 1: Empleados de Empresas***

Entrevista 1:

<img src="https://i.imgur.com/sb9EnAF.png" alt="">

* **Nombre:**  Dante Mateo Aleman Romano

* **Edad:** 25

* **Minuto de inicio:**  (aun por definir)

* **Resumen:**
*
En esta entrevista de validación, Raúl Villo Salas presenta a su compañero
Mateo el prototipo de Centralis**, una plataforma SaaS multiplataforma 
de comunicación interna diseñada para centralizar la interacción en pequeñas
y medianas empresas (pymes) y evitar la dispersión de herramientas como WhatsApp 
o el correo electrónico. Durante la demostración de la interfaz —compuesta por 
cuatro pantallas principales que incluyen el inicio, un feed de eventos y 
anuncios filtrados por relevancia, mensajería privada/grupal y el perfil 
de usuario—, Mateo elogia el diseño estético, limpio y minimalista de la
aplicación. Asimismo, el entrevistado aporta dos sugerencias clave para
la mejora del producto: la implementación de un tutorial interactivo de inicio
para guiar a los nuevos usuarios en las funcionalidades de la plataforma, y la
inclusión de ubicaciones o salas específicas en el apartado de eventos (ya sean virtuales o presenciales) para facilitar la organización del personal. Raúl concluye la sesión agradeciendo el feedback y asegurando que estas recomendaciones serán tomadas en cuenta para el desarrollo futuro de la aplicación.

***Segmento Objetivo 2: Gerentes y Líderes de Equipos***

Entrevista 3: 

<img src="https://i.imgur.com/Mcd6dpT.png" alt="">

* **Nombre:**  Grecia Rivera

* **Edad:** 28

* **Minuto de inicio:**  (aun por definir)

* **Resumen:** 

  La participante interactuó con la propuesta de valor móvil de Centralis, validando que la plataforma justifica la migración desde herramientas tradicionales como WhatsApp, debido a que estas últimas generan pérdida de información y carecen de un seguimiento del nivel de lectura de los colaboradores. Durante la fase de interacción en la aplicación, la usuaria completó con éxito las tareas de registro de compañía, agregación de empleados a la organización, publicación de anuncios urgentes y creación de eventos corporativos enlazados a chats privados.

  En términos de usabilidad, el flujo de creación fue evaluado como ágil y directo; sin embargo, se detectó una oportunidad de mejora heurística en el flujo de invitación a eventos, donde la usuaria tuvo que retroceder manualmente a la sección de perfiles y deslizar la pantalla hacia abajo para refrescar y actualizar la lista de miembros elegibles. Respecto al módulo analítico por perfil de usuario, confirmó que es altamente accesible, claro y que no transgrede la privacidad de los empleados al estar estrictamente limitado al ámbito laboral, otorgando el respaldo operativo necesario para garantizar la lectura de comunicados críticos.



Entrevista 4: 

<img src="https://i.imgur.com/klwtXgy.png" alt="">

* **Nombre:**  Gerendine Correa

* **Edad:** 30

* **Minuto de inicio:**  (aun por definir)

* **Resumen:** 

  La participante validó la propuesta de valor desde la perspectiva de la seguridad informática corporativa, afirmando que herramientas tradicionales como WhatsApp no constituyen medios formales ni seguros para el flujo de datos de una organización. Durante la interacción con la aplicación móvil, completó satisfactoriamente los flujos de creación de compañía , adición de empleados al entorno corporativo aplicando la actualización por deslizamiento manual y estructuración de anuncios, eventos y chats grupales.  

  En términos de usabilidad, el proceso fue evaluado como intuitivo, rápido y estético (*fancy*). No obstante, se detectó una falla técnica crítica de rendimiento: la aplicación se congeló momentáneamente (*"se quedó cargando"*) al intentar ingresar a las analíticas directamente desde la vista del anuncio. Esto obligó a desviar el flujo y acceder al historial de lecturas de manera indirecta a través del menú de miembros en el perfil de usuario. A pesar de este retraso en la carga, la usuaria validó que el módulo analítico es indispensable, claro y que no vulnera la privacidad de los colaboradores, ya que la auditoría utiliza cuentas corporativas y se restringe a verificar la lectura de asignaciones laborales. 

### 6.3.3. Evaluaciones según heurísticas



**UX Heuristics & Principles Evaluation**

 **Usability – Inclusive Design – Information Architecture**

**CARRERA : Ingeniería de Software**
**CURSO : Diseño de Experimentos de Ingeniería de Software
SECCIÓN : 1ASI0732-2610-17821**
**PROFESORES : Lennin Percy Cenas Vasquez**
**AUDITOR : Raúl Bellido Salas**
**CLIENTE(S) :Centralis User**


**SITE o APP A EVALUAR:**

**[Centralis]()** *(Plataforma SaaS multiplataforma de comunicación interna empresarial)*

**TAREAS A EVALUAR:**

*El alcance de esta evaluación incluye la revisión de la usabilidad de las siguientes tareas basadas en los flujos interactivos presentados:*

1. **Navegación por la pantalla de inicio (Home):** Visualización de eventos de la compañía, anuncios generales y lista de chats recientes.
2. **Filtrado del feed de eventos:** Clasificación y filtrado de elementos de comunicación según su orden de relevancia (Normal, Alto, Urgente).
3. **Gestión de mensajería interna:** Flujo para sostener chats privados individuales con empleados específicos y creación de chats grupales de coordinación corporativa.
4. **Consulta de perfil de usuario:** Visualización de las funcionalidades activas asignadas y validación de las compañías empresariales asociadas a la cuenta.

*No están incluidas en esta versión de la evaluación las siguientes tareas:*

1. Configuración del perfil de administrador para la creación de nuevos anuncios corporativos.
2. Integración y llamadas de voz o videoconferencia directas desde la interfaz.
3. Configuración y despliegue del sistema SaaS en servidores de múltiples compañías independientes.

---

#### ***ESCALA DE SEVERIDAD:***

| Nivel | Descripción |
| --- | --- |
| 1 | Problema superficial: puede ser fácilmente superado por el usuario u ocurre con muy poca frecuencia. No necesita ser arreglado a no ser que exista disponibilidad de tiempo. |
| 2 | Problema menor: puede ocurrir un poco más frecuentemente o es un poco más difícil de superar para el usuario. Se le debería asignar una prioridad baja de cara al siguiente release. |
| 3 | Problema mayor: ocurre frecuentemente o los usuarios no son capaces de resolverlos. Es importante que sean corregidos y se les debe asignar una prioridad alta. |
| 4 | Problema muy grave: un error de gran impacto que impide al usuario continuar con el uso de la herramienta. Es imperativo que sea corregido antes del lanzamiento. |

---

#### ***TABLA RESUMEN:***

| # | Problema | Escala de severidad | Heurística/Principio violada(o) |
| --- | --- | --- | --- |
| **1** | **Falta de orientación inicial o flujo de inducción para nuevos usuarios corporativos (Onboarding).** | **2** | **Usability: Ayuda y documentación / Flexibilidad y eficiencia de uso** |
| **2** | **Ausencia de datos de localización o salas específicas en las tarjetas de detalles de eventos.** | **3** | **Information Architecture: Is it findable? / Is it usable?** |
| **3** | **Uso exclusivo de datos estáticos/maquetados sin simulación de flujos de interacción dinámica.** | **2** | **Usability: Relación entre el sistema y el mundo real** |

---

#### ***DESCRIPCIÓN DE PROBLEMAS:***

**PROBLEMA #1: Falta de orientación inicial o flujo de inducción para nuevos usuarios corporativos (Onboarding).** **Severidad:** 2

**Heurística violada:** Usabilidad - Ayuda y documentación

* **Problema:** Al ingresar por primera vez a la interfaz o crear una cuenta, el usuario se encuentra directamente con las cuatro pantallas principales de forma abrupta. Al ser una herramienta que consolida múltiples flujos antes dispersos (reemplazo de WhatsApp, correos y SMS corporativos), el cliente experimenta incertidumbre sobre el alcance exacto de los botones o el propósito operativo de secciones específicas sin una guía previa.
  *(Incluir captura de pantalla de la barra lateral de navegación y la pantalla Home actual).*
* **Recomendación:** Diseñar e implementar un pequeño tutorial interactivo de bienvenida (tour de producto) gatillado de manera automática inmediatamente después de que el usuario inicie sesión por primera vez. Este componente debe resaltar secuencialmente las funcionalidades de la barra lateral y explicar cómo interactuar con el feed y la mensajería interna.

---

**PROBLEMA #2: Ausencia de datos de localización o salas específicas en las tarjetas de detalles de eventos.** **Severidad:** 3

**Heurística violada:** Arquitectura de la Información - Is it findable? (¿Es encontrable / útil?)

* **Problema:** Al inspeccionar el feed y los detalles de los eventos organizados por la empresa, la estructura actual solo despliega quiénes están asociados y cuándo está planeado el evento. Al no categorizar si el evento es virtual o presencial, ni proveer campos específicos para registrar auditorios, oficinas, salas de reuniones o enlaces remotos, el usuario se ve obligado a recurrir de forma externa a otros medios informales de comunicación para averiguar dónde debe asistir, anulando la premisa del producto de "tenerlo todo en un solo lugar".
  *(Incluir captura de pantalla de la vista detallada de una tarjeta de eventos sin campos de ubicación).*
* **Recomendación:** Enriquecer la estructura de datos y el diseño visual de las tarjetas de eventos. Se deben añadir de forma obligatoria campos específicos para la localización física (ej. Sala de juntas, Auditorio principal) o, en su defecto, un interruptor dinámico para eventos virtuales que renderice un botón directo de acceso al canal de la reunión.

---

**PROBLEMA #3: Uso exclusivo de datos estáticos/maquetados sin simulación de flujos de interacción dinámica.** **Severidad:** 2

**Heurística violada:** Usabilidad - Relación entre el sistema y el mundo real / Consistencia

* **Problema:** Las vistas del feed de eventos, mensajería y perfil dependen enteramente de textos fijos de prueba. Esto impide al evaluador validar componentes cruciales del comportamiento real de la aplicación en el ecosistema pyme, tales como la persistencia de las conversaciones al cambiar de pestañas, el orden cronológico reactivo de los chats en vivo o la actualización en tiempo real de los anuncios urgentes.
  *(Incluir captura de pantalla de la lista de mensajería con nombres fijos de prueba).*
* **Recomendación:** Alimentar la aplicación con un set mínimo de datos de prueba dinámicos (Mock Data) controlados por estados locales en el frontend (o un archivo JSON reactivo). Esto debe permitir simular el envío de un mensaje nuevo o la adición de un evento simulado para emular el flujo operativo antes de realizar la integración final con los servicios de backend.


## 6.4. Auditoría de Experiencias de Usuario

### 6.4.1. Auditoría realizada

#### 6.4.1.1. Información del grupo auditado

ClaudeFlow es una startup liderada por estudiantes de la Universidad Peruana de Ciencias Aplicadas (UPC), dedicada al desarrollo de soluciones digitales para la gestión financiera de restaurantes. Con el propósito de brindar a los dueños de negocios gastronómicos una herramienta accesible, intuitiva y especializada, se ha desarrollado el proyecto FoodFlow, una aplicación web orientada al monitoreo de la salud financiera del restaurante, la visualización de ingresos y gastos, el análisis de rentabilidad por plato, la gestión de inventario, el control de órdenes y la generación de reportes estratégicos. En ClaudeFlow, consideramos que una adecuada gestión financiera es fundamental para la sostenibilidad, rentabilidad y crecimiento de los restaurantes, especialmente en negocios pequeños y medianos que suelen operar con procesos manuales, hojas de cálculo o información dispersa. Por ello, FoodFlow busca convertirse en una solución tecnológica que permita transformar los datos operativos del restaurante en información clara y útil para la toma de decisiones.


#### 6.4.1.2. Cronograma de auditoría realizada

|   Fecha    | Actividad | Descripción |
|:----------:| :--- | :--- |
| 2026-06-01 | Revisión de la Landing Page | Evaluación de la propuesta de valor, claridad de características y arquitectura descrita en el sitio web de Centralis por Fudi. |
| 2026-06-02 | Validación del User Flow del Empleado | Evaluación de los flujos de comunicación horizontal (creación y visualización de anuncios global                     

#### 6.4.1.3. Contenido de auditoría realizada

**Anexo D. Formato para Evaluación de User Experience según Heurísticas**

**UX Heuristics & Principles Evaluation**

 **Usability – Inclusive Design – Information Architecture**

**CARRERA : Ingeniería de Software**
**CURSO : Diseño de Experimentos de Ingeniería de Software SECCIÓN : 1ASI0732-2610-17821**
**PROFESORES : Lennin Percy Cenas Vasquez**
**AUDITOR : Raúl Bellido Salas** **CLIENTE(S) : ClaudeFlow / FoodFlow Users** ---

**SITE o APP A EVALUAR:**

[FoodFlow-Frontend](https://food-flow-frontend-ipmc.vercel.app/login) *(Aplicación Web de Gestión de Restaurantes)*

**TAREAS A EVALUAR:**

*El alcance de esta evaluación incluye la revisión de la usabilidad de las siguientes tareas:*

1. Registro de usuario e inicio de sesión en la plataforma.
2. Gestión de inventario de productos (creación, edición, eliminación y búsqueda de insumos).
3. Configuración y gestión de platos (Dishes) y precios.
4. Creación y actualización de pedidos/órdenes y control de sus estados en el restaurante.
5. Visualización del rendimiento financiero y métricas comerciales en el Dashboard.
6. Ajuste de perfil, cambio de contraseña y actualización de suscripción en el módulo de Settings.

*No están incluidas en esta versión de la evaluación las siguientes tareas:*

1. Integración en tiempo real de pasarelas de pago externas (p. ej. Stripe, PayPal).
2. Reportes avanzados exportables en formato PDF o Excel.
3. Notificaciones push o alertas instantáneas en tiempo real para cambios de estado de órdenes multi-dispositivo.

---

***ESCALA DE SEVERIDAD:***

*Los errores serán puntuados tomando en cuenta la siguiente escala de severidad:*

| Nivel | Descripción |
| :---- | :---- |
| 1 | Problema superficial: puede ser fácilmente superado por el usuario o ocurre con muy poca frecuencia. No necesita ser arreglado a no ser que exista disponibilidad de tiempo. |
| 2 | Problema menor: puede ocurrir un poco más frecuentemente o es un poco más difícil de superar para el usuario. Se le debería asignar una prioridad baja de cara al siguiente release. |
| 3 | Problema mayor: ocurre frecuentemente o los usuarios no son capaces de resolverlo. Es importante que sea corregido y se le debe asignar una prioridad alta. |
| 4 | Problema muy grave: un error de gran impacto que impide al usuario continuar con el uso de la herramienta. Es imperativo que sea corregido antes del lanzamiento. |

---

***TABLA RESUMEN:***

| \# | Problema | Escala de severidad | Heurística/Principio violada(o) |
| :---: | ----- | ----- | :---- |
| 1 | Hardcodeo del símbolo de moneda `$` en listados en lugar de usar el helper centralizado | 2 | Usability: Consistencia y estándares |
| 2 | Elementos de imagen clave sin atributo descriptivo en `alt` (p. ej. Logo de marca en login) | 1 | Inclusive Design: Proporciona experiencias comparables |
| 3 | Redirección abrupta y deslogueo automático al cambiar email sin suficiente aviso o contador | 2 | Usability: Visibilidad del estado del sistema |
| 4 | Diálogos modales permiten cierre accidental perdiendo datos del formulario sin confirmación | 3 | Usability: Libertad y control del usuario |
| 5 | Falta de límites superiores claros y advertencia visual en los campos numéricos de stock | 2 | Usability: Prevención de errores |
| 6 | Inconsistencia de datos en la tarjeta de Órdenes entre el Dashboard y Finanzas | 3 | Usability: Consistencia y estándares |
| 7 | Etiquetas numéricas del eje Y truncadas o mal alineadas en el gráfico de Finanzas | 2 | Usability: Diseño estético y minimalista |
| 8 | Falta de botón para agregar un nuevo plato directamente en la vista de Menú/Platos | 2 | Usability: Flexibilidad y eficiencia de uso |

---

#### ***DESCRIPCIÓN DE PROBLEMAS:***

##### **PROBLEMA #1: Hardcodeo del símbolo de moneda `$` en listados de órdenes**
* **Severidad:** 2
* **Heurística violada:** Usability - Consistencia y estándares
* **Problema:** En OrdersPage, el total acumulado de la orden muestra el símbolo de moneda de forma fija (`${row.totalAmount.toFixed(2)}`). Esto rompe la consistencia con el helper `formatCurrency` configurado en `src/utils` y utilizado en otras partes de la aplicación como `SettingsPage.tsx` para adaptarse a las configuraciones regionales del restaurante.
* **Recomendación:** Reemplazar el hardcodeo de `$` por la invocación del método `formatCurrency(row.totalAmount)` para mantener el estándar global de la aplicación.

---

##### **PROBLEMA #2: Ausencia de descripción en logotipo de marca en autenticación**
* **Severidad:** 1
* **Heurística violada:** Inclusive Design - Proporciona experiencias comparables
* **Problema:** En `LoginPage.tsx` y `RegisterPage.tsx`, el logotipo principal de la aplicación `foodflow-mark.png` contiene un atributo `alt=""` vacío. Para usuarios con lectores de pantalla, esto omite el branding fundamental del sitio.
* **Recomendación:** Cambiar el atributo por `alt="FoodFlow Logo"` o `alt={t('app.name')}` para asegurar que sea accesible a todas las personas.

---

##### **PROBLEMA #3: Cierre de sesión y redirección abrupta al modificar correo electrónico**
* **Severidad:** 2
* **Heurística violada:** Usability - Visibilidad del estado del sistema
* **Problema:** En `SettingsPage.tsx`, al cambiar el correo electrónico del perfil del usuario, el sistema muestra un mensaje rápido y redirige al login cerrando la sesión de forma inmediata usando un `setTimeout` de 3 segundos sin feedback visual de progreso. El usuario puede desconcertarse al ver que su sesión expira sin una advertencia o un temporizador interactivo.
* **Recomendación:** Implementar un indicador de progreso visual o un cuadro de diálogo con confirmación donde se indique explícitamente "Cerrando sesión en X segundos..." para reducir la incertidumbre.

---

##### **PROBLEMA #4: Diálogos modales permiten cierre accidental al hacer click afuera sin confirmación de descarte**
* **Severidad:** 3
* **Heurística violada:** Usability - Libertad y control del usuario
* **Problema:** En `ProductsPage.tsx` y en la adición de pedidos, si el usuario tiene información a medio llenar en los diálogos modales y hace clic fuera del modal o presiona "Cancelar" por error, los modales se cierran inmediatamente perdiendo todo el progreso del formulario sin preguntar si desea descartar los cambios.
* **Recomendación:** Implementar una validación de confirmación (`ConfirmDialog` o comprobación de `isDirty` del formulario) si el usuario intenta cerrar el modal habiendo modificado datos.

---

##### **PROBLEMA #5: Ausencia de advertencias visuales de stock mínimo en listas de productos**
* **Severidad:** 2
* **Heurística violada:** Usability - Prevención de errores / Diseño visual
* **Problema:** Aunque el sistema define un umbral de stock bajo (`lowStockThreshold`), la interfaz de administración de inventario no resalta visualmente en la tabla principal aquellos artículos que están por debajo de este límite, obligando al gestor a comparar manualmente los valores numéricos actuales contra el umbral.
* **Recomendación:** Añadir un badge, color o icono de advertencia (como el icono `Warning` disponible en las importaciones) a las filas de la tabla de inventario cuando `stockLevel <= lowStockThreshold`.


---

##### **PROBLEMA #6: Truncamiento de etiquetas en el gráfico de barras de Finanzas**
* **Severidad:** 2
* **Heurística violada:** Usability - Diseño estético y minimalista
* **Problema:** En la vista de `Finanzas`, dentro del bloque "Ingresos vs gastos por categoría", las etiquetas numéricas del eje Y (por ejemplo, `$600.00`, `$450.00`) aparecen cortadas y pegadas al límite izquierdo del contenedor del gráfico. Esto da una sensación de interfaz rota y dificulta la lectura rápida de los montos.
* **Recomendación:** Ajustar las propiedades de la librería de gráficos utilizada (ej. Recharts o Chart.js), incrementando el margen izquierdo (`marginLeft` o el `width` del eje Y) para que los valores monetarios tengan suficiente espacio para renderizarse correctamente.

---

##### **PROBLEMA #7: Ausencia de botón de acción (CTA) en la vista de Menú / Platos**
* **Severidad:** 2
* **Heurística violada:** Usability - Flexibilidad y eficiencia de uso
* **Problema:** Si el usuario se dirige directamente a la pestaña `Menú / Platos` con la intención de agregar un nuevo ítem, no encuentra un botón para realizar esta acción principal. Actualmente, el usuario está forzado a regresar a la vista del `Panel` para usar el atajo de "Acciones rápidas > Agregar plato", lo cual rompe el flujo lógico de la tarea.
* **Recomendación:** Añadir un botón primario visible (ej. "+ Agregar plato" o "Nuevo") en la parte superior derecha de la vista `Menú / Platos`, preferiblemente a la misma altura de la barra de búsqueda.


#### 6.4.2. Auditoría recibida

#### 6.4.2.1. Información del grupo auditor

ClaudeFlow es una startup liderada por estudiantes de la Universidad Peruana de Ciencias Aplicadas (UPC), dedicada al desarrollo de soluciones digitales para la gestión financiera de restaurantes. Con el propósito de brindar a los dueños de negocios gastronómicos una herramienta accesible, intuitiva y especializada, se ha desarrollado el proyecto FoodFlow, una aplicación web orientada al monitoreo de la salud financiera del restaurante, la visualización de ingresos y gastos, el análisis de rentabilidad por plato, la gestión de inventario, el control de órdenes y la generación de reportes estratégicos. En ClaudeFlow, consideramos que una adecuada gestión financiera es fundamental para la sostenibilidad, rentabilidad y crecimiento de los restaurantes, especialmente en negocios pequeños y medianos que suelen operar con procesos manuales, hojas de cálculo o información dispersa. Por ello, FoodFlow busca convertirse en una solución tecnológica que permita transformar los datos operativos del restaurante en información clara y útil para la toma de decisiones.


#### 6.4.2.2. Cronograma de auditoría recibida

|   Fecha    | Actividad |
|:----------:| :--- |
| 2026-06-01 | Revisión inicial de la plataforma FoodFlow y familiarización con sus funcionalidades principales. |
| 2026-06-03 | Ejecución de tareas de usuario específicas en la aplicación web, enfocándose en los flujos de gestión de inventario, creación de platos y visualización de métricas financieras. |
| 2026-06-05 | Documentación detallada de problemas de usabilidad encontrados, asignación de severidad y elaboración de recomendaciones de mejora basadas en principios heurísticos. |
| 2026-06-07 | Preparación del informe de auditoría de experiencia de usuario, incluyendo la tabla resumen de problemas y la descripción detallada de cada uno. |
| 2026-06-10 | Presentación del informe de auditoría a los desarrolladores de FoodFlow para su revisión y planificación de correcciones en futuras iteraciones del producto. |          


#### 6.4.2.3. Contenido de auditoría recibida

**UX Heuristics & Principles Evaluation**

**Usability – Inclusive Design – Information Architecture**

**CARRERA:** Ingeniería de Software
**CURSO:** Diseño de Experimentos de Ingeniería de Software
**SECCIÓN:** 17821
**PROFESORES:** Todos
**AUDITOR:** Equipo de ClaudeFlow
**CLIENTE(S):** Fudi

**SITE o APP A EVALUAR:**
Centralis

**TAREAS A EVALUAR:**

El alcance de esta evaluación incluye la revisión de la usabilidad de las siguientes tareas:
1.	Intento de registro de usuario nuevo (Landing Page)
2.	Inicio de sesión de usuario (Landing Page)
3.	Navegación general y uso del pie de página (Landing Page)
4.	Configuración del idioma global (Landing Page)
5.	Visualización de eventos y anuncios en el Feed (Aplicación móvil)
6.	Visualización de métricas y analíticas de publicaciones (Aplicación móvil)
7.	Visualización de datos de perfil, compañía y miembros (Aplicación móvil)
8.	Interacción con botones de contacto rápido en el perfil (Aplicación móvil)

No están incluidas en esta versión de la evaluación las siguientes tareas:
1.	Registro de una compañía nueva
2.	Publicación activa de nuevos anuncios y eventos
3.	Envío de mensajes en chats directos o grupales
4.	Actualización de datos de perfil
5.	Funciones de subida de imágenes y archivos multimedia

**ESCALA DE SEVERIDAD:**
*Los errores serán puntuados tomando en cuenta la siguiente escala de severidad.*

| Nivel | Descripción |
|---|---|
| 1 | Problema superficial: puede ser fácilmente superador por el usuario u ocurre con muy poca frecuencia. No necesita ser arreglado a no ser que exista disponibilidad de tiempo. |
| 2 | Problema menor: puede ocurrir un poco más frecuentemente o es un poco más difícil de superar para el usuario. Se le debería asignar una prioridad baja resolverlo de cara al siguiente reléase. |
| 3 | Problema mayor: ocurre frecuentemente o los usuarios no son capaces de resolverlos. Es importante que sean corregidos y se les debe asignar una prioridad alta. |
| 4 | Problema muy grave: un error de gran impacto que impide al usuario continuar con el uso de la herramienta. Es imperativo que sea corregido antes del lanzamiento. |

**TABLA RESUMEN:**

| # | Problema | Escala de severidad | Heurística / principio violado(a) |
|---|---|---|---|
| 1 |	Botón CTA no redirige al usuario al destino esperado | 2 | Consistencia y estándares (Nielsen) / Information Architecture: Is it usable? |
| 2 |	Bajo contraste de texto en los enlaces y elementos del Footer. |	2	| Estética y diseño minimalista (Nielsen) / Information Architecture: Is it usable? |
| 3 |	Selector de idioma deshabilitado o inactivo en el Footer.	| 2 |	Consistencia y estándares (Nielsen) |
| 4 |	Derechos Reservados Desactualizados	| 1	| Information Architecture: Is it usable? |
| 5 |	Enlaces inactivos los botones de "Sign In" y "Start Meeting" de la barra de navegación. |	3 |	Consistencia y estándares (Nielsen) / Information Architecture: Is it usable? |
| 6 |	Botones de comunicación (Llamada, Mensaje, Correo) deshabilitados en la vista de Perfil. |	3	| Consistencia y estándares (Nielsen) / Information Architecture: Is it usable? |
| 7 |	Inclusión de usuarios sin acceso en el cálculo de métricas de analítica (Visualizations).	| 3 |	Information Architecture: Is it usable? |
| 8 | Presencia de texto residual fijo ("Button") en la tarjeta de eventos. | 2 | Estética y diseño minimalista (Nielsen) |
| 9 |	Ausencia de imágenes reales en los avatares de los miembros inscritos (Attendees). |	2	| Consistencia y estándares (Nielsen) / Information Architecture: Is it usable? |

**DESCRIPCIÓN DE PROBLEMAS:**
**Problema #1:** Botón CTA no redirige al usuario al destino esperado.
**Severidad:** 2
**Heurística violada:** Consistencia y estándares (Nielsen) / Information Architecture: Is it usable?

**Problema:**
El botón principal de llamada a la acción (CTA) en la sección Hero está apuntando a un enlace vacío (href="#"). Al hacer clic, el sitio realiza un leve salto hacia la parte superior de la página en lugar de redirigir al usuario al formulario de registro, inicio de sesión o sección correspondiente, quebrando la expectativa de navegación y deteniendo el flujo del usuario.

**Captura de pantalla:**
<p align="center">
  <img src="https://i.imgur.com/nxyVWvo.png" alt="P1">
</p>

**Recomendación:**
Vincular correctamente el botón a su destino final.

---

**Problema #2:** Bajo contraste de texto en los enlaces y elementos del Footer.
**Severidad:** 2
**Heurística violada:** Consistencia y estándares (Nielsen) / Information Architecture: Is it usable?

**Problema:**
Los textos de los enlaces ("Product", "About Team", etc.) y la descripción institucional debajo del logo utilizan un tono gris muy claro sobre un fondo blanco puro. Esto genera una falta de contraste severa que dificulta la lectura para cualquier usuario, y resulta inaccesible para personas con discapacidades visuales o pantallas con bajo brillo.

**Captura de pantalla:**
<p align="center">
  <img src="https://i.imgur.com/T35ORYz.png" alt="P2">
</p>

**Recomendación:**
Modificar el color de la tipografía secundaria del footer a un tono gris más oscuro o negro (por ejemplo, reducir la opacidad a un nivel que garantice un ratio de contraste mínimo de 4.5:1 según las pautas WCAG AA para texto normal). También se puede optar por oscurecer el fondo del footer a un gris claro/azul oscuro y mantener las letras legibles.

---

**Problema #3:** Selector de idioma deshabilitado o inactivo en el Footer.
**Severidad:** 2
**Heurística violada:** Consistencia y estándares (Nielsen)

**Problema:**
El menú desplegable de idioma ("EN") ubicado en la esquina inferior izquierda del footer visualmente parece un elemento interactivo, pero no ejerce ninguna acción al hacer clic ni despliega las opciones. Esto rompe con el comportamiento del mismo elemento que sí funciona correctamente en el Header (cabecera), quebrando la consistencia interna de la interfaz.

**Captura de pantalla:**
<p align="center">
  <img src="https://i.imgur.com/qoDlXAf.png" alt="P3">
</p>

**Recomendación:**
Replicar el mismo componente y lógica de programación del Header en el Footer para asegurar que el selector de idioma sea completamente funcional en ambas zonas de la Landing Page, manteniendo la consistencia de i18n a lo largo de todo el sitio.

---

**Problema #4:** Derechos Reservados Desactualizados
**Severidad:** 1
**Heurística violada:** Information Architecture: Is it usable?

**Problema:**
El texto al pie de página muestra el año anterior ("© 2024 Centralis by Fudi"), lo que puede dar al usuario la falsa impresión de que el sitio web o la herramienta está abandonada o no recibe soporte actual.

**Captura de pantalla:**
<p align="center">
  <img src="https://i.imgur.com/g6n0jSS.png" alt="P4">
</p>

**Recomendación:**
Actualizar el texto al año en curso. Se recomienda encarecidamente automatizar este campo mediante código para que se actualice de forma dinámica cada primero de enero sin requerir mantenimiento manual.

---

**Problema #5:** Enlaces inactivos los botones de "Sign In" y "Start Meeting" de la barra de navegación.
**Severidad:** 3
**Heurística violada:** Consistencia y estándares (Nielsen) / Information Architecture: Is it usable?

**Problema:**
Los botones situados en el extremo derecho del Header ("Sign In" y "Start Meeting") actúan como enlaces vacíos apuntando a #. Al ser presionados, el sistema solo recarga levemente la vista hacia arriba en lugar de abrir la pantalla de autenticación o iniciar el flujo de la reunión, quebrando la usabilidad elemental del flujo de acceso.

**Captura de pantalla:**
<p align="center">
  <img src="https://i.imgur.com/iIhOg0D.png" alt="P5">
</p>

**Recomendación:**
Conectar de inmediato ambos botones a sus respectivas rutas de producción o entornos de pruebas activos. Si estas interfaces aún se encuentran en fase de desarrollo, se debe implementar temporalmente una ventana modal simple que informe al usuario que la funcionalidad estará disponible próximamente, evitando por completo el uso de enlaces vacíos que dejen la pantalla suspendida.

---

**Problema #6:** Botones de comunicación (Llamada, Mensaje, Correo) deshabilitados en la vista de Perfil.
**Severidad:** 3
**Heurística violada:** Consistencia y estándares (Nielsen) / Information Architecture: Is it usable?

**Problema:**
El grupo de tres botones interactivos situados debajo del correo electrónico no ejecuta ninguna función ni responde a los gestos táctiles. Visualmente están diseñados como elementos accionables de alta prioridad, por lo que su inactividad contradice el modelo mental estándar de una aplicación de comunicación.

**Captura de pantalla:**
<p align="center">
  <img src="https://i.imgur.com/pjl9vnc.png" alt="P6">
</p>

**Recomendación:**
Implementar la lógica de programación para cada disparador:
1.	Botón Teléfono: Enlazar al marcador nativo del dispositivo (tel:).
2.	Botón Mensaje: Redirigir directamente al chat interno de la app con ese usuario.
3.	Botón Correo: Abrir la aplicación de email predeterminada del sistema (mailto:).
      Si el usuario visualiza su propio perfil y estas acciones no aplican para sí mismo, se deben ocultar estos botones de la vista "My Profile" y mostrarlos únicamente cuando se navegue en la pestaña "Members"

---

**Problema #7:** Inclusión de usuarios sin acceso en el cálculo de métricas de analítica (Visualizations).
**Severidad:** 3
**Heurística violada:** Information Architecture: Is it usable?

**Problema:**
El gráfico de progreso y el porcentaje de visualización (8%) están calculados sobre una base errónea de usuarios (2 de 25). El sistema incluye en el denominador (25 usuarios) a colaboradores externos o cuentas sin permisos que no tienen acceso para ver dicho anuncio, provocando que la métrica de rendimiento real se muestre drásticamente reducida.

**Captura de pantalla:**
<p align="center">
  <img src="https://i.imgur.com/dbZJ8nV.png" alt="P7">
</p>

**Recomendación:**
Modificar la consulta en el backend que alimenta esta vista. El total de usuarios objetivo (el denominador) debe filtrar e incluir única y exclusivamente a los miembros activos de la compañía que posean los roles o permisos necesarios para visualizar el anuncio. Los usuarios externos o sin acceso deben ser omitidos del cálculo para reflejar un porcentaje de analítica 100% real.

---

**Problema #8:** Presencia de texto residual fijo ("Button") en la tarjeta de eventos.
**Severidad:** 2
**Heurística violada:** Estética y diseño minimalista (Nielsen)

**Problema:**
Debajo del título aparece una etiqueta de texto flotante que dice "Button" en un tono gris claro. Este texto no corresponde a ninguna información ingresada por el creador del evento ni cumple ninguna función interactiva, revelando un descuido en la limpieza del código de la interfaz (UI)

**Captura de pantalla:**
<p align="center">
  <img src="https://i.imgur.com/GEbQALR.png" alt="P8">
</p>

**Recomendación:**
Eliminar por completo la cadena de texto fija o el elemento <Text> residual del archivo de maquetación del componente de la tarjeta de eventos para limpiar la UI.

---

**Problema #9:** Ausencia de imágenes reales en los avatares de los miembros inscritos (Attendees).
**Severidad:** 2
**Heurística violada:** Consistencia y estándares (Nielsen) / Information Architecture: Is it usable?

**Problema:**
Las burbujas de los miembros que asistirán al evento (esquina superior derecha de la tarjeta) solo muestran un ícono de usuario genérico y grisáceo en lugar de cargar las fotografías reales de perfil de los colaboradores de la empresa, rompiendo la consistencia con el diseño propuesto.

**Captura de pantalla:**
<p align="center">
  <img src="https://i.imgur.com/GEbQALR.png" alt="P8">
</p>

**Recomendación:**
Conectar las burbujas de avatar con el servicio de base de datos correspondiente. En caso de que un usuario no cuente con una foto de perfil subida, se debe reemplazar el ícono genérico gris por las iniciales del nombre de la persona sobre un fondo de color aleatorio para humanizar la interfaz.



#### 6.4.2.4. Resumen de modificaciones para subsanar hallazgos.
El equipo de desarrollo de Centralis ha tomado nota de cada uno de los problemas identificados en la auditoría de experiencia de usuario y ha comenzado a implementar las siguientes modificaciones para subsanar los hallazgos:
1.	Redirección del botón CTA en la sección Hero a la pantalla de registro.
2.	Ajuste del contraste de texto en el Footer para mejorar la legibilidad.
3.	Habilitación del selector de idioma en el Footer para que funcione de manera consistente con el Header.
4.	Actualización del año en los derechos reservados a 2026.
5.	Activación de los botones "Sign In" y "Start Meeting" para redirigir a las pantallas correspondientes.
6.	Implementación de la funcionalidad de los botones de comunicación en la vista de Perfil.
7.	Corrección del cálculo de métricas de analítica para incluir solo usuarios con acceso.
8.	Eliminación del texto residual "Button" de la tarjeta de eventos.
9.	Integración de imágenes reales en los avatares de los miembros inscritos en los eventos.


