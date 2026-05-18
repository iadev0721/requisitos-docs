# Respuesta — Pregunta 2

## El Product Owner "Nativo": Gobernanza Rota y Pérdida de Valor Real

---

## Análisis Inicial: Lo que la situación revela

El caso describe una patología organizacional que la Scrum Guide denomina falla de transparencia: el Product Owner (PO) ha dejado de ser el mecanismo que garantiza que el Product Backlog sea "transparent, visible and understood" para los stakeholders reales (Schwaber & Sutherland, 2020). Ha pasado a ser, en cambio, un filtro que protege al equipo técnico de la complejidad del negocio.

Esto no es un problema de comunicación ni de personalidad: es un **colapso de gobernanza**. El PO es "accountable for maximizing the value of the product resulting from the work of the Scrum Team" (Scrum Guide), pero cuando adopta la perspectiva del equipo de desarrollo pierde la capacidad de hacer precisamente eso. La fricción que eliminó no era disfuncional —era el mecanismo de calibración entre la realidad clínica y la solución técnica.

La afirmación del Director de Tecnología —"si el PO se integra totalmente al equipo, entonces SCRUM está funcionando perfectamente"— confunde **eficiencia técnica** con **eficacia del producto**. Es la definición exacta de la *build trap* de Perri (2018): una organización mide su éxito por outputs (funcionalidades entregadas, velocidad, ausencia de conflicto) en lugar de por outcomes (valor real para el médico frente al paciente). Un equipo perfectamente alineado que construye el sistema equivocado no es un ejemplo de SCRUM funcionando; es un ejemplo de SCRUM produciendo la ilusión de agilidad mientras la organización se deteriora.

---

## Acción 1: Panel de Validación Clínica con Rotación Obligatoria

### 1. Cómo funcionaría en este contexto específico

Se establece un **Panel de Validación Clínica (PVC)**: un grupo rotativo de 4 a 6 usuarios reales —médicos, enfermeros, personal administrativo— que cambia parcialmente cada dos sprints para evitar captura por un solo grupo de interés. El PVC tiene dos funciones formales dentro del marco SCRUM:

- **Antes del Sprint Planning**: El PVC revisa los ítems del Product Backlog propuestos para el siguiente sprint y registra por escrito si cada ítem refleja la realidad operativa actual. Esta revisión es input obligatorio para el Planning; no puede iniciarse sin ella.
- **Durante la Sprint Review**: La demostración del incremento es realizada por un miembro del PVC —no por el equipo técnico ni por el PO— ante los demás stakeholders. Si el usuario seleccionado no puede operar el incremento sin asistencia técnica, se registra como hallazgo de usabilidad con impacto directo sobre el Product Backlog.

La rotación del panel es el elemento crítico. Sin ella, el PO simplemente migra su sesgo de afinidad del equipo técnico al subgrupo de usuarios con los que interactúa más frecuentemente, reproduciendo el mismo problema a otra escala.

### 2. Problema humano, organizacional o comunicacional que intenta resolver

El PO ha caído en la **maldición del conocimiento**: cree que comprende la realidad clínica porque la conoció en el pasado, sin percibir cómo ha evolucionado. Simultáneamente, ejerce un **monopolio interpretativo**: es el único filtro entre los usuarios y el equipo, lo que le permite eliminar requerimientos del backlog sin que nadie lo detecte hasta que los médicos dejan de asistir a las revisiones.

El Panel ataca ambos problemas de forma estructural: quita al PO el monopolio de la interpretación sin reemplazarlo por un caos de voces contradictorias, y devuelve protagonismo a los usuarios sin convertirlos en co-gestores del producto.

### 3. Análisis

**Ventajas:**
- Restaura la transparencia del Product Backlog con evidencia directa, no filtrada.
- La demo por usuario en la Sprint Review expone la usabilidad real, no la percepción técnica de "done".
- La Scrum Guide establece que la Sprint Review es "a working session" y debe evitar "limiting it to a presentation" —esta acción lo hace operativo.

**Desventajas:**
- Requiere coordinación logística real con personal clínico con agendas complejas.
- Los usuarios pueden tener intereses contrapuestos; la rotación mitiga pero no elimina este riesgo.

**Riesgos de implementación:**
- Sin facilitación experta, el PVC puede capturarse por los usuarios más vocales o más jerárquicos (el jefe de servicio sobrerepresenta su perspectiva).
- La variedad de perfiles clínicos puede generar señales contradictorias que paralicen la toma de decisiones.

**Impacto sobre velocidad y calidad:**
- *Velocidad visible*: Disminuirá temporalmente porque el estándar de "done" se vuelve más exigente: el incremento debe ser operable por un no-técnico.
- *Calidad de valor*: Aumenta radicalmente. Se elimina el principal mecanismo de desperdicio: construir funcionalidades que nadie usa porque fueron definidas sin contacto con la realidad operativa.

### 4. Consecuencia de aplicación incorrecta o excesiva

Si el PVC se convierte en un órgano de aprobación permanente con poder de veto sobre cada historia de usuario, se produce un **diseño por comité**: el proceso ágil se transforma en un flujo de cascada con aprobaciones burocráticas. Los usuarios empezarán a micro-gestionar el desarrollo, los sprints se alargarán por ciclos de aprobación y el equipo perderá la autonomía que SCRUM requiere para ser efectivo. La fricción sana se convierte en parálisis.

---

## Acción 2: Separación Estructural del Rol: PO con Mandato de Adversario Constructivo

### 1. Cómo funcionaría en este contexto específico

Se redefine el rol del PO dentro de la organización con un **mandato explícito de tensión constructiva**: el PO no está para eliminar fricciones entre el equipo técnico y los usuarios, sino para representar críticamente los intereses del usuario aunque eso genere fricción.

La implementación tiene dos componentes concretos:

- **Separación física del backlog management**: El PO deja de tener asientos en los espacios de trabajo informal del equipo técnico. Trabaja primariamente en el entorno del negocio clínico. Los ítems del backlog deben incluir un campo obligatorio de "Impacto Clínico Observado": una descripción de primera mano del problema real que resuelve, no de la solución técnica que implementa. Si un ítem no puede llenarlo, no puede entrar al Sprint Planning.
- **Rendición de cuentas sobre valor, no sobre velocidad**: La evaluación del desempeño del PO se desconecta de la velocity del equipo y se conecta a métricas de adopción real: ¿cuántos médicos usan activamente la funcionalidad? ¿Ha disminuido el tiempo de registro en consulta? ¿Los usuarios reportan que el sistema refleja su flujo de trabajo? Este cambio elimina el incentivo perverso que lleva al PO a complacer al equipo técnico para mantener velocidad alta.

La Scrum Guide es explícita: "For Product Owners to succeed, the entire organization must respect their decisions." Pero respect no es sinónimo de ausencia de cuestionamiento: significa que cuando el PO decide priorizar un requerimiento del usuario sobre una preferencia técnica del equipo, esa decisión no puede ser ignorada. El cambio organizacional necesario es que la dirección respalde activamente cuando el PO ejerce ese mandato.

### 2. Problema humano, organizacional o comunicacional que intenta resolver

El problema de fondo no es de conocimiento sino de **incentivos y conflicto de poder**. El PO que elimina requerimientos del backlog "sin explicación clara" lo hace porque el camino de menor resistencia es complacer a quienes tiene más cerca —el equipo técnico— y la organización no ha establecido consecuencias por perder contacto con el usuario. Peor aún: la gerencia lo percibe positivamente porque "el equipo entrega rápido y con pocos conflictos internos."

Perri (2018) describe exactamente este patrón: organizaciones que miden el éxito por outputs (velocidad, features entregadas) crean incentivos que llevan a los product managers a optimizar para esas métricas en lugar de para el valor real. El PO "nativo" es una respuesta racional a un sistema de incentivos roto.

Esta acción ataca la causa raíz, no el síntoma.

### 3. Análisis

**Ventajas:**
- Reorienta estructuralmente los incentivos del PO hacia el outcome (valor clínico) en lugar del output (velocidad).
- El campo de "Impacto Clínico Observado" en cada ítem crea un rastro auditab de por qué se construyó cada funcionalidad.
- La separación del entorno de trabajo reduce la presión social que facilita el sesgo de afinidad.

**Desventajas:**
- La separación física puede generar percepción de distancia o desconfianza con el equipo técnico si no se comunica correctamente.
- Cambiar métricas de evaluación requiere voluntad de la dirección; si no se sostiene desde arriba, se revierte en el primer sprint con baja velocity.

**Riesgos de implementación:**
- Si el equipo técnico percibe al PO como "el enemigo del negocio", la colaboración se degrada. La tensión constructiva debe ser diferente de la adversidad destructiva; esto requiere formación y liderazgo.
- La métrica de adopción puede ser manipulada si se diseñan funcionalidades para ser fáciles de activar pero no genuinamente útiles.

**Impacto sobre velocidad y calidad:**
- *Velocidad*: La velocity como métrica perderá relevancia como indicador de desempeño del PO, lo que inicialmente generará incomodidad en la dirección.
- *Calidad*: Aumenta la calidad de la inversión: cada ítem construido tiene una justificación verificable en términos de valor clínico real.

### 4. Consecuencia de aplicación incorrecta o excesiva

Si se aplica con rigidez extrema, el PO puede desarrollar una postura de confrontación permanente con el equipo técnico que destruya la confianza necesaria para trabajar en sprints cortos. Un PO que percibe que su mandato es "adversarial" por naturaleza puede convertirse en el abogado irracional del usuario que rechaza toda consideración técnica legítima. La Scrum Guide requiere que el PO sea "one person, not a committee", con capacidad de tomar decisiones rápidas; si cada decisión escala a validación clínica obligatoria, el backlog se paraliza.

---

## Acción más efectiva: Justificación

La **Acción 2 (Separación Estructural con Mandato de Adversario Constructivo)** es más efectiva en este caso específico.

La razón es diagnóstica, no teórica. El problema no es principalmente de falta de conocimiento del dominio clínico (que la Acción 1 atacaría con el panel), sino de **gobernanza rota y sistema de incentivos perversos**. Los síntomas lo confirman: funcionalidades eliminadas del backlog sin explicación, usuarios que dejan de asistir a las revisiones porque "ya todo está decidido", y una dirección que interpreta la ausencia de conflicto como señal de éxito. Estos no son síntomas de un PO desinformado; son síntomas de un PO que ha aprendido qué comportamientos recibe refuerzo positivo en su organización y ha optimizado para ellos.

La Acción 1 es complementaria y valiosa, pero no suficiente por sí sola: un PO con incentivos alineados hacia la velocity seguirá filtrando la realidad clínica incluso si observa a los médicos trabajar, porque su evaluación de desempeño no cambia. La Acción 2, en cambio, ataca la causa raíz al redefinir qué constituye un buen desempeño del PO en esta organización.

Perri (2018) es directa al respecto: "Your company is not set up for that type of feedback. People are afraid to talk with you or their managers. You tie people's bonuses to shipping software, not to solving problems." Mientras el sistema de incentivos empuje hacia la entrega rápida sin fricción, cualquier técnica que dependa de la motivación individual del PO para mantener contacto con el usuario será insuficiente.

La afirmación del Director de Tecnología revela que el problema ya está institucionalizado. Cuando la cúpula directiva celebra explícitamente la eliminación de tensión como señal de que "SCRUM funciona perfectamente", el cambio de incentivos no es opcional: es la única intervención que puede sobrevivir al siguiente ciclo de evaluación de desempeño.

---

### Referencias

- Schwaber, K. & Sutherland, J. (2020). *The Scrum Guide*. Scrum.org.
- Perri, M. (2018). *Escaping the Build Trap: How Effective Product Management Creates Real Value*. O'Reilly Media.
- Renaud, O. M. (s.f.). *Tema 2: Metodología de Desarrollo de Software*. Universidad Católica Andrés Bello — Ext. Guayana.
- Renaud, O. M. (s.f.). *Tema 3: Metodologías de Desarrollo Ágiles*. Universidad Católica Andrés Bello — Ext. Guayana.
