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


# Video App Validation



# Video About-The-Team



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

Link Validation Interviews: https://shorturl.at/gH7kO
