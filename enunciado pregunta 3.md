# Examen: Ingeniería de Software - Pregunta 3 (6 puntos)

Una institución financiera desea reemplazar un sistema legado que ha estado en operación durante más de 15 años.

El nuevo sistema será desarrollado utilizando Extreme Programming (XP) debido a la presión por entregar valor rápidamente y adaptarse a cambios regulatorios frecuentes.

Sin embargo, durante la fase de planificación aparecen fuertes desacuerdos sobre un aspecto crítico: la **Migración y Carga Inicial (MCI)** de los datos históricos.

El problema es particularmente complejo porque:
* Los datos existentes contienen inconsistencias, duplicados y estructuras obsoletas.
* Nadie conoce completamente las reglas reales de negocio implementadas en el sistema antiguo.
* Muchos procesos históricos nunca fueron documentados.
* El cliente entiende las operaciones del negocio, pero **NO** sabe definir técnicamente cómo deben ejecutarse los procesos de extracción, transformación y carga (ETL).
* Algunos desarrolladores afirman que *“si no puede escribirse como historia de usuario, entonces no pertenece al backlog”*.
* La gerencia considera la migración como una “actividad técnica secundaria” y no como parte del producto.
* Existe presión política para apagar rápidamente el sistema anterior y reducir costos de operación paralela.
* Un error de migración podría afectar auditorías, trazabilidad y decisiones financieras históricas.

---

## Actividad

Explique y **JUSTIFIQUE** cómo debería manejarse en XP todo lo relacionado con los requerimientos de Migración y Carga Inicial (MCI) en este contexto.

Su respuesta debe abordar obligatoriamente los siguientes aspectos:

1.  **Analice si los requerimientos de MCI deberían tratarse como:**
    * Historias de usuario.
    * Tareas técnicas.
    * Spikes (tarea de investigación, experimentación o creación de prototipos).
    * Actividades paralelas.
    * O mediante otro mecanismo.
    * *Justifique su decisión.*
2.  **Explique qué riesgos aparecen** si el equipo intenta forzar artificialmente la MCI dentro del formato tradicional de historias de usuario.
3.  **Analice el conflicto entre:** “entregar funcionalidad visible rápidamente” vs. “garantizar integridad y trazabilidad de datos históricos”.
4.  **Proponga cómo deberían participar:**
    * Usuarios del negocio.
    * Especialistas técnicos.
    * Personal operativo del sistema legado.
    * Auditores o áreas de control.
5.  **Indique qué información NO debería depender únicamente del cliente** para ser descubierta o especificada.
6.  **Explique cuál podría ser la consecuencia más grave** de manejar incorrectamente la MCI aun cuando el nuevo sistema funcione técnicamente bien.

---

## Restricciones importantes

* No se aceptarán respuestas puramente teóricas sobre XP.
* Evite responder únicamente “hacer más reuniones con el cliente”.
* **Debe considerar explícitamente:**
  * Incertidumbre.
  * Conocimiento tácito.
  * Deuda histórica.
  * Riesgo organizacional.
  * Presión política.
  * Conflictos entre negocio y equipo técnico.
* **Su respuesta debe asumir que:**
  * El cliente **NO** domina conceptos ETL.
  * Parte del conocimiento real está oculto en el sistema legado.

---

*Uno de los arquitectos del proyecto afirma:* “La migración no genera valor de negocio visible; por lo tanto, no debería consumir iteraciones importantes de XP.”

**Analice en su respuesta si esta afirmación puede ser peligrosa y en qué condiciones podría parecer razonable.**

---

## Requerimiento adicional

Explique si considera que XP puro es suficiente para este proyecto o si requeriría complementarse con otras prácticas, artefactos o enfoques. Justifique sin responder únicamente “usar un híbrido”.