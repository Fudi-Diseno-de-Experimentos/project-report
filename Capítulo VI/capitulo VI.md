# Capítulo VI: Product Verification & Validation

## 6.1. Testing Suites & Validation

### 6.1.1. Core Entities Unit Tests

Para la elaboración de los principales tests de nuestra Landing Page (**Centralis**), hemos tenido en cuenta las secciones más importantes que garantizan la correcta navegación y propuesta de valor para el usuario:

* **Features:** Verificación de la visibilidad de las funcionalidades clave para la alineación de equipos.
* **How it works:** Validación del flujo de información sobre el funcionamiento del hub centralizado.
* **Product / Help Center:** Comprobación de los accesos a la documentación y soporte.
* **Sign In / Get Started:** Test de interactividad de los botones de llamada a la acción (Call to Action).

Gracias a la herramienta de **Selenium IDE**, se han logrado realizar los tests funcionales que aseguran que cada elemento de la interfaz responda correctamente a las acciones del usuario.

![img_1.png](img_1.png)
---

### 6.1.2. Core Integration Tests

#### **Landing Page test**
Se realizó un test automatizado utilizando Selenium IDE para verificar el correcto funcionamiento de la landing page de Centralis. El objetivo del test fue asegurarse de que los elementos clave de la página, como el título principal, la navegación y los botones de acción ("Get Started", "Explore Features"), se cargaran correctamente y fueran interactivos, garantizando una experiencia de usuario óptima.

![img_2.png](img_2.png)

#### **Mobile test**
Se realizó un test automatizado utilizando Selenium WebDriver para verificar el correcto funcionamiento de la interfaz móvil de la aplicación. El objetivo del test fue asegurarse de que los elementos clave de la página, el login y los botones de navegación interna se cargaran correctamente y fueran interactivos en resoluciones de dispositivos móviles, validando el diseño responsivo.

![img_3.png](img_3.png)

#### **User CRUD (Consultants/Clients)**
Se realizó un test automatizado para verificar el funcionamiento del CRUD de los usuarios principales (Consultores y Clientes), asegurando que el proceso de crear, leer, actualizar y eliminar los registros se realice correctamente. El test abarcó la funcionalidad de un usuario que gestiona su perfil, edita su información de contacto y elimina entradas, todo esto con el objetivo de garantizar que la plataforma maneje los datos de manera eficiente y sin errores.

![img_4.png](img_4.png)

#### **Appointment / Agenda CRUD**
Se realizó un test automatizado para validar el correcto funcionamiento del sistema de gestión de agendas y citas de Centralis, asegurando que los usuarios puedan registrar, visualizar, actualizar y eliminar sus compromisos o reuniones sin inconvenientes. Este test garantizó que los integrantes del equipo puedan interactuar con el calendario de forma fluida.

![img_5.png](img_5.png)

---

### 6.1.3. Core Behavior-Driven Development

*(Sección pendiente de desarrollo según los escenarios Gherkin definidos)*

### 6.1.4. Core System Tests

*(Sección para validación final de extremo a extremo en el entorno de producción)*