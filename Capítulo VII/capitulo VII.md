# Capítulo VII: DevOps Practices

## 7.1. Continuous Integration

### 7.1.1. Tools and Practices
*(Sección pendiente de desarrollo por el encargado)*

### 7.1.2. Build & Test Suite Pipeline Components
*(Sección pendiente de desarrollo por el encargado)*

---

## 7.2. Continuous Delivery

### 7.2.1. Tools and Practices
*(Sección pendiente de desarrollo por el encargado)*

### 7.2.2. Stages Deployment Pipeline Components
*(Sección pendiente de desarrollo por el encargado)*

---

## 7.3. Continuous Deployment

### 7.3.1. Tools and Practices
Las herramientas y prácticas utilizadas para implementar la infraestructura de desarrollo y despliegue continuo en **Centralis** incluyen:

* **Entorno de Desarrollo y Frameworks:** Se utiliza IntelliJ IDEA y Android Studio como IDEs principales para el desarrollo del backend en Spring Boot (Java 24) y la aplicación móvil en Flutter.
* **Gestión de Repositorios:** Uso de GitHub Organization, con repositorios independientes para la Landing Page, Web Services y la aplicación móvil, asegurando la trazabilidad de los commits y Pull Requests.
* **Control de Versiones:** Implementación de Conventional Commits y versionado semántico (Semantic Versioning) para estandarizar los cambios en el código y facilitar la comunicación técnica en el equipo.
* **Prácticas de Calidad:** Adopción de las JAVA Coding Conventions y Material Design 3 para garantizar un código limpio y una experiencia de usuario consistente en todas las plataformas.

### 7.3.2. Production Deployment Pipeline Components
Esta sección describe los componentes del pipeline de despliegue a producción que automatizan el flujo desde el repositorio hasta el usuario final:

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
* **Multimedia:** Uso de Cloudinary para el almacenamiento y gestión optimizada de imágenes dinámicas enviadas en anuncios y chats.
* **Mensajería:** Integración de Firebase Cloud Messaging (FCM) para la orquestación y envío de notificaciones push a los dispositivos móviles.