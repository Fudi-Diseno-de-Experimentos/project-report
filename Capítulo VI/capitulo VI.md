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

