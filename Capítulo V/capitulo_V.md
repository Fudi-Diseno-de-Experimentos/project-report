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
| US10    | Publicación básica de anuncios                               | TA10    | Publicación básica de anuncios                               | Como gerente, quiero publicar anuncios en la aplicación móvil para que los empleados estén informados de las novedades de la empresa. | 5                  | Fabrizio    | InProcess |
| US11    | Priorización de anuncios                                     | TA11    | Priorización de anuncios                                     | Como gerente, quiero marcar anuncios como prioritarios para que los empleados los vean primero. | 4                  | Sergio      | InProcess |
| US12    | Edición de anuncios                                          | TA12    | Edición de anuncios                                          | Como gerente, quiero editar anuncios ya publicados para corregir errores o actualizar información. | 4                  | Danitza     | InProcess |
| US13    | Eliminación de anuncios                                      | TA13    | Eliminación de anuncios                                      | Como gerente, quiero eliminar anuncios obsoletos para mantener la información actualizada. | 6                  | Sergio      | InProcess |
| US14    | Confirmaciones de lectura                                    | TA14    | Confirmaciones de lectura                                    | Como gerente, quiero ver confirmaciones de lectura de anuncios para saber quién ha leído la información importante. | 8                  | Neil        | InProcess |
| US15    | Comentarios en anuncios                                      | TA15    | Comentarios en anuncios                                      | Como empleado, quiero dar feedback sobre anuncios para aclarar dudas o hacer comentarios. | 5                  | Fabrizio    | InProcess |
| US16    | Subir imágenes en anuncios                                   | TA16    | Subir imágenes en anuncios                                   | Como gerente quiero poder adjuntar imágenes a los anuncios publicados, para que la información sea más clara y atractiva. | 9                  | Fabrizio    | InProcess |
| US17    | Visualizar imágenes en anuncios                              | TA17    | Visualizar imágenes en anuncios                              | Como empleado quiero poder ver las imágenes adjuntas en los anuncios, para comprender mejor la información publicada. | 7                  | Fabrizio    | InProcess |
| US18    | Creación básica de eventos                                   | TA18    | Creación básica de eventos                                   | Como gerente, quiero crear eventos en la aplicación móvil para organizar reuniones y actividades de la empresa. | 8                  | Neil        | InProcess |
| US19    | Cancelación de eventos                                       | TA19    | Cancelación de eventos                                       | Como gerente, quiero cancelar eventos cuando sea necesario para evitar confusiones. | 4                  | Raul        | InProcess |
| US20    | Modificación de eventos                                      | TA20    | Modificación de eventos                                      | Como gerente, quiero modificar detalles de eventos existentes para ajustar cambios de último momento. | 8                  | Neil        | InProcess |
| US21    | Eventos prioritarios                                         | TA21    | Eventos prioritarios                                         | Como gerente, quiero marcar eventos como prioritarios para que los empleados les presten especial atención. | 8                  | Danitza     | InProcess |
| US22    | Métricas de participación                                    | TA22    | Métricas de participación                                    | Como gerente, quiero ver métricas de participación en eventos para medir el engagement del equipo. | 7                  | Danitza     | InProcess |
| US23    | Creación de chats grupales                                   | TA23    | Creación de chats grupales                                   | Como empleado, quiero crear chats grupales para discutir temas específicos con mis colegas. | 5                  | Neil        | InProcess |
| US24    | Eliminar grupos de chats                                     | TA24    | Eliminar grupos de chats                                     | Como gerente, quiero eliminar chats grupales para mantener el orden de las conversaciones. | 9                  | Sergio      | InProcess |
| US25    | Envío de mensajes                                            | TA25    | Envío de mensajes                                            | Como empleado, quiero enviar mensajes para mantenerme comunicado con mi equipo | 4                  | Neil        | InProcess |
| US26    | Eliminación de mensajes enviados                             | TA26    | Eliminación de mensajes enviados                             | Como empleado, quiero eliminar mensajes que envié por error para corregir mis equivocaciones. | 7                  | Raul        | InProcess |
| US27    | Modificación de mensajes enviados                            | TA27    | Modificación de mensajes enviados                            | Como empleado, quiero editar mensajes que ya envié para corregir errores tipográficos. | 5                  | Raul        | InProcess |
| US28    | Eliminación de chats grupales por gerentes                   | TA28    | Eliminación de chats grupales por gerentes                   | Como gerente, quiero eliminar chats grupales obsoletos o inactivos para mantener la lista de chats organizada y relevante. | 4                  | Fabrizio    | InProcess |
| US29    | Listado organizado de chats                                  | TA29    | Listado organizado de chats                                  | Como empleado, quiero ver todos los chats de los que forma parte para encontrar rápidamente conversaciones específicas. | 3                  | Danitza     | InProcess |
| US30    | Enviar imágenes en chats grupales                            | TA30    | Enviar imágenes en chats grupales                            | Como empleado quiero poder enviar imágenes en los chats grupales, para compartir información visual con mi equipo. | 5                  | Raul        | InProcess |
| US31    | Eliminar imágenes enviadas en el chat                        | TA31    | Eliminar imágenes enviadas en el chat                        | Como usuario quiero poder eliminar una imagen enviada en un chat, para corregir errores o evitar confusiones. | 5                  | Neil        | InProcess |
| US32    | Visualizar imágenes en chats                                 | TA32    | Visualizar imágenes en chats                                 | Como empleado, quiero ver todos los chats de los que forma parte para encontrar rápidamente conversaciones específicas. | 4                  | Raul        | InProcess |
| US33    | Validar y almacenar datos cifrados de usuario al registrarse | TA33    | Validar y almacenar datos cifrados de usuario al registrarse | Como desarrollador, quiero validar los datos de registro entrantes y almacenar las credenciales cifradas  de los empleados para que las cuentas se creen de forma segura y estén protegidas contra accesos no autorizados. | 4                  | Fabrizio    | InProcess |
| US34    | Restringir el acceso a la API                                | TA34    | Restringir el acceso a la API                                | Como desarrollador, quiero proteger las rutas de la API mediante control de acceso basado en roles y protecciones de middleware para bloquear el acceso no autorizado. | 3                  | Fabrizio    | InProcess |
| US35    | Mantener la sesión iniciada                                  | TA35    | Mantener la sesión iniciada                                  | Como empleado, quiero mantener la sesión iniciada de forma segura en todas las sesiones para no tener que volver a autenticarme con frecuencia al volver a la aplicación. | 4                  | Fabrizio    | InProcess |
| US36    | Funcionalidad de Cierre de Sesión Seguro                     | TA36    | Funcionalidad de Cierre de Sesión Seguro                     | Como empleado, quiero cerrar sesión de forma segura en la aplicación para que mi sesión finalice por completo y no pueda ser reutilizada por terceros no autorizados. | 5                  | Neil        | InProcess |
| US37    | Invalidar tokens y borrar metadatos de sesión al cerrar sesión | TA37    | Invalidar tokens y borrar metadatos de sesión al cerrar sesión | Como desarrollador, quiero implementar un mecanismo de cierre de sesión que invalide los tokens de actualización y borre los metadatos de sesión para mejorar la seguridad | 3                  | Raul        | InProcess |
| US38    | Implementar autenticación segura con JWT y cifrado de contraseñas | TA38    | Implementar autenticación segura con JWT y cifrado de contraseñas | Como desarrollador, quiero implementar un endpoint de autenticación y emitir JWT firmados con gestión de expiración, para que se puedan establecer sesiones de empleados seguras. | 4                  | Fabrizio    | InProcess |
| US39    | Representación de navegación y acciones basada en roles.     | TA39    | Representación de navegación y acciones basada en roles.     | Como desarrollador, quiero ver los elementos de navegación según los roles autenticados, para que los empleados solo vean las secciones a las que están autorizados a acceder. | 5                  | Danitza     | InProcess |
| US40    | Investigar la Integración de Firebase Cloud Messaging para Notificaciones en la Plataforma Fudi | TA40    | Investigar la Integración de Firebase Cloud Messaging para Notificaciones en la Plataforma Fudi | Como equipo de desarrollo de Synera, quiero investigar y prototipar la integración de Firebase Cloud Messaging (FCM) para el envío de notificaciones push a las aplicaciones móviles, para entender los requisitos técnicos, los costos, las limitaciones y el esfuerzo necesario para implementar esta funcionalidad de manera robusta y escalable. | 5                  | Neil        | InProcess |
| US41    | Registro de nueva Compania                                   | TA41    | Registro de nueva Compania                                   | Como gerente, quiero registrar mi Company en la plataforma para empezar a gestionar la comunicación de mi equipo. | 5                  | Raul        | InProcess |
| US42    | Edición de perfil de Compania                                | TA42    | Edición de perfil de Compania                                | Como gerente, quiero actualizar la información de mi Company (logo, nombre, dirección) para que los empleados identifiquen la marca. | 3                  | Danitza     | InProcess |
| US43    | Baja del servicio de Compania                                | TA43    | Baja del servicio de Compania                                | Como gerente, quiero poder desactivar la cuenta de mi Company para que toda la información y acceso de los empleados sea revocado. | 4                  | Raul        | InProcess |
| US44    | Registro de empleados por Compania                           | TA44    | Registro de empleados por Compania                           | Como gerente, quiero registrar nuevos empleados vinculándolos automáticamente a mi Company para que tengan acceso al entorno privado. | 3                  | Raul        | InProcess |
| US45    | Eliminación de miembros de la Compania                       | TA45    | Eliminación de miembros de la Compania                       | Como gerente, quiero desvincular a un empleado de mi Company para que ya no pueda acceder a los anuncios, chats o eventos privados. | 3                  | Sergio      | InProcess |
| US46    | Panel de control corporativo                                 | TA46    | Panel de control corporativo                                 | Como gerente corporativo, quiero visualizar un dashboard con el progreso y las métricas de mis empleados, para medir la participación y el uso de la plataforma. | 3                  | Sergio      | InProcess |

### 5.2.2. Implemented Landing Page Evidence

### 5.2.3. Implemented Frontend-Web Application Evidence
### 5.2.4. Acuerdo de Servicio - SaaS

<p style="text-indent: 1.25cm;">El presente Acuerdo de Servicio establece el marco legal y operativo que rige el uso de la plataforma Centralis, provista por Fudi bajo el modelo de Software como Servicio (SaaS). Este documento garantiza la transparencia en la prestación del servicio y define las responsabilidades tanto del proveedor como de las organizaciones usuarias.

 

**1. Aceptación de los Términos y Condiciones de Servicio (TOS)**
<p style="text-indent: 1.25cm;">Al acceder, registrarse o utilizar cualquier componente de la solución Centralis (incluyendo su landing page, aplicación web, API RESTful y futuras aplicaciones móviles), la organización suscriptora y sus usuarios finales aceptan de manera explícita e irrevocable los presentes términos. Esta aceptación constituye un requisito legal y técnico previo para la habilitación de la cuenta corporativa y el acceso a los servicios.

**2. Descripción del Servicio, Modelo de Despliegue y Acuerdo de Nivel de Servicio (SLA)**
<p style="text-indent: 1.25cm;">Fudi provee Centralis bajo el modelo de Software como Servicio (SaaS). La plataforma se despliega utilizando una arquitectura multi-tenancy, garantizando el aislamiento lógico y físico de los datos de cada suscriptor.

- **Componentes del Servicio:** El servicio comprende el acceso a una infraestructura en la nube que soporta procesos de comunicación interna, gestión de anuncios y coordinación de equipos en tiempo real.
- **Compromiso de Disponibilidad (SLA):** El Proveedor se compromete a mantener una disponibilidad del **99.5%** mensual, excluyendo ventanas de mantenimiento programado que serán notificadas con al menos 72 horas de anticipación. El incumplimiento de este SLA dará derecho al Suscriptor a créditos de servicio según la tabla de compensaciones disponible en el portal de soporte.

**3. Responsabilidades del Usuario y Gobernanza de Datos**

- **Del Suscriptor:** La organización cliente es responsable de la administración de sus usuarios, la asignación y revocación del rol de **Manager** (administrador de la instancia corporativa), y el cumplimiento de las leyes de protección de datos aplicables (ej. Ley 29733 - Ley de Protección de Datos Personales, Perú).
- **De los Usuarios Finales:** Cada usuario se compromete a mantener la confidencialidad de sus credenciales de acceso, no compartirlas con terceros no autorizados, y utilizar la plataforma únicamente para fines profesionales y lícitos, respetando la privacidad e integridad de la comunicación organizacional.

**4. Propiedad Intelectual y Licencias de Uso**

- **Del Proveedor (Fudi):** Fudi retiene la titularidad exclusiva sobre todos los derechos de propiedad intelectual, incluyendo pero no limitándose a: código fuente (implementado en **Java Spring Boot** para el backend y **Flutter/Dart** para el frontend mobile), diseños de interfaz de usuario (basados en **Material Design**), arquitectura de software (diagramas C4, UML), algoritmos, marcas, logos, y documentación técnica del proyecto.
- **Del Suscriptor:** El Suscriptor mantiene la plena propiedad sobre todos los datos, contenidos e información que genere, ingrese o procese a través de la plataforma ("Sus Datos").
- **Licencia de Datos:** Al utilizar el servicio, el Suscriptor otorga a Fudi una licencia mundial, no exclusiva, libre de regalías y limitada en el tiempo para usar, procesar y almacenar "Sus Datos" exclusivamente con el propósito de: (a) proporcionar, mantener y mejorar el servicio; (b) generar informes agregados y anonimizados para análisis de rendimiento y seguridad; y (c) cumplir con obligaciones legales. Fudi no venderá ni compartirá "Sus Datos" con terceros para fines de marketing sin el consentimiento explícito del Suscriptor.

**5. Acuerdo de Nivel de Servicio (SLA) y Soporte Técnico**

- **Soporte:** Fudi proporcionará soporte técnico para la resolución de incidencias que afecten la funcionalidad crítica del sistema. Los niveles de severidad y los tiempos de respuesta se definen en la siguiente tabla:

| Nivel de Severidad    | Descripción                                                  | Tiempo de Respuesta Objetivo   |
| :-------------------- | :----------------------------------------------------------- | :----------------------------- |
| **Crítico (Nivel 1)** | El servicio no está disponible para toda la organización o se ha producido una pérdida/degradación severa de datos. | < 2 horas (24/7)               |
| **Alto (Nivel 2)**    | Una función principal está inoperable para un segmento de usuarios, pero existe un workaround temporal. | < 8 horas (en horario laboral) |
| **Medio (Nivel 3)**   | Un problema menor que no bloquea el uso del producto (ej. error en una etiqueta UI, comportamiento inesperado pero no crítico). | < 48 horas                     |

- **Mantenimiento:** Los mantenimientos programados se comunicarán a través de la plataforma (con al menos 5 días hábiles de anticipación) y se realizarán, de ser posible, en horarios de bajo impacto.

**6. Restricciones de Uso y Conducta Prohibida**
Queda estrictamente prohibido cualquier actividad que constituya una violación a la seguridad, integridad o disponibilidad del sistema. Esto incluye, pero no se limita a:

- Realizar ingeniería inversa, descompilar o desensamblar los productos digitales (aplicación web, API, etc.).
- Intentar vulnerar, eludir o sortear cualquier medida de seguridad, autenticación o control de acceso.
- Utilizar la plataforma para transmitir contenido ilegal, difamatorio, abusivo, obsceno o que infrinja derechos de propiedad intelectual de terceros.
- Realizar pruebas de carga, estrés o penetración sin la autorización previa y por escrito de Fudi.
- El incumplimiento de estas normas constituye una violación material del acuerdo y facultará a Fudi para suspender o terminar el servicio de forma inmediata.

**7. Limitación de Responsabilidad**
<p style="text-indent: 1.25cm;">En la máxima medida permitida por la ley aplicable, Fudi no será responsable por pérdidas indirectas, incidentales, especiales, consecuentes o punitivas, ni por pérdida de beneficios o datos, derivadas del uso o la imposibilidad de usar el servicio, incluso si se ha advertido de la posibilidad de dichos daños. La responsabilidad total acumulativa de Fudi por cualquier reclamación relacionada con este acuerdo no excederá el monto total de las tarifas pagadas por el Suscriptor durante los doce (12) meses anteriores a la reclamación.

**8. Legislación Aplicable y Confidencialidad**
<p style="text-indent: 1.25cm;">Este acuerdo se regirá e interpretará de acuerdo con las leyes de la República del Perú. Cualquier disputa será sometida a la jurisdicción exclusiva de los tribunales de Lima, Perú.

### 5.2.5. Implemented Native-Mobile Application Evidence
### 5.2.6. Implemented RESTful API and/or Serverless Backend Evidence
### 5.2.7. RESTful API documentation

<p style="text-indent: 1.25cm;">En el contexto del Sprint actual, se ha desarrollado y desplegado la API RESTful que sirve como backend para la plataforma Centralis. La documentación sigue el estándar OpenAPI Specification (Swagger) y está disponible de forma interactiva en el entorno de producción. A continuación, se presenta un resumen de los *bounded contexts* implementados, los endpoints principales, el esquema de autenticación y ejemplos de interacción.

**Base URL y Versiones**

Todos los endpoints descritos en esta sección están prefijados con `/api/v1` y se acceden a través de la siguiente base URL:

- **Producción:** `https://`
- **Staging:** `https://`

**Autenticación y Autorización**

La API utiliza **JSON Web Tokens (JWT)** para la autenticación. Para todos los requests que requieran autorización (endpoints protegidos), el cliente debe incluir el token en el encabezado `Authorization`:

```
Authorization: Bearer <your_jwt_token>
```

El token se obtiene mediante el endpoint de autenticación (`/auth/sign-in`). Los roles disponibles (`Admin`, `Manager`, `Employee`) determinan los permisos de acceso a cada recurso.

**Resumen de Contextos Implementados (Bounded Contexts)**

A continuación, se detallan los bounded contexts implementados en esta versión de la API, los cuales reflejan la arquitectura dirigida por dominio (DDD) de la solución.

| Bounded Context                          | Descripción                                                  | Endpoint Base                   |
| :--------------------------------------- | :----------------------------------------------------------- | :------------------------------ |
| **Identity and Access Management (IAM)** | Gestiona la autenticación, registro de usuarios, perfiles y roles. | `/api/v1/auth`, `/api/v1/users` |
| **Announcements**                        | Administra la creación, edición, eliminación y consulta de anuncios y sus comentarios. | `/api/v1/announcements`         |
| **Events**                               | Gestiona los eventos del calendario organizacional.          | `/api/v1/events`                |
| **Company**                              | Administra los datos de las empresas suscriptoras.           | `/api/v1/companies`             |
| **Profile**                              | Gestiona los perfiles extendidos de los usuarios, incluyendo su afiliación a compañías. | `/api/v1/profiles`              |
| **Chat**                                 | Proporciona funcionalidad de mensajería en tiempo real (grupos, mensajes, imágenes) y streaming de eventos vía SSE. | `/api/v1/groups`, `/api/v1/sse` |

**Endpoints Principales**

Para cada contexto, se listan los endpoints más relevantes, su verbo HTTP, sintaxis y un ejemplo de respuesta.

**1. Contexto: Identity and Access Management (IAM)**

| Acción             | Verbo  | Endpoint          | Descripción                                                  |
| :----------------- | :----- | :---------------- | :----------------------------------------------------------- |
| Registrar usuario  | `POST` | `/auth/sign-up`   | Crea un nuevo usuario en el sistema.                         |
| Iniciar sesión     | `POST` | `/auth/sign-in`   | Autentica al usuario y devuelve un `access_token` y `refresh_token`. |
| Obtener usuarios   | `GET`  | `/users`          | Retorna la lista de todos los usuarios (requiere rol `Admin`). |
| Actualizar usuario | `PUT`  | `/users/{userId}` | Actualiza los datos de un usuario específico.                |

**2. Contexto: Announcements**

| Acción                | Verbo  | Endpoint                                   | Descripción                                                  |
| :-------------------- | :----- | :----------------------------------------- | :----------------------------------------------------------- |
| Crear anuncio         | `POST` | `/announcements`                           | Crea un nuevo anuncio. En el body se envía título, contenido y prioridad. |
| Obtener anuncios      | `GET`  | `/announcements`                           | Obtiene todos los anuncios (soporta paginación vía `?page=0&size=10`). |
| Obtener por prioridad | `GET`  | `/announcements/priority/{priority}`       | Filtra anuncios por `HIGH`, `MEDIUM` o `LOW`.                |
| Agregar comentario    | `POST` | `/announcements/{announcementId}/comments` | Añade un comentario a un anuncio.                            |

**3. Contexto: Chat (Tiempo Real)**

| Acción               | Verbo  | Endpoint                     | Descripción                                                  |
| :------------------- | :----- | :--------------------------- | :----------------------------------------------------------- |
| Crear grupo          | `POST` | `/groups`                    | Crea un nuevo grupo de chat con nombre y visibilidad (`PUBLIC`/`PRIVATE`). |
| Enviar mensaje       | `POST` | `/groups/{groupId}/messages` | Envía un nuevo mensaje a un grupo específico.                |
| Obtener mensajes     | `GET`  | `/groups/{groupId}/messages` | Recupera el historial de mensajes de un grupo.               |
| Streaming de eventos | `GET`  | `/sse/chat/{groupId}`        | Establece una conexión Server-Sent Events (SSE) para recibir eventos de chat en tiempo real. |

### 5.2.8. Team Collaboration Insights
## 5.3. Video About-the-Product.