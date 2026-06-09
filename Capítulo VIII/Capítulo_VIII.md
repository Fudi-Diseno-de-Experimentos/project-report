# Capítulo VIII: Experiment-Driven Development

## 8.1. Experiment Planning

### 8.1.1. As-Is Summary

Esta sección consolida la información cualitativa y el material bruto recopilado a partir de las sesiones de validación e interacción con los segmentos objetivos (*Gerentes y Empleados*). El propósito de este bloque no es el diseño inmediato de soluciones técnicas, sino la identificación estructurada de los puntos de partida metodológicos, permitiendo transformar el comportamiento y las observaciones de los usuarios en preguntas de investigación y premisas científicas sujetas a experimentación.

### 8.1.2. Raw Material: Assumptions, Knowledge Gaps, Ideas, Claims

A partir de las auditorías de experiencia de usuario realizadas, se ha clasificado la materia prima del proyecto en cuatro ejes fundamentales para guiar el diseño de experimentos:

- **Ideas (Propuestas para resolver un problema):**
  - *Automatización de la Sincronización Reactiva (State Management):* Implementar un mecanismo de actualización en tiempo real o reactivo en el árbol de widgets de la aplicación Flutter. Esto evitaría que el usuario deba adivinar o recordar ejecutar un gesto de deslizamiento manual (*pull-to-refresh*) en vistas externas para actualizar la lista de miembros elegibles. El experimento asociado no debe evaluar la animación del indicador, sino validar si la persistencia automática reduce el tiempo de conversión de la tarea al estructurar eventos corporativos.
  - *Inclusión de Confirmación Binaria de Asistencia:* Añadir un componente interactivo de respuesta (*Aceptar/Rechazar asistencia*) en la vista del empleado para los eventos asignados. El objetivo de evaluar esta premisa es verificar si el flujo de retroalimentación bidireccional mejora la predictibilidad logística de la gerencia en la organización de actividades corporativas.
- **Claims (Afirmaciones de los Usuarios):**
  - *"WhatsApp no constituye un canal formal ni seguro para el flujo corporativo":* Los gerentes y empleados afirman de manera categórica que las herramientas de mensajería comercial tradicionales provocan pérdidas críticas de información y carecen de gobernanza de datos.
  - *"El control analítico por perfil es una necesidad operativa legítima y no una transgresión de la privacidad":* Los administradores certifican que auditar el historial de lecturas a nivel laboral es indispensable para garantizar la alineación del equipo, siempre y cuando los datos se limiten estrictamente a cuentas corporativas y no expongan registros personales como el número telefónico privado.
  - *"Dejar la publicación de anuncios globales abierta a todo el personal generará sobrecarga de información y desorden":* Ambos gerentes afirman que un canal sin restricciones jerárquicas saturará la pantalla principal de la aplicación móvil, afectando la visibilidad de los comunicados de alta prioridad.
- **Assumptions (Suposiciones del Equipo):**
  - *Suposición de Disponibilidad Inmediata:* El equipo asumió que por el hecho de ser una solución unificada 100% móvil, los usuarios tolerarían tiempos de carga asíncronos prolongados en módulos complejos. Sin embargo, la congelación momentánea de la interfaz (*"quedarse cargando"*) demostró que la tolerancia del usuario móvil a la latencia de procesamiento de las analíticas desde la tarjeta del anuncio es sumamente baja.
  - *Suposición de la Dirección del Flujo:* Se asumió que el flujo de eventos era unidireccional (la gerencia agenda y notifica, y el empleado simplemente acata). La observación del usuario demostró que la audiencia objetivo asume intrínsecamente que un "evento" requiere un mecanismo de confirmación activa de asistencia para ser considerado funcional.
- **Knowledge Gaps (Brechas de Conocimiento):**
  - *Permisología de Publicación Óptima:* El equipo desconoce cuál es el número máximo tolerable de usuarios con permisos de publicación global en una organización de tamaño mediano (50 empleados) antes de que la pantalla principal degrade la experiencia de usuario.
  - *Causa Raíz de la Latencia de Datos:* Existe una brecha técnica respecto a si el congelamiento de la pantalla al acceder a las analíticas se debe a un problema de rendimiento en el renderizado local del cliente móvil o a una ineficiencia en el tiempo de respuesta del backend modular en Render al procesar las consultas relacionales hacia Supabase.
  - *Tasa de Adopción con Confirmación de Asistencia:* Carecemos de datos cuantitativos sobre cuántos empleados interactuarán activamente con un botón de confirmación de asistencia en comparación con el simple acto pasivo de recibir la notificación del evento.

### 8.1.3. Experiment-Ready Questions

Esta sección define el cuestionario científico e instructivo que guiará el diseño de los experimentos de la plataforma **Centralis**. Para asegurar un enfoque riguroso, se utiliza la matriz inicial de *The 5 W’s and 2 H’s* del planteamiento del problema como un marco de contraste frente al comportamiento real de las usuarias en los entornos de producción, mapeando premisas ocultas y convirtiéndolas en variables medibles.

**Preguntas Impulsadas por Creencias (Belief-led Questions)**

Estas preguntas buscan someter a prueba las suposiciones preexistentes del equipo de ingeniería y las afirmaciones categóricas recolectadas en las sesiones de validación respecto al valor del producto:

- **Basada en el "Who" (Stakeholders) y "Why" (Seguridad frente a WhatsApp):**
  - *Pregunta:* ¿Cómo afecta la migración de un canal informal (WhatsApp) a un entorno unificado 100% móvil en la tasa de lectura a tiempo de los comunicados urgentes por parte de los empleados?
  - *Premisa a probar:* Se cree que al tener los colaboradores el dispositivo móvil permanentemente a la mano, un entorno corporativo dedicado incrementa la velocidad de recepción sin vulnerar su privacidad al usar identidades exclusivamente corporativas.
- **Basada en el "What" (Estructura de Anuncios) y el riesgo de Spam:**
  - *Pregunta:* ¿En qué medida la restricción jerárquica de los permisos de publicación de anuncios globales reduce la sobrecarga de información y el desorden visual en la pantalla principal de la aplicación móvil?
  - *Premisa a probar:* Se asume que permitir que el 100% de los empleados publique anuncios globales degrada la priorización de comunicados críticos, siendo necesario limitar esta función a jefes de área o gerencias para mantener la cohesión.
- **Basada en el "How" (Desarticulación de Eventos) y la brecha de Asistencia:**
  - *Pregunta:* ¿De qué manera la inclusión de un mecanismo interactivo de confirmación binaria de asistencia (*Aceptar/Rechazar*) incrementa la predictibilidad logística de la gerencia en comparación con un flujo de notificación puramente pasivo y unidireccional?
  - *Premisa a probar:* Se cree que los coordinadores de las PyMEs requieren una confirmación activa del colaborador en la app móvil para mitigar los errores de ejecución y la duplicación de esfuerzos descritos en el diagnóstico inicial.

**Preguntas Exploratorias (Exploratory Questions)**

Estas preguntas están orientadas a explorar y recopilar conocimiento cuantitativo en áreas técnicas y de comportamiento donde el equipo carece de datos previos:

- **Basada en el "When" (Latencia en Operaciones en el Día a Día):**
  - *Pregunta:* ¿Cuál es el umbral máximo de tiempo de espera (latencia en segundos) que un gerente tolera al cargar el módulo analítico desde la tarjeta de un anuncio antes de abandonar la tarea o percibir que la interfaz se ha congelado?
- **Basada en el "How Much" (Pérdida de Productividad e Ineficiencia Operativa):**
  - *Pregunta:* ¿Cuántos segundos adicionales invierte un usuario al ejecutar un proceso de actualización manual (*pull-to-refresh*) en una pantalla externa para reflejar los miembros de su organización, en comparación con un sistema con manejo de estado reactivo y automatizado?
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
| **Q1** | ¿Cuál es el umbral máximo de tiempo de espera (latencia) que un gerente tolera al cargar el módulo analítico desde el anuncio antes de percibir que la interfaz se congeló? | **Crítico para la retención.** Si la latencia en Render/Supabase congela la app, el gerente abandonará la auditoría, destruyendo el valor del core analítico. | 2               | **5**            | 5              | 5              | **17**    |
| **Q2** | ¿En qué medida la restricción jerárquica de los permisos de publicación reduce la sobrecarga de información y el desorden visual en la pantalla móvil? | **Evitar degradación de la UX.** Si el feed global se satura de spam por falta de roles, los comunicados urgentes perderán visibilidad por completo. | 3               | **4**            | 5              | 4              | **16**    |
| **Q3** | ¿De qué manera la inclusión de un mecanismo de confirmación binaria de asistencia (*Aceptar/Rechazar*) incrementa la predictibilidad logística de la gerencia? | **Cierre de brecha de valor.** El usuario asume que un evento requiere respuesta activa; sin esto, el flujo es unidireccional e ineficiente. | 2               | **4**            | 4              | 4              | **14**    |
| **Q4** | ¿Cuántos segundos adicionales invierte un usuario al ejecutar un refresco manual (*pull-to-refresh*) en comparación con un manejo de estado reactivo? | **Optimización de flujos.** Mitiga la fricción heurística detectada donde el usuario debe adivinar cuándo actualizar la pantalla externa. | 3               | **3**            | 4              | 4              | **14**    |
| **Q5** | ¿Cómo afecta la migración de WhatsApp a un entorno unificado móvil en la tasa de lectura a tiempo de los comunicados urgentes? | **Validar el Core Business.** Justifica la existencia de Centralis frente a los canales informales del mercado de PyMEs. | 4               | **2**            | 5              | 4              | **15**    |

### 8.1.5. Experiment Cards

En esta sección se formalizan los instrumentos de diseño experimental para las hipótesis de mayor criticidad y riesgo técnico identificadas en el *Question Backlog*. Cada tarjeta opera como un contrato científico que delimita el entorno de prueba, los indicadores clave de rendimiento (KPI) y los umbrales cuantitativos que determinarán si una suposición se consolida como característica definitiva en la arquitectura de producción de **Centralis** o si debe ser descartada.

Tarjeta de Experimento 1 (EX-01): Optimización de la Latencia del Core Analítico

| **Componente EDD**     | **Detalle y Especificación Técnica del Experimento**         |
| ---------------------- | ------------------------------------------------------------ |
| **Origen del Backlog** | **Q1:** ¿Cuál es el umbral máximo de latencia que un gerente tolera antes de percibir que la interfaz de analíticas se congeló? |
| **Hipótesis (Belief)** | **Creemos que** optimizar las consultas relacionales hacia Supabase e implementar un estado visual de carga (Shimmer/Spinner animado) en la transición de la pantalla de analíticas, **para** los administradores que auditan lecturas corporativas, **dará como resultado** un incremento en la tasa de éxito de la tarea y reducirá la percepción de congelamiento del sistema (*"se quedó cargando"*). |
| **Prueba (Test)**      | Desarrollar una prueba A/B en el entorno móvil. El **Grupo A (Control)** mantendrá la carga asíncrona directa actual sin indicadores intermedios. El **Grupo B (Experimental)** incluirá la optimización del backend en Render y la renderización del widget de carga reactivo. |
| **Métrica (Metric)**   | 1. Tiempo promedio de respuesta de la API de analíticas (medido en milisegundos desde Render).<br /> 2. Tasa de abandono de la pantalla por parte del usuario (%). |
| **Criterio de Éxito**  | **Estaremos en lo correcto si:** El tiempo de respuesta del servidor se reduce por debajo de los **1.5 segundos** y la tasa de abandono disminuye en más de un **80%** en el Grupo B en comparación con el Grupo A. |

Tarjeta de Experimento 2 (EX-02): Confirmación Binaria de Asistencia a Eventos

| **Componente EDD**     | **Detalle y Especificación Técnica del Experimento**         |
| ---------------------- | ------------------------------------------------------------ |
| **Origen del Backlog** | **Q3:** ¿De qué manera la inclusión de un mecanismo de confirmación de asistencia incrementa la predictibilidad logística? |
| **Hipótesis (Belief)** | **Creemos que** integrar botones interactivos de confirmación activa (*Aceptar / Rechazar asistencia*) en las tarjetas de eventos dentro del feed del empleado, **para** los colaboradores de las PyMEs, **dará como resultado** un ecosistema de retroalimentación bidireccional que otorgará un respaldo logístico inmediato a la gerencia, eliminando la desarticulación operativa de calendarios externos desincronizados. |
| **Prueba (Test)**      | Desplegar una versión de prueba de la app Flutter con 4 empleados. Se les asignará la tarea de revisar el cronograma semanal y confirmar su asistencia a una capacitación corporativa simulada. |
| **Métrica (Metric)**   | 1. Tasa de interacción activa con el componente (Total de clics en Aceptar/Rechazar entre Total de usuarios asignados).<br /> 2. Tiempo promedio de conversión de confirmación (horas desde la publicación del evento). |
| **Criterio de Éxito**  | **Estaremos en lo correcto si:** Al menos el **85%** de los empleados interactúa proactivamente con el componente binario dentro de las primeras 12 horas de emitido el evento, alcanzando un índice de error operativo del 0% para la gerencia |

Tarjeta de Experimento 3 (EX-03): Sincronización Reactiva de Estados (State Management)

| **Componente EDD**     | **Detalle y Especificación Técnica del Experimento**         |
| ---------------------- | ------------------------------------------------------------ |
| **Origen del Backlog** | **Q4:** ¿Cuántos segundos adicionales invierte un usuario al ejecutar un refresco manual (*pull-to-refresh*) en una pantalla externa? |
| **Hipótesis (Belief)** | **Creemos que** reestructurar el flujo con un gestor de estado reactivo en Flutter (sincronización automática de hilos con la base de datos de Supabase), **para** los gerentes que asignan empleados a un evento o chat grupal, **dará como resultado** la erradicación del gesto manual invasivo de retroceder al perfil y deslizar hacia abajo para refrescar los miembros del equipo. |
| **Prueba (Test)**      | Medición por cronómetro (*Time-to-Task*) de usuarios del segmento gerencial clonando el flujo. El **Grupo A** usará el flujo actual con recarga manual; el **Grupo B** operará con la reactividad automatizada en la vista de selección. |
| **Métrica (Metric)**   | 1. Tiempo de conversión total de la tarea de creación de un evento grupal (en segundos). <br />2. Número de acciones/clicks innecesarios realizados en la pantalla de asignación. |
| **Criterio de Éxito**  | **Estaremos en lo correcto si:** Los usuarios del Grupo B completan la estructuración y asignación del evento en un tiempo promedio menor a **15 segundos**, logrando una reducción del **100%** en la necesidad de ejecutar gestos de refresco manuales fuera del flujo. |

## 8.2. Experiment Design

### 8.2.1. Hypotheses

### 8.2.2. Domain Business Metrics

### 8.2.3. Measures

### 8.2.4. Conditions

### 8.2.5. Scale Calculations and Decisions

### 8.2.6. Methods Selection

### 8.2.7. Data Analytics: Goals, KPIs and Metrics Selection

### 8.2.8. Web and Mobile Tracking Plan

## 8.3. Experimentation

### 8.3.1. To-Be User Stories

### 8.3.2. To-Be Product Backlog