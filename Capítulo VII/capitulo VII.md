# Capítulo VII: DevOps Practices

## 7.1. Continuous Integration

### 7.1.1. Tools and Practices
Para garantizar la viabilidad técnica y la calidad del incremento de software, el equipo de desarrollo de la startup **Fudi** ha diseñado e implementado un entorno de Integración Continua (CI) automatizado. Este enfoque permite centralizar, compilar y verificar el código fuente de forma progresiva, minimizando los conflictos de integración y asegurando la estabilidad del producto **Centralis** antes de su puesta en producción.

- **Herramientas de la Suite de Integración Continua:**
  - **Servidor de Automatización (Orquestador):** **GitHub Actions** actúa como el motor de CI, encargándose de disparar los flujos de trabajo (*workflows*) automatizados ante cada evento de código.
  - **Ecosistema del Servidor (Backend):** Se utiliza **OpenJDK 26** en conjunto con el gestor de dependencias **Apache Maven** para la automatización de la compilación, empaquetado y ejecución de pruebas del *Web Service* desarrollado en **Spring Boot**.
  - **Ecosistema Móvil (Native-Mobile):** Se emplea el SDK de **Flutter** y herramientas de CLI optimizadas para compilar la solución nativa y resolver las dependencias del proyecto.
  - **Control de Versiones:** **Git** gestiona el historial de cambios local, mientras que **GitHub** opera como el repositorio centralizado público de la organización.
- **Prácticas de Ingeniería de Software Adoptadas:**
  - **Estrategia de Ramificación (GitFlow):** Se aplica estrictamente el modelo **GitFlow**. Las funcionalidades se desarrollan de manera aislada en ramas del tipo `feature/*` y se integran exclusivamente a la rama `develop` mediante *Pull Requests* validados.
  - **Estándar de Trazabilidad (Conventional Commits):** Cada modificación en el código debe seguir la especificación de *Conventional Commits* (ej. `feat:`, `test:`, `fix:`), asegurando un historial auditable y legible.
  - **Versionado Semántico (Semantic Versioning 2.0.0):** Se utiliza la nomenclatura `MAJOR.MINOR.PATCH` para el control riguroso de los lanzamientos (*releases*) de la plataforma, correlacionando el estado del reporte con las etiquetas del repositorio.
  - **Integración sin Pérdida de Historial:** Queda estrictamente restringido el uso de comandos destructivos como `force push`. La sincronización de código se realiza mediante merges controlados y revisiones por pares para salvaguardar la integridad de la base de código.


### 7.1.2. Build & Test Suite Pipeline Components
El *pipeline* de Integración Continua está estructurado en componentes y etapas secuenciales automatizadas mediante scripts de configuración de GitHub Actions. Esto asegura que ningún fragmento de código sea integrado a la rama común sin haber superado con éxito los umbrales de compilación y pruebas de calidad.

- **Etapa de Construcción Automatizada (Build Stage):**
  - **Desencadenamiento del Pipeline:** El flujo se activa de forma automática tras el registro de un *Push* o la apertura de un *Pull Request* hacia las ramas `develop` o `main`.
  - **Entorno de Compilación Backend:** El componente de Maven ejecuta de forma aislada la descarga de dependencias del archivo `pom.xml`, compila las clases de Java y empaqueta el servicio web en un archivo ejecutable, validando la ausencia de errores sintácticos o de configuración.
  - **Entorno de Compilación Móvil:** El pipeline inicializa el entorno de Flutter, realiza la limpieza de caché (*flutter clean*), descarga los paquetes definidos en el archivo `pubspec.yaml` y ejecuta la pre-compilación del código Dart para asegurar la compatibilidad estructural de la aplicación móvil.
- **Etapa de Validación e Inyección de Pruebas (Test Suite Stage):**
  - **Ejecución de Core Entities Unit Tests:** El pipeline corre las pruebas unitarias automatizadas en aislamiento absoluto. En el backend, valida las restricciones de atributos de dominio y, en el entorno móvil, comprueba la correcta creación y modificación de las entidades de **Anuncios** y **Eventos**.
  - **Ejecución de Core Integration Tests:** Se levanta un entorno controlado en la nube de CI para simular transacciones completas. En esta fase, se comprueba el flujo integral de mensajería, creación de anuncios y el cumplimiento estricto del **aislamiento multi-tenancy** entre organizaciones de la plataforma.
  - **Ejecución de Core System Tests (E2E):** Utilizando el framework especializado **Patrol**, el pipeline ejecuta pruebas de sistema automatizadas de extremo a extremo en el entorno móvil, validando la navegación por la interfaz, el consumo real de la API RESTful desplegada y la persistencia de datos bajo diferentes escenarios operativos.



**Web service Actions :**

![image-20260529200126870](https://i.imgur.com/TihqGBh.png)

---

## 7.2. Continuous Delivery

### 7.2.1. Tools and Practices
Para asegurar un flujo de lanzamientos eficiente y desacoplado, la startup **Fudi** ha adoptado la práctica de **Entrega Continua (CD)** para la plataforma **Centralis**. Esta práctica garantiza que cualquier incremento de software que haya superado la etapa de Integración Continua (CI) sea empaquetado y preparado automáticamente para su puesta en producción en la nube.

- **Herramientas de la Suite de Entrega Continua:**
  - **Orquestador de Despliegue Nativo:** **Render PaaS** actúa de manera directa como el motor de CD para los servicios web, integrándose de forma nativa a nivel de repositorio con la organización de GitHub.
  - **Distribución de la Solución Móvil:** Se emplea **Firebase App Distribution** para la Entrega Continua del cliente nativo en Flutter, automatizando la distribución de versiones ejecutables de prueba a los miembros del equipo y evaluadores.
  - **Persistencia Integrada:** **Supabase (PostgreSQL)** opera de manera aislada como el motor de base de datos relacional para el entorno operativo transaccional.
- **Prácticas de Entrega Automatizada:**
  - **Despliegue Basado en Eventos (Git-Driven Deployment):** Se restringe cualquier tipo de intervención manual o configuraciones locales en los computadores del equipo. El entorno de producción se sincroniza directamente con la rama estable `main`.
  - **Automatización por Confirmación:** Al aprobarse un *Pull Request* e integrarse los cambios en la rama `main`, la infraestructura de **Render** detecta automáticamente el evento de *push* mediante webhooks nativos del sistema de control de versiones, iniciando la construcción interna del contenedor de manera inmediata.

### 7.2.2. Stages Deployment Pipeline Components
El *pipeline* de Entrega Continua opera de forma automatizada y transparente. Dado que el aprovisionamiento de webhooks personalizados para activar flujos cruzados externos en Render se encuentra restringido a planes de suscripción comerciales, el equipo ha estructurado un pipeline optimizado basado en el comportamiento nativo de la plataforma:

- **Etapa de Detección e Integración en la Nube (Cloud Detection Stage):**
  - **Monitoreo de Producción:** Render mantiene un escucha activo (*listener*) sobre el repositorio de GitHub. Al consolidarse el código en la rama `main`, la plataforma jala automáticamente los últimos cambios (*Git pull*) hacia sus servidores de empaquetamiento.
- **Etapa de Construcción y Puesta en Operación (Build & Live Stage):**
  - **Empaquetamiento Backend Remoto:** El servidor de Render inicializa un entorno aislado, descarga las dependencias del proyecto utilizando Apache Maven y compila el código de Java Spring Boot directamente en la nube, garantizando que el artefacto binario generado esté optimizado para el entorno productivo.
  - **Despliegue Transparente (Zero-Downtime):** Una vez concluida la compilación, Render levanta el nuevo servicio web en paralelo y realiza la transición de tráfico sin interrumpir la disponibilidad de la plataforma para las PyMEs locales, manteniendo la consistencia de los datos en Supabase.



**Imagen de Render donde se muestra el despliegue continuo**

![image-20260529200126870](https://i.imgur.com/KEfzoTc.png)




---

## 7.3. Continuous Deployment

### 7.3.1. Tools and Practices
El proceso de Despliegue Continuo (CD) en la plataforma **Centralis** representa la automatización absoluta del flujo de liberación. Una vez que los incrementos de software son consolidados en la rama `main`, el sistema despliega las modificaciones de forma inmediata hacia los entornos de producción sin intervención manual, garantizando una alta disponibilidad y resiliencia de los servicios bajo el modelo *SaaS* de **Fudi**.

- **Prácticas de Despliegue Automatizado en Producción:**
  - **Despliegue de Extremo a Extremo (Git-Triggered Production):** Cada fusión exitosa (*merge*) activa la actualización inmediata del ecosistema productivo.
  - **Estrategia de Despliegue Impecable (Zero-Downtime Deployment):** Render y Vercel aprovisionan contenedores e instancias en paralelo. El tráfico de los usuarios no se interrumpe, ya que la versión anterior solo se apaga cuando la nueva está completamente operativa (*Live* y *Healthy*).
  - **Inyección Dinámica de Variables de Entorno:** Las credenciales de producción (como `DATABASE_URL` de Supabase o las llaves de Cloudinary) se inyectan en tiempo de ejecución en la nube, aislando por completo los secretos comerciales del código fuente público.

### 7.3.2. Production Deployment Pipeline Components

Esta sección describe la topología y los componentes de infraestructura en la nube donde reside operando la solución de **Centralis** en su entorno de producción definitivo:

- **Componentes del Entorno Productivo del Backend (API REST en Render):**
  - **Source Control & Trigger:** Repositorio centralizado `web-service` (rama `main`).
  - **Runtime Environment:** Servidor remoto optimizado ejecutando **OpenJDK 26** y embebiendo la arquitectura de **Spring Boot**.
  - **Persistencia Transaccional:** Base de datos relacional **PostgreSQL** hospedada de forma desacoplada en la nube de **Supabase**, vinculada de manera segura mediante variables de entorno cifradas.
- **Componentes del Entorno Productivo del Frontend (Landing Page en Vercel):**
  - **Source Control & Trigger:** Repositorio centralizado `landing-page` (rama `main`).
  - **Hosting & CDN Edge:** Infraestructura global de **Vercel**, configurada para optimizar el SEO y garantizar tiempos de carga mínimos para los visitantes y PyMEs interesadas.
- **Integración de Servicios Externos en el Entorno de Producción:**
  - **Almacenamiento de Multimedia:** **Cloudinary** opera como el microservicio en la nube para la persistencia, optimización y entrega dinámica de archivos multimedia (imágenes asociadas a los anuncios de las empresas y avatares de chats).
  - **Mensajería Instantánea:** Integración con servicios en la nube para asegurar la comunicación interactiva y la sincronización de eventos de la plataforma en tiempo real.



## 7.4. Continuous Monitoring

### 7.4.1. Tools and Practices

El enfoque de monitoreo de la plataforma se basa en la supervisión de la disponibilidad (*Uptime*) y la latencia de las peticiones en un entorno productivo 24/7.

- **Herramientas de la Suite de Monitoreo:**
  - **Motor de Vigilancia Externa (Uptime Engine):** Se utiliza **UptimeRobot / Better Stack** como la plataforma externa para realizar sondeos cíclicos sobre la disponibilidad del servicio web.
  - **Manejador de Eventos (Log Collector):** El panel de control nativo de **Render Logs** recopila los eventos de errores en tiempo de ejecución (Stack traces de Java Spring Boot).
  - **Centralizador de Comunicaciones:** **Discord Developer Webhooks** actúa como la plataforma receptora de notificaciones de incidentes en tiempo real para el equipo de desarrollo.
- **Prácticas de Monitoreo Adoptadas:**
  - **Inspección de Caja Negra (Synthetic Monitoring):** Se ejecutan peticiones automatizadas HTTP GET simuladas hacia los *endpoints* core de anuncios y eventos para asegurar que las rutas de la API devuelvan un código de estado exitoso (HTTP Status 200).
  - **Monitoreo Basado en Cron-Jobs:** Se integra en el repositorio de GitHub un flujo programado que audita la latencia del servidor a intervalos regulares, eliminando la necesidad de revisiones manuales por parte de los desarrolladores.

### 7.4.2. Monitoring Pipeline Components

El componente de monitoreo está automatizado mediante un flujo de trabajo síncrono que evalúa constantemente el estado del sistema en la nube:

- **Source Metric / Endpoint Validation:** El pipeline apunta directamente al *endpoint* de verificación de estado de la aplicación en Render.
- **Frecuencia de Sondeo:** El motor externo está configurado para emitir ráfagas de verificación cada **5 minutos**. Si el servicio responde dentro del umbral de tiempo tolerable, el evento se registra como exitoso (*Healthy*). Si se excede el tiempo límite (*Timeout*) o devuelve un error de servidor (HTTP 5xx), se activa de inmediato el flujo de contención de fallas.

### 7.4.3. Alerting Pipeline Components

Una vez que el componente de monitoreo detecta una anomalía estructural en los servicios de **Centralis**, el pipeline de alertas procesa la información bajo las siguientes métricas de evaluación:

- **Reglas de Activación de Alertas (Alerting Rules):** Una alerta se clasifica en estado crítico (*Triggered*) cuando el servidor encadenado acumula dos fallas consecutivas de conectividad, evitando falsos positivos por micro-caídas de red.
- **Cifrado y Seguridad de Datos:** Las alertas incluyen metadatos clave como el código del error HTTP, la hora exacta del incidente en formato UTC y la sección afectada (Backend API o Base de Datos), aislando cualquier credencial confidencial del mensaje.

### 7.4.4. Notification Pipeline Components. 

El último eslabón de la infraestructura DevOps de monitoreo se encarga de transferir la alerta procesada de forma transparente hacia los ingenieros responsables:

- **Canal de Destino Automatizado:** La alerta estructurada es enviada mediante una petición HTTP POST en formato JSON directamente hacia el webhook del canal privado de ingeniería en Discord (`#server-alerts`).
- **Información Desplegada:** El mensaje recibido en los dispositivos móviles y de escritorio de los desarrolladores detalla de forma clara el estado del incidente (Ej: `🔴 CRITICAL: Centralis API on Render is DOWN - HTTP Status 502 Bad Gateway`). Una vez solucionado el problema, el pipeline dispara de forma automática una notificación de cierre (Ej: `🟢 RESOLVED: Centralis API is operational - Uptime Restored`), cerrando el ciclo de retroalimentación de operaciones de la entrega.
