# Capítulo IV: Product Design

## 4.1. Style Guidelines.
### 4.1.1. General Style Guidelines.
### 4.1.2. Mobile Style Guidelines.
## 4.2. Information Architecture.

### 4.2.1. Organization Systems.
### 4.2.2. Labeling Systems.
### 4.2.3. SEO Tags and Meta Tags

<p style="text-indent: 1.25cm;">Los meta tags y etiquetas SEO son elementos fundamentales dentro de la sección "`<head>`" de cualquier página web, ya que permiten controlar cómo es interpretado, indexado y presentado el contenido de un sitio por parte de los motores de búsqueda (como Google) y las redes sociales (como Facebook o Twitter). Estas etiquetas no son visibles directamente por los usuarios, pero influyen de manera determinante en la forma en que una página se posiciona y aparece en los resultados de búsqueda, así como en la claridad con la que comunica su propósito al compartir enlaces.

<p style="text-indent: 1.25cm;">En el desarrollo de la plataforma Centralis, se han implementado meta etiquetas específicas para cada archivo HTML clave de la landing page con el fin de garantizar una correcta indexación, visibilidad en buscadores, claridad semántica y una presentación visualmente coherente al momento de compartir los enlaces en redes sociales. Estas prácticas fortalecen la identidad de marca y optimizan la experiencia de descubrimiento para nuevos usuarios.

**Figura 49**

*SEO tag and Meta tags*

<p align="center">
  <img src="https://i.imgur.com/hECft8E.png" alt="Descripción">
</p>

*Nota.* Elaboración propia.



**Estrategia SEO**

- **Palabras clave objetivo**: Comunicación interna, aplicación empresarial, plataforma colaborativa
- **Enfoque geográfico**: Mercado hispanohablante con potencial expansión internacional
- **Audiencia objetivo**: Gerentes de empresas, departamentos de RH, equipos de TI corporativos

<p style="text-indent: 1.25cm;">Esta implementación de SEO tags y meta tags asegura que Centralis tenga una presencia óptima en motores de búsqueda y redes sociales, facilitando el descubrimiento orgánico y mejorando la conversión de visitantes en usuarios de la aplicación.

### 4.2.4. Searching Systems.

### 4.2.5. Navigation Systems.
## 4.3. Landing Page UI Design.
### 4.3.1. Landing Page Wireframe.
### 4.3.2. Landing Page Mock-up.
## 4.4. Mobile Applications UX/UI Design.
### 4.4.1. Mobile Applications Wireframes.
### 4.4.2. Mobile Applications Wireflow Diagrams.
### 4.4.3. Mobile Applications Mock-ups.
### 4.4.4. Mobile Applications User Flow Diagrams.
## 4.5. Mobile Applications Prototyping.
<p style="text-indent: 1.25cm;">En esta sección se detalla el planteamiento de la propuesta de arquitectura y diseño de software, utilizando como base el conjunto de User Stories identificados y el Impact Map desarrollado previamente. El enfoque adoptado se fundamenta en la arquitectura dirigida por el dominio (Domain-Driven Design), permitiendo estructurar la solución de manera que responda directamente a las necesidades del negocio digital. A través de esta perspectiva, se busca garantizar que la plataforma sea escalable, mantenible y que exista una coherencia total entre el modelo de negocio y la implementación técnica.

URL de los diagramas: https://shorturl.at/mBpWF

### 4.8.1. Software Architecture Context Diagram.

<p style="text-indent: 1.25cm;">El Diagrama de Contexto representa el nivel más alto de abstracción dentro del Modelo C4 utilizado para describir la arquitectura del sistema. Su propósito fundamental es delimitar el alcance de la solución, mostrando cómo el sistema de software interactúa con los distintos perfiles de usuario (como Managers y Employees) y con sistemas externos o de terceros. Este diagrama permite visualizar el ecosistema completo del producto sin profundizar en detalles técnicos internos, facilitando la comunicación del flujo de información con todos los stakeholders del proyecto.

<p align="center">
  <img src="https://i.imgur.com/7UirUVR.jpeg" alt="Descripción">
</p>

<p style="text-indent: 1.25cm;">El Software Architecture Context Diagram de Centralis representa el nivel más alto de abstracción del sistema, permitiendo visualizar cómo interactúa la solución con los diferentes usuarios y servicios externos. A continuación, se detalla la explicación de los componentes presentados:

**Actores (Usuarios)**

- **Gerente (Manager):** Actor que utiliza la plataforma para organizar actividades, crear contenido y gestionar la comunicación dirigida a los empleados a su cargo.
- **Empleado (Employee):** Actor que utiliza Centralis como medio principal para comunicarse con sus colegas y participar en las actividades corporativas de la empresa de la cual forma parte.

**Sistema Central**

- **Centralis:** Es el sistema de software núcleo, definido como una aplicación de comunicación interna empresarial. Este actúa como el eje central que procesa las peticiones de los usuarios y coordina la lógica de negocio.

**Sistemas Externos y Servicios**

<p style="text-indent: 1.25cm;">El diagrama muestra una arquitectura moderna apoyada en servicios especializados en la nube para garantizar la escalabilidad y eficiencia:

- **Cloudinary:** Sistema de software externo utilizado exclusivamente para el almacenamiento y gestión optimizada de imágenes enviadas a través de anuncios y chats.
- **Supabase Postgres:** Contenedor que representa el esquema de base de datos. Es el servicio encargado de la persistencia y almacenamiento seguro de todos los datos transaccionales del sistema.
- **Firebase Cloud Messaging (FCM):** Servicio externo integrado para la gestión y envío de notificaciones automáticas hacia los dispositivos móviles de los usuarios, asegurando que la información vital llegue en tiempo real.



### 4.8.2. Software Architecture Container Diagrams.

<p style="text-indent: 1.25cm;">El Diagrama de Contenedores representa el segundo nivel de detalle del Modelo C4, enfocándose en desglosar el sistema de software en sus unidades principales de ejecución. A diferencia del diagrama de contexto, esta vista permite identificar las responsabilidades tecnológicas específicas, como las aplicaciones móviles, las interfaces de programación de aplicaciones (API) y los esquemas de almacenamiento. En esta sección, se detalla la interacción técnica entre los componentes internos de Centralis, especificando los protocolos de comunicación y la distribución de la lógica de negocio para asegurar una arquitectura robusta y escalable.

<p align="center">
  <img src="https://i.imgur.com/Gt8h5d4.jpeg" alt="Descripción">
</p>

<p style="text-indent: 1.25cm;">El diagrama detalla la arquitectura interna del sistema y cómo se distribuyen las tareas para cumplir con las funcionalidades de comunicación de la plataforma:

- **Mobile Application (Flutter):** Representa el contenedor de interfaz de usuario con el que interactúan los **Managers** y **Employees**. Está desarrollado en **Flutter**, lo que permite una experiencia multiplataforma. Este contenedor se encarga de consumir los servicios de la API mediante el protocolo **JSON/HTTPS**.
- **API Application (Spring Boot):** Es el núcleo de la lógica de negocio, desarrollado con el marco de trabajo **Spring Boot**. Este contenedor es responsable de procesar todas las solicitudes provenientes de la aplicación móvil, gestionar la autenticación, coordinar el envío de anuncios, mensajes y la organización de eventos.
- **Database (PostgreSQL):** Este contenedor de persistencia utiliza **PostgreSQL** (alojado en Supabase) para almacenar toda la información estructural del dominio, incluyendo los perfiles de usuario, el registro de la **Company**, anuncios, eventos y el historial de chats.
- **External API (Firebase Cloud Messaging):** La API de Spring Boot se comunica con este servicio para activar el envío de notificaciones push hacia la aplicación móvil cuando ocurren eventos relevantes (nuevos anuncios o mensajes).
- **External API (Cloudinary):** La aplicación móvil interactúa directamente con este contenedor para la subida y recuperación de archivos multimedia (imágenes), optimizando así el tráfico del servidor principal.

### 4.8.3. Software Architecture Components Diagrams.

<p style="text-indent: 1.25cm;">El Diagrama de Componentes representa el tercer nivel de detalle del Modelo C4, descomponiendo un contenedor específico —en este caso, la API Application— en sus partes integrantes. Esta vista permite identificar las responsabilidades lógicas internas, los módulos de código y cómo estos interactúan para implementar las funcionalidades del sistema. En esta sección se describe la organización interna del backend de Centralis, detallando cómo los componentes de negocio (anuncios, chats, eventos) consumen lógica compartida y se conectan con servicios externos para cumplir con los requerimientos funcionales.

<p align="center">
  <img src="https://i.imgur.com/Ckxmhq4.jpeg" alt="Descripción">
</p>

El diagrama detalla la estructura modular de la API desarrollada en **Spring Boot**, exponiendo la lógica interna que soporta a las aplicaciones móviles:

- **Módulos de Negocio Core:**
  - **Announcement:** Componente encargado de la gestión de anuncios; permite a los Gerentes crear publicaciones y las pone a disposición de los Empleados para su visualización.
  - **Chat:** Gestiona los grupos de chat bidireccionales, permitiendo la interacción fluida entre los usuarios de la organización.
  - **Event:** Controla la lógica de creación y organización de eventos corporativos, facilitando la programación de actividades para el equipo.
- **Componentes de Soporte y Gestión:**
  - **Company:** Módulo fundamental que gestiona la lógica de la organización, permitiendo el aislamiento de datos y la administración de la entidad empresa.
  - **Profile:** Encargado de la gestión de los perfiles de usuario, manejando la información personal y los roles dentro del sistema.
  - **Notification:** Centraliza la lógica de las notificaciones; recibe instrucciones de los módulos de Chat y Event para coordinar las alertas.
  - **Shared:** Proporciona lógica transversal y utilitarios reutilizables por los demás componentes de la aplicación.
- **Interacciones Externas y Persistencia:**
  - **Conectividad con Bases de Datos:** Todos los componentes de gestión (Profile, Company, Notification, etc.) se conectan con **Supabase Postgres** para la persistencia y recuperación de datos transaccionales.
  - **Integración con Servicios Cloud:** El componente *Shared* gestiona la subida de recursos multimedia hacia **Cloudinary**, mientras que el componente *Notification* se comunica con **Firebase Cloud Messaging** para despachar alertas en tiempo real a los dispositivos móviles.

## 4.9. Software Object-Oriented Design.
### 4.9.1. Class Diagrams.

1. Diagrama de `announcement` 

   <p align="center">
     <img src="https://i.imgur.com/1geIbTm.png" alt="Descripción">
   </p>
   
   
   Este módulo está pensado para la comunicación tipo foro o tablero de avisos corporativos.

- **`Announcement`**: Representa el aviso principal. Almacena la información central como el título, descripción, una imagen asociada, su prioridad y quién lo creó. Es una raíz de agregado (`AuditableAbstractAggregateRoot`).

- **`Comment`**: Permite a los empleados (`employeeId`) interactuar o responder a un anuncio específico mediante el `announcementId`.

- **Detalle a corregir**: En tu diagrama trazaste la asociación `PriorityLevel --> Comment`. Como el atributo `priority` le pertenece a `Announcement`, esa flecha debería apuntar hacia `Announcement` y no al comentario.

  2. Diagrama de  `chat`

  <p align="center">
    <img src="https://i.imgur.com/OyYZlym.png" alt="Descripción">
  </p>

Modela un sistema de comunicación instantánea estructurado alrededor de salas o grupos.

- **`Group`**: Es el núcleo (raíz de agregado) de este contexto. Define las propiedades de la sala, su visibilidad y mantiene un registro de los usuarios que pertenecen a ella (`members`).

- **`Message` y `ChatImage`**: Representan las entidades de contenido. Ambas saben a qué grupo pertenecen (`groupId`) y quién las originó (`senderId`) , permitiendo manejar texto plano o imágenes con URLs recortadas.

  

  3. Diagrama de  `event`

  

<p align="center">
  <img src="https://i.imgur.com/A28KvTu.png" alt="Descripción">
</p>


Es el dominio encargado de la gestión de la agenda o calendario.

- **`Event`**: Es una raíz de agregado única que encapsula toda la logística de una actividad. Registra el título, descripción, el momento exacto en que ocurrirá (`date`), la ubicación y, un punto importante, a quiénes va dirigido mediante el set de `recipients`.

  

4. Diagrama de  `profile`

<p align="center">
  <img src="https://i.imgur.com/N67dJAQ.png" alt="Descripción">
</p>


Actúa como el directorio de identidad dentro del sistema, separando los datos del usuario de sus credenciales de acceso.

- **`Profile`**: Centraliza la información personal y de presentación (nombres, correo, avatar).
- **Clasificación**: Se apoya en los Enums `Position` (para saber si es un Empleado, Gerente o Director) y `Department` para ubicar estructuralmente al usuario dentro de la organización.

5. Diagrama de  `company`

<p align="center">
  <img src="https://i.imgur.com/QvdI0tE.png" alt="Descripción">
</p>




- **Clase Company:** Es la entidad raíz que centraliza los datos legales (`ruc`, `nombre`) y el estado del cliente (`is_active`). Al heredar de la base de auditoría, rastrea automáticamente su creación y cambios.

### 4.9.2. Class Dictionary.

**Package: announcement**

Este paquete gestiona la comunicación unidireccional y formal de la empresa, permitiendo la retroalimentación de los empleados.

| **Clase**         | **Atributos**                                  | **Descripción**                                              |
| ----------------- | ---------------------------------------------- | ------------------------------------------------------------ |
| **Announcement**  | title, description, image, priority, createdBy | Representa una comunicación formal publicada por un Manager para informar a los miembros de la Company. |
| **Comment**       | announcementId, employeeId, content            | Representa el feedback escrito por un Employee o Manager asociado a un anuncio específico. |
| **PriorityLevel** | NORMAL, HIGH, URGENT                           | Enumeración que define el nivel de importancia de un anuncio para activar notificaciones prioritarias. |

**Package: chat**

Este paquete contiene la lógica para la mensajería instantánea y colaborativa organizada por grupos.

| **Clase**     | **Atributos**                                                | **Descripción**                                              |
| ------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **Group**     | name, description, imageUrl, visibility, createdBy, members  | Espacio de chat dedicado a un tema o departamento específico donde interactúan múltiples miembros. |
| **Message**   | messageId, groupId, senderId, body, status, sentAt, editedAt | Entidad que representa el contenido textual enviado por un usuario dentro de un grupo. |
| **ChatImage** | imageId, groupId, senderId, imageUrl, sentAt, isVisible, trimmedUrl | Especialización de mensaje que permite el envío y almacenamiento de recursos visuales en las conversaciones. |

**Package: event**

Gestiona la programación y convocatoria de actividades corporativas.

| **Clase** | **Atributos**                                             | **Descripción**                                              |
| --------- | --------------------------------------------------------- | ------------------------------------------------------------ |
| **Event** | title, description, date, location, createdBy, recipients | Define una actividad programada (reunión o capacitación) con una lista de invitados específica. |

**Package: profile**

Gestiona la identidad y jerarquía de los usuarios dentro de la organización.

| **Clase**      | **Atributos**                                                | **Descripción**                                              |
| -------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **Profile**    | userId, firstName, lastName, email, avatarUrl, position, department | Almacena los datos personales y profesionales del usuario vinculados a su cuenta. |
| **Position**   | EMPLOYEE, MANAGER, DIRECTOR                                  | Enumeración que define el rol jerárquico y el nivel de permisos del usuario en la plataforma. |
| **Department** | displayName                                                  | Define el área funcional (ej. TI, Ventas) a la que pertenece el empleado dentro de la Company. |

**Package: company**

Gestiona la información que le llega a cada usuario.

| **Elemento** | **Tipo**       | **Descripción**                                          | **Atributos**                                                |
| ------------ | -------------- | -------------------------------------------------------- | ------------------------------------------------------------ |
| **Company**  | Aggregate Root | Representa la organización o cliente dentro del sistema. | `ruc`: String `nombre`: String `iconUrl`: String `isActive`: boolean |



**Nota Técnica**

Todas las entidades principales (`Announcement`, `Comment`, `Group`, `Event`, `Profile`, `Company`) heredan de AuditableAbstractAggregateRoot, lo que garantiza que el sistema mantenga un registro automático de metadatos de auditoría de fechas de creación, fechas de edición y generación de uuid.

## 4.10. Database Design.
### 4.10.1. Relational/Non-Relational Database Diagram.



![](../Anexos/Database_Design_Diagram/diamagra_db.svg)
