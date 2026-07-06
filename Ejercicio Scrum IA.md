# Trabajo Práctico: Implementación de Scrum con Inteligencia Artificial

**Institución:** Universidad Abierta Interamericana (UAI)  
**Carrera:** Ingeniería en Sistemas Informáticos  
**Asignatura:** Metodologías Ágiles  
**Alumno:** Alvaro Gaston Morales  
**Fecha:** 6 de julio de 2026  

---

## Introducción
El presente documento detalla la resolución de los ejercicios de simulación de un entorno ágil (Scrum) apoyado en herramientas de Inteligencia Artificial. El caso de estudio aplicado corresponde al proyecto de desarrollo de una aplicación web para una empresa de logística.

---

## 1. Ejercicio 18: Secuencia de Prompts Scrum

A continuación se detallan los 5 prompts concatenados, diseñados para que la salida de uno funcione como entrada del siguiente. Se ha respetado la estructura recomendada: Contexto, Instrucción, Input y Output, aplicando técnicas de ingeniería de prompts para obtener resultados técnicos de alta calidad.

### 1.1. Prompt 1: Definición del Product Backlog

> **Contexto:** Actúa como un Product Owner experto en metodologías ágiles y en el dominio de desarrollo de software logístico. 
> **Instrucción:** Toma los requerimientos iniciales del cliente y transfórmalos en un Product Backlog inicial. Redacta historias de usuario utilizando el formato estándar ("Como [rol], quiero [acción] para [beneficio]") y define criterios de aceptación claros para cada una.
> **Input:** Los requerimientos iniciales son:
> - Registro y autenticación de usuarios.
> - Creación y seguimiento de envíos.
> - Generación de reportes de estado de envíos.
> - Integración con sistemas de terceros para rastreo de envíos.
> **Output:** Entrégame el resultado en formato de tabla Markdown con las columnas: ID, Historia de Usuario, Prioridad (Alta/Media/Baja) y Criterios de Aceptación.

**Resultado Obtenido:**

| ID | Historia de Usuario | Prioridad | Criterios de Aceptación |
| :--- | :--- | :--- | :--- |
| US-01 | Como usuario, puedo registrarme e iniciar sesión en la aplicación para acceder a mi panel. | Alta | 1. El registro requiere email válido y contraseña segura. 2. El login debe generar un token JWT. |
| US-02 | Como usuario, puedo crear un nuevo envío y seguir su estado para saber dónde está mi paquete. | Alta | 1. Formulario con origen, destino y peso. 2. Generación de un código de tracking alfanumérico. |
| US-03 | Como usuario, puedo generar reportes de estado de mis envíos para tener un control histórico. | Media | 1. Opción de exportar a PDF y CSV. 2. Filtros por rango de fechas. |
| US-04 | Como sistema, debo integrarme con APIs de terceros para centralizar el rastreo de envíos externos. | Alta | 1. Conexión exitosa vía webhooks. 2. Actualización de estado en tiempo real. |



---

### 1.2. Prompt 2: Planificación del Sprint

> **Contexto:** Actúa como un Scrum Master técnico facilitando la ceremonia de Sprint Planning.
> **Instrucción:** Toma el Product Backlog generado y crea un Plan para el Sprint 1. Desglosa cada historia de usuario en tareas técnicas específicas y asígnalas a los Desarrolladores (A, B, C y D) asegurando una carga de trabajo equilibrada.
> **Input:** *[Se ingresa la tabla obtenida en el Prompt 1]*
> **Output:** Un plan de Sprint en formato de lista, detallando la US, las tareas técnicas, el responsable asignado y la estimación en horas.

**Resultado Obtenido:**
* **US-01: Registro e inicio de sesión**
  * Tarea 1.1: Crear esquema de base de datos relacional para usuarios (Desarrollador A - 4h).
  * Tarea 1.2: Implementar endpoints de autenticación y seguridad en el backend (Desarrollador A - 8h).
* **US-02: Creación y seguimiento de envíos**
  * Tarea 2.1: Diseñar formulario en el frontend y validaciones (Desarrollador B - 6h).
  * Tarea 2.2: Implementar lógica backend para generación del código de tracking (Desarrollador B - 6h).
* **US-03: Reportes de estado**
  * Tarea 3.1: Integrar librería de generación de documentos PDF/CSV (Desarrollador C - 8h).
* **US-04: Integración con sistemas de terceros**
  * Tarea 4.1: Desarrollar consumo de APIs REST externas y mapeo de datos JSON (Desarrollador D - 12h).


---

### 1.3. Prompt 3: Ejecución del Sprint

> **Contexto:** Actúa como el Development Team (Equipo de Desarrollo) reportando el final del Sprint.
> **Instrucción:** Simula la ejecución del Sprint basándote en el plan provisto. Describe el incremento de software funcional generado, indicando si las tareas se completaron exitosamente y mencionando el stack tecnológico utilizado.
> **Input:** *[Se ingresa la lista de tareas del Prompt 2]*
> **Output:** Un resumen narrativo del Incremento de Software Funcional, separado por viñetas para cada módulo.

**Resultado Obtenido:**
El Sprint 1 ha finalizado con éxito, entregando el siguiente incremento de software funcional desplegado en el entorno de pruebas:
* **Módulo de Acceso:** Se implementó un sistema de registro y login seguro utilizando Node.js y encriptación bcrypt, permitiendo a los usuarios autenticarse correctamente.
* **Gestión de Envíos:** La interfaz desarrollada en React permite registrar nuevos paquetes, los cuales se guardan en la base de datos PostgreSQL, generando automáticamente el código de tracking.
* **Reportes e Integración:** Se finalizó el motor de exportación de reportes y la comunicación con la API externa funciona correctamente mediante webhooks, actualizando el estado de los paquetes de forma sincronizada.



---

### 1.4. Prompt 4: Revisión del Sprint

> **Contexto:** Actúa como el Cliente (Empresa de Logística) y los Stakeholders clave durante la ceremonia de Sprint Review.
> **Instrucción:** Evalúa el incremento de software funcional presentado por el equipo. Genera una retroalimentación realista y redacta las lecciones aprendidas detectadas durante el ciclo de desarrollo.
> **Input:** *[Se ingresa la narrativa del Prompt 3]*
> **Output:** Dos secciones claras: 1. Retroalimentación del cliente. 2. Lecciones aprendidas por el equipo.

**Resultado Obtenido:**

**Retroalimentación del cliente:**
* El cliente está muy satisfecho con la fluidez del inicio de sesión y la claridad de la interfaz para crear envíos.
* **Nuevo Requerimiento:** El cliente sugiere agregar con prioridad una opción para enviar notificaciones automáticas (vía email/SMS) a los destinatarios cuando el estado de su envío cambia.

**Lecciones Aprendidas del Equipo:**
* Faltó comunicación temprana sobre el diseño exacto que debía tener el PDF de los reportes, lo que causó demoras en el desarrollo de esa funcionalidad.
* Es necesario implementar pruebas unitarias más exhaustivas en la integración con la API externa antes de dar la tarea por finalizada.

* **Técnicas Utilizadas:** *Constraint Prompting* (forzar la inclusión de puntos positivos, áreas de mejora y nuevos requerimientos) y *Simulación de Stakeholders*.

---

### 1.5. Prompt 5: Retrospectiva del Sprint

> **Contexto:** Actúa como el Scrum Master liderando la Sprint Retrospective con el equipo interno.
> **Instrucción:** Analiza la retroalimentación del cliente y las lecciones aprendidas. Construye un plan de mejora accionable para aplicar en el Sprint 2.
> **Input:** *[Se ingresan las listas del Prompt 4]*
> **Output:** Un plan de mejora detallado (Action Items) especificando qué se hará, cómo se implementará y qué modificaciones sufrirá el próximo Backlog.

**Resultado Obtenido:**

**Plan de Mejora para el Sprint 2:**
1. **Mejora en la Comunicación:** Se implementarán reuniones de refinamiento (Refinement) de 30 minutos a mitad del Sprint para aclarar detalles con el PO (ej. formato visual de los reportes) antes de iniciar la programación.
2. **Calidad Técnica:** Se agregará a los Criterios de Terminado (*Definition of Done*) que toda integración con APIs de terceros debe incluir cobertura de pruebas unitarias y de integración.
3. **Actualización del Backlog:** Se priorizará e incorporará en el Sprint 2 el desarrollo de la funcionalidad solicitada por el cliente: "Envío de notificaciones automáticas a usuarios sobre el estado de sus envíos".



---

## 2. Ejercicio 19: Diseño de Bots (PoE) para Roles Scrum

Para configurar agentes en plataformas como Poe.com, se deben definir *System Prompts* estrictos que delimiten la personalidad y las funciones de cada rol.

* **Bot Cliente:** "Eres el cliente logístico de una aplicación web. Tu objetivo es formular requerimientos de negocio al PO de manera funcional, enfocándote en las necesidades del usuario final sin utilizar tecnicismos. Realizarás simulaciones de pruebas de usuario (UAT) reportando bugs o sugerencias, y emitirás una calificación del 1 al 5 tras cada release entregada."
* **Bot Scrum Master:** "Eres el Scrum Master del equipo de desarrollo. Tu rol es emitir recordatorios diarios a las 09:00 AM para realizar la *Daily Scrum*. Deberás estar atento a cuando los desarrolladores mencionen bloqueos, documentarlos en un registro de impedimentos y sugerir dinámicas ágiles para removerlos y proteger al equipo."
* **Bot Product Owner (Administración):** "Eres el PO del producto logístico. Tu responsabilidad interna es administrar el Product Backlog, asegurando que las historias de usuario estén correctamente priorizadas por valor de negocio. Emitirás recordatorios automáticos 48 horas antes de cada sesión de Sprint Planning."
* **Bot Desarrollador:** "Eres un Desarrollador de Software del equipo. Al recibir el plan del Sprint, te encargarás de recordar y desglosar tus tareas asignadas. Proporcionarás reportes de avance diarios estructurados (Qué hice ayer, qué haré hoy, qué me bloquea) para la Daily."
* **Bot PO (Interacción Externa):** "Eres la faceta pública del Product Owner. Tu tarea es entrevistar de forma interactiva y empática al cliente para extraer, clarificar y refinar requerimientos. Al finalizar cada ciclo, generarás encuestas de satisfacción automatizadas para medir el éxito del incremento entregado."

---

## 3. Recomendaciones y Análisis Final

1. **Técnicas utilizadas en los prompts:**
   Se empleó *Role Prompting* (asignación de roles específicos), *Context Chaining* (flujo secuencial de datos para mantener la coherencia temporal), *Structured Formatting* (tablas y listas), y *Constraint Prompting* (imposición de reglas estrictas para evitar ambigüedades en las respuestas de la IA).
2. **Estrategia de contextualización:**
   La estrategia se basó en establecer el dominio del problema (logística) y la ceremonia de Scrum específica (Planning, Review, etc.) en el bloque de "Contexto" inicial. Esto "ancló" al modelo de lenguaje en el marco mental correcto, garantizando que el vocabulario y las decisiones fueran propias de un equipo de ingeniería de software.
3. **Análisis de resultados de poca calidad:**
   Cuando no se especifica el nivel de detalle técnico (como ocurrió en iteraciones de prueba durante el Prompt 2), la IA tiende a generar tareas genéricas como "Hacer el backend". El motivo es que los LLMs promedian la información si no se los restringe. La solución fue exigir tecnologías, roles y estimaciones horarias, elevando drásticamente la calidad.
4. **Mejoras al proceso de creación de prompts:**
   Una mejora técnica significativa sería implementar técnicas *Few-Shot Prompting*. Es decir, brindarle a la IA en el Prompt 1 un ejemplo exacto de cómo la empresa suele redactar sus historias de usuario o criterios de aceptación, reduciendo el margen de alucinación o desvío de formato.
5. **Visión hacia el futuro: Agentes Autónomos:**
   Para que este proceso sea completamente automático, se debería migrar de ChatGPT a un sistema de orquestación de flujos (como LangChain o n8n). En esta arquitectura, el pipeline comenzaría con el requerimiento del cliente; al procesarlo, dispararía un webhook hacia el "Agente PO" para crear el backlog, que a su vez activaría al "Agente Scrum Master" para la planificación. El trabajo fluiría de forma autónoma pasando los datos en formato JSON entre los nodos de la IA hasta entregar el plan completo del Sprint sin intervención humana.