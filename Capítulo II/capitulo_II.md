# **Capítulo II: Requirements Elicitation & Analysis**

## **2.1. Competidores**

### ***2.1.1. Análisis competitivo***

<body>

| **Competitive Analysis Landscape**    |                                                              |                                                              |                                                              |                                                              |
| ------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| ¿Por qué llevar a cabo este análisis? | Identificar fortalezas, debilidades, oportunidades y amenazas de los principales competidores (Teams, Slack y WhatsApp), para diferenciar a Centralis como solución enfocada en PYMEs LATAM. |                                                              |                                                              |                                                              |
|                                       | Centralis<br />![img](https://i.imgur.com/AubQLcE.png)       | ![img](https://i.imgur.com/j8Gc3H2.png)                      | ![img](https://i.imgur.com/ybK6SRw.png)                      | ![img](https://i.imgur.com/tgMfF10.png)                      |
| Perfil                                | Plataforma integral para PYMEs, diseñada para centralizar la comunicación laboral. | Plataforma de colaboración de Microsoft, integrada en Microsoft 365. | Herramienta de mensajería y colaboración empresarial.        | Aplicación de mensajería instantánea de Meta, orientada a uso personal. |
| Ventaja competitiva                   | Simplicidad, bajo costo, funciones en anuncios, eventos y chat laboral. | Integración completa con Office 365, alta seguridad.         | Amplia integración con apps de terceros (Trello, Google Drive, Jira, etc.). | Facilidad de uso y adopción masiva global.                   |
| Perfil de Marketing                   | Pequeñas y medianas empresas en LATAM.                       | Empresas medianas y grandes.                                 | Empresas tecnológicas, startups, equipos distribuidos.       | Usuarios generales, comunicación personal y grupos informales. |
| Estrategias de marketing              | Marketing digital enfocado en PYMEs, alianzas con gremios y cámaras empresariales. | Incluido en licencias de Microsoft 365, ventas corporativas. | Modelo freemium, marketing digital, comunidad de desarrolladores. | Posicionamiento masivo y gratuito, expansión viral.          |
| Perfil de Producto                    | Anuncios formales, gestión de eventos, chats laborales segmentados. | Videollamadas, chat, colaboración documental, calendario.    | Canales temáticos, bots, integraciones externas, chat grupal. | Mensajería, llamadas, grupos, archivos multimedia.           |
| Precios & Costos                      | Suscripción accesible y escalable.                           | Desde $4 USD/usuario/mes (básico).                           | Desde $7.25 USD/usuario/mes (estándar).                      | Gratuito (limitado en funciones empresariales).              |
| Canales de distribución               | Mobile-first (Android/iOS) + versión web complementaria.     | Web, Desktop, Móvil (Android/iOS).                           | Web, Desktop, Móvil (Android/iOS).                           | Web, Desktop, Móvil (Android/iOS).                           |
| Análisis SWOT                         | Asequibilidad, enfoque LATAM, simplicidad laboral.           | Integración con Microsoft 365, seguridad.                    | Flexibilidad, ecosistema de apps.                            | Simplicidad, adopción masiva.                                |
| Debilidades                           | Startup nueva, menor reconocimiento de marca.                | Complejo para PYMEs, curva de aprendizaje alta.              | Costoso para equipos pequeños, saturación de apps.           | Baja seguridad, falta de funciones laborales.                |
| Oportunidades                         | Brecha en PYMEs que necesitan centralización simple y económica. | Creciente adopción de entornos híbridos.                     | Expansión en empresas medianas.                              | Uso laboral en mercados emergentes.                          |
| Amenazas                              | Copia rápida del modelo por grandes competidores.            | Competencia de Slack y Google Workspace.                     | Competencia de Teams y Zoom.                                 | Regulaciones de privacidad y nuevas apps laborales.          |

#

### ***2.1.2. Estrategias y tácticas frente a competidores***

<ul>
  <li><b>Diferenciación Tecnológica:</b> Arquitectura DDD y hexagonal, bounded contexts claros, uso de Render postgresql y Firebase para escalabilidad y costos bajos.</li>
  <li><b>Experiencia de Usuario:</b> Diseño mobile-first, minimalista y simple frente a la complejidad de Teams y Slack. Diferenciación clara de vida laboral y personal frente a WhatsApp.</li>
  <li><b>Seguridad y Privacidad:</b> Roles y permisos integrados, cumplimiento con GDPR, encriptación en tránsito y reposo, auditorías.</li>
  <li><b>Escalabilidad y Despliegue:</b> Arquitectura en microservicios, despliegue modular, infraestructura serverless y monitoreo con Prometheus/Sentry.</li>
  <li><b>Go-to-Market:</b> Posicionamiento como alternativa formal y económica para PYMEs en LATAM, con plan freemium inicial y escalabilidad progresiva.</li>
</ul>
</body>

#

## **2.2. Entrevistas**

<p style="text-indent: 1.25cm;">Con el objetivo de obtener información detallada acerca de las necesidades, expectativas y frustraciones de los usuarios objetivo de Centralis, se realizaron entrevistas estructuradas dirigidas a los dos segmentos estratégicos:  empleados y gerentes o líderes de equipos.

<p style="text-indent: 1.25cm;">El diseño de las entrevistas se elaboró considerando formularios específicos para cada segmento, formulando preguntas abiertas que permitieran a los participantes expresar libremente sus experiencias, desafíos y expectativas en torno a la comunicación interna.

<p style="text-indent: 1.25cm;">Cada entrevista fue registrada y documentada mediante notas detalladas, siguiendo las prácticas de obtención de requisitos y ética en investigación de usuarios. Posteriormente, los resultados se analizaron cualitativa y cuantitativamente, identificando patrones de comportamiento, puntos de dolor y oportunidades de mejora. Estos insights se consolidaron para la construcción de artefactos clave como User Personas, Empathy Maps y User Task Matrices, asegurando una base sólida para la definición de requisitos y el diseño de una plataforma centrada en las necesidades reales de sus usuarios.

<p style="text-indent: 1.25cm;">La metodología aplicada garantizó la recolección de información contextualizada y accionable, fundamental para el desarrollo de Centralis como una solución intuitiva, segura y efectiva para la comunicación interna empresarial.

### ***2.2.1. Diseño de entrevistas***

***-Segmento objetivo \#1: Empleados de Empresas***

* **Objetivo:** Comprender sus frustraciones cotidianas con las herramientas actuales, sus hábitos de comunicación y lo que valorarían en una solución como Centralis.

***Características demográficas:***

* ¿Cuál es tu nombre?
* ¿Cuantos años tienes?
* ¿En qué lugar trabajas o estás actualmente asignado(a)?

***Preguntas principales:***

1. ¿Qué aplicaciones o herramientas utilizas a diario para comunicarte con tus compañeros de trabajo y superiores?

2. ¿Has tenido problemas o inconvenientes usando estas herramientas? 

3. Cuando tu jefe o la empresa publican un anuncio o avisos importante, ¿cómo te enteras?

4. ¿Cómo te organizas para saber sobre reuniones, capacitaciones o eventos de la empresa?

5. ¿Cómo te sientes acerca de usar tu WhatsApp personal para temas de trabajo? 

6. Imagina una herramienta de comunicación ideal para tu trabajo. ¿Qué características debería tener para hacerte la vida más fácil? 

***Preguntas Complementarias:***

7. ¿Podrías contarme sobre la última vez que un malentendido o un fallo de comunicación te causó un problema o retraso en tu trabajo?

8. ¿Prefieres que las conversaciones de diferentes proyectos o temas estén separadas? ¿Por qué?

9. ¿Qué tipo de notificaciones te parecen útiles y cuáles te resultan molestas o intrusivas?

10. ¿Qué dispositivo usas más para comunicarte en el trabajo: el celular o la computadora?

#

***-Segmento objetivo \#2:  Gerentes y Líderes de Equipos*** 

* **Objetivo:** Descubrir sus desafíos de gestión, necesidades de control y accountability, y los criterios de decisión para implementar nuevas herramientas.

***Características demográficas: ***

* ¿Cuál es tu nombre?
* ¿Cuantos años tienes?
* ¿En qué lugar trabajas o estás actualmente asignado(a)?

***Preguntas principales:***

1. ¿Cómo se comunica oficialmente con su equipo hoy en día? ¿Qué herramientas utiliza? 

2. ¿Cuáles son los mayores desafíos o dolores de cabeza que enfrenta al gestionar la comunicación dentro de su equipo o empresa? 

3. ¿Ha tenido situaciones donde la información importante no llegó a todos? ¿Cuál fue el impacto?

4. ¿Cómo realiza el seguimiento para asegurarse de que su equipo ha visto y entendido las instrucciones o anuncios?

5. Al organizar una reunión o evento, ¿Qué herramientas usa?

6. Desde su perspectiva, ¿qué riesgos ve en el uso de aplicaciones informales como WhatsApp para la comunicación laboral?

7. ¿Qué criterios evalúa al considerar implementar una nueva herramienta tecnológica en la empresa? 

***Preguntas Complementarias:***

8. Cuando publica un anuncio importante, ¿necesita saber quiénes lo han leído y quiénes no? ¿Cómo le ayudaría esa información?

9. Imagina un panel de control donde pudiera ver el engagement de su equipo con la comunicación. ¿Qué métricas o datos serían más valiosos para usted?

10. Para la toma de decisiones, ¿le resultaría útil poder segmentar y enviar anuncios o eventos solo a departamentos o equipos específicos?

11. Desde el punto de vista de la seguridad, ¿qué tipo de controles o permisos considera indispensables en una herramienta de comunicación?

#

### 2.2.2. Registro de entrevistas 

***Segmento objetivo #1: Empleados de Empresas***

**Entrevista #1:**

**Figura 2**

*Imagen del usuario número 1 entrevistado*

<p align="center">
  <img src="https://res.cloudinary.com/df8xwy4xb/image/upload/v1758043275/Entrevista_elverth_empleado_gfkmen.png" alt="Class Diagram">
</p>

*Nota.* Elaboración propia. Link: https://goo.su/QQt8lAi

* **Nombre:** Leonardo Delgado Arriola
* **Edad:** 21 años
* **Minuto de inicio:** 0:55
* **Resumen:** Leonardo utiliza principalmente WhatsApp y correo electrónico para comunicarse en el trabajo. Señala que los mensajes laborales en WhatsApp suelen perderse entre los personales y que esto le ha causado retrasos. Se organiza con el calendario de su celular, aunque reconoce que no siempre es eficiente. Le resulta incómodo usar su WhatsApp personal para temas laborales porque no logra desconectarse. Prefiere separar conversaciones por proyectos y recibir solo notificaciones relevantes. Usa más el celular que la computadora para comunicarse.

* **Necesidades:**

  - Una herramienta exclusiva para el trabajo, separada de WhatsApp personal.

  - Organización por proyectos o equipos para no mezclar información.

  - Calendario integrado con recordatorios automáticos.

  - Notificaciones filtradas y priorizadas, solo lo realmente importante.

  - Evitar la mezcla entre lo laboral y lo personal para reducir distracciones.



**Entrevista #2:**

**Figura 3**

*Imagen del usuario número 2 entrevistado*

<p align="center">
  <img src="https://res.cloudinary.com/df8xwy4xb/image/upload/v1758039708/Etrevista_abigail_foto_vfnikz.jpg" alt="Class Diagram">
</p>

*Nota.* Elaboración propia. Link: https://goo.su/qwPRY

* **Nombre:** Abigail Goñe Arracata
* **Edad:** 22 años
* **Minuto de inicio:** 1:03
* **Resumen:** Abigail utiliza principalmente WhatsApp para la comunicación rápida con su equipo, y Gmail/Outlook para correos oficiales. Para reuniones puntuales usa Google Meet o Teams, mientras que se organiza con Google Calendar para recordatorios. Sin embargo, comenta que en WhatsApp las instrucciones suelen perderse entre mensajes personales, y que los correos importantes quedan enterrados si no los marca. También le incomoda usar su WhatsApp personal para temas laborales, porque invade su espacio privado y le genera estrés al no poder desconectarse.
Cuando recibe anuncios importantes, a veces llegan por correo y otras veces por WhatsApp, lo que le obliga a revisar en varios canales. Ha tenido problemas porque los cambios de horario se comunican solo por WhatsApp, sin confirmación formal, lo que ha causado retrasos y reclamos de clientes. Prefiere que las conversaciones estén separadas por proyectos o turnos para evitar confusiones y considera útiles las notificaciones de reuniones, cambios de última hora y anuncios prioritarios, pero molestas las reacciones o mensajes rutinarios. Usa más el celular que la computadora para comunicarse, ya que lo acompaña todo el día en el trabajo.

* **Necesidades:**

  - Una herramienta exclusiva para el trabajo que no invada su WhatsApp personal.

  - Un muro de anuncios donde lo formal quede separado de las conversaciones informales.

  - Calendario integrado y sincronizado con recordatorios automáticos en el celular.

  - Confirmación de lectura en anuncios importantes.

  - Segmentación por proyectos o áreas para encontrar la información más rápido.

  - Un sistema de notificaciones filtradas y prioritarias, evitando mensajes rutinarios o irrelevantes.

  - Acceso tanto en celular como en laptop.





**Entrevista #3:**

**Figura 4**

*Imagen del usuario número 6 entrevistado*

<p align="center">
  <img src="https://res.cloudinary.com/df8xwy4xb/image/upload/v1758039708/Entrevista_Milagros_foto_wpybdk.jpg" alt="Class Diagram">
</p>

*Nota.* Elaboración propia. Link: https://goo.su/RpcRZ2

* **Nombre:** Milagros Arelano Bendezu

* **Edad:** 23 años

* **Minuto de inicio:** 1:15

* **Resumen:** Milagros depende de herramientas de mensajería rápidas para coordinar operaciones diarias. Aunque WhatsApp es práctico, le genera confusión al mezclar mensajes laborales y personales, además de la falta de confirmación formal de lectura. El chat interno de la empresa no es confiable en zonas de baja señal, lo que limita su utilidad. Suele enterarse de anuncios importantes por WhatsApp o llamadas, mientras que los correos quedan relegados hasta que tiene acceso en oficina. Para organizar reuniones y eventos, intenta usar Google Calendar, pero termina dependiendo de recordatorios informales y apuntes en libreta. Milagros siente incomodidad usando su número personal para trabajo, ya que pierde la separación entre vida laboral y personal, y teme perder información importante al cambiar de número. Valora una herramienta que sea ordenada, funcional en condiciones de baja conectividad y que centralice la información en un solo espacio.

* **Necesidades:**

  - Separar lo personal de WhatsApp.

  - Funcionar con señal baja y sincronizar después.

  - Calendario con recordatorios automáticos.

  - Confirmación de lectura en avisos.

  - Segmentación por zonas o equipos.

  - Historial seguro y centralizado.

  - Notificaciones solo de lo importante.
  
    

**<u>Segmento objetivo #2: Gerentes y lideres de equipo</u>**


**Entrevista 4:**

**Figura 5**

*Imagen del usuario número 4 entrevistado*

<p align="center">
  <img src="https://res.cloudinary.com/df8xwy4xb/image/upload/v1758043275/entrevista_elverth_gerente_smwno4.png" alt="Class Diagram">
</p>

*Nota.* Elaboración propia. Link: https://goo.su/PGTYLE 

* **Nombre:** Ivan Lavado Vallejos
* **Edad:** 21 años
* **Minuto de inicio:** 1:01
- **Resumen:** Iván, estudiante de Ingeniería Civil y líder en una empresa de construcción, se comunica principalmente por WhatsApp y correo electrónico, además de usar Google Calendar y Meet para reuniones. Su mayor dificultad es asegurar que todos reciban y lean la información, ya que a menudo los mensajes se pierden, generando retrasos. También le preocupa la falta de seguridad y el uso de aplicaciones informales como WhatsApp para temas laborales.

- **Necesidades:** 

  - Herramienta de comunicación exclusiva para lo laboral.

  - Confirmación de lectura en anuncios y mensajes importantes.

  - Segmentación de información por área o proyecto.

  - Panel de métricas para medir engagement del equipo.

  - Controles de seguridad y permisos para publicar o crear grupos.

  - Facilidad de adopción en un entorno de construcción.



**Entrevista #5:**

**Figura 6**

*Imagen del usuario número 5 entrevistado*

<p align="center">
  <img src="https://res.cloudinary.com/df8xwy4xb/image/upload/v1758039740/Entrevista_Vania_Foto_kck9s4.jpg" alt="Class Diagram">
</p>

*Nota.* Elaboración propia. Link. https://goo.su/NdZQ

* **Nombre:** Vania Hidalgo Quincho
* **Edad:** 21 años
* **Minuto de inicio:** 1:10
* **Resumen:** Vania Hidalgo Quincho, Líder de equipo de Atención al Cliente en QuickBuy Perú, coordina un grupo de 8 personas responsables de atender pedidos y reclamos en canales digitales. Utiliza principalmente WhatsApp para avisos urgentes y un grupo interno de Facebook creado por la empresa, mientras que para reclamos más serios emplea el correo. También realizan reuniones rápidas en Google Meet, aunque no siempre todos se conectan. Su mayor desafío es lograr que todos los miembros de su equipo lean y confirmen los avisos a tiempo. Muchas veces algunos colaboradores no responden o aseguran que no vieron el mensaje, lo que genera retrasos y afecta directamente la atención al cliente. Esto ya le ha ocasionado problemas con clientes y llamados de atención de su jefa. Para asegurarse de que todos estén informados, debe preguntar uno por uno por privado, lo cual le quita tiempo valioso. Percibe riesgos en el uso de WhatsApp: mezcla de lo personal con lo laboral, mensajes fuera de horario y dispersión de la información porque cualquiera puede crear grupos. Le gustaría una herramienta más ordenada, donde pueda enviar avisos que queden registrados, con confirmación de lectura y segmentación por equipos. Considera clave que sea fácil de usar, ya que no todos en su equipo son expertos en tecnología.

* **Necesidades:**

  - Una plataforma de comunicación centralizada que reemplace WhatsApp y el grupo de Facebook.

  - Un panel de métricas que muestre quién leyó un comunicado y quién confirmó asistencia.

  - Notificaciones automáticas y recordatorios integrados con calendario.

  - Segmentación de mensajes por equipo o área, para evitar información irrelevante.

  - Controles de seguridad y permisos, donde solo líderes puedan enviar anuncios globales.

  - Historial respaldado, incluso si un colaborador deja la empresa.

  - Una interfaz sencilla y fácil de usar, adaptable a equipos con distintos niveles de conocimiento tecnológico.



**Entrevista #6:**

**Figura 7**

*Imagen del usuario número 6 entrevistado*

<p align="center">
  <img src="https://res.cloudinary.com/df8xwy4xb/image/upload/v1758039708/Entrevista_Guiliana_l9c16c.jpg" alt="Class Diagram">
</p>

*Nota.* Elaboración propia. Link: https://goo.su/LOTchFG

* **Nombre:** Guilianna Curipaco Huayllani
* **Edad:** 28 años
* **Minuto de inicio:** 1:07
* **Resumen:** Guiliana, Jefa de Recursos Humanos en una constructora de Lima, coordina a un equipo de 25 personas. Utiliza WhatsApp para comunicaciones rápidas y correo (Outlook) para lo formal, aunque muchas veces debe reforzar los mensajes por múltiples canales porque no todos leen a tiempo. Para reuniones virtuales emplea Teams, pero aun así suele enviar recordatorios por WhatsApp. Su mayor desafío es asegurarse de que todos lean y comprendan los comunicados importantes, lo cual le genera reprocesos y pérdida de tiempo al tener que confirmar manualmente. Ha enfrentado problemas cuando políticas internas no fueron leídas, ocasionando retrasos y quejas de gerencia. Además, considera que WhatsApp trae riesgos: mezcla de lo personal con lo laboral, falta de control de la información y poca seguridad. Al organizar eventos y reuniones, usa Outlook, pero desearía contar con una plataforma única que se sincronice con el calendario y que avise automáticamente al equipo. Valora especialmente la seguridad, el control sobre quién publica y la trazabilidad de la información. Para ella, sería clave poder segmentar los comunicados por área, ver métricas de lectura y contar con confirmación de asistencia.

* **Necesidades:**

  - Una plataforma centralizada que integre chat, anuncios y calendario en un solo lugar.

  - Confirmación de lectura automática en comunicados importantes.

  - Un panel de métricas con porcentajes de lectura, asistencia a eventos y nivel de participación.

  - Segmentación de mensajes por área o proyecto, evitando la sobrecarga de información.

  - Controles de seguridad y permisos, donde solo líderes puedan publicar anuncios globales.

  - Trazabilidad y respaldo de la información, incluso si un empleado se retira.

  - Separación clara de lo personal y lo laboral, para reducir quejas y estrés del equipo.



### ***2.2.3. Análisis de entrevistas***

<p style="text-indent: 1.25cm;">En este apartado se documenta de manera estructurada cada una de las entrevistas realizadas a los diferentes segmentos objetivo. Para cada entrevista, se incluye información relevante como el perfil del entrevistado, el registro de sus respuestas, observaciones contextuales, y un resumen de los principales hallazgos obtenidos.

<p style="text-indent: 1.25cm;">Esta sistematización permite asegurar la trazabilidad de los datos recolectados, facilitando su posterior análisis y su utilización en la construcción de artefactos de usuario, tales como User Personas, Empathy Maps y User Task Matrices.

<p style="text-indent: 1.25cm;">Características objetivas y subjetivas más comunes de cada segmento:

<u>**Segmento objetivo #1: Empleados de Empresas**</u>

* **Características Objetivas Comunes:**

  - Sexo: Femenino.
  - Edad: 28-35 años. 
  - Dispositivos: Laptop de marca Hp con sistema operativo Windows 10 y smartphone android.
  - Programas: WhatAspp , Meet, Google Calendar, Procreate.
  - Canales de información: WhatsApp, Google Gmail,
  - Marcas preferidas: Google Gmail, WhatsApp, Google Meet

* **Características Subjetivas Comunes:**

  - Problemas al encontrar mensajes importantes.
  - Dispersión de comunicación, uso de varias aplicaciones.
  - Disgusto por combinar conversiones de vida personal y laboral.
  - Interés por la centralización de la comunicación laboral
  - Mayor uso de dispositivos móviles.

<u>**Segmento objetivo #2: Gerentes o líderes de equipo**</u>

* **Características Objetivas Comunes:**

  - Sexo: Masculino.
  - Edad: 40-55 años.
  - Dispositivos: Laptop de marca HP con sistema operativo Windows 10 y iPhone.
  - Canales de información: Messenger , WhatsApp, Outlook.
  - Marcas preferidas: Messenger , WhatsApp, Outlook.

* **Características Subjetivas Comunes:**

  - Problemas con las confirmaciones de lectura 
  - Conflicto con la organización de archivos
  - Valora la facilidad del uso de la herramienta.
  - Orientación hacia la eficiencia y ahorro de tiempo.
  - Preocupación por la seguridad de la empresa y el profesionalismo de los empleados. 
  - Necesidad del control jerárquico. 

## **2.3. Needfinding**

<p style="text-indent: 1.25cm;">Para identificar las necesidades reales de los usuarios objetivo de Centralis, se realizaron entrevistas en profundidad a dos segmentos clave: empleados y gerentes/líderes. A través de estas entrevistas, se descubrieron patrones comunes y críticos en cada grupo, como la necesidad de centralizar la comunicación fragmentada en múltiples aplicaciones (WhatsApp, correo, calendarios), la frustración por la pérdida de información importante en entornos informales, la demanda de herramientas intuitivas y móviles que prioricen la usabilidad, y la urgencia por separar la comunicación laboral de la personal para mejorar el equilibrio vida-trabajo. 

### ***2.3.1. User Personas***

<p style="text-indent: 1.25cm;">En esta sección se construyeron perfiles representativos denominados “User Personas”, los cuales sintetizan características clave de los usuarios objetivo a partir del análisis cualitativo de las entrevistas. Cada User Persona refleja patrones comunes de comportamiento, motivaciones, frustraciones, objetivos, dispositivos utilizados y canales de información. Esta herramienta permitió traducir datos individuales en arquetipos comprensibles que orientan el diseño centrado en el usuario, facilitando decisiones estratégicas en cuanto a funcionalidades, experiencia de usuario y comunicación visual.

*“Anexo: User Persona”*: https://acortar.link/gN7rnw

Se desarrollaron dos perfiles principales:


<u>**Segmento objetivo #1: Empleados de Empresas**</u>

**Figura 8**

*User Persona Segmento Objetivo #1: Empleados de Empresas*

<p align="center">
  <img src="https://res.cloudinary.com/dpprgycup/image/upload/v1757951334/Mar%C3%ADa_Moreira_uqhhdr.png" alt="Class Diagram">
</p>

*Nota.* Elaboración propia.

#

<ins>**Segmento Objetivo 2: Gerentes y Líderes de Equipos**</ins>

**Figura 9**

*User Persona Segmento Objetivo #2: Gerentes y Líderes de Equipos*

<p align="center">
  <img src="https://res.cloudinary.com/dpprgycup/image/upload/v1757951331/Carlos_Rom%C3%A1n_qhu0ye.png" alt="Class Diagram">
</p>

*Nota.* Elaboración propia.

### ***2.3.2. User Task Matrix***

<p style="text-indent: 1.25cm;">A continuación se presenta el User Task Matrix, construido a partir de las entrevistas realizadas a los dos segmentos definidos: Empleados de Empresas y Gerentes o Líderes de Equipos.


| N°   | Task Matrix                                       | Maria Moreira | Maria Moreira | Carlos Román | Carlos Román |
| ---- | ------------------------------------------------- | ------------- | ------------- | ------------ | ------------ |
|      |                                                   | Frecuencia    | Importancia   | Frecuencia   | Importancia  |
| 1    | Explora la landing page y conoce la aplicación    | Baja          | Media         | Media        | Media        |
| 2    | Recibe notificaciones de los eventos              | Alta          | Alta          | Alta         | Alta         |
| 3    | Crea grupos de chats                              | Media         | Media         | Media        | Alta         |
| 4    | Crea eventos para un grupo específico             | Baja          | Media         | Alta         | Alta         |
| 5    | Publica noticias o anuncios importantes           | Baja          | Media         | Alta         | Alta         |
| 6    | Crea eventos para un sector específico            | Baja          | Baja          | Media        | Alta         |
| 7    | Revisar quienes leyeron el anuncio                | Baja          | Baja          | Alta         | Alta         |
| 8    | Marca como leído un anuncio importante            | Media         | Alta          | Media        | Media        |
| 9    | Administrar permisos para crear grupos o anuncios | Baja          | Baja          | Media        | Alta         |
| 10   | Revisar métricas en el panel de control           | Baja          | Baja          | Media        | Alta         |



* **Diferencias Clave entre Segmentos**

Enfoque en control vs. practicidad:

  - Carlos realiza tareas de gestión y supervisión (revisar métricas, administrar permisos, publicar anuncios) con alta frecuencia e importancia.
  - María se centra en tareas operativas y reactivas (recibir notificaciones, marcar anuncios como leídos) que simplifiquen su flujo de trabajo.

* **Uso de analytics**:

  - Carlos necesita paneles de control y métricas (ej: tasa de lectura de anuncios) para tomar decisiones.
  - María no usa analytics, pero valora confirmaciones simples (ej: "visto" en anuncios) para su tranquilidad.

* **Creación de contenido:**

  - Carlos genera anuncios y eventos constantemente
  - María principalmente los consume.

* **Coincidencias Relevantes**

  - Ambos comparten la necesidad de notificaciones efectivas y grupos de chat organizados.

  - Tareas como crear eventos son más frecuentes para Carlos, pero ambos las consideran importantes para la coordinación.

  - Marcar anuncios como leídos es relevante para ambos: para María, es una forma de confirmar recepción; para Carlos, un mecanismo de validación.

* **Implicancias para el Diseño de Centralis**

Priorizar funcionalidades para gerentes:

  - Paneles de control con métricas de engagement (ej: % de lectura de anuncios).
  - Herramientas de segmentación para enviar mensajes a grupos específicos.

* **Optimizar la experiencia para empleados:**

  - Notificaciones que destaquen lo urgente.
  - Flujos simples para confirmar lectura o asistencia a eventos.

Este análisis refuerza que Centralis debe equilibrar simplicidad para empleados como María con herramientas de gestión robustas para líderes como Carlos.


### ***2.3.3. User Journey Mapping***

<p style="text-indent: 1.25cm;">Con el objetivo de comprender en profundidad las necesidades, comportamientos, emociones y puntos de fricción de los usuarios de Centralis, se desarrolló un User Journey Mapping utilizando metodologías centradas en el usuario. Este proceso permitió visualizar de manera estructurada y empática el recorrido que cada segmento realiza desde el descubrimiento de la herramienta hasta su adopción y uso continuo, identificando oportunidades clave para optimizar la experiencia.

* **La actividad se centró en dos segmentos principales:**

  - María Moreira, empleada administrativa que busca centralizar la comunicación laboral y reducir el estrés causado por la fragmentación de canales.
  - Carlos Román, gerente de ventas que necesita controlar la difusión de información crítica y garantizar la accountability de su equipo.

* **Para cada perfil, se diseñó un mapa que incluye:**

  - Fases del proceso: Descubrimiento, Registro, Uso diario y Análisis de resultados.
  - Objetivos del usuario en cada etapa.
  - Acciones específicas (procesos) y canales utilizados.
  - Emociones experimentadas, representadas mediante un sistema visual intuitivo: Frustración, Alivio, Satisfacción.
  - Problemas identificados y oportunidades de mejora a lo largo del recorrido.

<p style="text-indent: 1.25cm;">Gracias a UXPressia, se logró una representación visual dinámica y clara que facilita la toma de decisiones centradas en el usuario. Este trabajo no solo mejora la comprensión de sus motivaciones y desafíos, sino que también guía el diseño de soluciones más relevantes, empáticas y funcionales para cada perfil identificado.

*“Anexo: Diagrama Journey Mapping”* : https://acortar.link/E1OgkX

<ins>**Segmento Objetivo 1: Empleados de Empresas**</ins>  

**Figura 10**

*User Journey Mapping Objetivo #1: Empleados de Empresas*

<p align="center">
  <img src="https://res.cloudinary.com/dpprgycup/image/upload/v1757951408/Journey_Mapping_Empleados_de_Empresas_knmgcv.png" alt="Class Diagram">
</p>

*Nota.* Elaboración propia. 

#

<ins>**Segmento Objetivo 2: Gerentes y Líderes de Equipos**</ins>

**Figura 11**

*User Journey Mapping Objetivo #2: Gerentes y Líderes de Equipos*

<p align="center">
  <img src="https://res.cloudinary.com/dpprgycup/image/upload/v1757951407/Journey_mapp_de_Gerentes_y_Lideres_de_Equipos_wzslfm.png" alt="Class Diagram">
</p>

*Nota.* Elaboración propia. 


### ***2.3.4. Empathy Mapping***

<p style="text-indent: 1.25cm;">Los siguientes mapas de empatía ilustran los conocimientos recopilados para cada uno de los dos segmentos objetivo definidos en el proyecto: 

<ins>**Segmento Objetivo 2: Gerentes y Líderes de Equipos**</ins>

**Figura 12**

*Empathy Mapping Empleados de Empresas*

<p align="center">
  <img src="https://res.cloudinary.com/dpprgycup/image/upload/v1757951612/Mapa-empatia-S1_aqgfll.png" alt="Class Diagram">
</p>

*Nota.* Elaboración propia.

#

<ins>**Segmento Objetivo 2: Gerentes y Líderes de Equipos**</ins>

 **Figura 13**

*Empathy Mapping Gerentes y Líderes de Equipos*

<p align="center">
  <img src="https://res.cloudinary.com/dpprgycup/image/upload/v1757951614/Mapa-empatia-S2_a62fxc.png" alt="Class Diagram">
</p>

*Nota.* Elaboración propia.

### ***2.3.5. As-is Scenario Mapping.***

<p style="text-indent: 1.25cm;">El As-Is Scenario Mapping representa el proceso actual "tal cual" funciona hoy en día para nuestros User Personas (Gerentes y Empleados). En este mapeo, se evidencia un ecosistema de comunicación fragmentado donde predomina el uso de herramientas no oficiales como WhatsApp, correos electrónicos saturados y avisos físicos.

- **Observaciones Clave:** Se detecta una alta carga de frustración en los **Gerentes** debido a la repetición manual de información y la falta de métricas (no saben quién lee los anuncios). Por otro lado, los **Empleados** experimentan una constante incertidumbre y fatiga informativa, al no poder distinguir fácilmente qué información es oficial o prioritaria.
- **Resultado:** El mapa visualiza un flujo caótico, con sentimientos de falta de control y desconexión organizacional.

<p align="center">
  <img src="https://i.imgur.com/9JcFOZH.png" alt="as is">
</p>



## 2.5. Ubiquitous Language.

| **Ubiquos Term**                | **Definition of Functional Domain**                          |
| ------------------------------- | ------------------------------------------------------------ |
| Employee (Empleado)             | Cualquier persona que trabaja para la empresa y utiliza la plataforma para comunicarse con colegas y gerentes, y acceder a información relevante. |
| Manager (Gerente)               | Líder o supervisor que utiliza la plataforma para comunicar anuncios formales, organizar eventos, crear equipos y asegurar la llegada de información vital a sus equipos. |
| Event (Evento)                  | Actividad programada (reunión, capacitación, evento social) publicada por un gerente. Los empleados pueden acceder a detalles. |
| Chat (Chat)                     | Funcionalidad de mensajería bidireccional organizada en Groups para diferentes propósitos (departamentos, proyectos, etc.). |
| Announcement (Anuncio)          | Comunicación formal publicada por un Manager. Contiene información relevante. |
| Reading (Lectura)               | Mecanismo que permite a un Manager verificar qué Employees han leído un Announcement específico. |
| Group (Grupo)                   | Espacio de Chat dedicado a un tema, departamento o proyecto específico. Puede ser creado por Managers o Employees (según Permissions). |
| Notification (Notificación)     | Alerta que informa a los usuarios sobre Events. Puede ser prioritaria o regular. |
| Permission (Permiso)            | Configuración que define qué acciones puede realizar un usuario (ej: crear Groups, publicar Announcements). Los Managers tienen permisos elevados. |
| Dashboard (Panel de Control)    | Interfaz exclusiva para Managers que muestra métricas de engagement (ej: porcentaje de lectura de Announcements). |
| Read Status (Estado de Lectura) | Indicador que muestra si un Employee ha abierto y visto un Announcement. |
| Comment (comentario)            | Respuesta o feedback escrito por un Employee o Manager que puede agregar a un Announcement existente. Los comentarios son visibles para todos los usuarios con acceso al anuncio. |
| Notification (Notificación)     | Notificación enviada a los empleados cuando se crea un anuncio, evento y se envía un mensaje. |
| Invitees (Invitados)            | Lista de empleados invitados a un evento, ya sea reunión, capacitación, etc. |
| Priority (Prioridad)            | Atributo que indica alta importancia y desencadena notificaciones urgentes. |
| Profiles (Perfiles)             | Perfiles de los usuarios donde se mostrará datos personales  |
| Company (Compañía)              | La entidad legal o comercial raíz en el sistema. Funciona como un entorno aislado que agrupa a sus propios Employees y Managers. Toda la información (Events, Chats, Announcements) está confinada al alcance de una única Company. |

