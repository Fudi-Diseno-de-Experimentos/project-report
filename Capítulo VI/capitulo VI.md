# Capítulo VI: Product Verification & Validation

## 6.1. Testing Suites & Validation

### 6.1.1. Core Entities Unit Tests

En esta sección se detalla la implementación y ejecución de las pruebas unitarias diseñadas para validar la lógica de negocio atómica de las entidades principales de **Centralis**. El objetivo primordial es garantizar que los modelos de dominio, validaciones de atributos y funciones clave operen correctamente en total aislamiento de dependencias externas como bases de datos o servicios de red.

**Landing Page test**

Para la elaboración de los principales tests de nuestra Landing Page (**Centralis**), hemos tenido en cuenta las secciones más importantes que garantizan la correcta navegación y propuesta de valor para el usuario:

* **Features:** Verificación de la visibilidad de las funcionalidades clave para la alineación de equipos.
* **How it works:** Validación del flujo de información sobre el funcionamiento del hub centralizado.
* **Product / Help Center:** Comprobación de los accesos a la documentación y soporte.
* **Sign In / Get Started:** Test de interactividad de los botones de llamada a la acción (Call to Action).

Gracias a la herramienta de **Selenium IDE**, se han logrado realizar los tests funcionales que aseguran que cada elemento de la interfaz responda correctamente a las acciones del usuario.



<img src="https://i.imgur.com/QMJS39R.png" alt="img">



---



**Web Service test**

A nivel de implementación (`BoundedContextsUnitTests`), las pruebas evalúan la creación de comandos dentro de los contextos acotados de Events, Chats y Announcements. Esto asegura que las abstracciones de dominio (como `CompanyId` o los distintos `UserId`) protejan la integridad de los datos. Se han ejecutado y superado un total de cuatro pruebas unitarias:

- Se procesan exitosamente los comandos de creación de dominio para los contextos de **ANNOUNCEMENT** y **EVENTS**.
- Se validan fallos intencionados al intentar crear un anuncio (`ANNOUNCEMENT`) o un grupo de chat (`CHATS (Groups)`) cuando falta información obligatoria o se incumplen reglas de negocio, corroborando que se lanzan las excepciones correspondientes para mantener la seguridad estructural del sistema.



<p align="center">
  <img src="https://i.imgur.com/NraHgCl.png" alt="Descripción">
</p>


**Aplicación Móvil (Flutter)**

Para complementar las evaluaciones de los servicios web, se diseñaron y ejecutaron pruebas unitarias en la aplicación móvil nativa con el fin de asegurar el aislamiento y correcto funcionamiento de la lógica de presentación y manejo de estado. Estas pruebas utilizan repositorios simulados (*mocks*) para evitar dependencias externas durante la validación de las entidades:

- **Contexto de Anuncios (Announcements):**
  - **`Create Announcement`**: Se probó el flujo de creación de un anuncio, verificando rigurosamente que tanto el ID como el título se guarden de forma correcta en el repositorio *mock*.
  - **`Get Announcements`**: Se evaluó la capacidad de listado del sistema, verificando el tamaño exacto de la lista de anuncios devuelta por el repositorio simulado.
  - **`Update Announcement`**: Se validó la lógica de actualización, comprobando que el cambio de título se refleje adecuadamente en el registro *mock*.
- **Contexto de Eventos (Events):**
  - **`Create Event`**: Se implementó una prueba para la creación de eventos, verificando que el ID y el nombre ingresados se almacenen correctamente en el repositorio *mock*.
  - **`Get Events`**: Se comprobó la visualización del listado de eventos mediante la verificación del tamaño de la lista obtenida desde el repositorio simulado.
  - **`Update Event`**: Se probó el flujo de modificación de un evento, validando el cambio efectivo de su nombre en el registro *mock*.

Test de Announcement

<p align="center">
  <img src="https://i.imgur.com/09O3VUx.png" alt="Descripción">
</p>

Test de Event

<p align="center">
  <img src="https://i.imgur.com/iQzBknY.png" alt="Descripción">
</p>

### 6.1.2. Core Integration Tests

En esta sección se detalla la realización de las pruebas de integración implementadas en la arquitectura. El objetivo central de estas evaluaciones es asegurar que los diferentes módulos, servicios y componentes del sistema funcionen correctamente de forma conjunta y cuando interactúan entre sí. A través de estas pruebas conjuntas, se verifica la interoperabilidad, garantizando que la comunicación entre contextos, la persistencia en las bases de datos y los flujos transaccionales mantengan la integridad estructural y la exactitud en el flujo de información de la plataforma.

**Landing Page test**

Se realizó un test automatizado utilizando Selenium IDE para verificar el correcto funcionamiento de la landing page de Centralis. El objetivo del test fue asegurarse de que los elementos clave de la página, como el título principal, la navegación y los botones de acción ("Get Started", "Explore Features"), se cargaran correctamente y fueran interactivos, garantizando una experiencia de usuario óptima.

<img src="https://i.imgur.com/VD9fYhk.png" alt="img2">



---

**Web Service**

A nivel de implementación (`MultiTenancyAndFlowIntegrationTests`), estas pruebas simulan un entorno más cercano al escenario de producción utilizando el framework Spring Boot y bases de datos en memoria (H2). Se han verificado exitosamente dos ejes críticos mediante pruebas automatizadas:

- **Aislamiento Multi-tenancy:** Se evalúa y corrobora de forma estricta que un usuario logueado perteneciente a una compañía no puede acceder ni recuperar eventos que pertenecen al dominio de otra distinta.
- **Flujo Operativo Completo:** Se simula el recorrido integral donde un administrador interacciona con los endpoints REST enviando *payloads* validados para crear un Evento corporativo. Esta integración confirma que todos los mecanismos de autorización y recuperación de información están operando sinérgicamente en los contextos principales.



<p align="center">
  <img src="https://i.imgur.com/rC1N1xt.png" alt="Descripción">
</p>
**Aplicación Móvil**

Adicionalmente a las pruebas de interoperabilidad y *multi-tenancy* realizadas en el entorno de Spring Boot, se implementaron pruebas de integración en el ecosistema móvil para asegurar que las distintas capas y módulos de la aplicación en Flutter operen de forma sinérgica al interactuar entre sí.

- **Integración Core (`Facade syncs both modules`):** Se desarrolló una prueba específica para evaluar el flujo de integración mediante el uso del patrón Facade. Esta prueba verifica las llamadas conjuntas a los repositorios de obtención de eventos y anuncios, simulando de manera precisa el proceso de sincronización de datos de la interfaz de usuario.

<p align="center">
  <img src="https://i.imgur.com/T03URRv.png" alt="Descripción">
</p>



### 6.1.3. Core Behavior-Driven Development

En esta sección se presentan las pruebas de desarrollo dirigido por comportamiento (BDD) implementadas para validar que las funcionalidades clave de Centralis cumplan con los requisitos del negocio desde la perspectiva del usuario final. A través de la metodología BDD, se formulan escenarios específicos en lenguaje natural (Given-When-Then) que describen el comportamiento esperado de las características principales del sistema, tales como la gestión de eventos, anuncios y chats grupales. Estas pruebas actúan como puente entre los requisitos funcionales y la implementación técnica, asegurando que cada funcionalidad entregue valor real a gerentes y empleados, y que los cambios y ajustes del producto respondan fielmente a las necesidades descritas en las historias de usuario.

**1. Description: Como gerente, quiero modificar detalles de eventos existentes para ajustar cambios de último momento.**

```gherkin
Feature: Modificación de eventos

Scenario: Cambiar fecha de evento
Given que el gerente necesita posponer un eventos,
When edita la fecha del evento y guarda los cambios,
Then el sistema notifica automáticamente a los invitados sobre la nueva fecha,
And actualiza el evento en la lista de eventos.
```

**Evidencias:**

 <img src="https://imgur.com/I52Q2nr.jpg" alt="cambiar fecha de evento">

**Interpretación:**

La evidencia demuestra que el gerente puede seleccionar un evento existente y modificar su fecha de forma intuitiva desde la interfaz móvil. El sistema procesa el cambio y lo refleja en tiempo real en la lista de eventos, confirmando que la funcionalidad de actualización opera correctamente sin perder los datos del evento.

**2. Description: Como empleado, quiero editar mensajes que ya envié para corregir errores tipográficos.**

```gherkin
Feature: Edición de mensajes

Scenario: Corregir error tipográfico en mensaje
Given que el empleado envió un mensaje con un error de ortografía,
When selecciona el mensaje y realiza la corrección,
Then el sistema actualiza el contenido del mensaje.
```

**Evidencias:**

 <img src="https://imgur.com/Ufbjivi.jpg" alt="Corregir error mensaje">

**Interpretación:**

La pantalla evidencia que el empleado tiene acceso a un menú de opciones sobre mensajes enviados, permitiendo seleccionar la opción de edición. El sistema captura la corrección del texto y la persiste, demostrando que los cambios en mensajes son procesados y almacenados sin afectar el timestamp original del envío.

**3. Description: Como empleado, quiero crear chats grupales para discutir temas específicos con mis colegas.**

```gherkin
Feature: Creación de chats grupales

Scenario: Crear chat grupal para proyecto
Given que el empleado necesita coordinar un proyecto con un equipo,
When crea un nuevo chat, añade participantes y establece un nombre para el grupo,
Then el sistema crea el chat con todos los miembros añadidos.
```

**Evidencias:**

 <img src="https://imgur.com/DIxgZEq.jpg" alt="crear chat">

**Interpretación:**

La interfaz muestra el flujo de creación de un nuevo chat grupal, donde el empleado puede ingresar el nombre del grupo y seleccionar múltiples participantes. La evidencia valida que el sistema genera correctamente el identificador único del grupo y que todos los miembros añadidos son incluidos en la conversación colectiva.

**4. Description: Como gerente, quiero crear eventos en la aplicación móvil para organizar reuniones y actividades de la empresa.**

```gherkin
Feature: Creación de eventos

Scenario: Crear un evento exitosamente
Given que el gerente ha iniciado sesión en la aplicación móvil,
When crea un evento llenando los datos necesarios,
Then el sistema guarda el evento en la base de datos,
And lo muestra a los empleados seleccionados.
```

**Evidencias:**

 <img src="https://imgur.com/e8XrUyv.jpg" alt="Crear evento">

**Interpretación:**

La pantalla captura el formulario de creación de eventos con campos como título, fecha, hora, descripción y selección de empleados destinatarios. La evidencia confirma que los datos ingresados se guardan en la base de datos y que el evento es visible inmediatamente para los empleados seleccionados en sus vistas correspondientes.

**5. Description: Como gerente, quiero editar anuncios ya publicados para corregir errores o actualizar información.**

```gherkin
Feature: Editar anuncio
Scenario: Editar un anuncio existente
Given que el gerente visualiza un anuncio publicado previamente,
When modifica y guarda los cambios de la nueva información del anuncio,
Then el sistema actualiza el anuncio en la base de datos,
And los cambios se reflejan inmediatamente.
```

**Evidencias:**

 <img src="https://imgur.com/XaXh2Zv.jpg" alt="editar add">

**Interpretación:**

La interfaz demuestra que el gerente puede acceder a anuncios publicados previamente y modificar su contenido (título, descripción, etc.). La evidencia valida que la actualización se persiste en la base de datos y que los cambios son reflejados instantáneamente en la aplicación de todos los empleados sin requerir recargas manuales.

**6. Description: Como gerente, quiero publicar anuncios en la aplicación móvil para que los empleados estén informados de las novedades de la empresa.**

```gherkin
Feature: Publicación de anuncios

Scenario: Publicar un anuncio exitosamente
Given que el gerente ha iniciado sesión en la aplicación móvil,
When quiera publicar un anuncio con información relevante,
Then el sistema guarda el anuncio en la base de datos,
And muestra el anuncio donde los empleados puedan verlo.
```

**Evidencias:**

 <img src="https://i.imgur.com/ncv7zQB.jpeg" alt="Publicar add">

**Interpretación:**

La pantalla muestra el formulario de creación de anuncios donde el gerente ingresa información relevante para la empresa. La evidencia comprueba que el anuncio se almacena correctamente en la base de datos y que aparece en el feed de anuncios de todos los empleados, garantizando que la información llega a toda la organización de forma centralizada.

### 6.1.4. Core System Tests

En esta sección se detallan las pruebas de sistema realizadas para validar la integridad de la plataforma **Centralis** en su totalidad. Estas evaluaciones aseguran que la interacción entre la aplicación móvil y los servicios de backend operen correctamente bajo escenarios de uso real, cubriendo flujos completos de navegación y sincronización de datos.

**Escenarios de Prueba de Sistema (E2E)**

Se han ejecutado pruebas integrales que validan la respuesta del sistema en los siguientes escenarios críticos:

1. **Flujo de Comunicación Organizacional:**

   - **Escenario:** Un administrador publica un anuncio desde la plataforma web y un colaborador lo visualiza en la aplicación móvil nativa.
   - **Validación:** Se confirma la correcta interacción con la API RESTful en Render y la actualización inmediata de la interfaz en Flutter, asegurando que la latencia y el formato de los datos sean los esperados.

   

   *Link del video:*  https://shorturl.at/LZBGu
   Inicio 00:00 		Fin: 00:10

   <img src="https://i.imgur.com/hh2gAQI.png" alt="crear chat">

   

2. **Sincronización de Eventos y Calendario:**

   - **Escenario:** Registro de un evento corporativo y verificación de su disponibilidad para todos los usuarios pertenecientes al mismo `company_id`.
   - **Validación:** Se valida la navegación entre módulos y la persistencia de la información en la base de datos PostgreSQL, garantizando que no existan errores de sincronización entre el estado del servidor y la vista del cliente móvil.

   

   *Link del video:*  https://shorturl.at/LZBGu
   Inicio 00:10 		Fin: 00:34

<img src="https://i.imgur.com/dXVz6K5.png" alt="crear chat">