# Capítulo III: Requirements Specification

## 3.1. To-Be Scenario Mapping.

<p style="text-indent: 1.25cm;">El To-Be Scenario Mapping proyecta la experiencia optimizada una vez implementada la plataforma Centralis y la nueva estructura de Company. Este modelo rediseña el flujo de trabajo para eliminar los puntos de dolor identificados en la fase anterior.

- **Transformación del Proceso:** En este escenario, la comunicación se centraliza en un entorno único y seguro. El proceso de registro de la **Company** mediante RUC y la carga de logos establece un sentido de pertenencia formal. Las fases de publicación de anuncios y creación de eventos ahora incluyen automatizaciones (notificaciones push, confirmaciones de lectura y asistencia) que eliminan la incertidumbre.
- **Impacto en el Usuario:** El **Gerente** recupera el control estratégico mediante el *Dashboard* de métricas, mientras que el **Empleado** se siente más integrado y valorado al contar con canales directos de feedback y una interfaz clara.
- **Resultado:** El flujo se vuelve lineal y eficiente, sustituyendo la frustración por sentimientos de confianza, orden y compromiso proactivo.

<p align="center">
  <img src="https://i.imgur.com/TCNr03W.png" alt="To-Be">
</p>



## 3.2. User Stories.

<p style="text-indent: 1.25cm;">En esta sección se presentan los requisitos funcionales del sistema expresados como User Stories. Estas historias de usuario representan las necesidades de los diferentes roles que interactuarán con la plataforma Centralis, priorizando la entrega de valor para el usuario final. Cada story incluye su criterio de aceptación en formato Gherkin, asegurando que los requisitos sean claros, testeables y alineados con los objetivos del negocio. Las stories cubren tanto la experiencia móvil como la web, incluyendo el Landing Page y los Web Services.

<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US01</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">visitante</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">3</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Pagina de presentación</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; ">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Cambiar el idioma de la landing page</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como visitante, quiero traducir la página para leer el contenido en mi idioma preferido.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Traducción<br><br>Escenario: Traducir contenido<br>Dado que el visitante se encuentra en la landing page, <br>Cuando elige su idioma preferido,<br>Entonces se traduce al idioma seleccionado,<br>Y el cambio se mantiene.</td>
  </tr>
</table>


<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US02</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">visitante</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">3</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Pagina de presentación</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Sección About de la landing page</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como visitante, quiero ver una sección About en la landing page para entender la misión, visión y propósito de Centralis.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Sección About<br><br>Escenario: Visualizar información de la empresa<br>Dado que un visitante navega a la landing page de Centralis,<br>Cuando navega por la sección About,<br>Entonces ve un texto claro que explica el propósito de la aplicación, misión y visión de la empresa .</td>
  </tr>
</table>


<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US03</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">visitante</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">3</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Pagina de presentación</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Historia de la startup</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como visitante, quiero conocer la historia y origen de Centralis para generar confianza en la marca.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Historia de la compañía<br><br>Escenario: Leer la historia fundacional<br>Dado que el visitante está en la la landing page,<br>Cuando navega por la sección About,<br>Entonces ve una información relevante acerca de la historia de Centralis.</td>
  </tr>
</table>


<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US04</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">visitante</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">3</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Pagina de presentación</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Sección FAQ</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como visitante, quiero acceder a una sección FAQ para resolver mis dudas comunes sobre el producto.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Sección FAQ<br><br>Escenario: Consultar preguntas frecuentes<br>Dado que el visitante tiene dudas sobre funcionalidades de Centralis,<br>Cuando navega a la sección FAQ desde el menú principal,<br>Entonces ve una lista organizada de preguntas y respuestas,<br>Y puede expandir cada pregunta para ver la respuesta completa.</td>
  </tr>
</table>


<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US05</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">visitante</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">3</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Pagina de presentación</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Sección Team</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como visitante, quiero conocer al equipo detrás de Centralis para humanizar la marca y generar confianza.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Sección Team<br><br>Escenario: Ver información del equipo<br>Dado que el visitante quiere conocer a los creadores de Centralis,<br>Cuando navega a la sección Team,<br>Entonces ve fotos y perfiles de los miembros del equipo de desarrollo,<br>Y puede conocer sus roles y experiencia relevante.</td>
  </tr>
</table>


<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US06</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">visitante</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">3</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Pagina de presentación</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Links profesionales del equipo</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como visitante, quiero acceder a los perfiles profesionales del equipo para verificar su expertise.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Links profesionales<br><br>Escenario: Acceder a los perfiles profesionales de los desarrolladores<br>Dado que el visitante está en la sección Team,<br>Cuando hace clic en el perfil de un desarrollador,<br>Entonces es redirigido al perfil profesional del desarrollador,<br>Y puede verificar su experiencia.</td>
  </tr>
</table>


<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US07</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">visitante</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">3</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Pagina de presentación</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Compatibilidad con múltiples dispositivos</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como visitante, quiero poder ver la landing page en mi dispositivo móvil para no tener que abrir el sitio web en un dispositivo similar a una computadora de escritorio.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Diseño adaptable<br><br>Escenario: Diseño adaptable<br>Dado que el visitante se encuentra un dispositivo móvil, <br>Cuando abre la landing page,<br>Entonces la landing page muestra una versión adaptada a su dispositivo móvil</td>
  </tr>
</table>


<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US08</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">visitante</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">2</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Pagina de presentación</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Acceso a Centralis desde la landing page</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como visitante, quiero acceder a Centralis directamente desde la landing page para poder interactuar con la aplicacion.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Acceder a Centralis<br><br>Escenario: Redirigir a Centralis<br>Dado que el visitante se encuentra en la landing page.<br>Cuando se registra o inicia sesión,<br>Entonces se le redirige a Centralis.<br>Y puede interactuar con la aplicación.</td>
  </tr>
</table>


<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US09</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">visitante</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">3</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Pagina de presentación</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Navegación Accesible</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como visitante que utiliza tecnologías de asistencia, quiero que la landing page anuncie claramente las etiquetas de las secciones para comprender su estructura y propósito.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Integración de Accesibilidad ARIA<br><br>Escenario: Escuchar etiquetas descriptivas<br>Dado que el visitante utiliza un lector de pantalla para navegar por los sitios web, <br>Cuando navega por la landing page con el teclado, <br>Entonces se anuncian los roles ARIA correspondientes a cada sección.<br>Escenario: Navegación por puntos de referencia<br>Dado que el visitante utiliza un lector de pantalla con la navegación activada, <br>Cuando navega por la landing page usando puntos de referencia o accesos directos, <br>Entonces puede acceder a las secciones clave.</td>
  </tr>
</table>






---



---



---




<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US10</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">gerente</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">8</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Publicacion de anuncios</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Publicación básica de anuncios</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como gerente, quiero publicar anuncios en la aplicación móvil para que los empleados estén informados de las novedades de la empresa.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Publicación de anuncios<br><br>Escenario: Publicar un anuncio exitosamente<br>Dado que el gerente ha iniciado sesión en la aplicación móvil,<br>Cuando quiera publicar un anuncio con información relevante,<br>Entonces el sistema guarda el anuncio en la base de datos,<br>Y muestra el anuncio donde los empleados puedan verlo.</td>
  </tr>
</table>

---

<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US11</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">gerente</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">5</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Publicacion de anuncios</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Priorización de anuncios</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como gerente, quiero marcar anuncios como prioritarios para que los empleados los vean primero.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Anuncios prioritarios<br><br>Escenario: Marcar un anuncio como prioritario<br>Dado que el gerente está creando un nuevo anuncio,<br>Cuando marca el anuncio como prioritario y completa la publicación,<br>Entonces el sistema muestra el anuncio en la sección destacada,<br>Y envía una notificación urgente a todos los empleados.</td>
  </tr>
</table>
<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US12</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">gerente</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">5</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Publicacion de anuncios</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Edición de anuncios</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como gerente, quiero editar anuncios ya publicados para corregir errores o actualizar información.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Editar anuncio<br>Escenario: Editar un anuncio existente<br>Dado que el gerente visualiza un anuncio publicado previamente,<br>Cuando modifica y guarda los cambios de la nueva información del anuncio,<br>Entonces el sistema actualiza el anuncio en la base de datos,<br>Y los cambios se reflejan inmediatamente.</td>
  </tr>
</table>

---

<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US13</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">gerente</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">3</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Publicacion de anuncios</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Eliminación de anuncios</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como gerente, quiero eliminar anuncios obsoletos para mantener la información actualizada.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Eliminación de anuncios<br><br>Escenario: Eliminar un anuncio publicado<br>Dado que el gerente visualiza un anuncio,<br>Cuando selecciona el anuncio a eliminar y confirma la acción,<br>Entonces el sistema remueve el anuncio de la base de datos,<br>Y los empleados ya no pueden visualizarlo en sus dispositivos.</td>
  </tr>
</table>




---

<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US14</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">gerente</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">5</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Publicacion de anuncios</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Confirmaciones de lectura</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como gerente, quiero ver confirmaciones de lectura de anuncios para saber quién ha leído la información importante.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Confirmaciones de lectura<br><br>Escenario: Ver reporte de lecturas de un anuncio<br>Dado que el gerente ha publicado un anuncio prioritario,<br>Cuando selecciona el anuncio,<br>Entonces el sistema muestra la lista de empleados que han leído el anuncio,</td>
  </tr>
</table>

---





---





---


<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US15</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">empleado</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">5</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Publicacion de anuncios</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Comentarios en anuncios</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como empleado, quiero dar feedback sobre anuncios para aclarar dudas o hacer comentarios.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Comentarios en anuncios<br><br>Escenario: Comentar un anuncio<br>Dado que el empleado está visualizando un anuncio sobre nuevas políticas,<br>Cuando selecciona el anuncio y escribe su pregunta,<br>Entonces el sistema publica el comentario asociado al anuncio,</td>
  </tr>
</table>


---

<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US16</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">gerente</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">5</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Publicacion de anuncios</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Subir imágenes en anuncios</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como gerente quiero poder adjuntar imágenes a los anuncios publicados, para que la información sea más clara y atractiva.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Subir imágenes en anuncios<br><br>Escenario: Adjuntar imagen a un anuncio<br>Dado que un gerente está creando un anuncio,<br>Cuando selecciona la opción de adjuntar una imagen desde su dispositivo,<br>Entonces la imagen se carga en Cloudinary y queda asociada al anuncio.</td>
  </tr>
</table>

<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US17</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">empleado</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">5</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Publicacion de anuncios</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Visualizar imágenes en anuncios</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como empleado quiero poder ver las imágenes adjuntas en los anuncios, para comprender mejor la información publicada.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Visualizar imágenes en anuncios<br>Escenario: Mostrar imagen en un anuncio publicado<br>Dado que un empleado visualiza un anuncio,<br>Cuando el anuncio tiene una imagen adjunta,<br>Entonces la imagen se muestra con buena resolución y adaptada a su dispositivo.</td>
  </tr>
</table>

<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US18</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">gerente</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">8</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Creación de eventos</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Creación básica de eventos</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como gerente, quiero crear eventos en la aplicación móvil para organizar reuniones y actividades de la empresa.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Creación de eventos<br><br>Escenario: Crear un evento exitosamente<br>Dado que el gerente ha iniciado sesión en la aplicación móvil,<br>Cuando crea un evento llenando los datos necesarios,<br>Entonces el sistema guarda el evento en la base de datos,<br>Y lo muestra a los empleados seleccionados.</td>
  </tr>
</table>



---

<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US19</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">gerente</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">3</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Creación de eventos</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Cancelación de eventos</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como gerente, quiero cancelar eventos cuando sea necesario para evitar confusiones.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Cancelación de eventos<br><br>Escenario: Cancelar evento programado<br>Dado que el gerente visualiza un evento futuro en la lista de eventos,<br>Cuando selecciona un evento para cancelarlo y proporciona una razón,<br>Entonces el sistema notifica automáticamente a todos los invitados sobre la cancelación,<br>Y elimina el evento de la lista de eventos.</td>
  </tr>
</table>

---

<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US20</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">gerente</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">3</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Creación de eventos</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Modificación de eventos</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como gerente, quiero modificar detalles de eventos existentes para ajustar cambios de último momento.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Modificación de eventos<br><br>Escenario: Cambiar fecha de evento<br>Dado que el gerente necesita posponer un eventos,<br>Cuando edita la fecha del evento y guarda los cambios,<br>Entonces el sistema notifica automáticamente a los invitados sobre la nueva fecha,<br>Y actualiza el evento en la lista de eventos.</td>
  </tr>
</table>

---

<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US21</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">gerente</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">3</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Creación de eventos</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Eventos prioritarios</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como gerente, quiero marcar eventos como prioritarios para que los empleados les presten especial atención.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Eventos prioritarios<br><br>Escenario: Marcar evento como prioritario<br>Dado que el gerente está creando un evento importante,<br>Cuando marque el evento como importante antes de publicar,<br>Entonces el sistema muestra el evento como prioritario.</td>
  </tr>
</table>


<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US22</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">gerente</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">5</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Creación de eventos</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Métricas de participación</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como gerente, quiero ver métricas de participación en eventos para medir el engagement del equipo.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Métricas de eventos<br><br>Escenario: Ver tasa de asistencia a eventos<br>Dado que el gerente navega al dashboard de eventos,<br>Cuando selecciona un evento,<br>Entonces el sistema muestra el porcentaje de asistencia promedio por evento.</td>
  </tr>
</table>
<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US23</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">empleado</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">5</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Comunicación por chats</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Creación de chats grupales</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como empleado, quiero crear chats grupales para discutir temas específicos con mis colegas.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Creación de chats grupales<br><br>Escenario: Crear chat grupal para proyecto<br>Dado que el empleado necesita coordinar un proyecto con un equipo,<br>Cuando crea un nuevo chat, añade participantes y establece un nombre para el grupo,<br>Entonces el sistema crea el chat con todos los miembros añadidos.</td>
  </tr>
</table>


---

<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US24</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">gerente</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">5</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Comunicación por chats</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Eliminar grupos de chats</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como gerente, quiero eliminar chats grupales para mantener el orden de las conversaciones.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Moderación de chats<br><br>Escenario: Eliminar mensaje inapropiado<br>Dado que un empleado envía un mensaje inadecuado en un chat grupal,<br>Cuando el gerente selecciona el mensaje y confirma su eliminación,<br>Entonces el sistema remueve el mensaje para todos los participantes.</td>
  </tr>
</table>


<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US25</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">empleado</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">3</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Comunicación por chats</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Envío de mensajes</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como empleado, quiero enviar mensajes para mantenerme comunicado con mi equipo</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Entrega de mensajes<br><br>Escenario: Enviar mensaje <br>Dado que el empleado envía un mensaje importante en un chat,<br>Cuando el mensaje es entregado al servidor,<br>Entonces el sistema muestra el mensaje en el chat del grupo.</td>
  </tr>
</table>
<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US26</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">empleado</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">5</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Comunicación por chats</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Eliminación de mensajes enviados</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como empleado, quiero eliminar mensajes que envié por error para corregir mis equivocaciones.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Eliminación de mensajes propios<br><br>Escenario: Eliminar mensaje recién enviado<br>Dado que el empleado envió un mensaje con información incorrecta,<br>Cuando selecciona el mensaje y lo elimina,<br>Entonces el sistema remueve el mensaje para todos los participantes.</td>
  </tr>
</table>


<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US27</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">empleado</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">3</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Comunicación por chats</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Modificación de mensajes enviados</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como empleado, quiero editar mensajes que ya envié para corregir errores tipográficos.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Edición de mensajes<br><br>Escenario: Corregir error tipográfico en mensaje<br>Dado que el empleado envió un mensaje con un error de ortografía,<br>Cuando selecciona el mensaje y realiza la corrección,<br>Entonces el sistema actualiza el contenido del mensaje.</td>
  </tr>
</table>

<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US28</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">gerente</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">3</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Comunicación por chats</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Eliminación de chats grupales por gerentes</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como gerente, quiero eliminar chats grupales obsoletos o inactivos para mantener la lista de chats organizada y relevante.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Eliminación de chats grupales<br><br>Escenario: Eliminar chat grupal inactivo<br>Dado que un chat grupal ya no es de utilidad,<br>Cuando el gerente selecciona el chat y confirma la eliminación,<br>Entonces el sistema elimina permanentemente el chat y todo su historial.</td>
  </tr>
</table>
<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US29</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">empleado</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">3</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Comunicación por chats</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Listado organizado de chats</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como empleado, quiero ver todos los chats de los que forma parte para encontrar rápidamente conversaciones específicas.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Escenario: Ver chats de los que forma parte<br>Dado que el empleado está en la aplicación móvil,<br>Cuando navega a la lista principal de chats,<br>Entonces el sistema muestra todos los chats de los que forma parte.</td>
  </tr>
</table>


<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US30</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">empleado</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">3</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Comunicación por chats</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Enviar imágenes en chats grupales</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como empleado quiero poder enviar imágenes en los chats grupales, para compartir información visual con mi equipo.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Enviar imágenes en chats grupales<br><br>Escenario: Enviar imagen en un chat grupal<br>Dado que un usuario participa en un chat grupal,<br>Cuando adjunta y envía una imagen,<br>Entonces el sistema sube la imagen a Cloudinary y la muestra en la conversación.<br>Escenario: Error al enviar imagen<br>Dado que un usuario participa en un chat,<br>Cuando intenta enviar una imagen y ocurre un error de carga,<br>Entonces el sistema muestra un mensaje de error y le permite reintentar.</td>
  </tr>
</table>

---

<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US31</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">usuario</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">3</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Comunicación por chats</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Eliminar imágenes enviadas en el chat</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como usuario quiero poder eliminar una imagen enviada en un chat, para corregir errores o evitar confusiones.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Eliminar imágenes enviadas en el chat<br><br>Escenario: Eliminar una imagen enviada<br>Dado que un usuario envió una imagen en un chat,<br>Cuando selecciona la opción de eliminar,<br>Entonces la imagen desaparece del chat y se muestra un marcador de "archivo eliminado".<br>Escenario: Visualizar imagen eliminada en el historial<br>Dado que un usuario eliminó una imagen,<br>Cuando otro participante revisa el historial del chat,<br>Entonces debe visualizar el marcador de "archivo eliminado" en lugar de la imagen.</td>
  </tr>
</table>
<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US32</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">empleado</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">3</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Comunicación por chats</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Visualizar imágenes en chats</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como empleado, quiero ver todos los chats de los que forma parte para encontrar rápidamente conversaciones específicas.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Visualizar imágenes en chats<br><br>Escenario: Mostrar imagen recibida en un chat<br>Dado que un usuario recibe una imagen en un chat,<br>Cuando abre la conversación,<br>Entonces puede ver la imagen dentro del mensaje.<br>Escenario: Ampliar imagen recibida<br>Dado que un usuario recibe una imagen,<br>Cuando presiona sobre la imagen,<br>Entonces puede visualizarla en pantalla completa.</td>
  </tr>
</table>


<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US33</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">desarrollador</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">2</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Seguridad de acceso y protección de la información</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Validar y almacenar datos cifrados de usuario al registrarse</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como desarrollador, quiero validar los datos de registro entrantes y almacenar las credenciales cifradas de los empleados para que las cuentas se creen de forma segura y estén protegidas contra accesos no autorizados.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Validar y almacenar datos cifrados de usuario al registrarse<br><br>Escenario: Validar los campos de entrada de registro<br><br>Dado que un empleado realiza una solicitud de registro, <br>Cuando se procesa la entrada de solicitud, <br>Entonces se validan los campos obligatorios.<br>Si algún campo obligatorio falta o es inválido, se rechaza la solicitud.<br>Escenario: Asegurar que el correo electrónico sea único<br><br>Dado que un nuevo empleado intenta registrarse, <br>Cuando se detecta que el correo electrónico proporcionado ya está en uso,<br>Entonces se rechaza la solicitud de registro.</td>
  </tr>
</table>
<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US34</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">desarrollador</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">3</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Seguridad de acceso y protección de la información</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Restringir el acceso a la API</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como desarrollador, quiero proteger las rutas de la API mediante control de acceso basado en roles y protecciones de middleware para bloquear el acceso no autorizado.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Restringir el acceso a la API<br><br>Escenario: Bloquear el acceso a rutas protegidas sin autenticación<br><br>Dado que se presenta una solicitud no autenticada<br>Cuando se procesa la solicitud<br>Entonces, se devuelve una respuesta no autorizada<br>Y se impide la ejecución de cualquier lógica<br><br>Escenario: Denegar el acceso con permisos insuficientes<br><br>Dado que un empleado autenticado sin el rol requerido realiza una solicitud<br>Cuando se procesa la solicitud<br>Entonces se devuelve una respuesta restringida.</td>
  </tr>
</table>
<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US35</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">empleado</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">5</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Seguridad de acceso y protección de la información</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Mantener la sesión iniciada</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como empleado, quiero mantener la sesión iniciada de forma segura en todas las sesiones para no tener que volver a autenticarme con frecuencia al volver a la aplicación.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Mantener la sesión iniciada<br><br>Escenario: Regresar a la plataforma sin volver a iniciar sesión<br>Dado que el empleado ha iniciado sesión<br>Cuando vuelva a la aplicación sin cerrar sesión <br>Entonces su sesión es válida y sigue conectado<br><br>Escenario: Cerrar sesión manually<br>Dado que un empleado tiene la sesión iniciada<br>Cuando quiera cerrar sesión,<br>Entonces la sesión es cerrada.</td>
  </tr>
</table>


<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US36</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">empleado</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">2</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Seguridad de acceso y protección de la información</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Funcionalidad de Cierre de Sesión Seguro</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como empleado, quiero cerrar sesión de forma segura en la aplicación para que mi sesión finalice por completo y no pueda ser reutilizada por terceros no autorizados.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Cierre de Sesión<br><br>Escenario: Finalizar la sesión<br>Dado que el empleado se encuentra en la aplicación móvil,<br>Cuando cierra sesión, <br>Entonces la sesión es cerrada<br>y se eliminan todas las autenticaciones<br><br>Escenario: Redirigir al inicio de sesión después de cerrar sesión<br>Dado que el empleado se encuentra en la aplicación móvi,<br>Cuando cierra sesión correctamente,<br>Entonces se redirige al inicio de sesión.</td>
  </tr>
</table>
<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US37</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">desarrollador</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">2</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Seguridad de acceso y protección de la información</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Invalidar tokens y borrar metadatos de sesión al cerrar sesión</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como desarrollador, quiero implementar un mecanismo de cierre de sesión que invalide los tokens de actualización y borre los metadatos de sesión para mejorar la seguridad</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Invalidar tokens de actualización y metadatos de sesión<br><br>Escenario: Invalidar tokens de actualización al cerrar sesión<br><br>Dado que un empleado se encuentra con su sesión iniciada,<br>Cuando cierra sesión,<br>Entonces se elimina el token de actualización<br><br>Escenario: Eliminar metadatos de sesión<br><br>Dado que un empleado se encuentra con su sesión iniciada,<br>Cuando cierra sesión,<br>Entonces se eliminan los metadatos de sesión<br><br>Escenario: Rechazar la reutilización de tokens<br><br>Dado que un empleado ha cerrado sesión, <br>Cuando usa un token previamente invalidado<br>Entonces se deniega la solicitud</td>
  </tr>
</table>





<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US38</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">desarrollador</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">2</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Seguridad de acceso y protección de la información</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Implementar autenticación segura con JWT y cifrado de contraseñas</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como desarrollador, quiero implementar un endpoint de autenticación y emitir JWT firmados con gestión de expiración, para que se puedan establecer sesiones de empleados seguras.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Autenticación segura con JWT y cifrado de contraseñas<br>Escenario: Validar las credenciales del empleado de forma segura<br>Dado que un empleado realiza una solicitud de inicio de sesión con correo electrónico y contraseña,<br>Cuando se confirma la solicitud utilizando un algoritmo hash seguro,<br>Entonces solo se permite el inicio de sesión si las credenciales coinciden.<br>Escenario: Gestionar credenciales no válidas<br>Dado que un empleado proporciona un correo electrónico o contraseña incorrectos,<br>Cuando intenta autenticarse,<br>Entonces se devuelve una respuesta no autorizada y no se emite ningún token.<br>Escenario: Forzar la expiración del token<br>Dado que se emite un JWT con un tiempo de expiración definido,<br>Cuando el token se usa más allá de su validez,<br>Entonces se rechaza por caducado y se solicita al usuario que inicie sesión de nuevo.</td>
  </tr>
</table>
<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US39</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">desarrollador</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">2</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Seguridad de acceso y protección de la información</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Representación de navegación y acciones basada en roles.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como desarrollador, quiero ver los elementos de navegación según los roles autenticados, para que los empleados solo vean las secciones a las que están autorizados a acceder.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Navegación basada en roles<br>Escenario: Solo acciones permitidas por roles<br>Dado que un empleado se autentica con un rol,<br>Cuando accede a la aplicación móvil,<br>Entonces sólo son visibles las acciones configuradas para ese rol, y no se muestran las acciones restringidas.<br>Escenario: Las rutas no autorizadas están protegidas<br>Dado que un empleado se autentica con un rol,<br>Cuando navega a una ruta no permitida para su rol,<br>Entonces se le redirige a una vista permitida para su rol.</td>
  </tr>
</table>

---

<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US40</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Equipo Fudi</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">2</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Notificaciones</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Investigar la Integración de Firebase Cloud Messaging para Notificaciones en la Plataforma Fudi</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como equipo de desarrollo de Fudi, quiero investigar y prototipar la integración de Firebase Cloud Messaging (FCM) para el envío de notificaciones push a las aplicaciones móviles, para entender los requisitos técnicos, los costos, las limitaciones y el esfuerzo necesario para implementar esta funcionalidad de manera robusta y escalable.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Investigar la Documentación de FCM:<br><br>Dado que el equipo necesita entender las capacidades de FCM para notificaciones push en Android,<br>Cuando el desarrollador revise la documentación oficial de FCM (API, límites, mejores prácticas),<br>Entonces deberá documentar los pasos clave para la configuración, los tipos de notificaciones soportadas y las limitaciones (ej: tamaño de payload, tasa de envío).<br><br>Integrar FCM en la Aplicación Móvil (Kotlin):<br><br>Dado que la app móvil debe recibir notificaciones,<br>Cuando el desarrollador integre el SDK de FCM en la app Android (Kotlin) y implemente la lógica para recibir y mostrar notificaciones,<br>Entonces deberá verificar que la app pueda registrar un token único de dispositivo y recibir notificaciones de prueba desde la consola de Firebase<br><br>Implementar el Envío desde el Backend (Spring Boot):<br><br>Dado que el backend debe enviar notificaciones,<br>Cuando el desarrollador implemente un servicio en Spring Boot que utilice la API HTTP de FCM o el Admin SDK de Firebase,<br>Entonces deberá enviar una notificación de prueba a un dispositivo específico usando el token de dispositivo registrado.</td>
  </tr>
</table>


<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US41</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">gerente</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">2</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Gestión de compañía</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Registro de nueva compañía</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como gerente, quiero registrar mi compañía en la plataforma para empezar a gestionar la comunicación de mi equipo.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Escenario: Registro exitoso de una nueva compañía  Dado que un representante legal accede al formulario de registro, Cuando ingresa un Nombre Legal, un RUC de 11 dígitos no registrado y carga un Logo , Entonces el sistema crea la Company y asigna automáticamente el rol de Manager al usuario.<br><br>Escenario: Validación de RUC duplicado  Dado que una compañía ya está registrada en la plataforma con un RUC específico, Cuando otro usuario intenta registrar una nueva Company con ese mismo RUC, Entonces el sistema muestra un mensaje de error indicando que la organización ya existe.</td>
  </tr>
</table>



<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US42</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">gerente</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">2</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Gestión de Company</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Edición de perfil de compañía</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como gerente, quiero actualizar la información de mi compañía (logo, nombre, dirección) para que los empleados identifiquen la marca.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Escenario: Actualización de datos básicos y logo  Dado que un Manager está en el panel de configuración de su compañía, Cuando modifica la Dirección Física y sube un nuevo Logo, Entonces el sistema guarda los cambios y los refleja inmediatamente en la interfaz de todos los empleados.</td>
  </tr>
</table>



<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US43</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">gerente</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">2</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Gestión de Company</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Baja del servicio de compañía</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como gerente, quiero poder desactivar la cuenta de mi compañía para que toda la información y acceso de los empleados sea revocado.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Escenario: Confirmación de seguridad para eliminación  Dado que un Manager solicita dar de baja su compañía, Cuando el sistema pide la palabra de seguridad "ELIMINAR" y el usuario la ingresa correctamente, Entonces la cuenta cambia a estado inactivo.<br><br>Escenario: Revocación inmediata de accesos  Dado que una compañía ha sido dada de baja, Cuando cualquier empleado intenta realizar una acción en la app (como leer un anuncio), Entonces el sistema invalida su sesión y lo redirige al login con un mensaje de cuenta desactivada.<br><br>Escenario: Protección de datos post-baja  Dado que el estado de una compañía es "Inactive", Cuando se intenta realizar una petición API a sus recursos (chats o eventos), Entonces el servidor responde con un error 403 Forbidden.</td>
  </tr>
</table>



<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US44</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">gerente</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">2</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Gestión de Company</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Registro de empleados por compañía</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como gerente, quiero registrar nuevos empleados vinculándolos automáticamente a mi compañía para que tengan acceso al entorno privado.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Escenario: Registro individual de empleado  Dado que un Manager desea agregar un nuevo colaborador, Cuando ingresa el Nombre, DNI y Correo, Entonces el sistema vincula al empleado al company del Manager automáticamente.<br><br>Escenario: Validación de correo duplicado en la empresa  Dado que un empleado ya existe en la compañía, Cuando el Manager intenta registrar a otra persona con el mismo correo electrónico, Entonces el sistema impide el registro para evitar duplicidad de cuentas.</td>
  </tr>
</table>




<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US45</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">gerente</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">2</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Gestión de Company</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Eliminación de miembros de la compañía</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como gerente, quiero desvincular a un empleado de mi compañía para que ya no pueda acceder a los anuncios, chats o eventos privados.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Escenario: Desvinculación de empleado (Borrado Lógico)  Dado que un Manager decide eliminar a un miembro del equipo, Cuando confirma la acción en el panel de control, Entonces el estado del empleado cambia a "Terminated" pero se conserva su historial de lectura de anuncios.<br><br>Escenario: Cese de notificaciones  Dado que un empleado ha sido desvinculado, Cuando la Company publica un nuevo Announcement prioritario, Entonces el sistema no genera ni envía ninguna notificación push a dicho usuario.</td>
  </tr>
</table>



<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">US46</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">gerente</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">3</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Gestión de Company</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Panel de control corporativo</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como gerente corporativo, quiero visualizar un dashboard con el progreso y las métricas de mis empleados, para medir la participación y el uso de la plataforma.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Panel corporativo<br><br>Escenario: Visualización de métricas<br>Dado que el gerente accede al panel corporativo,<br>Cuando ingresa a la pestaña de estadísticas,<br>Entonces puede ver la cantidad total de eventos asistidos, mensajes enviados y nivel de participación de su equipo.</td>
  </tr>
</table>
<br>

## 3.3. Impact Mapping.

<p style="text-indent: 1.25cm;">El Impact Mapping es una técnica de planificación estratégica que conecta los objetivos de negocio (Business Goals) con las acciones de desarrollo a través de cuatro preguntas clave: ¿POR QUÉ? (objetivo), ¿QUIÉN? (personas involucradas), ¿CÓMO? (impactos en su comportamiento) y ¿QUÉ? (entregables software). Este ejercicio asegura que cada funcionalidad desarrollada esté alineada directamente con las metas del negocio.

***1. Business Goals (¿POR QUÉ?)***

Definimos dos objetivos principales, cada uno enfocado en un segmento usuario específico:

- **Business Goal 1:** Enfocado en gerentes. El objetivo es cuantificable (80% de adopción), medible (uso como canal principal) y con un timeframe claro (6 meses). Esto asegura que la herramienta se convierta en el estándar para la comunicación formal descendente.
- **Business Goal 2:** Enfocado en empleados. El objetivo es igualmente medible (70% de uso diario) y critical para el éxito general, ya que la herramienta debe ser adoptada masivamente para reemplazar canales informales como WhatsApp. La métrica "diariamente" es clave para medir el engagement real.

***2. Personas (¿QUIÉN?)***

<p style="text-indent: 1.25cm;">Identificamos a los actores principales cuyo comportamiento debemos influir para lograr los objetivos. Son los mismos segmentos objetivo definidos en el Lean UX Canvas:

- **Gerentes:** Tomadores de decisión que necesitan control y visibilidad.
- **Empleados:** Usuarios finales que necesitan simplicidad y utilidad en su día a día.

***3. Impacts (¿CÓMO?)***

<p style="text-indent: 1.25cm;">Para cada objetivo, definimos los cambios de comportamiento específicos que debemos lograr en las personas:

* **Para Gerentes (Goal 1):**

  - **Impact 1.1:** Cambiar el hábito de publicar anuncios en emails o WhatsApp hacia Centralis. Esto resuelve el problema de la falta de trazabilidad.
  - **Impact 1.2:** Centralizar la planificación de eventos en una sola herramienta. Esto resuelve el problema de la descoordinación.

* **Para Empleados (Goal 2):**

  - **Impact 2.1:** Convertir a Centralis en la fuente principal de información corporativa. Esto resuelve el problema de la información dispersa.
  - **Impact 2.2:** Migrar las conversaciones de trabajo de apps personales a Centralis. Esto resuelve el problema de la falta de separación vida laboral/personal.

***4. Deliverables (¿QUÉ?)***

<p style="text-indent: 1.25cm;">Son las funcionalidades específicas que debemos construir para generar los impacts deseados. Cada deliverable es una respuesta directa a un "Cómo".

- **Para Impact 1.1:** No basta con un muro de anuncios. Se necesita confirmación de lectura para generar confianza en el canal y un panel de control para demostrar el valor al gerente.
- **Para Impact 1.2:** La creación de eventos debe ir acompañada de recordatorios automáticos para ser efectiva y de integración con calendarios para reducir la fricción de uso.
- **Para Impact 2.1:*+ La información debe llegar al empleado de forma proactiva via notificaciones push y debe ser fácil de encontrar en una interfaz intuitiva.
- **Para Impact 2.2:** Los chats grupales deben estar bien organizados para ser útiles, y el historial permanente es un advantage clave sobre WhatsApp (donde los mensajes pueden perderse).

**5. User Stories**

<p style="text-indent: 1.25cm;">Cada deliverable se traduce en una o más user stories que el equipo de desarrollo puede priorizar, estimar y implementar. Las user stories aquí presentadas son el nivel más granular del mapa, conectando directamente la necesidad del usuario con una funcionalidad técnica.

**Figura 14**

*Impact Mappping*

<p align="center">
  <img src="https://res.cloudinary.com/dpprgycup/image/upload/v1757951834/Impact_map_bxfo1g.png" alt="Class Diagram">
</p>
*Nota.* Elaboración propia. Link: https://shorturl.at/6ucAR

## 3.4. Product Backlog.

<p align="center">
  <img src="https://i.imgur.com/LKaqcfW.png" alt="Class Diagram">
</p>

Link del tablero en Trello: https://goo.su/iCaq6


| N°   | StoryID | Título                                                       | Story Points |
| ---- | ------- | ------------------------------------------------------------ | ------------ |
| 1    | US01    | Cambiar el idioma de la landing page                         | 3            |
| 2    | US02    | Sección About de la landing page                             | 3            |
| 3    | US03    | Historia de la startup                                       | 3            |
| 4    | US04    | Sección FAQ                                                  | 3            |
| 5    | US05    | Sección Team                                                 | 3            |
| 6    | US06    | Links profesionales del equipo                               | 3            |
| 7    | US07    | Compatibilidad con múltiples dispositivos                    | 3            |
| 8    | US08    | Acceso a Centralis desde la landing page                     | 2            |
| 9    | US09    | Navegación Accesible                                         | 3            |
| 10    | US10    | Publicación básica de anuncios                               | 8            |
| 11    | US11    | Priorización de anuncios                                     | 5            |
| 12    | US12    | Edición de anuncios                                          | 5            |
| 13    | US13    | Eliminación de anuncios                                      | 3            |
| 14    | US14    | Confirmaciones de lectura                                    | 5            |
| 15    | US15    | Comentarios en anuncios                                      | 5            |
| 16    | US16    | Subir imágenes en anuncios                                   | 5            |
| 17    | US17    | Visualizar imágenes en anuncios                              | 5            |
| 18    | US18    | Creación básica de eventos                                   | 8            |
| 19    | US19    | Cancelación de eventos                                       | 3            |
| 20    | US20    | Modificación de eventos                                      | 3            |
| 21    | US21    | Eventos prioritarios                                         | 3            |
| 22    | US22    | Métricas de participación                                    | 5            |
| 23    | US23    | Creación de chats grupales                                   | 5            |
| 24    | US24    | Eliminar grupos de chats                                     | 5            |
| 25    | US25    | Envío de mensajes                                            | 3            |
| 26    | US26    | Eliminación de mensajes enviados                             | 5            |
| 27    | US27    | Modificación de mensajes enviados                            | 3            |
| 28    | US28    | Eliminación de chats grupales por gerentes                   | 3            |
| 29    | US29    | Listado organizado de chats                                  | 3            |
| 30    | US30    | Enviar imágenes en chats grupales                            | 3            |
| 31    | US31    | Eliminar imágenes enviadas en el chat                        | 3            |
| 32    | US32    | Visualizar imágenes en chats                                 | 3            |
| 33    | US33    | Validar y almacenar datos cifrados de usuario al registrarse | 2            |
| 34    | US34    | Restringir el acceso a la API                                | 3            |
| 35    | US35    | Mantener la sesión iniciada                                  | 5            |
| 36    | US36    | Funcionalidad de Cierre de Sesión Seguro                     | 2            |
| 37    | US37    | Invalidar tokens y borrar metadatos de sesión al cerrar sesión | 2            |
| 38    | US38    | Implementar autenticación segura con JWT y cifrado de contraseñas | 2            |
| 39    | US39    | Representación de navegación y acciones basada en roles.     | 2            |
| 40    | US40    | Investigar la Integración de Firebase Cloud Messaging para Notificaciones en la Plataforma Fudi | 8            |
| 41    | US41    | Registro de nueva compañía                                   | 3            |
| 42    | US42    | Edición de perfil de compañía                                | 3            |
| 43    | US43    | Baja del servicio de compañía                                | 3            |
| 44    | US44    | Registro de empleados por compañía                           | 3            |
| 45    | US45    | Eliminación de miembros de la compañía                       | 3            |
| 46    | US46    | Panel de control corporativo                                 | 8            |

