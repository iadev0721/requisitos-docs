# Respuesta — Pregunta 1

## Selección de Modelos Tradicionales de Proceso de Software bajo Restricciones Reales

---

## I. Sistema de Evaluación de Servicios

### Modelo seleccionado: Entrega Incremental

**¿Por qué este modelo y no otro?** El contexto exige resolver una contradicción: requisitos que el cliente *dice* simples pero que cambia frecuentemente, presión política por resultados visibles, un equipo junior y un plazo de 6 semanas. La Entrega Incremental resuelve esta tensión porque —como establece el Tema 2— "los clientes identifican, a grandes rasgos, los servicios que proporcionará el sistema", se priorizan, y "una vez que un incremento está listo, los clientes pueden ponerlo en servicio, resultando en una entrega temprana de parte de la funcionalidad del sistema". Esto es exactamente lo que los directivos necesitan para liberar presupuesto: algo funcionando, no un documento de especificación.

**Problema crítico que controla:** La **incertidumbre de requisitos disfrazada de simplicidad**. El cliente "cambia frecuentemente de opinión sobre las métricas". Esto no es un requisito simple: es un requisito volátil de tipo *cambiante* (Tema 5 — Especificación de Requerimientos), resultado de que el cliente no comprende del todo su propia necesidad. El modelo incremental permite absorber estos cambios entre incrementos sin desestabilizar lo ya entregado, porque cada incremento es un subconjunto funcional completo que puede validarse de forma independiente.

**Factores del contexto considerados:**

- **Estabilidad de requisitos:** Baja. Las métricas cambian, lo que implica requisitos volátiles. Sin embargo, la funcionalidad base (encuestas, recolección de datos) es estable. El modelo incremental permite separar lo estable (primer incremento) de lo volátil (incrementos posteriores con métricas refinadas).
- **Participación real del usuario:** Los directivos quieren "ver algo funcionando rápido", lo que indica disposición a participar *si el sistema existe*. El modelo aprovecha esto: los incrementos iniciales funcionan como prototipos naturales que generan retroalimentación real, no hipotética.
- **Riesgo humano/organizacional:** Equipo junior. El Tema 2 señala como ventaja que los incrementos pequeños permiten concentrar esfuerzo en metas acotadas. Un junior no necesita comprender la arquitectura completa del sistema para entregar un formulario de encuesta funcional.
- **Impacto del error:** Bajo. El sistema no es crítico para la operación institucional. Un error en una encuesta de satisfacción no genera consecuencias legales ni financieras. Esto permite tolerar la imprecisión inherente a un equipo inexperto trabajando con requisitos inestables.
- **Restricciones de tiempo y presupuesto:** 6 semanas, presupuesto condicionado a resultados visibles. La entrega incremental ofrece un primer incremento utilizable en 2-3 semanas, asegurando continuidad de financiamiento.

**Modelo descartado: Cascada.** A primera vista, el Rector pide evitar "modas ágiles" y la aparente simplicidad de los requisitos sugiere un enfoque secuencial. Pero Cascada sería catastrófico aquí. El Tema 2 es taxativo sobre su desventaja central: "el congelamiento prematuro de los requerimientos puede implicar un sistema que no haga lo que los usuarios desean". Si los requisitos de métricas cambian *durante* la fase de diseño —que es lo que sucederá dado el patrón del cliente—, Cascada obliga a retroceder con costo multiplicado. Además, la fase de documentación exhaustiva consumiría buena parte de las 6 semanas sin producir código funcional, contradiciendo directamente la exigencia del Rector de evitar "demasiada documentación".

**Consecuencia más grave de elegir incorrectamente:** Cancelación del proyecto. Si se elige Cascada, las 6 semanas se consumirán en especificación y diseño sin software funcionando. Los directivos no verán resultados, no liberarán presupuesto, y el proyecto muere por inanición financiera. Si se elige un modelo con demasiada documentación, se activa la profecía autocumplida: la burocracia *causa* el retraso que el Rector temía.

---

## II. Sistema de Contabilidad Universitaria

### Modelo seleccionado: Modelo en V (Verificación y Validación)

**¿Por qué este modelo y no otro?** El contexto presenta un dominio altamente regulado, procesos mal documentados, resistencia al cambio, consecuencias legales por errores, integración con múltiples sistemas existentes y un patrocinador que exige predictibilidad. El Modelo en V extiende el Cascada con una correspondencia explícita entre cada fase de definición y su fase de prueba. El Tema 2 establece que Cascada es "ideal para grandes proyectos de ingeniería de sistemas" y produce "documentación de cada fase". El Modelo en V hereda estas virtudes y añade la verificación formal que un sistema contable exige: cada requisito legal tiene su prueba correspondiente *antes* de que el código se escriba.

**Problema crítico que controla:** La **integridad de datos financieros durante la migración**. Reemplazar un sistema contable legado de 10 años no es solo construir software nuevo: es trasladar una década de datos, procesos y conocimiento tácito de empleados que *se resisten al cambio*. La Gestión de Riesgos (Tema 4) identifica como riesgo de alta probabilidad y efecto catastrófico "los cambios en los requerimientos que obligan a rehacer el diseño". En un sistema contable, un requisito mal capturado —un cálculo de retención fiscal incorrecto, un redondeo erróneo en nómina— no es un bug: es una contingencia legal. El Modelo en V obliga a que cada requisito contable tenga su caso de prueba definido antes de la implementación, creando una red de seguridad formal.

**Factores del contexto considerados:**

- **Estabilidad de requisitos:** Alta. La contabilidad universitaria está regida por normativas legales y fiscales que no cambian por capricho del cliente. Los requisitos son en su mayoría *duraderos*, "derivados de la actividad principal de la organización" (Tema 5). Las leyes contables, las estructuras de nómina y los formatos de auditoría son restricciones externas estables.
- **Participación real del usuario:** Baja disponibilidad. El enunciado lo dice explícitamente: "los usuarios finales tienen poca disponibilidad para reuniones frecuentes". Esto descarta cualquier modelo que dependa de retroalimentación continua. El Modelo en V funciona con sesiones de validación puntuales al final de cada fase de prueba, no con interacción constante.
- **Riesgo humano/organizacional:** Resistencia al cambio. Los empleados "dominan el sistema actual" y ven el nuevo como amenaza. El Tema 5 señala que "la resistencia al cambio es la norma y no la excepción" y recomienda que "el cambio ha de ser progresivo". El enfoque disciplinado del Modelo en V —con documentación clara de qué cambia y por qué, validaciones formales que incluyen a los usuarios, y una transición planificada— reduce la ansiedad organizacional que un enfoque "flexible" agravaría.
- **Impacto del error:** Catastrófico. "Un error en cálculos financieros podría generar problemas legales y auditorías". El Tema 4 clasifica este tipo de riesgo como de efecto catastrófico. No hay margen para el "vamos iterando y vemos": el primer cálculo de nómina debe ser correcto.
- **Restricciones de tiempo y presupuesto:** El patrocinador exige "fechas y costos predecibles". El Modelo en V, al ser secuencial con hitos claros, permite la calendarización precisa que el Tema 4 describe: "identificación de actividades, entregas, puntos de control" con estimaciones formales de recursos.

**Modelo descartado: Desarrollo Evolutivo (Prototipado).** El Director de TI propone un enfoque "muy flexible" porque "las metodologías rígidas ya no se usan". Esta afirmación confunde *popularidad* con *adecuación*. El Tema 2 advierte explícitamente las desventajas del modelo evolutivo: "los sistemas tienden a tener una estructura deficiente" porque "los cambios continuos pueden corromper la estructura de la solución", y "los problemas de este enfoque se agudizan particularmente en sistemas complejos y grandes". Un sistema contable integrado con nómina, compras y tesorería *es* un sistema complejo y grande. Además, el modelo evolutivo tiene un problema de visibilidad: "el proceso no es visible, deben realizarse entregas regulares para medir el progreso" y "no es rentable producir documentos que reflejen cada versión del sistema". ¿Cómo demuestras ante una auditoría que el cálculo fiscal es correcto si no hay documentación formal del requisito ni de la prueba que lo valida?

**Consecuencia más grave de elegir incorrectamente:** Sanciones legales y descuadres financieros. Si se elige un modelo "flexible", los cálculos contables pueden implementarse sin verificación formal, los datos del sistema legado pueden migrarse con errores silenciosos, y los procesos mal documentados se replican sin validación. El resultado: una auditoría fiscal encuentra inconsistencias, la universidad enfrenta sanciones, y el sistema nuevo se percibe como *peor* que el anterior —confirmando la resistencia al cambio y destruyendo cualquier posibilidad futura de modernización.

---

## III. Sistema Inteligente de Planificación de Viajes Sostenibles

### Modelo seleccionado: Desarrollo en Espiral

**¿Por qué este modelo y no otro?** El contexto presenta la mayor densidad de incertidumbre de los tres casos: usuarios que no saben qué esperan, tecnología experimental (algoritmos de IA), mercado cambiante, potencial evolución a startup y tensión entre inversores con prioridades opuestas. El Modelo en Espiral es, según el Tema 2, un modelo que "combina las fases del desarrollo en cascada con el desarrollo evolutivo añadiendo el análisis de riesgo". Cada ciclo de la espiral comprende cuatro sectores —definición de objetivos, evaluación y reducción de riesgos, desarrollo y validación, planificación— que permiten avanzar de forma controlada en un terreno donde la principal constante es la incertidumbre.

**Problema crítico que controla:** El **riesgo de inversión en una dirección técnica o de mercado equivocada**. A diferencia de los otros dos casos, aquí no hay un cliente institucional con requisitos derivables de la operación conocida. Los usuarios "no tienen claro qué esperan", los algoritmos pueden resultar inviables, y el mercado puede no responder. La Espiral obliga a un "análisis detallado para cada uno de los riesgos identificados" antes de comprometer recursos en la siguiente iteración (Tema 2). Esto satisface simultáneamente a los inversores que quieren "resultados rápidos" (cada ciclo produce un prototipo evaluable) y a los que exigen "evidencia técnica sólida" (cada ciclo incluye análisis de riesgo documentado).

**Factores del contexto considerados:**

- **Estabilidad de requisitos:** Muy baja. Los requisitos son *emergentes* (Tema 5): "surgen al incrementarse la comprensión del cliente durante el proceso de desarrollo del sistema". Los usuarios no saben qué quieren, lo que hace imposible una especificación inicial completa. La Espiral abraza esta realidad: cada ciclo refina los requisitos con base en evidencia, no en suposiciones.
- **Participación real del usuario:** Necesaria pero indefinida. "Se necesita validar aceptación del usuario antes de invertir grandes recursos". La Espiral incluye validación con usuarios en cada ciclo (sector de "desarrollo y validación"), pero no exige la disponibilidad continua que sería irreal con un mercado objetivo difuso.
- **Riesgo humano/organizacional:** Tensión entre stakeholders con intereses divergentes. Los inversores que quieren rapidez vs. los que exigen rigor técnico. La Gestión de Riesgos (Tema 4) señala que "los riesgos del negocio afectan a la organización que desarrolla o suministra el software". La Espiral gestiona esta tensión porque produce entregables tangibles (prototipos, análisis de viabilidad) que satisfacen ambos perfiles de inversor en cada ciclo.
- **Impacto del error:** Variable. Un error técnico (algoritmo inviable) se detecta tempranamente gracias al análisis de riesgos por ciclo. Un error de mercado (producto que nadie quiere) se mitiga con validación de usuario en cada iteración. El costo del error se mantiene acotado al ciclo actual, no al proyecto completo.
- **Restricciones de tiempo y presupuesto:** Presupuesto condicionado a resultados parciales. La Espiral permite "abortar" el proyecto al final de cualquier ciclo si los riesgos superan los beneficios esperados, protegiendo la inversión acumulada.

**Modelo descartado: Prototipado Evolutivo puro.** A primera vista, la incertidumbre del dominio sugiere prototipar y evolucionar. Pero el prototipado puro tiene dos problemas fatales en este contexto. Primero, el Tema 2 advierte que "los sistemas tienden a tener una estructura deficiente" con este modelo. Una startup que aspira a escalar con "algoritmos de IA" no puede construirse sobre una arquitectura corrompida por cambios continuos sin evaluación de riesgo. Segundo, el prototipado puro no satisface a los inversores que exigen "evidencia técnica sólida": un prototipo funcional no es evidencia de viabilidad técnica ni de mercado, es solo una demostración de interfaz. La Espiral añade la capa de análisis de riesgos que convierte cada prototipo en una decisión informada de inversión.

**Consecuencia más grave de elegir incorrectamente:** Quiebra total de la iniciativa. Si se elige un modelo sin gestión explícita de riesgos, el equipo puede invertir meses en un algoritmo que resulta inviable, o construir un producto que el mercado rechaza. Los inversores pierden confianza, retiran financiamiento, y la potencial startup muere antes de validar su propuesta de valor. La Espiral, al forzar la evaluación de riesgos por ciclo, establece puntos de "go/no-go" que permiten pivotar o cancelar antes de consumir todo el capital.

---

## Proyecto con Mayor Probabilidad de Fracaso

**Caso III — Sistema Inteligente de Planificación de Viajes Sostenibles**, incluso utilizando el modelo correcto.

**Razonamiento:** Los otros dos casos operan dentro de un dominio institucional conocido —la UCAB— con usuarios internos, necesidades derivables de operaciones existentes y criterios de éxito definibles. El Caso III opera en un terreno donde *todas* las variables críticas son inciertas simultáneamente:

1. **Incertidumbre de mercado.** No existe validación previa de que los usuarios quieran o paguen por este servicio. La Gestión de Riesgos (Tema 4) clasifica como riesgo del *negocio* cuando "un producto competitivo se pone en venta antes que el sistema se complete" —y en un mercado cambiante, esta posibilidad es constante.

2. **Incertidumbre técnica.** Los algoritmos de recomendación con criterios de sostenibilidad ambiental son experimentales. El Tema 5 señala que "la gestión de proyectos de software se enfrenta al hecho de que a menudo los proyectos grandes son únicos" y que "la rapidez de los cambios tecnológicos pueden hacer obsoleta la experiencia previa".

3. **Conflicto de stakeholders.** La tensión inversores-de-rapidez vs. inversores-de-rigor no tiene resolución natural. La Identificación de Riesgos (Tema 4) advierte que "los factores políticos pueden influir en los requerimientos del sistema". Cuando los financistas tienen prioridades opuestas, incluso un modelo con gestión de riesgos puede fracasar por parálisis de decisión o por compromiso político que sacrifica la viabilidad técnica.

4. **Ausencia de requisitos base.** En los Casos I y II existen procesos organizacionales que generan requisitos derivables. En el Caso III, los requisitos son especulativos: nadie sabe qué quiere el usuario porque el producto no existe. Esto coloca al proyecto en la categoría de requisitos *emergentes* y *consecuentes* simultáneamente —la combinación más volátil según el Tema 5.

El Modelo en Espiral mitiga estos riesgos, pero no los elimina. La probabilidad de fracaso es estructuralmente más alta porque el éxito depende de factores *externos* al proceso de desarrollo —aceptación de mercado, viabilidad de algoritmos experimentales, alineación de inversores— que ningún modelo de proceso puede controlar.

---

### Referencias del material de curso

- Tema 1: Sistemas y Sistemas de Información
- Tema 2: Metodología de Desarrollo de Software
- Tema 3: Metodología de Desarrollo (Modelos Ágiles y Tradicionales)
- Tema 4: Inicio del Proyecto — Gestión de Riesgos
- Tema 5: Claves para Implantar Metodologías
- Tema 6: Especificación de Requerimientos
