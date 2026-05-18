# Examen: Ingeniería de Software - Pregunta 3

## Propuesta de Manejo de Migración y Carga Inicial (MCI) en Extreme Programming (XP)

Para abordar la complejidad de la Migración y Carga Inicial (MCI) en la institución financiera, se propone una estrategia que integra la agilidad de XP con el rigor técnico necesario para la gestión de datos críticos.

### 1. Categorización de los requerimientos de MCI
En este contexto de alta incertidumbre y obsolescencia, los requerimientos de MCI no deben tratarse como Historias de Usuario (HU) convencionales, sino mediante una combinación de **Spikes** y **Tareas Técnicas**.

* **Spikes (Investigación):** Debido a que las reglas de negocio están ocultas en el sistema legado y los procesos no están documentados, se deben dedicar iteraciones iniciales a realizar *Spikes* de exploración. El objetivo es realizar ingeniería inversa sobre los datos y el código antiguo para descubrir la lógica real antes de intentar migrar.
* **Tareas Técnicas:** Una vez que la incertidumbre técnica disminuye gracias a los Spikes, la ejecución del ETL se descompone en tareas técnicas asociadas a las historias de usuario funcionales que requieren esos datos.
* **Justificación:** Tratar la MCI como HU es inviable porque el cliente no puede definir los criterios de aceptación técnicos de un ETL. Un Spike permite al equipo fallar rápido y aprender sobre la "deuda histórica" sin comprometer la velocidad de la funcionalidad visible.

### 2. Riesgos de forzar la MCI en Historias de Usuario
Si el equipo intenta encajar la migración en el formato "Como [rol], quiero [acción], para [valor]", aparecen riesgos críticos:
* **Historias "Hinchadas" e Imposibles de Estimar:** La incertidumbre sobre la calidad del dato legado haría que las estimaciones fueran pura ficción.
* **Criterios de Aceptación Superficiales:** El cliente validaría que "ve los datos", pero no podría validar si la integridad financiera o la trazabilidad se mantuvo en las capas profundas.
* **Negligencia de Requerimientos No Funcionales:** Se corre el riesgo de ignorar la limpieza de duplicados y la consistencia estructural por cumplir con el formato narrativo de la historia.

### 3. Conflicto: Funcionalidad Visible vs. Integridad de Datos
Existe una tensión real entre la presión política por "apagar el sistema" y la necesidad de integridad. En XP, el valor de negocio no es solo una pantalla nueva; la **integridad de los datos históricos** es un requisito de supervivencia organizacional.
* **Resolución:** La integridad debe considerarse una "restricción del sistema" (o parte de la *Definition of Done*). No se puede dar por terminada una funcionalidad si los datos que la sustentan no han pasado las pruebas de auditoría y trazabilidad. La "funcionalidad visible" sin datos íntegros es una ilusión de progreso que genera riesgo sistémico.

### 4. Participación de los Stakeholders
La MCI es un esfuerzo multidisciplinario que requiere:
* **Usuarios del negocio:** Definen la semántica de los datos (qué significa un campo hoy).
* **Especialistas técnicos:** Diseñan y ejecutan las tuberías ETL robustas.
* **Personal operativo del sistema legado:** Son los "arqueólogos" que poseen el **conocimiento tácito** de las excepciones y parches aplicados durante 15 años. Su participación es vital para el descubrimiento de reglas no escritas.
* **Auditores o áreas de control:** Establecen los umbrales de error tolerables y los protocolos de validación para garantizar que el nuevo sistema sea auditable desde el día uno.

### 5. Información que NO debe depender únicamente del cliente
Dado que el cliente no domina conceptos ETL y el sistema legado es una "caja negra", el equipo de desarrollo debe asumir la responsabilidad de descubrir:
* **La estructura real y calidad del dato:** El cliente dirá qué "debería" haber; el equipo debe verificar qué hay realmente (inconsistencias, nulos, duplicados).
* **Reglas de transformación técnica:** El mapeo exacto de estructuras obsoletas a la nueva arquitectura.
* **Manejo de excepciones históricas:** Qué hacer con registros que violan las reglas de negocio actuales pero que existen en el histórico.

### 6. Consecuencia más grave de un manejo incorrecto
La consecuencia más grave no es que el sistema falle técnicamente, sino la **pérdida de la integridad y trazabilidad financiera**. Si se migran datos erróneos, la institución podría:
* Fallar en auditorías regulatorias, acarreando multas millonarias.
* Tomar decisiones estratégicas basadas en saldos o históricos de clientes incorrectos.
* Perder la confianza del mercado, lo cual, para una institución financiera, es un daño irreversible que trasciende cualquier éxito de software.

---

### Análisis de la afirmación del Arquitecto
*"La migración no genera valor de negocio visible; por lo tanto, no debería consumir iteraciones importantes de XP."*

Esta afirmación es **extremadamente peligrosa**. Ignorar la migración bajo la premisa de que "no se ve" es confundir valor estético con valor estructural. La MCI es la que garantiza que el nuevo sistema tenga continuidad operativa. 
* **¿Cuándo podría ser razonable?** Solo en un escenario donde el sistema anterior se mantenga encendido como archivo de consulta y el nuevo sistema comience desde cero (Greenfield). Sin embargo, bajo la **presión política de reducir costos de operación paralela**, la migración se vuelve el camino crítico del proyecto y debe consumir iteraciones prioritarias.

---

### Complemento de XP con otros enfoques
XP puro, aunque excelente para la construcción de software, es insuficiente para este proyecto. Se requiere complementar con:
* **Ingeniería de Requisitos orientada a Puntos de Vista:** Para gestionar el conflicto entre la agilidad exigida por gerencia y el rigor exigido por los auditores.
* **Modelado de Datos (DDD - Domain-Driven Design):** Para asegurar que la transformación de los datos del sistema legado se alinee con el nuevo modelo de dominio y no solo se "copien los vicios" del pasado.
* **Gestión de Riesgos Explícita:** XP gestiona el riesgo a través de ciclos cortos, pero un error en migración bancaria requiere una evaluación de riesgos formal (estilo Espiral) para decidir las estrategias de *rollback* y los puntos de no retorno en la transición.