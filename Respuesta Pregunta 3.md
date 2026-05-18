# Respuesta — Pregunta 3

## Migración y Carga Inicial en XP: Cuando el Backlog No Alcanza

---

## I. Categorización de los Requerimientos de MCI en XP

El documento de cátedra (Tema 3) describe a XP como una metodología donde "los requerimientos se registran en tarjetas de historias" y los desarrolladores las descomponen en "tareas de programación". Esta definición asume una condición que el enunciado viola explícitamente: que existe alguien capaz de describir *qué* se requiere. En la MCI bancaria, esa condición no se cumple.

Tratar la MCI como **Historias de Usuario convencionales es inviable** por una razón técnica precisa: el formato "Como [rol], quiero [acción], para [valor de negocio]" exige que el usuario pueda articular un comportamiento observable. La extracción, transformación y carga de un legado de 15 años con inconsistencias estructurales, duplicados y reglas de negocio no documentadas NO produce un comportamiento observable para el usuario final —produce datos. Y los datos correctos son la precondición silenciosa de toda funcionalidad visible.

La estrategia correcta combina tres mecanismos de forma secuencial y deliberada:

**1. Spikes de investigación (iteraciones 1-2).** Dado que nadie conoce completamente las reglas reales del sistema antiguo, el punto de partida obligatorio es la exploración. XP contempla los Spikes como iteraciones de tiempo fijo dedicadas a reducir incertidumbre técnica antes de comprometerse con estimaciones. En este caso, los Spikes deben responder preguntas precisas: ¿qué tan sucia es la data? ¿qué reglas de transformación existen implícitamente en el código legado? ¿qué excepciones históricas han sido parches manuales? Sin estas respuestas, cualquier estimación de la MCI será ficción.

**2. Tareas técnicas (no historias) vinculadas al Definition of Done.** Una vez reducida la incertidumbre, los componentes ETL se modelan como tareas técnicas asociadas a las historias funcionales que dependen de ellos. No son independientes: ninguna historia de usuario puede darse por "terminada" si los datos que la sustentan no han pasado validación de integridad. La Ingeniería de Requerimientos (Tema 5) establece que los requerimientos de sistema deben estar "completos y ser consistentes" —la MCI es el proceso que garantiza esa consistencia en la capa de datos.

**3. Actividad paralela con gestión de riesgos explícita.** La MCI no puede competir por puntos de historia con funcionalidades visibles. Debe ejecutarse en un carril paralelo con su propio calendario, sus propios criterios de aceptación técnicos y su propia supervisión. El Tema 4 advierte que en proyectos complejos "las estimaciones son siempre optimistas" y recomienda agregar un 30% al tiempo estimado y un 20% adicional para imprevistos. Ambos márgenes aplican con especial urgencia a la MCI.

**Justificación integrada:** Esta combinación respeta el espíritu de XP (ciclos cortos, retroalimentación continua, adaptabilidad) sin forzar una plantilla narrativa sobre un problema de naturaleza arqueológica y técnica.

---

## II. Riesgos de Forzar la MCI en el Formato de Historias de Usuario

Si el equipo cede a la presión de los desarrolladores que afirman "si no puede escribirse como historia de usuario, no pertenece al backlog", se activan riesgos sistémicos que van más allá del software:

**Criterios de aceptación inaplicables.** La historia de usuario "Como auditor, quiero ver el historial de transacciones para verificar compliance" puede cerrarse cuando la pantalla muestra datos. Pero si esos datos fueron migrados sin validar la integridad referencial, la historia "pasa" técnicamente mientras el riesgo regulatorio se acumula de forma invisible. El Tema 5 es explícito: los requerimientos deben ser *verificables* —y en el caso de la MCI, la verificabilidad requiere pruebas de auditoría que trascienden el criterio de aceptación funcional típico.

**Estimaciones de ficción.** El Tema 4 señala que los "cambios en los requerimientos" y la "estimación subestimada" son riesgos de probabilidad alta con efectos catastróficos. En la MCI, la incertidumbre sobre la calidad del dato es estructural: el equipo no sabe lo que no sabe. Encajar esa incertidumbre en puntos de historia produce compromiso sin información, lo que corrompe la planificación de toda la iteración.

**Negligencia del conocimiento tácito.** El Tema 6 describe la etnografía como técnica para capturar "los requerimientos que se derivan de lo que la gente realmente hace en contraposición con las definiciones formales". En un sistema legado de 15 años, ese conocimiento tácito vive en el personal operativo —no en el cliente de negocio. Un formato de historia de usuario escrita por el cliente ignora esa fuente crítica de información.

**Deuda histórica sin visibilidad.** Una historia cerrada desaparece del tablero. Si la MCI se trata como historias que "se completan" iteración a iteración, los problemas de integridad quedan fuera del radar del equipo hasta que un auditor los descubre post-producción. En una institución financiera, ese momento puede implicar sanciones regulatorias que dwarfan cualquier beneficio de velocidad de entrega.

---

## III. El Conflicto Real: Funcionalidad Visible vs. Integridad de Datos Históricos

Este es el nudo central de la pregunta, y exige ser formulado con precisión: no se trata de un conflicto entre *velocidad* e *integridad* —se trata de un conflicto entre **valor aparente** y **valor real**.

XP define su primer principio como "la razón de su existencia": todo software debe aportar valor real al usuario (Tema 2). Una pantalla que muestra transacciones incorrectas no aporta valor real; genera la *ilusión* de valor mientras erosiona la confianza de la institución, distorsiona decisiones financieras y expone a la organización a consecuencias legales.

La presión política por "apagar rápidamente el sistema anterior" introduce lo que el Tema 4 clasifica como **riesgo organizacional de alta probabilidad y efecto catastrófico**: cuando los problemas financieros u organizacionales obligan a comprimir el proyecto, la calidad —y en este caso, la integridad de los datos— es siempre la primera víctima.

La resolución correcta no es "balancear" ambos objetivos —es reconocer que la integridad de datos es una **restricción del sistema, no un requerimiento opcional**. Debe formar parte de la *Definition of Done* de cualquier historia que dependa de datos históricos. No puede liberarse una funcionalidad financiera si los datos subyacentes no han pasado las pruebas de integridad definidas con los auditores.

La operación paralela de ambos sistemas —el legado y el nuevo— no es un costo evitable: es el mecanismo de control más básico disponible. Presionar por apagar el sistema legado antes de que la MCI esté validada equivale a demoler el andamio antes de que la estructura soporte su propio peso.

---

## IV. Participación de los Stakeholders

XP establece que "un representante de los usuarios finales debe estar disponible al equipo a tiempo completo" (Tema 3, Roles en XP: Cliente). En un proyecto de migración financiera, un solo representante de cliente es insuficiente. La complejidad exige una estructura más articulada:

**Usuarios del negocio.** Definen la semántica actual de los datos: qué significa un campo, qué regla de negocio rige hoy, qué excepciones son legítimas y cuáles son errores históricos. Su participación no es en la especificación del ETL —es en la validación del significado de los datos transformados. El Tema 6 advierte que "los stakeholders expresan los requerimientos con un conocimiento implícito de su propio trabajo": hay que extraer ese conocimiento mediante técnicas activas (entrevistas estructuradas, revisión de escenarios reales).

**Especialistas técnicos.** Diseñan y ejecutan las tuberías ETL. Son los únicos capaces de traducir las reglas semánticas del negocio en transformaciones verificables. Dado que el Tema 6 incluye los requerimientos de "interoperabilidad con otros sistemas" como requerimientos externos, estos especialistas deben también garantizar la compatibilidad entre el esquema legado y la arquitectura nueva.

**Personal operativo del sistema legado.** Son los "arqueólogos" del proyecto. Poseen el conocimiento tácito de 15 años de parches, excepciones, ajustes manuales y procesos no documentados. La etnografía (Tema 6) es aquí la técnica más valiosa: observar cómo trabajan, no solo preguntarles. Muchas reglas reales están en sus hábitos operativos, no en sus respuestas a entrevistas.

**Auditores y áreas de control.** Definen los criterios de aceptación que el equipo de negocio no puede definir: umbrales de error tolerables, protocolos de validación, trazabilidad requerida por ley. Su participación es desde el inicio —no al final cuando piden verificar que "todo esté bien". El Tema 6 clasifica los requerimientos legales y regulatorios como **requerimientos no funcionales externos** de carácter no negociable.

---

## V. Información que NO Debe Depender Únicamente del Cliente

El enunciado establece que "el cliente NO domina conceptos ETL". El Tema 5 documenta esta limitación como un fenómeno estructural: "puede resultarles difícil expresar lo que quieren que el sistema lleve a cabo" y "expresan los requerimientos con un conocimiento implícito de su propio trabajo". Aceptar este límite no es una crítica al cliente —es una descripción técnica de los límites de su dominio.

El equipo de desarrollo y los especialistas técnicos deben asumir la responsabilidad de descubrir autónomamente:

- **La calidad real del dato.** El cliente describirá lo que "debería" haber en la base de datos; el equipo debe auditar lo que *hay*: duplicados, nulos, inconsistencias de tipo, registros huérfanos. Esta brecha entre expectativa y realidad es predecible y debe tratarse como un riesgo de estimación explícito (Tema 4).
- **Las reglas de transformación técnica.** El mapeo entre estructuras de datos obsoletas y el nuevo modelo de dominio es responsabilidad técnica. El cliente puede validar el resultado semántico, pero no puede especificar la transformación.
- **El manejo de registros excepcionales.** Registros que existen en el historial pero violan las reglas de negocio actuales (transacciones de cuentas cerradas, saldos negativos históricos, etc.) requieren decisiones técnico-legales que el cliente no puede tomar unilateralmente.
- **Los requisitos de trazabilidad regulatoria.** Qué campos deben conservarse, con qué granularidad y durante cuánto tiempo es materia regulatoria —no preferencia del usuario.

---

## VI. La Consecuencia Más Grave del Manejo Incorrecto

La pregunta plantea el escenario más peligroso: un sistema que "funciona técnicamente bien" pero fue migrado de forma deficiente. Este es el escenario donde el daño es estructuralmente diferido e irreversible.

La consecuencia más grave no es un fallo técnico detectable —es la **corrupción silenciosa de la verdad operativa de la institución**. Si los datos migrados contienen errores no detectados, la institución comienza a operar sobre una realidad falsa que nadie puede corregir retroactivamente: saldos incorrectos en registros históricos, trazabilidad de transacciones rota, auditorías basadas en información que no refleja lo que realmente ocurrió.

En el contexto regulatorio financiero, esto puede implicar:
- Incumplimiento de normativas de compliance que exigen trazabilidad completa de operaciones.
- Sanciones de entes reguladores basadas en registros que el sistema reporta incorrectamente.
- Decisiones estratégicas (provisiones de riesgo, clasificación de cartera, estados financieros) construidas sobre datos viciados.
- Pérdida de la habilitación para operar, en casos extremos.

El Tema 4 clasifica los problemas financieros organizacionales derivados de errores de proyecto como riesgos de **efecto catastrófico**. En una institución financiera, la integridad de los datos históricos es el activo más crítico —más que el código. Un software nuevo con datos corruptos es peor que el sistema legado con datos imperfectos, porque al menos el legado es conocido y auditado.

---

## Análisis de la Afirmación del Arquitecto

*"La migración no genera valor de negocio visible; por lo tanto, no debería consumir iteraciones importantes de XP."*

Esta afirmación es **peligrosa en el contexto específico del enunciado, y sólo razonable bajo supuestos que el caso no cumple**.

**Por qué es peligrosa:** Confunde "valor visible" con "valor real". El Principio 1 del desarrollo de software (Tema 2) establece que todo software debe responder a la pregunta "¿esto añade VALOR REAL?". Los datos íntegros no son visibles, pero son la precondición de toda funcionalidad que sí lo sea. Negar iteraciones a la MCI es construir el sistema nuevo sobre cimientos que nadie ha verificado —es la versión digital de inaugurar un edificio sin haber inspeccionado las fundaciones.

Además, la afirmación ignora el riesgo organizacional documentado en el Tema 4: cuando la presión política impone una fecha de apagado del sistema legado, la MCI deja de ser optativa y se convierte en el camino crítico del proyecto. Minimizarla no la elimina —la convierte en un pasivo no gestionado.

**Cuándo podría ser razonable:** Si la institución decidiera mantener el sistema legado como archivo de consulta sin apagarlo, y el nuevo sistema comenzara desde cero (enfoque *greenfield*), la afirmación tendría fundamento parcial. En ese escenario, la migración sería opcional y diferible. Pero el enunciado describe explícitamente "presión política para apagar rápidamente el sistema anterior" —lo que hace que ese escenario alternativo sea inaplicable.

---

## ¿Es XP Puro Suficiente?

No. Y la razón no es que XP sea una metodología débil —es que XP fue diseñado bajo una precondición que este proyecto viola: que los requerimientos, aunque cambiantes, son articulables por el cliente.

XP puro requiere complementarse con tres elementos que no contradigan su espíritu ágil sino que lo sustenten:

**Ingeniería de Requerimientos orientada a Puntos de Vista (Tema 6).** Los conflictos entre la gerencia (velocidad), los auditores (integridad), el personal operativo (conocimiento tácito) y los desarrolladores (factibilidad técnica) no se resuelven con más historias de usuario —se resuelven con un proceso estructurado de descubrimiento y negociación de requerimientos que reconozca a cada grupo como fuente legítima de restricciones. El análisis de puntos de vista es precisamente la herramienta para esto.

**Gestión de Riesgos explícita con categorización formal (Tema 4).** XP gestiona el riesgo a través de ciclos cortos y retroalimentación. Pero un error en migración bancaria no se puede detectar en la siguiente iteración —puede permanecer latente durante años. Se requiere un análisis de riesgos formal que clasifique la probabilidad y el efecto de los escenarios de corrupción de datos, y que defina estrategias de prevención, minimización y planes de contingencia antes de que el proceso de migración comience.

**Modelado de Datos con trazabilidad explícita.** El Tema 4 documenta la necesidad de herramientas que generen "puntos de control" y productos verificables en cada fase. Para la MCI, esto se traduce en un modelo de datos de origen, un modelo de datos de destino, y reglas de transformación versionadas y auditables —artefactos que XP puro no prescribe pero que en este contexto son requisitos de compliance, no burocracia opcional.

La combinación correcta no es "usar un híbrido" genérico —es identificar con precisión cuáles limitaciones de XP son estructurales en este contexto, y cubrirlas con herramientas específicas sin abandonar la agilidad donde sí aplica.

---

### Referencias

- Renaud, O. (s.f.). *Tema 2: Metodología de Desarrollo de Software*. UCAB – Ext. Guayana.
- Renaud, O. (s.f.). *Tema 3: Metodologías de Desarrollo – XP y Ágiles*. UCAB – Ext. Guayana.
- Renaud, O. (s.f.). *Tema 4: Inicio del Proyecto – Gestión de Proyectos y Riesgos*. UCAB – Ext. Guayana.
- Renaud, O. (s.f.). *Tema 5: Especificación de Requerimientos – Ingeniería de Requerimientos*. UCAB – Ext. Guayana.
