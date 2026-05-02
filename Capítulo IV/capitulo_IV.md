# Capítulo IV: Product Design

## 4.1. Style Guidelines.
### 4.1.1. General Style Guidelines.

<p style="text-indent: 1.25cm;">La presente sección establece las bases visuales y conceptuales que rigen la identidad de Centralis, funcionando como un repositorio central de diseño para asegurar una experiencia de usuario coherente, profesional y enfocada. El objetivo principal de estas guías es consolidar los elementos fundamentales del sistema, tales como la marca, la paleta cromática y la tipografía, permitiendo que todos los miembros del equipo mantengan una presentación visual consistente en los diversos productos digitales de la plataforma.

<p style="text-indent: 1.25cm;">A través de la definición de estos estándares, se busca no solo fortalecer el reconocimiento de la marca, sino también garantizar la legibilidad y accesibilidad de las interfaces. De este modo, las decisiones de diseño aquí detalladas responden a un análisis de los principios de comunicación y lenguaje adoptados por la startup, asegurando que cada interacción dentro de la plataforma sea fluida y transmita los valores de eficiencia y seguridad del entorno corporativo.

**Paleta de Colores**

<p style="text-indent: 1.25cm;">La selección cromática se fundamenta en una escala monocromática de azules, que ha sido elegida para proyectar estabilidad, seguridad y tecnología. Según la paleta de colores implementada, se utiliza el tono Blue-500 (#5d737e) como color primario para elementos de acción y navegación, mientras que el Blue-900 (#273035) define los contrastes más profundos para fondos y textos de alta jerarquía. El uso de tonos claros, como el Blue-50, facilita la creación de interfaces limpias y espaciosas en los campos de entrada de datos. Cabe destacar que esta elección no es puramente estética; se ha validado que los contrastes entre los tonos oscuros y los fondos claros cumplen con los estándares de accesibilidad WCAG (AAA), permitiendo una lectura óptima para todos los usuarios.

<p align="center">
  <img src="https://i.imgur.com/8QCPwd5.png" alt="Description">
</p>

*Nota.* Elaboración propia.

**Tipografía y Fuente **

<p style="text-indent: 1.25cm;">Para la tipografía, se ha optado por una fuente principal de tipo "Inter" de estilo geométrico y moderno y una secundaria de tipo "SF Pro Display", lo que garantiza una legibilidad excepcional en dispositivos móviles y navegadores web. La jerarquía visual se establece mediante el uso de pesos: los encabezados y títulos de las aplicaciones utilizan un peso mayor ("Bold") para destacar la identidad de la sección, mientras que el cuerpo del texto emplea pesos ligeros para priorizar la claridad del contenido. Esta decisión tipográfica responde a la arquitectura de la información, donde la simplicidad de las etiquetas y el sistema de rotulado buscan evitar confusiones en los visitantes y usuarios finales de la plataforma.


<div style="display: flex; justify-content: center; align-items: center; gap: 16px; flex-wrap: wrap; width: 100%;">
  <img src="https://i.imgur.com/Nr6vJfk.png" alt="img1" style="width: 100%; max-width: 300px; height: auto;">
  <img src="https://i.imgur.com/yRYzj2S.png" alt="img2" style="width: 100%; max-width: 300px; height: auto;">
</div>

*Nota.* Elaboración propia.

**Identidad Logométrica**

<p style="text-indent: 1.25cm;">El logotipo de Centralis funciona como la pieza central del branding y representa el flujo constante de información dentro de una organización. El isotipo utiliza formas geométricas interconectadas y flechas direccionales integradas en un ciclo infinito, simbolizando la retroalimentación y la comunicación bidireccional entre los distintos niveles jerárquicos. Visualmente, el logo se presenta dentro de un contenedor redondeado con un degradado de azul profundo que refuerza la identidad tecnológica del producto. Esta simbología es coherente con el lenguaje ubicuo del proyecto, actuando como un identificador visual inmediato para la entidad de la compañía y sus procesos de negocio.


<p align="center">
  <img src="https://i.imgur.com/NQ3HtCj.png" alt="Description">
</p>

*Nota.* Elaboración propia.

### 4.1.2. Mobile Style Guidelines.

#### 4.1.2.1. iOS Mobile Style Guidelines. 

<p style="text-indent: 1.25cm;">En esta sección se describen las directrices de estilo aplicadas para dispositivos con sistema operativo iOS. Aunque la aplicación se desarrolla utilizando el framework "Flutter" para garantizar la consistencia visual, el diseño respeta principios clave de las "Human Interface Guidelines" de Apple para asegurar que los usuarios de iOS se sientan familiarizados con la navegación.

- **Adaptación de Componentes:** Se utilizan bordes redondeados pronunciados en botones y contenedores, alineados con la estética de iOS.
- **Iconografía:** Se emplean iconos de trazo fino y minimalista que mantienen la claridad incluso en densidades de pantalla Retina.
- **Tipografía:** La fuente Sans Serif se ajusta en escala para cumplir con los estándares de legibilidad de Apple, priorizando el espacio en blanco para evitar la saturación visual.

<p align="center">
  <img src="https://i.imgur.com/UwhDTMb.png" alt="Description">
</p>



#### 4.1.2.2. Android Mobile Style Guidelines

<p style="text-indent: 1.25cm;">Para la plataforma Android, las directrices de estilo se fundamentan en "Material Design", tal como lo requiere la documentación técnica del proyecto. Al ser una aplicación desarrollada en "Flutter", se aprovecha el catálogo de componentes de "Material" para ofrecer una interfaz táctil altamente eficiente.

- **Jerarquía de Colores:** Se aplica la paleta de azules de la startup, utilizando elevaciones y sombras sutiles para diferenciar las capas de la interfaz (anuncios, chats y perfiles).
- **Interacción Táctil:** Los elementos de acción cuentan con áreas de contacto amplias (mínimo 48dp) para cumplir con los estándares de accesibilidad y diseño inclusivo.
- **Navegación:** Se implementa una estructura de navegación clara, facilitando el acceso a las funciones de "Company" mediante gestos naturales del sistema operativo.


<p align="center">
  <img src="https://i.imgur.com/XiTZj3L.png" alt="Description">
</p>


## 4.2. Information Architecture.

### 4.2.1. Organization Systems.

<p style="text-indent: 1.25cm;">En esta sección se detallan las decisiones de diseño que dirigen la organización del contenido en la aplicación móvil de Centralis, orientadas a que los miembros de la Company encuentren la información necesaria sin esfuerzo. Se aplican esquemas que responden a la naturaleza corporativa del producto y a la jerarquía de roles establecida.


**1. Organización Jerárquica (Visual Hierarchy)**


<p style="text-indent: 1.25cm;">Se implementa para establecer una relación de importancia entre los elementos y guiar la atención hacia la información crítica de la organización.

- **Identidad Corporativa:** El logo y nombre de la **Company** se sitúan en el nivel jerárquico superior de la interfaz para reforzar el sentido de pertenencia.
- **Priorización de Contenido:** En los listados de anuncios, se utiliza un contraste tipográfico mayor (negrita y color Blue-900) para los títulos y etiquetas de prioridad (High, Urgent), relegando los metadatos de fecha y autor a un segundo plano visual.
- **Perfiles Profesionales:** La información se organiza priorizando el nombre del usuario y su cargo (*Position*), seguidos por detalles secundarios como el departamento.

**2. Organización Secuencial (Step-by-step)**

<p style="text-indent: 1.25cm;">Este sistema se aplica en flujos lógicos donde el usuario debe completar pasos específicos para cumplir un objetivo.

- **Registro de la Company:** El flujo guía al **Manager** desde la validación del RUC hasta la carga del logo y creación del perfil administrativo en pasos lineales y obligatorios.
- **Creación de Entidades:** La publicación de anuncios y eventos sigue un orden vertical descendente, facilitando el ingreso de datos en pantallas móviles.
- **Autenticación:** El proceso de registro e inicio de sesión se presenta como una secuencia de pasos necesarios para garantizar la seguridad de la cuenta.

**3. Organización por Esquemas de Categorización**

<p style="text-indent: 1.25cm;">Se aplican esquemas específicos para categorizar el contenido según el dominio del negocio:

- **Por Tópicos (Temática):** El contenido se divide en los dominios principales de la plataforma: Gestión (*Management*), Comunicaciones (*Announcements*), Colaboración (*Chats*) y Logística (*Events*).
- **Cronológica:** Los anuncios y mensajes de chat se organizan temporalmente, mostrando la información más reciente para asegurar la vigencia del mensaje.
- **Por Audiencia (Role-based):** La interfaz organiza las opciones de navegación según los permisos; los **Managers** visualizan herramientas de control y métricas, mientras que los **Employees** acceden a funciones de interacción y consumo.
- **Alfabética:** Se utiliza exclusivamente en el directorio de miembros de la **Company** y en la búsqueda de departamentos para agilizar la localización de contactos específicos.

<p style="text-indent: 1.25cm;">La integración de estos sistemas de organización permite que Centralis funcione como un entorno aislado y eficiente, manteniendo la coherencia estética y funcional en todas las vistas de la aplicación.


### 4.2.2. Labeling Systems.

<p style="text-indent: 1.25cm;">El sistema de etiquetado en Centralis tiene como objetivo principal representar los datos y asociaciones de información de manera que se evite la confusión para los visitantes y usuarios finales. Para lograr una navegación intuitiva, se han especificado etiquetas con el mínimo número de palabras posible para representar conjuntos de información y las acciones disponibles dentro de la plataforma.

**1. Principios de Etiquetado**

- **Precisión Organizacional:** Se utilizan términos que reflejan la estructura jerárquica de la empresa (ej. *Company*, *Department*, *Position*).
- **Accionabilidad:** Las etiquetas de control utilizan verbos en infinitivo que describen resultados directos, minimizando el error humano.
- **Consistencia de Dominio:** En cumplimiento con la arquitectura **DDD**, se mantiene una uniformidad terminológica entre los componentes del sistema (backend) y las etiquetas de la interfaz (frontend).

**2. Categorías de Etiquetas y Aplicación**

**A. Navegación y Estructura Global** Representan los contextos de nivel superior accesibles desde la barra de navegación principal:

- **Announcements:** Centraliza el flujo de noticias y comunicados oficiales.
- **Events:** Gestiona la agenda de actividades y reuniones corporativas.
- **Chats:** Engloba los canales de comunicación colaborativa.
- **Management / Company:** Etiqueta exclusiva para perfiles administrativos que agrupa herramientas de gestión de la organización y métricas.
- **Profile:** Contiene la identidad profesional y configuración del usuario.

**B. Gestión de la Entidad "Company"** Etiquetas específicas introducidas para el soporte de múltiples organizaciones:

- **Register Company:** Proceso de alta de una nueva entidad legal.
- **Company ID / RUC:** Identificadores únicos para la validación de la empresa.
- **Join Company:** Flujo de ingreso para empleados mediante invitación o código.
- **Active Status:** Indicador de vigencia operativa de la organización.

**C. Títulos de Acción y Contexto** Definen el propósito de la pantalla actual y el alcance de la tarea:

- **Create Announcement:** Indica la apertura del editor de noticias.
- **Event Logistics:** Señala la visualización de detalles de ubicación y horario.
- **Group Settings:** Permite la administración de visibilidad y miembros de un chat.
- **Organization Dashboard:** Identifica el panel de control con métricas de lectura y participación.

**D. Etiquetas de Formulario e Inputs** Guían la entrada de datos mediante descriptores técnicos concisos:

- **Priority Level (Normal, High, Urgent):** Clasificación del impacto de un mensaje.
- **Position / Role:** Define el nivel de permisos (Manager, Employee, Director).
- **Department Name:** Identifica el área funcional dentro de la empresa.
- **Visibility (Public/Private):** Define el alcance de acceso a grupos de chat.

**E. Botones de Acción y Estado** Utilizan un lenguaje directo basado en los casos de uso del sistema:

- **Publish / Discard:** Para la gestión del ciclo de vida de anuncios.
- **Confirm Attendance:** Para la validación de participación en eventos.
- **Mark as Read:** Etiqueta de confirmación de recepción para el empleado.
- **Register / Sign In:** Acciones de acceso y creación de cuenta.


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

​    

### 4.2.4. Searching Systems.

<p style="text-indent: 1.25cm;">El sistema de búsqueda de Centralis tiene como objetivo principal evitar que los usuarios se sientan perdidos ante el volumen de información generado dentro de su organización. Se han diseñado mecanismos de recuperación de datos específicos que permiten localizar activos de comunicación y perfiles profesionales de manera ágil, garantizando que los resultados siempre estén confinados al alcance de la Company del usuario.  
**1. Opciones y Escenarios de Búsqueda**

<p style="text-indent: 1.25cm;">El sistema implementa capacidades de búsqueda en tres contextos críticos identificados en el flujo operativo:

- **Directorio de Miembros:** Permite localizar colegas por nombre o cargo para facilitar el contacto directo y la visualización de perfiles profesionales.
- **Gestión de Audiencias:** Utilizado por los **Managers** durante la creación de **Events** o **Groups** para seleccionar destinatarios específicos de forma masiva o individual.
- **Repositorio de Comunicaciones:** Localización de **Announcements** históricos mediante palabras clave contenidas en el título o descripción.

*Search Bar Material Design 3*

<p align="center">
  <img src="https://i.imgur.com/E8nZ3f8.png" alt="Descripción">
</p>



**2. Filtros y Criterios de Recuperación**

<p style="text-indent: 1.25cm;">Para refinar los resultados y mejorar la precisión, el usuario cuenta con los siguientes filtros basados en los esquemas de organización del sistema:

- **Filtro por Departamento:** Permite segmentar las búsquedas para mostrar solo miembros pertenecientes a áreas específicas (ej. TI, Recursos Humanos).
- **Filtro por Prioridad:** En el caso de los anuncios, permite recuperar únicamente aquellos marcados como *High* o *Urgent*.
- **Filtro de Visibilidad:** Clasificación de grupos de chat en categorías de *Public* o *Private*.

*Filter Chips Material Design 3*

<p align="center">
  <img src="https://i.imgur.com/v0lBwfW.png" alt="Descripción">
</p>



**3. Visualización y Estados de los Datos**

<p style="text-indent: 1.25cm;">La interfaz de búsqueda ha sido diseñada siguiendo los principios de **Material Design** para asegurar una respuesta visual coherente:

- **Búsqueda en Tiempo Real:** Los resultados se actualizan dinámicamente mediante el patrón *Search-as-you-type*, reduciendo la latencia percibida por el usuario.
- **Visualización de Resultados:** Los datos se presentan en forma de *Lists* o *Cards*, mostrando el nombre, cargo y avatar para una identificación visual rápida.
- **Empty States (Estados Vacíos):** En caso de no encontrar coincidencias, el sistema muestra una ilustración amigable con la etiqueta "No results found", evitando la confusión del usuario frente a una pantalla en blanco.

*Search Results List Material Design 3*

<p align="center">
  <img src="https://i.imgur.com/6KQcKBU.png" alt="Descripción">
</p>



<p style="text-indent: 1.25cm;">La Landing Page de Centralis está diseñada como una página de presentación estática cuyo propósito principal es proporcionar información esencial sobre la aplicación y dirigir a los usuarios hacia las plataformas de descarga. Dada su naturaleza informativa y la limitada cantidad de contenido, no se implementa un sistema de búsqueda por las siguientes razones:

- **Volumen de contenido reducido:** La Landing Page contiene únicamente secciones clave (valor proposition, características, testimonios, llamados a la acción) que pueden recorrerse completamente mediante scroll tradicional.
- **Propósito orientado a la conversión:** El objetivo principal es guiar al usuario hacia la descarga de la aplicación, no proporcionar acceso a bases de datos extensas o contenido complejo que requiera mecanismos de búsqueda.
- **Experiencia lineal planificada:** El contenido está estructurado para ser consumido de manera secuencial, presentando la información en un orden lógico que maximiza la comprensión y el engagement.

<p style="text-indent: 1.25cm;">Este sistema de búsqueda está optimizado para los casos de uso más frecuentes en Centralis, permitiendo a los gerentes completar sus tareas de selección de personal de manera rápida y sin distracciones, mientras mantiene una interfaz limpia y comprensible. 

### 4.2.5. Navigation Systems.

**1. Navegación Principal **

Constituye el eje de movimiento entre los contextos delimitados de la aplicación mediante una **Navigation Bar** persistente (Material Design 3):

- **Estructura de Secciones:** Acceso directo a *Announcements*, *Events*, *Chats* y *Profile*.
- **Navegación por Roles:** Para usuarios con rol de **Manager**, se habilita dinámicamente el acceso al *Management Dashboard* para la gestión de la organización.
- **Indicadores de Estado:** Uso de estados activos (*Active states*) con contenedores de color para indicar la sección actual, reduciendo la carga cognitiva.



*Navigation bar Material Design 3*

<p align="center">
  <img src="https://i.imgur.com/ckYxcdu.png" alt="Descripción">
</p>





**2. Navegación Jerárquica y de Profundidad**

Permite el tránsito desde vistas de resumen hacia el detalle técnico de cada entidad:

- **Flujo Drill-down:** Los usuarios acceden a los detalles de un anuncio o evento mediante gestos de toque en las *Cards* de la lista principal.
- **Navegación de Retorno:** Implementación de una *Back Button* estandarizada en la **Top App Bar** y soporte para gestos nativos de retroceso en iOS y Android (vía Flutter *PopScope*).
- **Migas de Pan (Breadcrumbs) Lógicas:** El sistema preserva el estado de filtrado y scroll al retornar a una vista de lista anterior.



*Top App Bar Material Design 3*

<p align="center">
  <img src="https://i.imgur.com/fYUIpnU.png" alt="Descripción">
</p>



**3. Navegación Contextual y Acciones Flotantes**

Optimiza la ejecución de tareas críticas según la vista activa:

- **Floating Action Button (FAB):** Ubicado estratégicamente en la esquina inferior derecha para acciones de creación (ej. publicar anuncio o crear grupo de chat) en pantallas de gestión.
- **Top App Bar Actions:** Iconos contextuales para filtrado por departamentos, búsqueda avanzada y acceso a notificaciones push pendientes.



*Floating Action Button Material Design 3*

<p align="center">
  <img src="https://i.imgur.com/NJr1P5S.png" alt="Descripción">
</p>





**4. Navegación Secuencial (Task-flow Navigation)**

Diseñada para procesos transaccionales que requieren una progresión lógica:

- **Onboarding y Multi-tenancy:** Flujo guiado para el registro de una nueva **Company**, validación de datos legales y configuración inicial.
- **Steppers de Creación:** Los formularios complejos se dividen en pasos lógicos (ej. Datos generales -> Selección de destinatarios -> Confirmación).

**5. Sistema de Navegación para Landing Page**

La página de aterrizaje utiliza un sistema simplificado orientado a la conversión y exposición del producto:

- **Scroll Unidireccional:** Navegación vertical continua que guía al visitante a través de la propuesta de valor, características y planes de precios.
- **Sticky Navigation Bar:** Un menú superior persistente que permite el salto rápido entre secciones (Features, Pricing, About Us) y botones de *Call to Action* (CTA) para el registro de empresas.
- **Navegación Adaptativa:** Menú lateral (*Drawer*) para resoluciones móviles, garantizando la accesibilidad en cualquier dispositivo.



## 4.3. Landing Page UI Design.
### 4.3.1. Landing Page Wireframe.

<p style="text-indent: 1.25cm;">En esta sección se presenta el diseño estructural de la página de aterrizaje de Centralis, la cual sirve como el portal principal para comunicar la propuesta de valor del ecosistema a las organizaciones. El wireframe ha sido diseñado bajo una estética minimalista y profesional, enfocándose en la claridad de las funciones core de la plataforma: la centralización de anuncios oficiales, la gestión de eventos corporativos y la integración de chats internos en tiempo real.

<p style="text-indent: 1.25cm;">A través de esta interfaz, se busca demostrar cómo Centralis facilita la cohesión empresarial y elimina la fragmentación de la información, permitiendo que cada miembro del equipo se mantenga alineado con la visión y las actividades de la empresa mediante una navegación intuitiva y directa.

**Sección 1: Hero Page**

Esta imagen representa la cabecera principal de la landing page de **Centralis**, diseñada para establecer la identidad de la marca desde el primer contacto.

- **Propósito de la sección**: Presentar a la plataforma como el eje central que garantiza la alineación corporativa mediante anuncios oficiales y comunicación en tiempo real.

- **Jerarquía Visual**:

  - **Encabezado principal**: El mensaje "Where your team stays aligned" destaca el valor central de la herramienta: la unidad y la visión compartida dentro de la empresa.
  - **Llamados a la acción (CTA)**: Los botones "Get Started" y "Explore Features" guían al usuario hacia una interacción inmediata con el ecosistema de la plataforma.

- **Experiencia del Usuario (UX)**: El diseño minimalista reduce la carga cognitiva, permitiendo que el colaborador se enfoque en el mensaje principal: mantenerse conectado con la organización.

  

  ![](https://i.imgur.com/bBJoe5L.png)

**Sección 2: Funcionalidades Core**

En esta sección del wireframe se detallan los pilares funcionales de la aplicación móvil, la cual está desarrollada con **Flutter** y **Firebase**.

- **Propósito de la sección**: Desglosar los tres servicios principales: publicación de anuncios, organización de eventos y chats internos.
- **Jerarquía Visual**: Se utiliza un diseño de tarjetas (cards) modulares para otorgar el mismo peso visual a cada característica, facilitando la comprensión de la versatilidad de la plataforma.
- **Componentes del Wireframe**:
  - **Official Announcements**: Un espacio dedicado para noticias críticas, eliminando la pérdida de información importante.
  - **Event Management**: Herramientas para organizar actividades, charlas y convenciones con recordatorios automáticos.
  - **Secure Internal Chat**: Un entorno de mensajería nativo que se integra directamente con la agenda corporativa.



![](https://i.imgur.com/YoNQUGa.png)

**Sección 3: Metodología de Uso**

Esta sección explica el flujo de trabajo simplificado que propone **Centralis** para las empresas.

- **Propósito de la sección**: Demostrar la facilidad con la que una organización puede transicionar de una comunicación fragmentada a un flujo de trabajo unificado.
- **Jerarquía Visual**: Un proceso numerado paso a paso simplifica el concepto de adopción de la herramienta para posibles clientes corporativos.
- **Integración del flujo**:
  - **Paso 1**: Centralización de la información mediante la creación de canales globales o por departamentos.
  - **Paso 2**: Programación y organización de eventos internos con notificaciones directas al dispositivo móvil del usuario.
  - **Paso 3**: Fomento de la participación mediante chats colaborativos y seguimiento de eventos en tiempo real.



![](https://i.imgur.com/djzQZFa.png)

**Sección 4: Llamado a la Acción Final**

Representa el cierre estratégico del wireframe para fomentar la conversión y adopción del software.

- **Propósito de la sección**: Convertir el interés del visitante en una acción concreta, invitando a las organizaciones a unirse a la comunidad de **Centralis**.
- **Jerarquía Visual**: El uso de tipografía de alto contraste enfoca la atención en la pregunta final: "¿Ready to unite your workforce?".
- **Estrategia de Conversión**: Ofrece puntos de entrada de baja fricción, como una prueba gratuita o la solicitud de una demostración personalizada para equipos corporativos de mayor tamaño.

![](https://i.imgur.com/200t5GL.png)



### 4.3.2. Landing Page Mock-up.

<p style="text-indent: 1.25cm;">A continuación, se detallan las secciones finales del diseño, donde la estética inspirada en la simplicidad de herramientas de colaboración líderes se combina con la robustez funcional de la plataforma.

**Sección Hero**

En esta versión final, la cabecera utiliza un diseño limpio con un fuerte enfoque en la fotografía de producto.

- **Identidad Visual**: Se observa la implementación de botones con estados visuales claros ("Get Started" con relleno sólido y "Explore Features" con delineado), mejorando la intuitividad del sitio.
- **Imagen de Producto**: El contenedor de la derecha muestra ahora una interfaz móvil real de la aplicación, destacando la simplicidad del diseño inspirado en la estética moderna de herramientas de colaboración líderes.

![](https://i.imgur.com/el9xq7W.png)

**Propuesta de Valor**

Esta sección traduce los conceptos técnicos en beneficios tangibles para la empresa mediante una cuadrícula de características refinada.

- **Iconografía**: Se utilizan iconos vectoriales estilizados para representar los tres pilares: **Official Announcements** (anuncios oficiales), **Event Management** (gestión de eventos) y **Secure Internal Chat** (chat interno seguro).
- **Claridad Textual**: El uso de una tipografía *sans-serif* de alta legibilidad asegura que el usuario comprenda rápidamente que la plataforma elimina el "ruido" comunicativo para enfocarse en la cohesión corporativa.

![](https://i.imgur.com/asQdTeb.png)

**Flujo de Trabajo**

El mockup utiliza una imagen de estilo *lifestyle* empresarial para humanizar la tecnología y mostrar el impacto de la herramienta en el día a día de un equipo.

- **Proceso de Conexión**: La sección detalla visualmente los tres pasos clave: **Centralize Information** (centralizar la información), **Organize and Schedule** (organizar y programar) y **Engage and Collaborate** (interactuar y colaborar).
- **Equilibrio Visual**: La composición equilibra la imagen aspiracional a la izquierda con una lista de pasos limpia a la derecha, facilitando una lectura rápida de arriba hacia abajo.

![](https://i.imgur.com/f2K1zbt.png)

**Cierre y Pie de Página**

La sección final está diseñada para maximizar la tasa de conversión mediante un bloque de color sólido que contrasta con el resto del sitio.

- **Call to Action (CTA)**: El mensaje principal "¿Ready to unite your workforce?" actúa como un cierre persuasivo, acompañado de opciones claras para iniciar una prueba gratuita o agendar una demostración.
- **Footer Profesional**: Se incluye un pie de página con enlaces legales y redes sociales, junto con el *copyright* de 2026, lo que refuerza la seriedad y el soporte institucional de la plataforma **Centralis**.

![](https://i.imgur.com/ChdVg86.png)

## 4.4. Mobile Applications UX/UI Design.
### 4.4.1. Mobile Applications Wireframes.

Pantalla de Login: Interfaz de acceso con campos para correo y contraseña, incluyendo opciones para recuperación de cuenta y acceso directo al registro de nuevos usuarios.
 
<img width="550" height="1147" alt="image" src="https://github.com/user-attachments/assets/85a7a325-8c4e-4fce-841b-77f74e764fc1" />

Pantalla de Registro: Formulario de creación de cuenta que solicita nombre, correo y contraseña, con una casilla de verificación para la aceptación de términos y políticas legales.

 
<img width="548" height="1130" alt="image" src="https://github.com/user-attachments/assets/a2f5ae9a-536b-44e2-adbd-b3f15be4b457" />


Pantalla de Verificación: Paso de seguridad que requiere un código OTP de 5 dígitos enviado al correo electrónico para validar la identidad del usuario antes de ingresar.
 

<img width="523" height="1136" alt="image" src="https://github.com/user-attachments/assets/941f1361-08d0-49ea-81c1-f4871e326fb8" />


Pantalla de Home: Panel principal que centraliza el acceso a chats recientes, un carrusel de anuncios destacados de la empresa y una lista de eventos programados.
 

<img width="527" height="1152" alt="image" src="https://github.com/user-attachments/assets/30c0aa64-f5a8-4066-995f-4c3fc266cde3" />


Pantalla de Company Feed (General): Muro informativo con buscador y filtros para alternar entre anuncios y eventos, destacando las noticias más importantes de la organización.
 
<img width="364" height="1334" alt="image" src="https://github.com/user-attachments/assets/300093cd-52a5-4e93-9cdc-07175fc8af29" />


Sección de Actividad Reciente: Historial cronológico de publicaciones categorizadas por etiquetas (como General o Tech Stack), que permite seguir el flujo diario de actualizaciones del equipo.
 

<img width="416" height="905" alt="image" src="https://github.com/user-attachments/assets/b20e186c-8190-46e6-9074-3f6f1691ff64" />



Vista detallada del usuario que muestra su avatar, cargo e información de contacto corporativa (correo, teléfono y ubicación). Además, incluye una sección de biografía, métricas destacadas (como proyectos e integrantes gestionados) y un registro de sus actividades o logros recientes.


<img width="417" height="1338" alt="image" src="https://github.com/user-attachments/assets/8fb16bdb-f690-46fb-89b2-d46e2f0afa15" />


Esta vista especializada organiza la agenda corporativa mediante un selector de fechas semanal interactivo y una lista de tarjetas con los eventos próximos. Cada tarjeta detalla información clave como la lista de asistentes y la ubicación (ya sea presencial o mediante enlaces a Google Meet), concluyendo con un bloque integrado que permite a los usuarios proponer y crear nuevas actividades.
 
<img width="513" height="1342" alt="image" src="https://github.com/user-attachments/assets/a3c194d2-bf92-4376-8791-ecad8c834878" />


### 4.4.2. Mobile Applications Wireflow Diagrams.

### 

<p style="text-indent: 1.25cm;">En esta sección se detallan los diagramas de flujo de usuario para la aplicación móvil desarrollada en Flutter, los cuales representan de manera lógica y secuencial las rutas que los colaboradores de las organizaciones siguen para completar sus objetivos dentro de la plataforma. Estos diagramas integran los mockups de alta fidelidad con las decisiones de navegación, permitiendo visualizar tanto el camino esperado como las rutas alternativas en las interacciones críticas del sistema.  




<p style="text-indent: 1.25cm;">La elaboración de estos flujos asegura que la experiencia del usuario sea intuitiva y coherente con el modelo de Multi-tenancy de Fudi, garantizando que procesos como la visualización de anuncios, la gestión de eventos y la comunicación por chat se realicen de forma eficiente y sin fricciones dentro de la infraestructura móvil.


Flow 1: Usuario no cuenta con cuenta, se mueve al sign up y es redireccionado a la pagina donde llena sus datos. Siguiente se le pide la confirmación de código para el correo. 

<p align="center">
  <img src="https://i.imgur.com/KMZmodt.png" alt="Descripción">
</p>




Flow 2: Entra en el feed donde el feed se parte entre eventos y anuncios el usuario es capaz de navegar entre ambas libremente. 

<p align="center">
  <img src="https://i.imgur.com/Ulm1TKE.png" alt="Descripción">
</p>





Flow 3: El usuario explora las siguientes opciones  de navegación. Donde puede visualizar sus chats, asimismo, su propio perfil. 

<p align="center">
  <img src="https://i.imgur.com/gJ6zU0e.png" alt="Descripción">
</p>



### 4.4.3. Mobile Applications Mock-ups.

Pantalla de Log in: Interfaz de inicio de sesión refinada que presenta el imagotipo azul de la marca, campos de texto con fondo gris claro y un botón de "Sign in" en un tono verde azulado oscuro (teal) que destaca la acción principal.

<img width="374" height="801" alt="image" src="https://github.com/user-attachments/assets/f786e796-56fb-4b84-b0b5-186db412a6f5" />

Pantalla de Register: Formulario de registro estilizado que mantiene la coherencia visual con campos minimalistas para los datos del usuario y un botón de "Sign up", integrando sutilmente la casilla de términos y condiciones.

<img width="368" height="801" alt="image" src="https://github.com/user-attachments/assets/e9a367c6-9c61-41fc-b609-21d6c314a0a9" />

Pantalla de Verification: Diseño limpio y centrado en la conversión para ingresar el código OTP, utilizando cinco cajas de texto individuales y destacando el botón de "Verify" con el color primario de la aplicación.

<img width="370" height="796" alt="image" src="https://github.com/user-attachments/assets/94a5daef-62d5-476c-85f1-52414499d368" />

Pantalla de Home: Panel principal vibrante que ahora muestra fotografías reales en los avatares de los chats y tarjetas con imágenes de fondo para los anuncios de la empresa, manteniendo la sección de eventos estructurada y clara.

<img width="377" height="808" alt="image" src="https://github.com/user-attachments/assets/7a17f117-0ef0-4f22-af18-d715f97f33e1" />

Pantalla de Company Feed (Announcements):
Muro informativo de alta fidelidad que destaca la noticia principal con una imagen atractiva y resalta los comunicados de Recursos Humanos con una llamada a la acción ("Read Policy") en contraste oscuro. Presenta un flujo de actividad reciente organizado con iconos, etiquetas de categoría y textos reales, finalizando con un botón flotante prominente para crear nuevas publicaciones.

<img width="232" height="841" alt="image" src="https://github.com/user-attachments/assets/ed87cbce-a8ab-4714-b4b3-8f44d332556d" />

Pantalla de Chats (Communications): Interfaz de mensajería refinada que ahora muestra conversaciones con fotografías reales de los usuarios y vistas previas del texto. Facilita la navegación con filtros visuales oscuros para el estado activo y destaca los mensajes no leídos con contadores numéricos.

<img width="358" height="751" alt="image" src="https://github.com/user-attachments/assets/24d06d5c-9d76-4733-8878-18ef6aa4cf5b" />

Pantalla de Perfil (Profile): Vista personal detallada que integra la foto de perfil, un texto biográfico real ("About") y los datos de contacto del empleado. Muestra de forma elegante las métricas de desempeño y un historial concreto de tareas completadas o reconocimientos recientes.

<img width="259" height="815" alt="image" src="https://github.com/user-attachments/assets/901ec38c-1d48-4fd7-90bf-a7184f66f94a" />

Pantalla de Eventos (Company Feed - Events): Agenda corporativa visualmente pulida que organiza las reuniones en tarjetas detalladas con etiquetas de prioridad (como "Mandatory" o "Internal"). Incluye miniaturas fotográficas de los asistentes y define claramente si la cita es presencial (sala de conferencias) o virtual (Google Meet).

<img width="331" height="840" alt="image" src="https://github.com/user-attachments/assets/cedb416d-4f76-42cd-83f4-c08421a3abb5" />

### 4.4.4. Mobile Applications User Flow Diagrams.

<p style="text-indent: 1.25cm;">En esta sección se detallan los diagramas de flujo de usuario para la aplicación móvil desarrollada en Flutter, los cuales representan de manera lógica y secuencial las rutas que los colaboradores de las organizaciones siguen para completar sus objetivos dentro de la plataforma. Estos diagramas integran los mockups de alta fidelidad con las decisiones de navegación, permitiendo visualizar tanto el camino esperado como las rutas alternativas en las interacciones críticas del sistema.  



<p style="text-indent: 1.25cm;">La elaboración de estos flujos asegura que la experiencia del usuario sea intuitiva y coherente con el modelo de Multi-tenancy de Fudi, garantizando que procesos como la visualización de anuncios, la gestión de eventos y la comunicación por chat se realicen de forma eficiente y sin fricciones dentro de la infraestructura móvil.

Flow 1: Usuario no cuenta con cuenta, se mueve al sign up y es redireccionado a la pagina donde llena sus datos. Siguiente se le pide la confirmación de código para el correo. 

<p align="center">
  <img src="https://i.imgur.com/nxLyuCd.png" alt="Descripción">
</p>



Flow 2: Entra en el feed donde el feed se parte entre eventos y anuncios el usuario es capaz de navegar entre ambas libremente. 


<p align="center">
  <img src="https://i.imgur.com/RrkwWe0.png" alt="Descripción">
</p>




Flow 3: El usuario explora las siguientes opciones  de navegación. Donde puede visualizar sus chats, asimismo, su propio perfil. 

<p align="center">
  <img src="https://i.imgur.com/AMyTlBP.png" alt="Descripción">
</p>



## 4.5. Mobile Applications Prototyping.

<p style="text-indent: 1.25cm;">En esta sección se detalla el planteamiento de la propuesta de arquitectura y diseño de software, utilizando como base el conjunto de User Stories identificados y el Impact Map desarrollado previamente. El enfoque adoptado se fundamenta en la arquitectura dirigida por el dominio (Domain-Driven Design), permitiendo estructurar la solución de manera que responda directamente a las necesidades del negocio digital. A través de esta perspectiva, se busca garantizar que la plataforma sea escalable, mantenible y que exista una coherencia total entre el modelo de negocio y la implementación técnica.

URL de los diagramas: https://shorturl.at/mBpWF

### 4.6.1. Software Architecture Context Diagram.

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



### 4.6.2. Software Architecture Container Diagrams.

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

### 4.6.3. Software Architecture Components Diagrams.

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

## 4.7. Software Object-Oriented Design.
### 4.7.1. Class Diagrams.

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

### 4.7.2. Class Dictionary.

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

## 4.8. Database Design.
### 4.8.1. Relational/Non-Relational Database Diagram.

<p style="text-indent: 1.25cm;">La persistencia de datos en Centralis se ha diseñado mediante un modelo relacional que refleja fielmente los contextos delimitados identificados en la arquitectura de software. Este diseño garantiza la integridad referencial y el aislamiento de la información entre las distintas organizaciones que utilizan la plataforma. El esquema utiliza un enfoque de multi-tenancy basado en identificadores de compañía (`company_id`), permitiendo que una única instancia de base de datos soporte a múltiples empresas de forma segura y eficiente.

**Explicación del Diagrama de Base de Datos**

<p style="text-indent: 1.25cm;">El modelo de datos se organiza en esquemas que corresponden a los Bounded Contexts del dominio, asegurando una separación clara de responsabilidades:

- **Esquema Company:** Es el núcleo del sistema. Contiene la tabla `companies`, donde se registran los datos legales (RUC) y de marca de cada organización. Es la entidad raíz de la que dependen todos los demás datos del sistema.
- **Esquema Profile:** Gestiona la identidad de los usuarios dentro de una compañía específica. Incluye tablas para perfiles, departamentos y posiciones jerárquicas, permitiendo definir roles como **Manager** o **Employee**.
- **Esquema Announcement:** Maneja la comunicación oficial. La tabla principal de anuncios se vincula tanto al creador (Manager) como a la compañía, permitiendo además la persistencia de comentarios y niveles de prioridad para las notificaciones.
- **Esquema Chat:** Diseñado para la colaboración en tiempo real. Almacena grupos, mensajes de texto y referencias a recursos multimedia (imágenes). Este esquema está optimizado para consultas rápidas de historial de mensajes.
- **Esquema Event:** Administra la logística de actividades. Utiliza una tabla intermedia (`event_recipients`) para gestionar la relación de muchos a muchos entre los eventos programados y los usuarios invitados.

<p style="text-indent: 1.25cm;">Este diseño relacional permite que Centralis mantenga una alta consistencia en los datos, facilitando la generación de métricas en los dashboards administrativos y asegurando que cada usuario acceda exclusivamente a la información perteneciente a su organización.



![](../Anexos/Database_Design_Diagram/diamagra_db.svg)
