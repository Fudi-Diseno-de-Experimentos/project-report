# Capítulo V: Product Implementation
## 5.1. Software Configuration Management.

### 5.1.1. Software Development Environment Configuration.

<p style="text-indent: 1.25cm;">En esta sección se detalla el ecosistema de herramientas y servicios seleccionados para garantizar la consistencia en el ciclo de vida del desarrollo de Centralis. Con el fin de optimizar la colaboración y el rendimiento del equipo, se especifican los productos de software organizados por categorías funcionales, que abarcan desde la gestión estratégica del proyecto hasta el despliegue continuo de la plataforma.  
<p style="text-indent: 1.25cm;">Cada herramienta ha sido elegida respetando las restricciones tecnológicas del curso y los requerimientos de escalabilidad de nuestra arquitectura multi-tenancy. A continuación, se presentan los nombres de los productos, su propósito específico en el proyecto y los enlaces de acceso o descarga necesarios para la configuración del entorno local de cada miembro del equipo: 



| **Producto/Herramienta** | **Categoría**         | **Ruta de Descarga/Acceso**            | **Propósito en el Proyecto**                            |
| ------------------------ | --------------------- | -------------------------------------- | ------------------------------------------------------- |
| **OpenJDK**              | Desarrollo Backend    | https://openjdk.org/                   | Entorno de ejecución para aplicaciones Java             |
| **Apache Maven**         | Desarrollo Backend    | https://maven.apache.org/              | Gestión de dependencias y construcción del proyecto     |
| **Spring Boot**          | Desarrollo Backend    | https://spring.io/projects/spring-boot | Framework para desarrollo de APIs RESTful               |
| **Android Studio**       | Desarrollo Móvil      | https://developer.android.com/studio   | IDE para desarrollo de aplicaciones Android nativas     |
| **Render PostgreSQL**    | Base de Datos         | https://render.com/docs/postgresql     | Base de datos relacional en la nube                     |
| **Material Design 3**    | Diseño UX/UI          | https://m3.material.io/                | Sistema de diseño para interfaces consistentes          |
| **Trello**               | Gestión de Proyectos  | https://trello.com/es                  | Gestión de backlog y sprints                            |
| **UXPressia**            | Gestión de Requisitos | https://uxpressia.com/                 | Creación de User Personas, Journey Maps, Impact Mapping |
| **PlantUML**             | Documentación         | https://plantuml.com/                  | Creación de diagramas de arquitectura y flujos          |
| **Git**                  | Control de Versiones  | https://git-scm.com/                   | Control de versiones del código fuente                  |
| **GitHub**               | Repositorio           | https://github.com/                    | Almacenamiento y colaboración en código                 |
| **Render**               | Despliegue Backend    | https://render.com/                    | Plataforma de despliegue para aplicaciones Spring Boot  |
| **Cloudinary**           | Almacenamiento        | https://cloudinary.com/                | Gestión y almacenamiento de archivos multimedia         |

### 5.1.2. Source Code Management.

<p style="text-indent: 1.25cm;">La gestión del código fuente en el proyecto Centralis se fundamenta en la implementación de estándares de control de versiones que aseguran la integridad, estabilidad y trazabilidad de cada componente del sistema. A través del uso de herramientas avanzadas y metodologías de colaboración, el equipo garantiza un flujo de trabajo estructurado que permite la integración continua de funcionalidades y la resolución eficiente de errores.

<p style="text-indent: 1.25cm;">En este apartado, se detallan las estrategias adoptadas para la administración de repositorios, los protocolos de ramificación y las convenciones de nomenclatura y versionado que rigen el desarrollo de nuestra solución SaaS *multi-tenancy*.

**1. Gestión de Repositorios**

<p style="text-indent: 1.25cm;">Esta sección describe la estrategia de almacenamiento y organización del código. En proyectos de arquitectura moderna, como tu solución SaaS *multi-tenancy*, no se suele colocar todo en un solo bloque. Se explica que el código se divide en repositorios especializados (por ejemplo: uno para los *Web Services* en el backend y otro para la aplicación móvil). El objetivo es permitir que cada componente evolucione, se pruebe y se despliegue de forma independiente sin afectar a los demás.

**2. Implementación de GitFlow**

Es el marco de trabajo (framework) de ramificación que define cómo colabora el equipo en Git. En lugar de trabajar todos sobre una misma línea, GitFlow organiza el trabajo en:

- **Ramas permanentes:** `main` (código en producción) y `develop` (código integrado listo para la siguiente versión).
- **Ramas temporales:** `feature` (para nuevas funcionalidades), `release` (para preparación de lanzamientos) y `hotfix` (para corregir errores urgentes en producción). Esto garantiza que nunca se envíe código incompleto a los usuarios finales.

**3. Convenciones de Nomenclatura**

<p style="text-indent: 1.25cm;">Define las reglas de etiquetado para las ramas del repositorio. Sin estándares, es imposible saber qué contiene una rama llamada "arreglo1". Al usar convenciones como `feature/auth-login` o `hotfix/v1.0.1-db-error`, cualquier miembro del equipo (o el profesor al revisar el repositorio) puede entender inmediatamente el propósito de la rama, mejorando la trazabilidad y el orden administrativo del proyecto.

**4. Versionado Semántico (SemVer)**

Es un **protocolo de comunicación** a través de números de versión (ej. `MAJOR.MINOR.PATCH`).

- **MAJOR:** Cambios incompatibles (reestructuración de la arquitectura de la empresa).
- **MINOR:** Nuevas funcionalidades (añadir el rol de *Manager*).
- **PATCH:** Corrección de errores internos. Esto es vital en una startup como Fudi, ya que los clientes necesitan saber si una actualización de la plataforma requerirá cambios en su forma de uso o si es una mejora transparente.

**5. Conventional Commits**

<p style="text-indent: 1.25cm;">Es una especificación para los mensajes de confirmación (commits). En lugar de escribir mensajes vagos, se utiliza una estructura: `tipo(alcance): descripción` (ej. `feat(api): add multi-tenancy filtering`).

- **Beneficio técnico:** Permite que herramientas automatizadas lean el historial de Git para generar reportes de cambios (*changelogs*) sin intervención humana y facilita la identificación de en qué momento exacto se introdujo una mejora o un error.




**Repositorios GitHub**

| **Producto**                   | **URL del Repositorio**                                      | **Descripción**                                     |
| :----------------------------- | :----------------------------------------------------------- | :-------------------------------------------------- |
| **Landing Page**               | https://github.com/Fudi-Diseno-de-Experimentos/landing-page  | Sitio web estático de presentación                  |
| **Web Services**               | https://github.com/Fudi-Diseno-de-Experimentos/web-service   | APIs RESTful con pruebas unitarias y de integración |
| **Mobile Application Flutter** | https://github.com/Fudi-Diseno-de-Experimentos/centralis-flutter | Aplicación móvil                                    |
| **Project Report**             | https://github.com/Fudi-Diseno-de-Experimentos/proyect-report | Reporte del proyecto                                |

### 5.1.3. Source Code Style Guide & Conventions.

<p style="text-indent: 1.25cm;">La definición de estándares de codificación en el proyecto Centralis es fundamental para asegurar la escalabilidad de la arquitectura "multi-tenancy" de la startup Fudi. Mediante la adopción de guías de estilo internacionales, el equipo garantiza un código base uniforme, legible y de fácil mantenimiento, permitiendo que cualquier miembro del equipo pueda comprender y evolucionar los componentes del sistema de manera eficiente.

**1. Estándares de Nomenclatura y Estilo**

- **Idioma y Gramática**: Todos los identificadores, incluyendo nombres de clases, variables, métodos y comentarios, se redactan obligatoriamente en inglés para mantener la consistencia internacional del proyecto.  
- **Formatos Estándar**: Se aplica *PascalCase* para nombres de clases y *camelCase* para variables y métodos, evitando el uso de abreviaturas ambiguas que dificulten la legibilidad del código.  
- **Restricción de Términos**: Se prohíbe estrictamente el uso de términos mutados como "deployar" o "comitear", utilizando en su lugar las traducciones correctas en español ("desplegar", "confirmar cambios") o el término original en inglés.  

**2. Convenciones para Backend y Servicios Web**

- **Marco de Trabajo**: El desarrollo de los *Web Services* se realiza bajo el estilo arquitectónico RESTful utilizando el framework Spring Boot y el lenguaje de programación Java.  
- **Guías de Codificación**: Se adoptan las JAVA Coding Conventions y las Spring Boot  Coding Guidelines para la estructuración de controladores y servicios.  
- **Documentación de Endpoints**: Todos los servicios web deben estar documentados siguiendo la especificación OpenAPI mediante la herramienta Swagger, detallando verbos HTTP, parámetros y ejemplos de respuesta.  

**3. Estándares para Desarrollo Móvil**

- **Entorno de Desarrollo**: La aplicación móvil nativa se construye utilizando Android Studio como IDE principal.  
- **Arquitectura Visual**: La interfaz de usuario móvil debe estar fundamentada en los principios de *Material Design*, asegurando una experiencia consistente con la versión web de Centralis.  
- **Accesibilidad e i18n**: Se deben incluir características de internacionalización (i18n) para los idiomas inglés (en_US) y español latinoamericano (es_419).

**4. Convenciones para Pruebas y Especificaciones**

- **Lenguaje de Especificación**: Para las pruebas de comportamiento (BDD), se utiliza obligatoriamente el lenguaje Gherkin en archivos con extensión *.feature*.  
- **Estructura Gherkin**: Los criterios de aceptación deben seguir el formato *Given-When-Then*, estar redactados en tiempo presente y tercera persona, y ser totalmente comprobables sin referencia a detalles de la interfaz.  
- **Tipos de Pruebas**: Se requiere la implementación y evidencia de *Core Entities Unit Tests* para lógica interna y *Core Integration Tests* para validar la comunicación entre el frontend y el backend.  

**5. Guías para Frontend y Documentación**

- **Tecnologías de Frontend**: El desarrollo de la *Landing Page* se realiza con HTML5, CSS3 y JavaScript, mientras que las *Frontend Web Applications* utilizan el framework Vue con la biblioteca PrimeVue.  
- **Estilo Web**: Se aplican las directrices del *Google HTML/CSS Style Guide* y se requiere la configuración de atributos ARIA para garantizar el diseño inclusivo.  
- **Documentación del Proyecto**: El informe principal se elabora en formato Markdown mediante un repositorio público en GitHub, evidenciando la colaboración de todos los miembros del equipo de Fudi mediante *commits* frecuentes. 

### 5.1.4. Software Deployment Configuration.

<p style="text-indent: 1.25cm;">El proyecto Centralis implementa una estrategia de despliegue diferenciada por componente, utilizando servicios en la nube especializados para cada tipo de aplicación. Esta aproximación permite optimizar los recursos y aprovechar las capacidades específicas de cada plataforma de despliegue.

**Plataforma: Render**

- **Tipo de servicio:** Web Service
- **Configuración:** Despliegue automático desde la rama main del repositorio de backend
- **Runtime:** Java 24 con Spring Boot
- **Base de datos:** PostgreSQL mediante Render PostgreSQL
- **Variables de entorno:**
  - `DATABASE_URL`: Conexión a Render PostgreSQL
  - `JWT_SECRET`: Clave para tokens de autenticación
- **Health checks:** Endpoints de verificación de estado configurados


**Plataforma: Render PostgreSQL**

- **Tipo de servicio:** Database as a Service
- **Versión:** PostgreSQL 18

**Configuración Pendiente: Landing Page**


- **Plataforma:** Netlify

- **Requisitos:** Hosting para sitio estático (HTML, CSS, JavaScript)

<p style="text-indent: 1.25cm;">Esta configuración de despliegue asegura una entrega continua y confiable de todos los componentes del sistema Centralis, con la base de datos PostgreSQL alojada en Supabase para una mejor integración y desempeño.

## 5.2. Product Implementation & Deployment.
### 5.2.1. Sprint Backlogs.

<p style="text-indent: 1.25cm;">En esta sección se detallan los conjuntos de elementos seleccionados del "Product Backlog" para ser ejecutados durante cada ciclo de desarrollo o "Sprint". El objetivo es segmentar los requerimientos del proyecto Centralis en unidades de trabajo manejables, permitiendo un enfoque claro en la entrega de valor incremental y la validación de hipótesis de negocio.  

<p style="text-indent: 1.25cm;">A continuación, se presentan las tareas, historias de usuario y objetivos específicos definidos por el equipo de Fudi, asegurando la trazabilidad entre las necesidades del negocio y la evolución técnica del producto digital.  

| StoryID | Title                                                        | ID task | Título                                                       | Descripción                                                  | Estimation (Hours) | Assigned To | Status    |
| ------- | ------------------------------------------------------------ | ------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------ | ----------- | --------- |
| US01    | Cambiar el idioma de la landing page                         | TA01    | Cambiar el idioma de la landing page                         | Como visitante, quiero traducir la página para leer el contenido en mi idioma preferido. | 5                  | Fabrizio    | InProcess |
| US02    | Sección About de la landing page                             | TA02    | Sección About de la landing page                             | Como visitante, quiero ver una sección About en la landing page para entender la misión, visión y propósito de Centralis. | 5                  | Fabrizio    | InProcess |
| US03    | Historia de la startup                                       | TA03    | Historia de la startup                                       | Como visitante, quiero conocer la historia y origen de Centralis para generar confianza en la marca. | 5                  | Sergio      | InProcess |
| US04    | Sección FAQ                                                  | TA04    | Sección FAQ                                                  | Como visitante, quiero acceder a una sección FAQ para resolver mis dudas comunes sobre el producto. | 5                  | Neil        | InProcess |
| US05    | Sección Team                                                 | TA05    | Sección Team                                                 | Como visitante, quiero conocer al equipo detrás de Centralis para humanizar la marca y generar confianza. | 5                  | Raul        | InProcess |
| US06    | Links profesionales del equipo                               | TA06    | Links profesionales del equipo                               | Como visitante, quiero acceder a los perfiles profesionales del equipo para verificar su expertise. | 5                  | Fabrizio    | InProcess |
| US07    | Compatibilidad con múltiples dispositivos                    | TA07    | Compatibilidad con múltiples dispositivos                    | Como visitante, quiero poder ver la landing page en mi dispositivo móvil para no tener que abrir el sitio web en un dispositivo similar a una computadora de escritorio. | 5                  | Sergio      | InProcess |
| US08    | Acceso a Centralis desde la landing page                     | TA08    | Acceso a Centralis desde la landing page                     | Como visitante, quiero acceder a Centralis directamente desde la landing page para poder interactuar con la aplicacion. | 4                  | Fabrizio    | InProcess |
| US09    | Navegación Accesible                                         | TA09    | Navegación Accesible                                         | Como visitante que utiliza tecnologías de asistencia, quiero que la landing page anuncie claramente las etiquetas de las secciones para comprender su estructura y propósito. | 7                  | Sergio      | InProcess |
| US10    | Acceder a las descripciones de las imágenes                  | TA10    | Acceder a las descripciones de las imágenes                  | Como visitante que utiliza un lector de pantalla, quiero que todas las imágenes significativas de la página de destino incluyan texto alternativo claro para poder comprender el contenido visual y navegar por el sitio web. | 8                  | Sergio      | InProcess |
| US11    | Explorar redes sociales                                      | TA11    | Explorar redes sociales                                      | Como visitante, quiero ver enlaces a las cuentas oficiales de redes sociales para seguir las actualizaciones, mantenerme informado o contactar al equipo. | 3                  | Danitza     | InProcess |
| US12    | Mostrar representaciones visuales de la aplicación.          | TA12    | Mostrar representaciones visuales de la aplicación.          | Como visitante, quiero ver ejemplos visuales de cómo funciona la aplicación para conocer más acerca de la aplicación. | 4                  | Raul        | InProcess |
| US13    | Traducir la aplicación móvil                                 | TA13    | Traducir la aplicación móvil                                 | Como empleado, quiero elegir mi idioma preferido en la interfaz de usuario para poder interactuar con la plataforma en mi idioma nativo. | 4                  | Raul        | InProcess |
| US14    | Vincular el selector de idioma al módulo i18n y activar el cambio de idioma | TA14    | Vincular el selector de idioma al módulo i18n y activar el cambio de idioma | Como desarrollador, quiero vincular un selector de idioma desplegable al módulo i18n  y activar la función dinámicamente. | 7                  | Fabrizio    | InProcess |
| US15    | Publicación básica de anuncios                               | TA15    | Publicación básica de anuncios                               | Como gerente, quiero publicar anuncios en la aplicación móvil para que los empleados estén informados de las novedades de la empresa. | 5                  | Fabrizio    | InProcess |
| US16    | Priorización de anuncios                                     | TA16    | Priorización de anuncios                                     | Como gerente, quiero marcar anuncios como prioritarios para que los empleados los vean primero. | 4                  | Sergio      | InProcess |
| US17    | Edición de anuncios                                          | TA17    | Edición de anuncios                                          | Como gerente, quiero editar anuncios ya publicados para corregir errores o actualizar información. | 4                  | Danitza     | InProcess |
| US18    | Eliminación de anuncios                                      | TA18    | Eliminación de anuncios                                      | Como gerente, quiero eliminar anuncios obsoletos para mantener la información actualizada. | 6                  | Sergio      | InProcess |
| US19    | Segmentación de anuncios por departamento                    | TA19    | Segmentación de anuncios por departamento                    | Como gerente, quiero dirigir anuncios a departamentos específicos para que la información relevante llegue solo a quienes corresponda. | 7                  | Raul        | InProcess |
| US20    | Confirmaciones de lectura                                    | TA20    | Confirmaciones de lectura                                    | Como gerente, quiero ver confirmaciones de lectura de anuncios para saber quién ha leído la información importante. | 8                  | Neil        | InProcess |
| US21    | Marcar anuncios como leídos                                  | TA21    | Marcar anuncios como leídos                                  | Como empleado, quiero marcar anuncios como leídos para llevar un control de la información revisada. | 6                  | Neil        | InProcess |
| US22    | Filtrado de anuncios por prioridad                           | TA22    | Filtrado de anuncios por prioridad                           | Como empleado, quiero filtrar anuncios por prioridad para ver primero lo más importante. | 7                  | Sergio      | InProcess |
| US23    | Comentarios en anuncios                                      | TA23    | Comentarios en anuncios                                      | Como empleado, quiero dar feedback sobre anuncios para aclarar dudas o hacer comentarios. | 5                  | Fabrizio    | InProcess |
| US24    | Subir imágenes en anuncios                                   | TA24    | Subir imágenes en anuncios                                   | Como gerente quiero poder adjuntar imágenes a los anuncios publicados, para que la información sea más clara y atractiva. | 9                  | Fabrizio    | InProcess |
| US25    | Visualizar imágenes en anuncios                              | TA25    | Visualizar imágenes en anuncios                              | Como empleado quiero poder ver las imágenes adjuntas en los anuncios, para comprender mejor la información publicada. | 7                  | Fabrizio    | InProcess |
| US26    | Creación básica de eventos                                   | TA26    | Creación básica de eventos                                   | Como gerente, quiero crear eventos en la aplicación móvil para organizar reuniones y actividades de la empresa. | 8                  | Neil        | InProcess |
| US27    | Invitación a departamentos específicos                       | TA27    | Invitación a departamentos específicos                       | Como gerente, quiero invitar a departamentos específicos a eventos para asegurar que solo participen los empleados requeridos. | 5                  | Danitza     | InProcess |
| US28    | Confirmación de asistencia                                   | TA28    | Confirmación de asistencia                                   | Como empleado, quiero confirmar mi asistencia a eventos para que los organizadores sepan cuántos asistirán. | 6                  | Neil        | InProcess |
| US29    | Cancelación de eventos                                       | TA29    | Cancelación de eventos                                       | Como gerente, quiero cancelar eventos cuando sea necesario para evitar confusiones. | 4                  | Raul        | InProcess |
| US30    | Modificación de eventos                                      | TA30    | Modificación de eventos                                      | Como gerente, quiero modificar detalles de eventos existentes para ajustar cambios de último momento. | 8                  | Neil        | InProcess |
| US31    | Eventos prioritarios                                         | TA31    | Eventos prioritarios                                         | Como gerente, quiero marcar eventos como prioritarios para que los empleados les presten especial atención. | 8                  | Danitza     | InProcess |
| US32    | Métricas de participación                                    | TA32    | Métricas de participación                                    | Como gerente, quiero ver métricas de participación en eventos para medir el engagement del equipo. | 7                  | Danitza     | InProcess |
| US33    | Creación de chats grupales                                   | TA33    | Creación de chats grupales                                   | Como empleado, quiero crear chats grupales para discutir temas específicos con mis colegas. | 5                  | Neil        | InProcess |
| US34    | Chats por departamentos                                      | TA34    | Chats por departamentos                                      | Como gerente, quiero crear chats automáticos por departamentos para facilitar la comunicación interna. | 9                  | Danitza     | InProcess |
| US35    | Eliminar grupos de chats                                     | TA35    | Eliminar grupos de chats                                     | Como gerente, quiero eliminar chats grupales para mantener el orden de las conversaciones. | 9                  | Sergio      | InProcess |
| US36    | Envío de mensajes                                            | TA36    | Envío de mensajes                                            | Como empleado, quiero enviar mensajes para mantenerme comunicado con mi equipo | 4                  | Neil        | InProcess |
| US37    | Eliminación de mensajes enviados                             | TA37    | Eliminación de mensajes enviados                             | Como empleado, quiero eliminar mensajes que envié por error para corregir mis equivocaciones. | 7                  | Raul        | InProcess |
| US38    | Modificación de mensajes enviados                            | TA38    | Modificación de mensajes enviados                            | Como empleado, quiero editar mensajes que ya envié para corregir errores tipográficos. | 5                  | Raul        | InProcess |
| US39    | Eliminación de mensajes por moderadores                      | TA39    | Eliminación de mensajes por moderadores                      | Como gerente, quiero eliminar mensajes inapropiados de cualquier chat para mantener la profesionalidad. | 6                  | Fabrizio    | InProcess |
| US40    | Eliminación de chats grupales por gerentes                   | TA40    | Eliminación de chats grupales por gerentes                   | Como gerente, quiero eliminar chats grupales obsoletos o inactivos para mantener la lista de chats organizada y relevante. | 4                  | Fabrizio    | InProcess |
| US41    | Listado organizado de chats                                  | TA41    | Listado organizado de chats                                  | Como empleado, quiero ver todos los chats de los que forma parte para encontrar rápidamente conversaciones específicas. | 3                  | Danitza     | InProcess |
| US42    | Enviar imágenes en chats grupales                            | TA42    | Enviar imágenes en chats grupales                            | Como empleado quiero poder enviar imágenes en los chats grupales, para compartir información visual con mi equipo. | 5                  | Raul        | InProcess |
| US43    | Eliminar imágenes enviadas en el chat                        | TA43    | Eliminar imágenes enviadas en el chat                        | Como usuario quiero poder eliminar una imagen enviada en un chat, para corregir errores o evitar confusiones. | 5                  | Neil        | InProcess |
| US44    | Visualizar imágenes en chats                                 | TA44    | Visualizar imágenes en chats                                 | Como empleado, quiero ver todos los chats de los que forma parte para encontrar rápidamente conversaciones específicas. | 4                  | Raul        | InProcess |
| US45    | Notificaciones de anuncios                                   | TA45    | Notificaciones de anuncios                                   | Como empleado, quiero recibir notificaciones de nuevos anuncios para estar informado. | 3                  | Neil        | InProcess |
| US46    | Notificaciones de cambios                                    | TA46    | Notificaciones de cambios                                    | Como empleado, quiero recibir notificaciones cuando los eventos cambien para estar siempre actualizado. | 5                  | Raul        | InProcess |
| US47    | Validar y almacenar datos cifrados de usuario al registrarse | TA47    | Validar y almacenar datos cifrados de usuario al registrarse | Como desarrollador, quiero validar los datos de registro entrantes y almacenar las credenciales cifradas  de los empleados para que las cuentas se creen de forma segura y estén protegidas contra accesos no autorizados. | 4                  | Fabrizio    | InProcess |
| US48    | Restringir el acceso a la API                                | TA48    | Restringir el acceso a la API                                | Como desarrollador, quiero proteger las rutas de la API mediante control de acceso basado en roles y protecciones de middleware para bloquear el acceso no autorizado. | 3                  | Fabrizio    | InProcess |
| US49    | Mantener la sesión iniciada                                  | TA49    | Mantener la sesión iniciada                                  | Como empleado, quiero mantener la sesión iniciada de forma segura en todas las sesiones para no tener que volver a autenticarme con frecuencia al volver a la aplicación. | 4                  | Fabrizio    | InProcess |
| US50    | Funcionalidad de Cierre de Sesión Seguro                     | TA50    | Funcionalidad de Cierre de Sesión Seguro                     | Como empleado, quiero cerrar sesión de forma segura en la aplicación para que mi sesión finalice por completo y no pueda ser reutilizada por terceros no autorizados. | 5                  | Neil        | InProcess |
| US51    | Invalidar tokens y borrar metadatos de sesión al cerrar sesión | TA51    | Invalidar tokens y borrar metadatos de sesión al cerrar sesión | Como desarrollador, quiero implementar un mecanismo de cierre de sesión que invalide los tokens de actualización y borre los metadatos de sesión para mejorar la seguridad | 3                  | Raul        | InProcess |
| US52    | Implementar la transmisión segura de datos y el cifrado.     | TA52    | Implementar la transmisión segura de datos y el cifrado.     | Como desarrollador, quiero asegurarme de que todos los datos confidenciales estén cifrados en reposo y se transmitan de forma segura para la seguridad de los datos. | 5                  | Neil        | InProcess |
| US53    | Implementar autenticación segura con JWT y cifrado de contraseñas | TA53    | Implementar autenticación segura con JWT y cifrado de contraseñas | Como desarrollador, quiero implementar un endpoint de autenticación y emitir JWT firmados con gestión de expiración, para que se puedan establecer sesiones de empleados seguras. | 4                  | Fabrizio    | InProcess |
| US54    | Representación de navegación y acciones basada en roles.     | TA54    | Representación de navegación y acciones basada en roles.     | Como desarrollador, quiero ver los elementos de navegación según los roles autenticados, para que los empleados solo vean las secciones a las que están autorizados a acceder. | 5                  | Danitza     | InProcess |
| US55    | Investigar la Integración de Firebase Cloud Messaging para Notificaciones en la Plataforma Fudi | TA55    | Investigar la Integración de Firebase Cloud Messaging para Notificaciones en la Plataforma Fudi | Como equipo de desarrollo de Synera, quiero investigar y prototipar la integración de Firebase Cloud Messaging (FCM) para el envío de notificaciones push a las aplicaciones móviles, para entender los requisitos técnicos, los costos, las limitaciones y el esfuerzo necesario para implementar esta funcionalidad de manera robusta y escalable. | 5                  | Neil        | InProcess |
| US56    | Registro de nueva Compania                                   | TA56    | Registro de nueva Compania                                   | Como gerente, quiero registrar mi Company en la plataforma para empezar a gestionar la comunicación de mi equipo. | 5                  | Raul        | InProcess |
| US57    | Edición de perfil de Compania                                | TA57    | Edición de perfil de Compania                                | Como gerente, quiero actualizar la información de mi Company (logo, nombre, dirección) para que los empleados identifiquen la marca. | 3                  | Danitza     | InProcess |
| US58    | Baja del servicio de Compania                                | TA58    | Baja del servicio de Compania                                | Como gerente, quiero poder desactivar la cuenta de mi Company para que toda la información y acceso de los empleados sea revocado. | 4                  | Raul        | InProcess |
| US59    | Registro de empleados por Compania                           | TA59    | Registro de empleados por Compania                           | Como gerente, quiero registrar nuevos empleados vinculándolos automáticamente a mi Company para que tengan acceso al entorno privado. | 3                  | Raul        | InProcess |
| US60    | Eliminación de miembros de la Compania                       | TA60    | Eliminación de miembros de la Compania                       | Como gerente, quiero desvincular a un empleado de mi Company para que ya no pueda acceder a los anuncios, chats o eventos privados. | 3                  | Sergio      | InProcess |
| US61    | Panel de control corporativo                                 | TA61    | Panel de control corporativo                                 | Como gerente corporativo, quiero visualizar un dashboard con el progreso y las métricas de mis empleados, para medir la participación y el uso de la plataforma. | 3                  | Sergio      | InProcess |

### 5.2.2. Implemented Landing Page Evidence

### 5.2.3. Implemented Frontend-Web Application Evidence
### 5.2.4. Acuerdo de Servicio - SaaS
### 5.2.5. Implemented Native-Mobile Application Evidence
### 5.2.6. Implemented RESTful API and/or Serverless Backend Evidence
### 5.2.7. RESTful API documentation
### 5.2.8. Team Collaboration Insights
## 5.3. Video About-the-Product.