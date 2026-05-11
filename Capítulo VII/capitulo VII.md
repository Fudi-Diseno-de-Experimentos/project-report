# Capítulo VII: DevOps Practices

## 7.1. Continuous Integration

### 7.1.1. Tools and Practices
En el desarrollo del proyecto se ha adoptado un conjunto de herramientas y prácticas orientadas a asegurar la integración continua del software, facilitando la colaboración entre los distintos miembros del equipo y garantizando la calidad del código a lo largo del ciclo de desarrollo.
* **Herramientas utilizadas**
  * Backend: OpenJDK, Spring Boot y Apache Maven para la construcción y ejecución del servicio backend.
  * Frontend móvil: Android Studio como entorno de desarrollo principal para la aplicación móvil.
  * Base de datos: PostgreSQL desplegado en Render para la persistencia de datos.
  * Control de versiones: Git como sistema de control de versiones y GitHub como repositorio central del proyecto.
  * Despliegue: Render como plataforma de despliegue del backend.
  * Almacenamiento externo: Cloudinary para la gestión de recursos multimedia.
  * Gestión del proyecto: Trello para la organización de tareas y seguimiento del progreso.
  * Gestión de requisitos: UXPressia para modelado de necesidades de usuario.
  * Documentación técnica: PlantUML para diagramas de arquitectura y diseño.
  * Diseño UI/UX: Material Design 3 como guía de diseño visual, complementado con herramientas de prototipado (como Figma en algunos casos).


* **Prácticas de desarrollo**
El equipo adopta una metodología basada en GitFlow, utilizando ramas estructuradas como develop, feature/* y ramas de integración. Además, se aplican prácticas de commits estructurados mediante Conventional Commits, lo que permite mantener un historial de cambios claro y trazable.
Asimismo, se emplea versionado semántico (SemVer), facilitando la gestión de releases del sistema. La integración del código se realiza de manera progresiva mediante merges controlados hacia la rama develop, evitando el uso de force push para preservar la integridad del historial del repositorio.


### 7.1.2. Build & Test Suite Pipeline Components
El pipeline de integración del proyecto se compone de distintas etapas orientadas a la construcción y validación del software antes de su integración al entorno compartido.

**Etapa de construcción (Build)**
* El backend es construido utilizando Apache Maven, que gestiona dependencias, compilación y empaquetado del proyecto Spring Boot.
* La aplicación móvil es construida mediante Android Studio, generando las versiones ejecutables del sistema móvil.
* El código fuente es obtenido desde GitHub, específicamente desde la rama develop, donde se integran las funcionalidades del equipo.

**Etapa de pruebas (Testing Suite)**
*El sistema incorpora distintos niveles de pruebas para garantizar la calidad del software.*
* Core Entities Unit Tests: validan la lógica de dominio de los principales componentes del sistema.
* Core Integration Tests: verifican la correcta interacción entre módulos del backend, incluyendo flujos multi-tenancy y comunicación entre contextos.
* System/UI Tests: realizados mediante Selenium IDE, validando el correcto funcionamiento de la landing page y sus componentes interactivos.
  Estas pruebas permiten detectar errores de forma temprana antes de la integración de nuevas funcionalidades al sistema principal.

---

## 7.2. Continuous Delivery

### 7.2.1. Tools and Practices
El proceso de entrega continua del sistema se basa en un conjunto de herramientas que permiten la publicación y actualización progresiva de los componentes del sistema en entornos de desarrollo y producción.
* **Herramientas utilizadas**
  * Render: Utilizado para el despliegue del backend en la nube.
  * PostgreSQL (Render): Base de datos gestionada en la nube para el entorno de producción.
  * Cloudinary: Almacenamiento y gestión de recursos multimedia en la nube.
  * GitHub: Repositorio central desde donde se obtienen las versiones del código para despliegue.
  * Android Studio: Utilizado para generar y actualizar las versiones de la aplicación móvil.


* **Prácticas de entrega**
El equipo sigue un flujo de entrega basado en la rama develop, desde la cual se integran las funcionalidades listas para ser desplegadas. Las actualizaciones del sistema se realizan de manera controlada, asegurando que cada cambio pase por un proceso de construcción y validación antes de su publicación.
El despliegue del backend se realiza manualmente en Render a partir de la versión estable del repositorio, mientras que la aplicación móvil se actualiza mediante generación de nuevas versiones desde Android Studio.

### 7.2.2. Stages Deployment Pipeline Components
El pipeline de despliegue del sistema se estructura en varias etapas que garantizan la correcta entrega de las funcionalidades al entorno de producción.
1. Integración del código:
    Los cambios realizados por los desarrolladores son integrados en la rama develop del repositorio en GitHub, siguiendo el flujo de GitFlow.
2. Construcción del sistema:
    * El backend es compilado utilizando Maven.
    * La aplicación móvil es construida en Android Studio. 
3. Validación mediante pruebas:
    Antes del despliegue, se ejecutan pruebas unitarias, de integración y pruebas de interfaz (Selenium), asegurando la estabilidad del sistema.
4. Despliegue del backend:
   El backend es desplegado en la plataforma Render, que gestiona la ejecución del servicio en la nube. 
5. Persistencia y servicios externos:
   La base de datos PostgreSQL y el almacenamiento en Cloudinary son integrados como servicios externos del sistema en producción.
6. Actualización del cliente móvil:
   Las nuevas versiones de la aplicación móvil son generadas desde Android Studio y preparadas para su distribución.


---

## 7.3. Continuous Deployment

### 7.3.1. Tools and Practices
El proceso de despliegue continuo en el sistema Centralis se basa en un conjunto de herramientas, frameworks y prácticas de desarrollo que permiten automatizar la entrega de nuevas versiones del software hacia entornos de producción, garantizando consistencia, trazabilidad y calidad del código.

**Entorno de desarrollo y frameworks**  
El desarrollo del sistema se realiza utilizando IntelliJ IDEA para el backend implementado en Spring Boot (Java 24), mientras que la aplicación móvil es desarrollada en Flutter mediante Android Studio como entorno principal.

**Gestión de repositorios**     
Se utiliza GitHub Organization que contiene repositorios independientes para los distintos componentes del sistema: Landing Page, Web Services y aplicación móvil. Esta separación permite una gestión modular del código, facilitando la escalabilidad y el mantenimiento del sistema.

**Control de versiones**    
El equipo adopta prácticas basadas en Conventional Commits junto con Semantic Versioning, lo que permite estandarizar los cambios en el código, mejorar la trazabilidad del desarrollo y facilitar la coordinación entre los miembros del equipo.

**Prácticas de calidad**    
Se aplican estándares de desarrollo como Java Coding Conventions, asegurando un código limpio y mantenible en el backend. Asimismo, se utiliza Material Design 3 para garantizar una experiencia de usuario consistente en la aplicación móvil y web.

### 7.3.2. Production Deployment Pipeline Components
El pipeline de despliegue a producción está compuesto por distintos módulos que automatizan el flujo de entrega del sistema desde el repositorio hasta el usuario final.

#### **Componentes del Pipeline del Backend (Spring Boot en Render)**
* **Source Control:** El código fuente reside en el repositorio web-service de GitHub.
* **Build & Runtime:** Configurado bajo Java 24 con Spring Boot, gestionado por Apache Maven para la administración de dependencias.
* **Deployment Host:** Despliegue automatizado en Render, sincronizado directamente con la rama main del repositorio.
* **Persistencia:** Base de datos PostgreSQL alojada también en Render, permitiendo una conexión segura mediante variables de entorno (DATABASE_URL).

#### **Componentes del Pipeline del Frontend (Landing Page en Vercel)**
* **Framework:** Desarrollada con Astro para optimizar la velocidad y el SEO.
* **Source Control:** Repositorio landing-page en GitHub.
* **Hosting y CDN:** Despliegue automático en la infraestructura de Vercel, aprovechando su red de entrega de contenidos para garantizar acceso global rápido.

#### **Integración de Servicios Externos en Producción**
* **Multimedia:** Se utiliza Cloudinary como servicio externo para el almacenamiento y optimización de imágenes utilizadas en el sistema (anuncios, chats y recursos dinámicos).
* **Mensajería:** Se integra Firebase Cloud Messaging (FCM) para el envío de notificaciones push hacia dispositivos móviles, mejorando la comunicación en tiempo real dentro de la plataforma.
