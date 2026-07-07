# Conclusiones

**TB1:**

<p style="text-indent: 1.25cm;">El equipo de desarrollo "Fudi", materializado en la plataforma Centralis, ha demostrado ser una respuesta efectiva y técnicamente sólida a la fragmentación de la comunicación interna en las PYMES. A través de un enfoque iterativo, se validó la necesidad crítica de centralizar anuncios, eventos y chats en un entorno profesional que separe la vida laboral de la personal. Este proceso permitió que la arquitectura, basada en Domain-Driven Design (DDD), evolucionara desde la identificación de *bounded contexts* (Announcement, Event, Chat, Profile y la incorporación de Company) hasta convertirse en una solución modular y desacoplada, preparada para gestionar múltiples organizaciones de forma independiente.  

<p style="text-indent: 1.25cm;">Desde la perspectiva tecnológica, la transición hacia una aplicación *cross-platform* en Flutter garantizó una experiencia de usuario unificada bajo los estándares de Material Design 3, asegurando la consistencia visual tanto para gerentes como para empleados. La implementación de un modelo de datos robusto permitió la segregación de la información mediante el concepto de Company, donde cada entidad legal posee su propia configuración, usuarios y flujos de comunicación aislados. El uso de Spring Boot para el backend y PostgreSQL para la persistencia de datos facilitó la creación de una infraestructura escalable que soporta el crecimiento de diversas empresas dentro de un mismo ecosistema tecnológico.  
<p style="text-indent: 1.25cm;">En términos de valor de negocio, el cumplimiento de los hitos permitió entregar funcionalidades avanzadas, incluyendo la gestión administrativa de la Company, sistemas de confirmación de lectura en anuncios y la organización logística de eventos. La incorporación de herramientas de moderación y dashboards para el rol de Gerente refuerza la capacidad de control y trazabilidad de la comunicación corporativa. En conclusión, el proyecto no solo cumple con los requisitos funcionales actuales, sino que sienta las bases para una solución escalable capaz de integrar múltiples organizaciones bajo un modelo de software como servicio (SaaS) altamente eficiente. </p>

​    

**TP:** 

<p style="text-indent: 1.25cm;">El proceso de desarrollo de Centralis comenzó con una base sólida de investigación y diseño orientado al usuario, lo que permitió a la startup Fudi identificar con precisión los problemas de comunicación en las PyMEs locales. Mediante la aplicación de metodologías como Lean UX y el diseño de artefactos como User Personas y User Stories, el equipo logró establecer un Product Backlog priorizado que sirvió como hoja de ruta ética y profesional para el resto del ciclo de vida del proyecto.

<p style="text-indent: 1.25cm;">En la fase de diseño y arquitectura, la implementación de las Style Guidelines y el diseño de prototipos de alta fidelidad aseguraron una experiencia de usuario coherente y profesional, basada en el lenguaje visual de Material Design 3. La definición técnica de la arquitectura mediante el modelo C4 y diagramas de componentes facilitó la construcción de una solución robusta y escalable, garantizando que el sistema sea capaz de gestionar anuncios, eventos y chats bajo un esquema de aislamiento multi-tenancy.

<p style="text-indent: 1.25cm;">La etapa de implementación técnica marcó un hito crítico al desplegar exitosamente la Landing Page en Vercel y el Web Service en Render, utilizando tecnologías de alto rendimiento como Astro y Java Spring Boot. Se completaron las funcionalidades core de la aplicación móvil nativa en Flutter, incluyendo la gestión dinámica de anuncios y la agenda de eventos corporativos, asegurando que la herramienta esté operativa y accesible para los colaboradores en un entorno de producción real.

<p style="text-indent: 1.25cm;">Finalmente, la validación del sistema se consolidó a través de una rigurosa suite de pruebas que cubrió todos los niveles de la arquitectura. Se ejecutaron con éxito Unit Tests e Integration Tests en el backend y el entorno móvil, verificando flujos transaccionales y de seguridad críticos. Además, el uso de herramientas avanzadas como Patrol para los Core System Tests permitió confirmar que la interacción de extremo a extremo entre los dispositivos móviles y los servicios en la nube es fluida, garantizando una solución de ingeniería de software confiable, transparente y de alto impacto organizacional.


**TB2:** 

<p style="text-indent: 1.25cm;">La exitosa corrección técnica del flujo de DevOps y la incorporación del enfoque de Experiment-Driven Development (Desarrollo Guiado por Experimentos) han permitido al equipo establecer una infraestructura de despliegue continuo altamente eficiente. Esta optimización no solo asegura una entrega de software más ágil y automatizada, sino que también introduce una metodología científica para validar nuevas funcionalidades mediante experimentos controlados, mitigando los riesgos técnicos antes de su liberación en el entorno de producción.

<p style="text-indent: 1.25cm;">La actualización y ampliación exhaustiva de las suites de pruebas —abarcando los niveles Unitario, de Integración y de Sistema (Core System Tests)— garantizan la robustez estructural y la estabilidad operativa de la plataforma. Al documentar formalmente estos componentes, se ha fortalecido la trazabilidad del código y se ha establecido una red de seguridad técnica indispensable para sostener el crecimiento del sistema, minimizando la aparición de regresiones o fallos en las funcionalidades críticas de la aplicación móvil.

<p style="text-indent: 1.25cm;">La ejecución de la auditoría de experiencias de usuario, respaldada por la evaluación de heurísticas y el análisis de las entrevistas de validación, ha sido fundamental para identificar fricciones operativas en el ecosistema móvil. A través de este diagnóstico, plasmado formalmente en la Sección 6.4 del informe, el equipo logró ejecutar correcciones de interfaz precisas y centradas en el usuario, elevando significativamente los estándares de usabilidad, accesibilidad y fluidez de la aplicación de cara a su despliegue definitivo.
<p style="text-indent: 1.25cm;">El registro, edición y consolidación sistemática del material audiovisual correspondiente a las entrevistas de validación aportaron el sustento empírico necesario para legitimar las decisiones de diseño e ingeniería adoptadas por el equipo. La sincronización entre las actividades de validación heurística, la documentación técnica y la configuración de infraestructura refleja un alto nivel de madurez organizativa y un esfuerzo colaborativo cohesionado, logrando cumplir de manera integral con los objetivos de calidad exigidos para esta fase del proyecto.


   **TF:**     

<p style="text-indent: 1.25cm;">En esta entrega final , se consolidó la implementación e integración de todas las características clave de la plataforma Centralis, logrando un prototipo completamente funcional de extremo a extremo. Esto incluyó la adición de la redirección al botón de descarga en la Landing Page, la confirmación interactiva y reactiva de asistencia a eventos en la aplicación móvil, la asignación dinámica de miembros del equipo con sincronización reactiva, y la exposición de endpoints robustos para la lógica de negocios y streaming analítico en tiempo real mediante SSE en el backend.</p>

<p style="text-indent: 1.25cm;">La adopción de la metodología de Experiment-Driven Development permitió validar empíricamente cada una de las hipótesis planteadas en el Question Backlog. Los resultados cuantitativos medidos manualmente durante las sesiones de prueba de usabilidad y los pilotos con participantes reales evidenciaron un cumplimiento del 100% de los criterios de éxito establecidos para las métricas de dominio. Características críticas como la reactividad de la UI y la reserva de salas libre de colisiones  registraron un éxito absoluto, lo que condujo al rechazo de las hipótesis nulas y al soporte científico de las hipótesis de trabajo.</p>

<p style="text-indent: 1.25cm;">Asimismo, las entrevistas estructuradas de validación aportaron una rica retroalimentación cualitativa que legitima las decisiones de diseño heurístico y de interfaz. Los usuarios destacaron la practicidad de contar con notificaciones de asistencia y lectura en una sola tarjeta integrada, y valoraron especialmente la separación de las comunicaciones formales de canales cotidianos como WhatsApp. Esta separación no solo redujo la sobrecarga cognitiva y eliminó el spam visual gracias a la restricción jerárquica de permisos, sino que también aumentó significativamente el foco de los empleados y la velocidad de lectura de anuncios urgentes.</p>

<p style="text-indent: 1.25cm;">Por último, el establecimiento del workflow de aprendizaje continuo y la formalización de las Learning Cards estructuradas en el reporte permitieron documentar de manera profesional las lecciones clave de cada hipótesis y definir un plan de acción concreto para la estabilización y consolidación final del código. Este proceso demuestra que Centralis ha madurado hasta convertirse en una solución de ingeniería de software confiable, probada y centrada en el usuario, sentando una línea base metodológica y técnica que garantiza la sostenibilidad del producto en futuras expansiones académicas o profesionales.</p>



# Video App Validation

<p style="text-indent: 1.25cm;">El video de validación de la aplicación Video App Validation constituye una evidencia empírica fundamental del Trabajo Final del proyecto Centralis. Este material audiovisual consolida las sesiones de pruebas de usabilidad y entrevistas estructuradas realizadas con los participantes de los segmentos objetivo. En el video se puede observar de forma directa la interacción de los usuarios con las características experimentales implementadas, tales como la confirmación de asistencia con un solo clic, la visualización progresiva de analíticas en tiempo real (SSE) y la reserva interactiva de salas sin conflictos de ocupación.</p>

<p style="text-indent: 1.25cm;">El propósito del video es documentar de manera transparente la validación de las hipótesis de usabilidad y la respuesta cualitativa de los participantes, quienes expresaron sus testimonios y apreciaciones sobre la reducción de la sobrecarga de información y el desorden visual en comparación con herramientas de mensajería informal de uso diario. A continuación se incluye una captura de pantalla del video y el enlace directo para su reproducción en línea:</p>

<img src="https://i.imgur.com/9PRKrZO.png" width="450">

Link del video Validation Interviews: https://shorturl.at/RSCEz

# Video About-The-Team

El proceso de ingeniería de software y gestión DevOps no solo se valida a través del correcto funcionamiento de la arquitectura tecnológica, sino también mediante el crecimiento, la sinergia y el aprendizaje técnico consolidado por el equipo de desarrollo a lo largo de las fases de construcción del producto. Con este propósito, se ha elaborado el recurso audiovisual **"About-the-Team Video"**, un material de cierre que recopila el testimonio directo de los ingenieros detrás de **Centralis**, exponiendo la evolución metodológica del equipo durante el desarrollo del ecosistema móvil.

Link About-The-Team: https://shorturl.at/adFLr

<img src="https://i.imgur.com/Inj7ob0.png" width="450">



# Bibliografía 

* Evans, E. (2003). *Domain-Driven Design: Tackling Complexity in the Heart of Software*. Addison-Wesley Professional.

* Vernon, V. (2013). *Implementing Domain-Driven Design*. Addison-Wesley.

* Fowler, M. (2002). *Patterns of Enterprise Application Architecture*. Addison-Wesley.

* Richardson, C. (2018). *Microservices Patterns: With examples in Java*. Manning Publications.

* Render postgresql. (2023). *Render postgresql Documentation*. https://render.com/docs/postgresql

* Google. (2023). *Firebase Cloud Messaging Documentation*. https://firebase.google.com/docs/cloud-messaging

* Schwaber, K., & Sutherland, J. (2020). *The Scrum Guide*. https://scrumguides.org/

* Cohn, M. (2004). *User Stories Applied: For Agile Software Development*. Addison-Wesley.

* Gamma, E., Helm, R., Johnson, R., & Vlissides, J. (1994). *Design Patterns: Elements of Reusable Object-Oriented Software*. Addison-Wesley.

* Martin, R. C. (2008). *Clean Code: A Handbook of Agile Software Craftsmanship*. Prentice Hall.



# Anexos

Link del tablero en Trello: https://goo.su/iCaq6

Lean UX Canvas  https://acortar.link/7r4p4d

User Persona: https://acortar.link/gN7rnw

Diagrama Journey Mapping : https://acortar.link/E1OgkX

As-is Scenario Mapping: https://i.imgur.com/9JcFOZH.png

To-Be Scenario Mapping: https://i.imgur.com/TCNr03W.png

Link del prototipo mobile: https://shorturl.at/Fy7KA

Link Validation Interviews: https://shorturl.at/RSCEz

Link About the Product: https://shorturl.at/Br5Fg

Link About-The-Team: https://shorturl.at/adFLr

Link de la landing page: https://landing-page-rmy9.vercel.app/en

Link del web service: https://web-service-1mm7.onrender.com/swagger-ui/index.html
