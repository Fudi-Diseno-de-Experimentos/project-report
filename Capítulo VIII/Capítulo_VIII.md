# Capítulo VIII: Experiment-Driven Development

## 8.1. Experiment Planning

### 8.1.1. As-Is Summary

Esta sección consolida la información cualitativa y el material bruto recopilado a partir de las sesiones de validación e interacción con los segmentos objetivos (*Gerentes y Empleados*). El propósito de este bloque no es el diseño inmediato de soluciones técnicas, sino la identificación estructurada de los puntos de partida metodológicos, permitiendo transformar el comportamiento y las observaciones de los usuarios en preguntas de investigación y premisas científicas sujetas a experimentación.

Asimismo, se identifica una problemática operativa adicional en la gestión de eventos corporativos: la falta de centralización en la reserva de espacios físicos internos. Los gerentes actuales coordinan la ubicación de reuniones, capacitaciones y actividades a través de canales informales (mensajes de texto, correos dispersos o verbalmente), lo que genera conflictos de ocupación, duplicación de reservas y pérdida de trazabilidad logística. Esta desarticulación evidencia la necesidad de experimentar con un mecanismo integrado dentro de la creación de eventos que permita asignar formalmente espacios corporativos como laboratorios, oficinas, salas de reuniones, auditorios y áreas comunes.

### 8.1.2. Raw Material: Assumptions, Knowledge Gaps, Ideas, Claims

A partir de las auditorías de experiencia de usuario realizadas, se ha clasificado la materia prima del proyecto en cuatro ejes fundamentales para guiar el diseño de experimentos:

- **Ideas (Propuestas para resolver un problema):**
  - *Automatización de la Sincronización Reactiva (State Management):* Implementar un mecanismo de actualización en tiempo real o reactivo en el árbol de widgets de la aplicación Flutter. Esto evitaría que el usuario deba adivinar o recordar ejecutar un gesto de deslizamiento manual (*pull-to-refresh*) en vistas externas para actualizar la lista de miembros elegibles. El experimento asociado no debe evaluar la animación del indicador, sino validar si la persistencia automática erradica las acciones innecesarias de refresco manual al estructurar eventos corporativos.
  - *Inclusión de Confirmación Binaria de Asistencia:* Añadir un componente interactivo de respuesta (*Aceptar/Rechazar asistencia*) en la vista del empleado para los eventos asignados. El objetivo de evaluar esta premisa es verificar si el flujo de retroalimentación bidireccional mejora la predictibilidad logística de la gerencia en la organización de actividades corporativas.
  - *Reserva de Espacios Físicos Corporativos:* Integrar un módulo de selección y asignación de espacios físicos internos (laboratorios, oficinas, salas de reuniones, auditorios y áreas comunes) dentro del flujo de creación de eventos en la aplicación móvil. El experimento busca validar si la centralización de la reserva de espacios reduce los conflictos de ocupación, elimina la dependencia de canales informales (mensajes de texto o verbal) y mejora la puntualidad de los empleados al conocer de forma precisa la ubicación física de la actividad.
- **Claims (Afirmaciones de los Usuarios):**
  - *"WhatsApp no constituye un canal formal ni seguro para el flujo corporativo":* Los gerentes y empleados afirman de manera categórica que las herramientas de mensajería comercial tradicionales provocan pérdidas críticas de información y carecen de gobernanza de datos.
  - *"El control analítico por perfil es una necesidad operativa legítima y no una transgresión de la privacidad":* Los administradores certifican que auditar el historial de lecturas a nivel laboral es indispensable para garantizar la alineación del equipo, siempre y cuando los datos se limiten estrictamente a cuentas corporativas y no expongan registros personales como el número telefónico privado.
  - *"Dejar la publicación de anuncios globales abierta a todo el personal generará sobrecarga de información y desorden":* Ambos gerentes afirman que un canal sin restricciones jerárquicas saturará la pantalla principal de la aplicación móvil, afectando la visibilidad de los comunicados de alta prioridad.
  - *"La coordinación de espacios físicos para eventos mediante canales informales genera conflictos de ocupación y retrasa la productividad":* Los gerentes afirman que, al no contar con un sistema centralizado de reserva, es frecuente encontrar dos eventos programados en el mismo laboratorio u oficina, o que los empleados lleguen al lugar equivocado porque la comunicación de la ubicación se perdió en el chat informal.
- **Assumptions (Suposiciones del Equipo):**
  - *Suposición de Disponibilidad Inmediata:* El equipo asumió que por el hecho de ser una solución unificada 100% móvil, los usuarios tolerarían tiempos de carga asíncronos prolongados en módulos complejos. Sin embargo, la congelación momentánea de la interfaz (*"quedarse cargando"*) demostró que la tolerancia del usuario móvil a la latencia de procesamiento de las analíticas desde la tarjeta del anuncio es sumamente baja. Dado que el equipo opera bajo planes gratuitos de Render y Supabase y no puede escalar la infraestructura backend, la mejora debe enfocarse en el cliente móvil mediante técnicas de renderizado progresivo (SSE) para mitigar la percepción de bloqueo.
  - *Suposición de la Dirección del Flujo:* Se asumió que el flujo de eventos era unidireccional (la gerencia agenda y notifica, y el empleado simplemente acata). La observación del usuario demostró que la audiencia objetivo asume intrínsecamente que un "evento" requiere un mecanismo de confirmación activa de asistencia para ser considerado funcional.
  - *Suposición de la Irrelevancia de la Ubicación Física:* El equipo asumió inicialmente que la ubicación del evento era un dato secundario que podía comunicarse de forma informal sin impactar la experiencia. Sin embargo, las sesiones de validación revelaron que tanto gerentes como empleados perciben la falta de un campo formal para asignar espacios físicos (laboratorios, oficinas, salas de reuniones, auditorios y áreas comunes) como una brecha crítica que causa incertidumbre logística y retrasa la confirmación de asistencia.
- **Knowledge Gaps (Brechas de Conocimiento):**
  - *Permisología de Publicación Óptima:* El equipo desconoce cuál es el número máximo tolerable de usuarios con permisos de publicación global en una organización de tamaño mediano (50 empleados) antes de que la pantalla principal degrade la experiencia de usuario.
  - *Causa Raíz de la Percepción de Latencia:* Existe una brecha técnica respecto a cuánto mejora la percepción de fluidez y la tasa de retención en la pantalla de analíticas al usar Server-Sent Events (SSE) para renderizado progresivo en Flutter, en comparación con una petición HTTP bloqueante tradicional que espera toda la respuesta antes de renderizar. El equipo no puede optimizar el backend en Render (plan gratuito), por lo que debe validar si el streaming de datos desde el cliente móvil es suficiente para reducir el abandono.
  - *Tasa de Adopción con Confirmación de Asistencia:* Carecemos de datos cuantitativos sobre cuántos empleados interactuarán activamente con un botón de confirmación de asistencia en comparación con el simple acto pasivo de recibir la notificación del evento.
  - *Catálogo y Demanda de Espacios Físicos:* El equipo desconoce el volumen y la tipología de espacios físicos que una PyME gestiona habitualmente, así como la frecuencia de uso de cada tipo (laboratorios, oficinas, salas de reuniones, auditorios y áreas comunes). 



### 8.1.3. Experiment-Ready Questions

Esta sección define el cuestionario científico e instructivo que guiará el diseño de los experimentos de la plataforma **Centralis**. Para asegurar un enfoque riguroso, se utiliza la matriz inicial de *The 5 W’s and 2 H’s* del planteamiento del problema como un marco de contraste frente al comportamiento real de las usuarias en los entornos de producción, mapeando premisas ocultas y convirtiéndolas en variables medibles.

**Preguntas Impulsadas por Creencias (Belief-led Questions)**

Estas preguntas buscan someter a prueba las suposiciones preexistentes del equipo de ingeniería y las afirmaciones categóricas recolectadas en las sesiones de validación respecto al valor del producto:

- **Basada en el "Who" (Stakeholders) y "Why" (Seguridad frente a WhatsApp):**
  - *Pregunta:* ¿Cómo afecta la migración de un canal informal (WhatsApp) a un entorno unificado 100% móvil en la tasa de lectura de los comunicados urgentes por parte de los empleados?
  - *Premisa a probar:* Se cree que al tener los colaboradores el dispositivo móvil permanentemente a la mano, un entorno corporativo dedicado incrementa la tasa de lectura y recepción de comunicados sin vulnerar su privacidad al usar identidades exclusivamente corporativas.
- **Basada en el "What" (Estructura de Anuncios) y el riesgo de Spam:**
  - *Pregunta:* ¿En qué medida la restricción jerárquica de los permisos de publicación de anuncios globales reduce la sobrecarga de información y el desorden visual en la pantalla principal de la aplicación móvil?
  - *Premisa a probar:* Se asume que permitir que el 100% de los empleados publique anuncios globales degrada la priorización de comunicados críticos, siendo necesario limitar esta función a jefes de área o gerencias para mantener la cohesión.
- **Basada en el "How" (Desarticulación de Eventos) y la brecha de Asistencia:**
  - *Pregunta:* ¿De qué manera la inclusión de un mecanismo interactivo de confirmación binaria de asistencia (*Aceptar/Rechazar*) incrementa la predictibilidad logística de la gerencia en comparación con un flujo de notificación puramente pasivo y unidireccional?
  - *Premisa a probar:* Se cree que los coordinadores de las PyMEs requieren una confirmación activa del colaborador en la app móvil para mitigar los errores de ejecución y la duplicación de esfuerzos descritos en el diagnóstico inicial.
- **Basada en el "Where" (Ubicación Física del Evento) y la reserva de espacios:**
  - *Pregunta:* ¿De qué manera la inclusión de un selector de espacios físicos corporativos (laboratorios, oficinas, salas de reuniones, auditorios y áreas comunes) dentro del flujo de creación de eventos reduce los conflictos de ocupación y mejora la puntualidad logística de los empleados?
  - *Premisa a probar:* Se cree que al centralizar la asignación de espacios físicos en la misma plataforma donde se crea el evento, se eliminarán las duplicaciones de reserva y los empleados tendrán mayor certeza de la ubicación, incrementando la tasa de asistencia puntual y reduciendo la dependencia de canales informales para coordinar la logística interna.

**Preguntas Exploratorias (Exploratory Questions)**

Estas preguntas están orientadas a explorar y recopilar conocimiento cuantitativo en áreas técnicas y de comportamiento donde el equipo carece de datos previos:

- **Basada en el "When" (Efecto del renderizado en el cliente móvil):**
  - *Pregunta:* ¿En qué medida la implementación de Server-Sent Events (SSE) para el renderizado progresivo de analíticas en la app móvil reduce la tasa de abandono de la pantalla por parte del gerente, en comparación con una petición HTTP bloqueante tradicional?
- **Basada en el "How Much" (Acciones manuales e ineficiencia operativa):**
  - *Pregunta:* ¿En qué medida la sincronización reactiva de estados en la app móvil erradica la necesidad de realizar gestos de actualización manual (*pull-to-refresh*) por parte de los usuarios para reflejar los miembros asignables en una organización?
  - *Pregunta:* ¿Cuál es la tasa de adopción y el número promedio de mensajes diarios que registraría un canal de chat general informal exclusivo para empleados, en contraste con los grupos de chat formales pre-configurados y restringidos por la gerencia?

### 8.1.4. Question Backlog

Esta sección constituye el núcleo de gobernanza del proceso experimental. El Question Backlog organiza y prioriza las preguntas de investigación formuladas anteriormente en función de su nivel de incertidumbre, criticidad de negocio y riesgo técnico, asegurando que el esfuerzo de desarrollo se dirija a mitigar las suposiciones más vulnerables antes de construir código definitivo.

**Sistema de Puntuación y Priorización**

Para establecer un orden objetivo, cada pregunta del backlog se evalúa en una escala del 1 al 5 en cuatro criterios clave:

- **Confianza (Confidence):** Qué tanta certeza tiene el equipo sobre la respuesta (a menor certeza, mayor necesidad de experimentar).
- **Riesgo (Risk):** El peligro potencial para el producto o el negocio si la suposición subyacente resulta ser falsa.
- **Impacto (Impact):** El beneficio operativo o de valor para las PyMEs y la startup si se valida la hipótesis.
- **Interés (Interest):** La relevancia estratégica para los stakeholders y el equipo de ingeniería.

**Matriz del Question Backlog1**

A continuación, se presenta la lista priorizada de preguntas, justificando el **"Por qué"** de su experimentación para fundamentar el esfuerzo invertido:

| **ID** | **Pregunta de Investigación (Experiment-Ready)**             | **El "Por qué" (Motivación y Justificación)**                | **Conf. (1-5)** | **Riesgo (1-5)** | **Imp. (1-5)** | **Int. (1-5)** | **Total** |
| ------ | ------------------------------------------------------------ | ------------------------------------------------------------ | --------------- | ---------------- | -------------- | -------------- | --------- |
| **Q1** | ¿En qué medida la implementación de Server-Sent Events (SSE) para el renderizado progresivo de analíticas en la app móvil reduce la tasa de abandono de la pantalla, en comparación con una petición HTTP bloqueante tradicional? | **Crítico para la retención.** La mejora debe enfocarse en el cliente móvil. Si la interfaz se percibe congelada al esperar una respuesta bloqueante, el gerente abandonará la auditoría, destruyendo el valor del core analítico. | 2               | **5**            | 5              | 5              | **17**    |
| **Q2** | ¿En qué medida la restricción jerárquica de los permisos de publicación reduce la sobrecarga de información y el desorden visual en la pantalla móvil? | **Evitar degradación de la UX.** Si el feed global se satura de spam por falta de roles, los comunicados urgentes perderán visibilidad por completo. | 3               | **4**            | 5              | 4              | **16**    |
| **Q3** | ¿De qué manera la inclusión de un mecanismo de confirmación binaria de asistencia (*Aceptar/Rechazar*) incrementa la predictibilidad logística de la gerencia? | **Cierre de brecha de valor.** El usuario asume que un evento requiere respuesta activa; sin esto, el flujo es unidireccional e ineficiente. | 2               | **4**            | 4              | 4              | **14**    |
| **Q4** | ¿En qué medida la sincronización reactiva de estados en la app móvil erradica la necesidad de realizar gestos de actualización manual (*pull-to-refresh*) por parte de los usuarios? | **Optimización de flujos.** Mitiga la fricción heurística detectada donde el usuario debe forzar la actualización de miembros de forma manual en vistas externas para poder asignarlos. | 3               | **3**            | 4              | 4              | **14**    |
| **Q5** | ¿Cómo afecta la migración de WhatsApp a un entorno unificado móvil en la tasa de lectura de los comunicados urgentes? | **Validar el Core Business.** Justifica la existencia de Centralis frente a los canales informales del mercado de PyMEs. | 4               | **2**            | 5              | 4              | **15**    |
| **Q6** | ¿De qué manera la inclusión de un selector de espacios físicos corporativos (laboratorios, oficinas, salas de reuniones, auditorios y áreas comunes) dentro del flujo de creación de eventos reduce los conflictos de ocupación y mejora la puntualidad logística? | **Cierre de brecha logística.** Los gerentes y empleados reportan que la coordinación informal de espacios genera duplicaciones de reserva y retrasos. Sin un sistema centralizado, el valor del módulo de eventos permanece incompleto. | 3               | **4**            | 4              | 4              | **15**    |

### 8.1.5. Experiment Cards

En esta sección se formalizan los instrumentos de diseño experimental para las hipótesis de mayor criticidad y riesgo técnico identificadas en el *Question Backlog*. Cada tarjeta opera como un contrato científico que delimita el entorno de prueba, los indicadores clave de rendimiento (KPI) y los umbrales cuantitativos que determinarán si una suposición se consolida como característica definitiva en la arquitectura de producción de **Centralis** o si debe ser descartada.

Tarjeta de Experimento 1 (EX-01): Renderizado Progresivo de Analíticas con Server-Sent Events

| **Componente EDD**     | **Detalle y Especificación Técnica del Experimento**         |
| ---------------------- | ------------------------------------------------------------ |
| **Origen del Backlog** | **Q1:** ¿En qué medida la implementación de Server-Sent Events (SSE) para el renderizado progresivo de analíticas en la app móvil reduce la tasa de abandono de la pantalla, en comparación con una petición HTTP bloqueante tradicional? |
| **Hipótesis (Belief)** | **Creemos que** implementar Server-Sent Events (SSE) en la app móvil Flutter para recibir datos analíticos progresivamente desde el backend en Render, combinado con un indicador de carga (Spinner) y renderizado incremental, **para** los administradores que auditan lecturas corporativas, **dará como resultado** una reducción significativa en la percepción de congelamiento de la pantalla y una disminución de la tasa de abandono, a pesar de no poder optimizar el backend en su plan gratuito. |
| **Prueba (Test)**      | Realizar una prueba de usabilidad con **6 gerentes** (3 en control y 3 en experimental). Se les solicitará abrir las analíticas de lectura de un anuncio corporativo reciente y completar la auditoría. El **Grupo A (Control)** utiliza la petición HTTP bloqueante tradicional. El **Grupo B (Experimental)** utiliza la conexión SSE con Spinner y renderizado progresivo. |
| **Métrica (Metric)**   | 1. **DBM-01** (Screen Abandonment Rate): Porcentaje de gerentes que abandonan la pantalla de analíticas antes de completar la auditoría.<br /> 2. **DBM-02** (Task Success Rate): Porcentaje de gerentes que completan exitosamente la revisión de analíticas. |
| **Criterio de Éxito**  | **Estaremos en lo correcto si:** Ningún gerente del Grupo B abandona la pantalla, y al menos **2 de 3** completan la auditoría con éxito. |

Tarjeta de Experimento 2 (EX-02): Confirmación Binaria de Asistencia a Eventos

| **Componente EDD**     | **Detalle y Especificación Técnica del Experimento**         |
| ---------------------- | ------------------------------------------------------------ |
| **Origen del Backlog** | **Q3:** ¿De qué manera la inclusión de un mecanismo de confirmación de asistencia incrementa la predictibilidad logística? |
| **Hipótesis (Belief)** | **Creemos que** integrar botones interactivos de confirmación activa (*Aceptar / Rechazar asistencia*) en las tarjetas de eventos dentro del feed del empleado, **para** los colaboradores de las PyMEs, **dará como resultado** un ecosistema de retroalimentación bidireccional que otorgará un respaldo logístico inmediato a la gerencia, eliminando la desarticulación operativa de calendarios externos desincronizados. |
| **Prueba (Test)**      | Realizar una prueba de usabilidad con **5 empleados**. Se les asignará la tarea de revisar el cronograma semanal y confirmar su asistencia a una capacitación corporativa simulada. Cada empleado probará ambas versiones en sesiones separadas (secuencia balanceada). |
| **Métrica (Metric)**   | **DBM-04** (Active Interaction Rate): Porcentaje de empleados que interactúan con los botones de confirmación (Aceptar/Rechazar) entre el total de usuarios notificados. |
| **Criterio de Éxito**  | **Estaremos en lo correcto si:** Al menos **4 de 5** empleados (80%) interactúan proactivamente con el componente binario, y ninguno reporta confusión sobre el significado de las opciones. |

Tarjeta de Experimento 3 (EX-03): Sincronización Reactiva de Estados (State Management)

| **Componente EDD**     | **Detalle y Especificación Técnica del Experimento**         |
| ---------------------- | ------------------------------------------------------------ |
| **Origen del Backlog** | **Q4:** ¿En qué medida la sincronización reactiva de estados en la app móvil erradica la necesidad de realizar gestos de actualización manual (*pull-to-refresh*) por parte de los usuarios? |
| **Hipótesis (Belief)** | **Creemos que** reestructurar el flujo con un gestor de estado reactivo en Flutter, **para** los gerentes que asignan empleados a un evento o chat grupal, **dará como resultado** la erradicación del gesto manual invasivo de retroceder al perfil y deslizar hacia abajo para refrescar los miembros del equipo. |
| **Prueba (Test)**      | Realizar una prueba de usabilidad con **5 gerentes**. Se les solicitará crear un evento grupal y asignar 3 empleados. Cada gerente probará ambas versiones en sesiones separadas (secuencia balanceada). El **Grupo A** usa el flujo actual con recarga manual; el **Grupo B** usa el flujo con reactividad automatizada. |
| **Métrica (Metric)**   | **DBM-08** (Unnecessary Actions Count): Conteo de gestos manuales de refresco (*pull-to-refresh*) o clics de recarga innecesarios fuera del flujo óptimo durante la ejecución de la tarea. |
| **Criterio de Éxito**  | **Estaremos en lo correcto si:** Al menos **4 de 5** gerentes no requieren ejecutar gestos de refresco manual en la versión reactiva (el promedio de acciones innecesarias es igual a cero para el Grupo B). |

Tarjeta de Experimento 4 (EX-04): Reserva de Espacios Físicos Corporativos en Eventos

| **Componente EDD**     | **Detalle y Especificación Técnica del Experimento**         |
| ---------------------- | ------------------------------------------------------------ |
| **Origen del Backlog** | **Q6:** ¿De qué manera la inclusión de un selector de espacios físicos corporativos reduce los conflictos de ocupación y mejora la puntualidad logística? |
| **Hipótesis (Belief)** | **Creemos que** integrar un selector de espacios físicos internos (laboratorios, oficinas, salas de reuniones, auditorios y áreas comunes) dentro del flujo de creación de eventos en la app móvil, **para** los gerentes de PyMEs que organizan actividades corporativas, **dará como resultado** una eliminación de los conflictos de doble reserva y un incremento en la tasa de puntualidad de los empleados, al proporcionar una ubicación precisa y trazable desde el mismo canal oficial. |
| **Prueba (Test)**      | Realizar una prueba de usabilidad con **2 gerentes y 4 empleados** (6 participantes). Se les solicitará programar y confirmar asistencia a **dos eventos simulados** (una reunión de área y una actividad grupal). El **Grupo A (Control)** crea eventos sin campo de espacio físico. El **Grupo B (Experimental)** utiliza el flujo con el selector de espacios habilitado. |
| **Métrica (Metric)**   | 1. **DBM-06** (Occupancy Conflict Rate): Porcentaje de eventos con doble reserva o sin espacio asignado.<br /> 2. **DBM-05** (Logistical Punctuality Rate): Porcentaje de empleados que llegan a la ubicación correcta en el tiempo estipulado. |
| **Criterio de Éxito**  | **Estaremos en lo correcto si:** El Grupo B no reporta conflictos de doble reserva (0%), y al menos **3 de 4** empleados confirman la llegada a la ubicación correcta. |

## 8.2. Experiment Design

### 8.2.1. Hypotheses

Esta sección presenta las declaraciones de creencia para cada experimento identificado en el *Question Backlog*. Cada hipótesis de trabajo (H₁) es formulada para ser testable y medible, y se empareja con una hipótesis nula (H₀) que postula que no existirá diferencia significativa como resultado del cambio. Estas hipótesis serán sometidas a prueba, no validadas como "verdaderas", alineándose con el enfoque científico del *Experiment-Driven Development*.

**Experimento 1 (EX-01): Renderizado Progresivo de Analíticas con Server-Sent Events**
- **H₁ (Hipótesis de Trabajo):** *Implementar Server-Sent Events (SSE) en la app móvil Flutter para recibir datos analíticos progresivamente desde el backend en Render, combinado con un indicador de carga (Spinner) y renderizado incremental, disminuirá significativamente la tasa de abandono de la pantalla de analíticas al evitar que la interfaz se perciba congelada.*
- **H₀ (Hipótesis Nula):** *No existirá diferencia significativa en la tasa de abandono de la pantalla de analíticas entre la versión con petición HTTP bloqueante (control) y la versión con SSE progresivo (experimental). Cualquier diferencia observada se atribuye al azar.*

**Experimento 2 (EX-02): Confirmación de Asistencia a Eventos**
- **H₁ (Hipótesis de Trabajo):** *Integrar botones interactivos de confirmación activa (*Aceptar / Rechazar*) en las tarjetas de eventos incrementará significativamente la tasa de interacción activa de los empleados y la predictibilidad logística para la gerencia.*
- **H₀ (Hipótesis Nula):** *No existirá diferencia significativa en la tasa de interacción activa ni en la predictibilidad logística entre el flujo actual sin confirmación y el flujo con confirmación binaria. Cualquier diferencia observada se atribuye al azar.*

**Experimento 3 (EX-03): Sincronización Reactiva de Estados (State Management)**
- **H₁ (Hipótesis de Trabajo):** *Reestructurar el flujo con un gestor de estado reactivo en Flutter erradicará completamente la necesidad de realizar gestos de actualización manual (*pull-to-refresh*) para sincronizar los miembros de la organización.*
- **H₀ (Hipótesis Nula):** *No existirá diferencia significativa en la cantidad de acciones innecesarias de refresco manual ejecutadas entre el flujo con recarga manual (control) y el flujo con reactividad automatizada (experimental). Cualquier diferencia observada se atribuye al azar.*

**Experimento 4 (EX-04): Reserva de Espacios Físicos Corporativos en Eventos**
- **H₁ (Hipótesis de Trabajo):** *Integrar un selector de espacios físicos internos dentro del flujo de creación de eventos eliminará los conflictos de doble reserva e incrementará la tasa de llegada de los empleados a la ubicación física correcta.*
- **H₀ (Hipótesis Nula):** *No existirá diferencia significativa en la tasa de conflictos de ocupación ni en la llegada a la ubicación correcta entre el flujo sin selector de espacios (control) y el flujo con selector (experimental). Cualquier diferencia observada se atribuye al azar.*

### 8.2.2. Domain Business Metrics

Esta sección define el catálogo centralizado de métricas de negocio para el dominio de **Centralis**. Su propósito es alinear la medición de todos los experimentos con objetivos de negocio concretos, evitando el uso de *vanity metrics* o métricas ad-hoc no predefinidas. Todas las *Experiment Cards* y secciones posteriores únicamente harán referencia a las métricas aquí establecidas. Cada métrica incluye su fórmula de cálculo, técnica de recolección y meta deseada.

| **ID** | **Métrica de Negocio** | **Fórmula de Cálculo** | **Técnica de Recolección** | **Meta Deseada** |
| ------ | ---------------------- | ---------------------- | -------------------------- | ---------------- |
| **DBM-01** | **Screen Abandonment Rate** | (Número de usuarios que abandonan la pantalla antes de completar la tarea / Número total de usuarios que inician la tarea) × 100. | Observación directa en sesiones de prueba de usabilidad y registro en hoja de cálculo. | < 10% |
| **DBM-02** | **Task Success Rate** | (Número de usuarios que completan exitosamente la tarea / Número total de usuarios que inician la tarea) × 100. | Observación directa en sesiones de prueba y registro manual. | > 90% |
| **DBM-04** | **Active Interaction Rate** | (Número de usuarios que interactúan activamente con el componente objetivo / Número total de usuarios expuestos al componente) × 100. | Consulta de registros en la base de datos (Supabase) del total de interacciones (clics en Aceptar/Rechazar) guardadas. | > 85% |
| **DBM-05** | **Logistical Punctuality Rate** | (Número de asistencias registradas en la ubicación correcta dentro del horario / Número total de asistencias esperadas) × 100. | Confirmación de check-in manual en la app móvil y consulta SQL en la base de datos (Supabase). | > 90% |
| **DBM-06** | **Occupancy Conflict Rate** | (Número de eventos con doble reserva o sin espacio asignado / Número total de eventos creados en el período) × 100. | Consulta en base de datos (Supabase) de registros de eventos con colisiones de espacio y timestamp. | 0% |
| **DBM-07** | **Read Confirmation Rate** | (Número de anuncios confirmados como leídos por el destinatario / Número total de anuncios enviados) × 100. | Consulta SQL en la base de datos (Supabase) del estado de lectura de anuncios. | > 90% en 24 horas |
| **DBM-08** | **Unnecessary Actions Count** | Conteo de gestos o interacciones fuera del flujo óptimo (ej. *pull-to-refresh* manual, retroceso innecesario) durante la ejecución de una tarea. | Observación directa en sesiones de prueba de usabilidad y conteo manual. | 0 acciones innecesarias |

### 8.2.3. Measures

Esta sección detalla los criterios seleccionados para recopilar la evidencia que permitirá responder las preguntas de investigación y detectar evidencia secundaria.

**Medidas para EX-01: Renderizado Progresivo de Analíticas con Server-Sent Events**
- **Medida 1 (M1-01):** Tasa de abandono de la pantalla de analíticas (DBM-01). Se observará directamente durante las sesiones de prueba con 6 gerentes, anotando cuántos abandonan antes de completar la auditoría.
- **Medida 2 (M1-02):** Tasa de éxito de la tarea de auditoría (DBM-02). Se registrará de forma observacional directa durante las sesiones de prueba, verificando si el gerente logra visualizar y comprender las analíticas de lectura.

**Medidas para EX-02: Confirmación Binaria de Asistencia a Eventos**
- **Medida 1 (M2-01):** Tasa de interacción activa con el componente de confirmación (DBM-04). Se recolectará mediante consultas en la base de datos (Supabase) al final de la sesión de pruebas con los 5 empleados.
- **Medida 2 (M2-02):** Registro de respuesta de confirmación en la base de datos (Supabase) al finalizar la sesión, validando si cada usuario interactuó con los botones de confirmación.

**Medidas para EX-03: Sincronización Reactiva de Estados**
- **Medida 1 (M3-01):** Tasa de finalización exitosa de la tarea de asignación (DBM-02), registrada observacionalmente al verificar si el gerente logra guardar el evento con los miembros deseados.
- **Medida 2 (M3-02):** Número de acciones innecesarias (DBM-08). Se registrará mediante observación directa en las sesiones de prueba, contando las instancias en las que el usuario ejecuta un gesto de *pull-to-refresh* manual.

**Medidas para EX-04: Reserva de Espacios Físicos Corporativos**
- **Medida 1 (M4-01):** Tasa de conflictos de ocupación (DBM-06). Se observará directamente durante las sesiones de prueba con 2 gerentes, verificando si ocurren doble reservas en la base de datos.
- **Medida 2 (M4-02):** Tasa de puntualidad logística (DBM-05). Se medirá mediante confirmación de check-in manual en la app móvil y posterior consulta SQL en Supabase para registrar la llegada a la ubicación correcta en el evento.

### 8.2.4. Conditions

Esta sección describe los factores que permiten identificar el motivo subyacente detrás de una respuesta. Para cada experimento se definen una **condición experimental** (bajo la cual se busca obtener evidencia a favor de la hipótesis alternativa H₁) y una **condición de control** (que actúa bajo la suposición de que la hipótesis nula H₀ es correcta). Las condiciones se aplican exclusivamente sobre la app móvil de **Centralis**, dado que el backend (Web Service) actúa como infraestructura de soporte indistinta para ambos grupos.

**Condiciones para EX-01: Renderizado Progresivo de Analíticas con Server-Sent Events**
- **Condición de Control (C-01):** La app móvil mantiene el flujo actual de petición HTTP bloqueante tradicional. Al abrir la pantalla de analíticas, la app envía una única petición al backend en Render y espera la respuesta completa antes de renderizar cualquier dato. No hay indicadores visuales intermedios ni feedback progresivo. El gerente percibe la latencia como una congelación de la interfaz.
- **Condición Experimental (E-01):** La app móvil abre una conexión SSE (Server-Sent Events) al endpoint de analíticas en el backend de Render. Recibe los datos analíticos en chunks progresivos y los renderiza incrementalmente en la interfaz. Durante los primeros 500 ms de espera se muestra un indicador de carga (Spinner). El backend permanece en su configuración actual sin optimización, dado que el equipo opera bajo plan gratuito.

**Condiciones para EX-02: Confirmación Binaria de Asistencia a Eventos**
- **Condición de Control (C-02):** El empleado recibe la notificación del evento en su feed, pero la tarjeta de evento no contiene botones de confirmación. El flujo es puramente pasivo y unidireccional: la gerencia publica y el empleado solo visualiza.
- **Condición Experimental (E-02):** La tarjeta de evento en el feed del empleado incluye botones interactivos de confirmación activa (*Aceptar / Rechazar asistencia*). La respuesta se registra en tiempo real en la base de datos de Supabase.

**Condiciones para EX-03: Sincronización Reactiva de Estados**
- **Condición de Control (C-03):** El flujo de creación de eventos mantiene la arquitectura actual. El gerente debe retroceder al perfil y ejecutar un gesto de *pull-to-refresh* para actualizar la lista de miembros elegibles en una vista externa. No existe sincronización automática entre la base de datos y la interfaz de selección.
- **Condición Experimental (E-03):** El flujo se reestructura con un gestor de estado reactivo en Flutter que sincroniza automáticamente los hilos con la base de datos de Supabase. La lista de miembros se actualiza en tiempo real sin requerir gestos manuales de refresco.

**Condiciones para EX-04: Reserva de Espacios Físicos Corporativos**
- **Condición de Control (C-04):** El flujo de creación de eventos no incluye campo de ubicación física. El gerente comunica la ubicación del evento mediante canales externos (mensaje de texto o verbalmente). No existe trazabilidad ni control de disponibilidad de espacios.
- **Condición Experimental (E-04):** El flujo de creación de eventos incluye un selector de espacios físicos internos (laboratorios, oficinas, salas de reuniones, auditorios y áreas comunes) con visualización de disponibilidad y capacidad en tiempo real. El espacio seleccionado se bloquea automáticamente en la base de datos para evitar doble reserva.

### 8.2.5. Scale Calculations and Decisions

Esta sección determina la cantidad de evidencia necesaria para cada experimento, basándose en la **Certeza** (probabilidad de error aceptable) y la **Precisión** (granularidad del cambio a detectar). Se establece el nivel de significancia (α), el poder estadístico (1-β) y el Efecto Mínimo Detectable (MDE) para cada experimento. A partir de estos parámetros, se calcula el tamaño de muestra mínimo requerido para cada grupo (control y experimental).

**Parámetros Generales**
- **Nivel de Significación (α):** 0.05 (5%). Esto implica que se acepta un 5% de probabilidad de cometer un error Tipo I (rechazar H₀ cuando es verdadera).
- **Poder Estadístico (1-β):** 0.80 (80%). Esto establece que se desea un 80% de probabilidad de detectar un efecto real cuando existe, minimizando el riesgo de error Tipo II.
- **Nivel de Confianza:** 95% (1 - α).

**Cálculos por Experimento**

**EX-01: Renderizado Progresivo de Analíticas con Server-Sent Events**
- **MDE:** Se busca detectar una reducción cualitativa en la tasa de abandono de la pantalla de analíticas. En una prueba de usabilidad con muestra pequeña, el objetivo es que **ningún participante** del grupo experimental abandone la pantalla, en comparación con el control donde se espera que al menos 1 de 3 abandone.
- **Cálculo de Tamaño de Muestra:** Para una prueba de usabilidad con comparación entre dos variantes de interfaz, un tamaño de **n = 3 usuarios por grupo** (6 en total) permite detectar problemas críticos de usabilidad según las heurísticas de Nielsen. Se adopta **n = 3 por grupo** como tamaño mínimo viable.
- **Decisión:** Dado que la intervención se realiza únicamente en el cliente móvil (SSE + Spinner) y el objetivo es obtener evidencia rápida para iterar, un tamaño de 3 gerentes por grupo es suficiente para una prueba de usabilidad estructurada.

**EX-02: Confirmación Binaria de Asistencia a Eventos**
- **MDE:** Se busca detectar un incremento en la tasa de interacción activa. En una prueba de usabilidad con diseño within-subjects (misma persona prueba ambas versiones), se espera que al menos 4 de 5 empleados interactúen con el botón de confirmación.
- **Cálculo de Tamaño de Muestra:** Para una prueba de usabilidad within-subjects con un componente UI binario, un tamaño de **n = 5 empleados** permite capturar la variabilidad de comportamiento y detectar problemas de comprensión del componente.
- **Decisión:** Un tamaño de 5 empleados es viable para una prueba de usabilidad rápida y permite obtener feedback cualitativo sobre la claridad del componente binario.

**EX-03: Sincronización Reactiva de Estados**
- **MDE:** Se busca detectar la erradicación de las acciones innecesarias de refresco manual. En una prueba de usabilidad within-subjects, se espera que los gerentes no requieran realizar gestos de refresco manual.
- **Cálculo de Tamaño de Muestra:** Un tamaño de **n = 5 gerentes** permite obtener una observación clara de si los usuarios ejecutan gestos manuales innecesarios al asignar miembros.
- **Decisión:** Un tamaño de 5 gerentes es suficiente para una prueba de usabilidad estructurada orientada al conteo de acciones manuales innecesarias.

**EX-04: Reserva de Espacios Físicos Corporativos**
- **MDE:** Se busca detectar una eliminación de conflictos de ocupación y un incremento en la llegada a la ubicación correcta. En una prueba de usabilidad con 2 gerentes y 4 empleados, se espera 0 conflictos de reserva.
- **Cálculo de Tamaño de Muestra:** Para una prueba piloto de un nuevo flujo de creación de eventos, un tamaño de **2 gerentes + 4 empleados (6 en total)** permite evaluar tanto la experiencia de creación como la de asistencia en un contexto realista.
- **Decisión:** Un tamaño de 6 participantes es adecuado para una prueba piloto de un flujo completo, capturando la interacción entre ambos segmentos objetivo en un escenario controlado.

**Resumen de Escalabilidad**

| **Experimento** | **Método** | **Tamaño por Grupo (n)** | **Total de Usuarios** | **Duración** |
| --------------- | ---------- | ------------------------ | --------------------- | ------------ |
| **EX-01** | Prueba de usabilidad between-subjects | 3 gerentes | 6 | 1 sesión por participante |
| **EX-02** | Prueba de usabilidad within-subjects | 5 empleados | 5 | 1 sesión por participante |
| **EX-03** | Prueba de usabilidad within-subjects | 5 gerentes | 5 | 1 sesión por participante |
| **EX-04** | Prueba piloto estructurada | 2 gerentes + 4 empleados | 6 | 2 eventos simulados |

### 8.2.6. Methods Selection

Esta sección describe la técnica de investigación seleccionada para cada experimento, aplicando el principio del **Simplest Useful Thing** (la cosa más simple y útil) para alcanzar el tamaño de muestra y las condiciones necesarias. Se distingue claramente entre el objeto de investigación (la pregunta o hipótesis) y el método (la técnica aplicada). Se considera la norma ética de no ejecutar simultáneamente dos o más experimentos sobre el mismo tema que puedan exponer a un solo usuario a ambos.

**Método para EX-01: Renderizado Progresivo de Analíticas con Server-Sent Events**
- **Método seleccionado:** Prueba de usabilidad con observación directa (Usability Testing) en entorno controlado, diseño between-subjects.
- **Justificación:** Es el método más simple para comparar la percepción de fluidez entre dos variantes de renderizado de analíticas con un número reducido de participantes. Con 3 gerentes por grupo se puede detectar problemas críticos de usabilidad y obtener evidencia cualitativa sobre la percepción de congelamiento. No requiere despliegue a producción ni seguimiento prolongado.
- **Consideración ética:** Los gerentes participantes no serán expuestos simultáneamente a ningún otro experimento relacionado con el módulo de anuncios o analíticas durante la sesión de prueba.

**Método para EX-02: Confirmación Binaria de Asistencia a Eventos**
- **Método seleccionado:** Prueba de usabilidad con observación directa (Usability Testing) en entorno controlado, diseño within-subjects.
- **Justificación:** Dado que se busca validar la interacción proactiva de los empleados con un nuevo componente UI, la observación directa con 5 empleados es el método más simple para capturar la tasa de interacción y detectar confusiones en la interfaz. El diseño within-subjects (mismo empleado prueba ambas versiones) reduce la varianza entre participantes y permite obtener feedback comparativo directo.
- **Consideración ética:** Los empleados participantes no serán asignados simultáneamente al experimento EX-03 (sincronización reactiva) para evitar sesgos en el flujo de eventos.

**Método para EX-03: Sincronización Reactiva de Estados**
- **Método seleccionado:** Prueba de usabilidad con observación directa y conteo de acciones innecesarias.
- **Justificación:** Es el método más simple para registrar si los usuarios intentan forzar la actualización de la lista de miembros asignables. La observación directa permite contar de forma manual los gestos de refresco manual ejecutados por los gerentes durante el flujo de trabajo en la app.
- **Consideración ética:** Los gerentes participantes no serán expuestos simultáneamente al experimento EX-04 (reserva de espacios) para evitar sobrecarga cognitiva en el flujo de creación de eventos.

**Método para EX-04: Reserva de Espacios Físicos Corporativos**
- **Método seleccionado:** Prueba piloto estructurada (Pilot Test) con observación directa en entorno simulado.
- **Justificación:** Es el método más simple para evaluar la eficacia de un nuevo flujo de selección de espacios con un número reducido de participantes. Con 2 gerentes y 4 empleados se puede observar la interacción completa entre creador y asistente en un escenario realista, capturando la tasa de conflictos y la llegada correcta a la ubicación sin requerir despliegue a escala.
- **Consideración ética:** Los gerentes del grupo experimental no utilizarán simultáneamente el módulo de confirmación binaria (EX-02) para evitar que la interacción con la confirmación de asistencia distraiga de la evaluación del selector de espacios.

### 8.2.7. Data Analytics: Goals, KPIs and Metrics Selection

Esta sección establece la preparación analítica para garantizar la economía en el rastreo de datos, asegurando que las métricas y KPIs seleccionados permitan detectar diferencias precisas y cambios significativos en el comportamiento del usuario. Todos los objetivos se alinean con las métricas de dominio (DBM) definidas en la sección 8.2.2.

**Metas Analíticas (Goals)**
- **G1: Validar la reducción de fricción técnica en el cliente móvil.** Confirmar que la implementación de SSE para renderizado progresivo de analíticas en la app móvil reduce la tasa de abandono de la pantalla.
- **G2: Validar el incremento de participación activa.** Confirmar que la confirmación binaria de asistencia transforma el flujo de eventos de unidireccional a bidireccional mediante interacciones guardadas en la base de datos.
- **G3: Validar la eficiencia en flujos de creación.** Confirmar que la sincronización reactiva erradica las acciones innecesarias de refresco manual en la gestión de eventos.
- **G4: Validar la integridad logística de eventos.** Confirmar que la reserva de espacios físicos elimina conflictos y mejora la puntualidad de llegada del personal.

**KPIs (Indicadores Clave de Rendimiento)**
- **KPI-1 (Retención de Auditoría):** Tasa de usuarios que completan la auditoría de lecturas sin abandonar. *Métrica asociada: DBM-01 (Screen Abandonment Rate).*
- **KPI-2 (Participación en Eventos):** Porcentaje de empleados que confirman/rechazan asistencia en la base de datos de Supabase. *Métrica asociada: DBM-04 (Active Interaction Rate).*
- **KPI-3 (Eficiencia de Flujo):** Tasa de usuarios que finalizan la asignación sin ejecutar refrescos manuales (*pull-to-refresh*). *Métrica asociada: DBM-08 (Unnecessary Actions Count).*
- **KPI-4 (Precisión Logística):** Porcentaje de eventos ejecutados sin conflictos de espacio y con asistencia en la ubicación física registrada. *Métricas asociadas: DBM-05 (Logistical Punctuality Rate) y DBM-06 (Occupancy Conflict Rate).*

**Métricas de Seguimiento (Tracking Metrics)**
- **Métricas de Rendimiento Técnico:** No se definen métricas automáticas de backend. El rendimiento de carga progresiva se evalúa de manera cualitativa en el cliente móvil mediante la percepción de fluidez declarada verbalmente por los usuarios en las pruebas de usabilidad.

- **Métricas de Comportamiento de Usuario:** DBM-02 (Task Success Rate) y DBM-08 (Unnecessary Actions Count) para detectar patrones de uso y fricción heurística.

  

### 8.2.8. Web and Mobile Tracking Plan

Dado que la solución de **Centralis** se compone exclusivamente de una **aplicación móvil nativa** (desarrollada en Flutter) y un **Web Service** (backend RESTful desplegado en Render con base de datos en Supabase), el plan de rastreo se centra en la recolección de datos desde estos dos componentes. No se incluye seguimiento de Landing Page ni de Frontend Web Applications, ya que estos productos no forman parte del alcance experimental ni del modelo de negocio digital actual de la plataforma.

**Arquitectura de Rastreo**
- **App Móvil (Flutter):** Recolección de datos observacional mediante registro manual por parte del evaluador en una hoja de cálculo para el análisis de comportamiento de usuarios (abandonos, éxito de tareas e interacciones no deseadas como gestos manuales de refresco).
- **Backend (Web Service en Render) y Base de Datos (Supabase):** Consultas directas a las tablas transaccionales de Supabase (`asistencias`, `reservas_espacios`, `confirmaciones_lectura`) para verificar la persistencia y la tasa de interacción activa real de los participantes.

**Criterios de Registro por Experimento**

**EX-01: Renderizado Progresivo de Analíticas con Server-Sent Events**
- **Registro Observacional (Hoja de cálculo):**
  - Si el gerente abandona la pantalla antes de completarse la carga de analíticas (Sí/No).
  - Si el gerente completa la tarea de auditoría con éxito (Sí/No).
  - Comentarios del gerente respecto a la percepción de fluidez (cualitativo).

**EX-02: Confirmación Binaria de Asistencia a Eventos**
- **Registro en Base de Datos (Supabase):**
  - Inserción/actualización de registros en la tabla de asistencias (`confirmado` o `rechazado`).
- **Registro Observacional (Hoja de cálculo):**
  - Si el empleado interactúa con el botón binario de confirmación (Sí/No).

**EX-03: Sincronización Reactiva de Estados**
- **Registro Observacional (Hoja de cálculo):**
  - Conteo de gestos manuales de refresco (*pull-to-refresh*) ejecutados por el gerente durante el flujo.
  - Si el gerente completa la asignación de miembros con éxito (Sí/No).

**EX-04: Reserva de Espacios Físicos Corporativos**
- **Registro en Base de Datos (Supabase):**
  - Registro de reservas de espacio en la tabla de eventos para verificar si existen colisiones (Occupancy Conflict Rate).
  - Registro de confirmaciones de check-in en la tabla de asistencias con el campo de ubicación para verificar la llegada del personal.
- **Registro Observacional (Hoja de cálculo):**
  - Si el empleado llegó a la ubicación física correcta indicada en la app (Sí/No).

**Dashboard de Seguimiento**
- Se utilizará una hoja de cálculo simple (Google Sheets o Excel) para consolidar manualmente los resultados observados por el evaluador en cada sesión de prueba (abandonos, acciones incorrectas y respuestas cualitativas).
- Se utilizará la consola de Supabase para realizar consultas SQL básicas directas a las tablas y verificar el correcto guardado de los registros en tiempo real durante los eventos simulados.

## 8.3. Experimentation

### 8.3.1. To-Be User Stories

En esta sección se definen las historias de usuario del estado futuro (To-Be) que materializan las funcionalidades experimentales diseñadas para validar las hipótesis de valor. Cada historia está directamente vinculada con un experimento (EX-01 a EX-04) y representa el incremento de producto mínimo necesario para recolectar métricas de negocio en un entorno de producción. Se mantienen los mismos segmentos objetivo (gerentes y empleados) y se incorpora el rol de desarrollador para las technical stories relacionadas con rendimiento y arquitectura.

---

<table style="width: 100%; border-collapse: collapse; margin: 0 auto;">
  <tr>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Story ID</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">User</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Priority</th>
    <th style="border: 1px solid black; padding: 8px; text-align: center; width: 20%;">Epic</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">TB-US01</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">desarrollador</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">1</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Rendimiento y Experiencia de Usuario</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Renderizado progresivo de analíticas con Server-Sent Events</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como desarrollador, quiero implementar Server-Sent Events (SSE) para el renderizado progresivo de analíticas de lectura de anuncios, para que los gerentes no abandonen la pantalla de auditoría por la percepción de congelamiento de la interfaz.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Renderizado progresivo de analíticas con SSE<br><br>Escenario: Conexión SSE exitosa y renderizado incremental<br>Dado que un gerente abre la pantalla de analíticas de un anuncio,<br>Cuando el sistema establece una conexión SSE con el backend,<br>Entonces se muestra un indicador de carga (Spinner) durante los primeros 500 ms,<br>y los datos analíticos se renderizan progresivamente en chunks sin bloquear la interfaz.<br><br>Escenario: Reducción de abandono de pantalla<br>Dado que un gerente accede a las analíticas de lectura,<br>Cuando se realiza el renderizado progresivo en el cliente móvil,<br>Entonces el gerente puede seguir interactuando con la interfaz mientras llegan los datos,<br>y la tasa de abandono (DBM-01) se mantiene por debajo del 10%.</td>
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
    <td style="border: 1px solid black; padding: 8px; text-align: center;">TB-US02</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">empleado</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">1</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Gestión de Eventos</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Confirmación binaria de asistencia a eventos</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como empleado, quiero confirmar o rechazar mi asistencia a eventos corporativos mediante botones interactivos (Aceptar / Rechazar), para que la gerencia pueda predecir la logística de las actividades y planificar recursos.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Confirmación binaria de asistencia a eventos<br><br>Escenario: Confirmar asistencia a un evento<br>Dado que un empleado visualiza la tarjeta de un evento en su feed,<br>Cuando presiona el botón "Aceptar asistencia",<br>Entonces el sistema registra su respuesta positiva en la base de datos,<br>y el gerente visualiza la confirmación en el panel del evento.<br><br>Escenario: Rechazar asistencia a un evento<br>Dado que un empleado visualiza la tarjeta de un evento en su feed,<br>Cuando presiona el botón "Rechazar asistencia",<br>Entonces el sistema registra su respuesta negativa en la base de datos,<br>y el gerente visualiza el contador de rechazos en el panel del evento.<br><br>Escenario: Alta tasa de interacción activa<br>Dado que un evento es emitido a 5 empleados,<br>Cuando se mide la interacción en las respuestas guardadas en base de datos,<br>Entonces al menos el 80% de los empleados han interactuado con el componente de confirmación (DBM-04).</td>
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
    <td style="border: 1px solid black; padding: 8px; text-align: center;">TB-US03</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">desarrollador</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">2</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Rendimiento y Experiencia de Usuario</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Sincronización reactiva de estados en flujo de eventos</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como desarrollador, quiero implementar un gestor de estado reactivo en Flutter que sincronice automáticamente la lista de miembros elegibles con la base de datos, para que los gerentes no necesiten ejecutar pull-to-refresh manual ni retroceder a la pantalla anterior al crear eventos grupales.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Sincronización reactiva de estados en flujo de eventos<br><br>Escenario: Actualización automática de lista de miembros<br>Dado que un gerente se encuentra en el flujo de creación de un evento grupal,<br>Cuando un nuevo empleado es registrado en la compañía desde otra sesión,<br>Entonces la lista de miembros elegibles se actualiza automáticamente en tiempo real sin requerir gestos manuales de refresco.<br><br>Escenario: Reducción de acciones innecesarias<br>Dado que un gerente crea un evento y asigna 3 empleados,<br>Cuando finaliza la tarea de asignación,<br>Entonces la sincronización se realiza en tiempo real sin requerir refrescos manuales (el conteo de acciones innecesarias DBM-08 es igual a cero).</td>
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
    <td style="border: 1px solid black; padding: 8px; text-align: center;">TB-US04</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">gerente</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">1</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Gestión de Eventos</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Reserva de espacios físicos corporativos en eventos</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como gerente, quiero seleccionar y reservar espacios físicos internos (laboratorios, oficinas, salas de reuniones, auditorios y áreas comunes) al crear un evento, para eliminar conflictos de ocupación, evitar duplicación de reservas y mejorar la puntualidad logística de los empleados.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Reserva de espacios físicos corporativos en eventos<br><br>Escenario: Selección y bloqueo de espacio físico<br>Dado que un gerente crea un nuevo evento corporativo,<br>Cuando selecciona un espacio físico disponible del catálogo (laboratorio, oficina, sala, auditorio o área común),<br>Entonces el sistema bloquea automáticamente el espacio para el horario del evento en la base de datos,<br>y registra la ubicación para evitar doble reserva.<br><br>Escenario: Alerta de conflicto de ocupación<br>Dado que un gerente intenta crear un evento en un horario ya ocupado,<br>Cuando selecciona un espacio que ya tiene una reserva vigente en Supabase,<br>Entonces el sistema muestra una alerta de conflicto de ocupación (DBM-06),<br>y no permite la creación del evento hasta seleccionar otro espacio o horario.<br><br>Escenario: Mejora de puntualidad logística<br>Dado que un evento incluye un espacio físico reservado,<br>Cuando los empleados reciben la notificación del evento,<br>Entonces visualizan la ubicación exacta del espacio,<br>y la tasa de llegada a la ubicación correcta registrada en base de datos (DBM-05) supera el 90%.</td>
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
    <td style="border: 1px solid black; padding: 8px; text-align: center;">TB-US05</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">gerente</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">2</td>
    <td style="border: 1px solid black; padding: 8px; text-align: center;">Gestión de Eventos</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Title</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Visualización de confirmaciones de asistencia en panel de eventos</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold;">Description</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left;">Como gerente, quiero visualizar en el panel de un evento el listado de empleados que confirmaron, rechazaron o no respondieron la invitación, para planificar la logística, recursos y espacios necesarios.</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px; text-align: left; font-weight: bold; vertical-align: top;">Acceptance Criteria</td>
    <td colspan="3" style="border: 1px solid black; padding: 8px; text-align: left; vertical-align: top;">Feature: Visualización de confirmaciones de asistencia en panel de eventos<br><br>Escenario: Ver resumen de respuestas<br>Dado que un gerente accede al detalle de un evento creado,<br>Cuando visualiza la sección de asistencias,<br>Entonces el sistema muestra tres contadores: Confirmados, Rechazados y Pendientes,<br>junto con la lista de empleados correspondiente a cada categoría obtenida de Supabase.<br><br>Escenario: Actualización en tiempo real de respuestas<br>Dado que un gerente está en el panel de un evento,<br>Cuando un empleado confirma o rechaza su asistencia desde su dispositivo,<br>Entonces el contador y la lista se actualizan automáticamente en la pantalla del gerente sin requerir refresco manual.</td>
  </tr>
</table>

### 8.3.2. To-Be Product Backlog

<p style="text-indent: 1.25cm;">El To-Be Product Backlog consolida las historias de usuario experimentales en una lista priorizada, ordenada por valor de negocio, riesgo técnico e impacto en los objetivos de aprendizaje. Las historias técnicas (TB-US01, TB-US03) se ubican en las primeras posiciones porque habilitan la infraestructura de medición y reducen fricción crítica; las historias funcionales (TB-US02, TB-US04, TB-US05) se priorizan según su contribución a las métricas de dominio (DBM) y su criticidad para la validación de hipótesis.</p>

| Orden | Story ID | Título | Descripción | Story Points |
| ----- | -------- | ------ | ----------- | ------------ |
| 1 | TB-US01 | Renderizado progresivo de analíticas con Server-Sent Events | Como desarrollador, quiero implementar SSE para el renderizado progresivo de analíticas de lectura, para reducir la percepción de congelamiento y la tasa de abandono de la pantalla de auditoría. | 8 |
| 2 | TB-US03 | Sincronización reactiva de estados en flujo de eventos | Como desarrollador, quiero implementar un gestor de estado reactivo en Flutter para sincronizar automáticamente la lista de miembros, eliminando el refresco manual en la creación de eventos grupales. | 5 |
| 3 | TB-US04 | Reserva de espacios físicos corporativos en eventos | Como gerente, quiero seleccionar y reservar espacios físicos internos al crear un evento, para eliminar conflictos de ocupación y mejorar la puntualidad logística. | 8 |
| 4 | TB-US02 | Confirmación binaria de asistencia a eventos | Como empleado, quiero confirmar o rechazar mi asistencia a eventos mediante botones interactivos, para que la gerencia pueda predecir la logística. | 5 |
| 5 | TB-US05 | Visualización de confirmaciones de asistencia en panel de eventos | Como gerente, quiero visualizar el listado de confirmaciones, rechazos y pendientes de un evento, para planificar la logística y recursos. | 3 |
