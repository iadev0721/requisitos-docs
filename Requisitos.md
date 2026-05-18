# Respuesta — Pregunta 4

## Análisis Crítico: SCRUM Remoto, Seguridad Psicológica e IA Generativa

---

## I. Cumplimiento Efectivo de los Roles SCRUM

### Product Owner

**Riesgo:** Desconexión empática con los usuarios finales. El PO de MKS se comunica "principalmente por mensajería" y rara vez interactúa con usuarios reales. Perri (2018) advierte que cuando el PO pierde contacto con el usuario, la organización cae en la *build trap*: mide funcionalidades entregadas en lugar de valor generado.

**Invisibilidad en remoto:** En oficina, el PO recibe correctivos informales —expresiones de stakeholders, conversaciones espontáneas—. En remoto, puede mantener un backlog ordenado pero construido sobre supuestos no validados. La Scrum Guide exige que el PO asegure que "the Product Backlog is transparent, visible and understood", pero en remoto la transparencia se reduce a artefactos escritos que ocultan los "malentendidos funcionales" que MKS reporta.

**Mitigación:** Sesiones de descubrimiento con usuarios reales cada dos sprints. Documentos de hipótesis de valor compartidos asincrónicamente antes de cada Planning (Neeley, 2021, Cap. 5: "Prepare Alone, End in Sync"). Criterio de éxito medible por ítem, vinculado al usuario.

**Contrapartida:** Las sesiones con usuarios pueden ritualizarse sin propósito. La documentación previa puede percibirse como burocracia que contradice el Manifiesto Ágil. Deben ser ligeras y enfocadas en decisiones.

### Scrum Master

**Riesgo:** Pérdida de lectura emocional. El caso lo describe: "el SM percibe agotamiento, pero los indicadores aparentan ser normales". Edmondson (2019) documenta que sin seguridad psicológica, las personas realizan un "cálculo inconsciente de riesgo interpersonal" donde callan para proteger su imagen. El SM ve métricas verdes sobre un equipo en *silencio peligroso*.

**Invisibilidad en remoto:** En oficina, el SM observa lenguaje corporal y dinámicas de poder. Neeley (2021) advierte que "remote workers' feelings of professional isolation lead to reduced job performance", pero esta erosión es invisible mientras velocity y burn-down se mantengan estables. La actividad visible no equivale a colaboración real.

**Mitigación:** Retrospectivas con retroalimentación anónima (Neeley, Cap. 5: herramientas digitales que permiten comentarios sin identificación). One-on-ones privados enfocados en bienestar, no solo impedimentos técnicos. Rotación de facilitación para reducir la dominancia de seniors.

**Contrapartida:** La anonimidad puede generar comentarios destructivos. Los one-on-ones excesivos contribuyen a la fatiga digital. La rotación requiere coaching previo.

### Equipo de Desarrollo

**Riesgo:** Fragmentación en silos individuales y dependencia acrítica de IA generativa. La Scrum Guide establece que los Developers son responsables de "holding each other accountable as professionals", pero en remoto cada persona trabaja en su burbuja. Los seniors dominan videollamadas; los juniors se refugian en IA que genera código sin comprensión.

**Invisibilidad en remoto:** Neeley describe la "natural awareness by proximity" como esencial para equipos ágiles. Sin ella, un junior puede generar código con IA durante días sin cuestionamiento. Los commits parecen "productivos" mientras la deuda técnica se acumula.

**Mitigación:** Pair programming rotativo senior-junior (2-3 sesiones/sprint). Política de IA: todo código generado requiere explicación de la lógica por el autor —la IA proporciona predicción, pero el juicio sigue siendo humano (Agrawal, Gans & Goldfarb, 2022). Sincronización deliberada tras trabajo asincrónico individual.

**Contrapartida:** El pair programming obligatorio puede percibirse como vigilancia. Las restricciones sobre IA generan resistencia. Deben ser normas acordadas por el equipo, no impuestas.

---

## II. Ceremonias SCRUM en Contexto Remoto

### Sprint Planning

**Problema real:** Se convierte en monólogo del PO seguido de silencios que se interpretan como consenso. La fatiga de videollamadas largas reduce la capacidad de cuestionar. Los tres temas de la Scrum Guide (¿por qué es valioso? ¿qué se puede hacer? ¿cómo?) se comprimen sin debate genuino.

**Señales de degradación:** Sprint Goal genérico o repetitivo. Sin debate sobre estimaciones. Nadie cuestiona el "cómo".

**Ajuste remoto:** Pre-trabajo asincrónico: el PO comparte backlog priorizado 48h antes; developers publican preguntas en documento compartido. La sesión síncrona se dedica a resolver desacuerdos, no a presentar información.

**Práctica contraproducente:** Extender la duración "para compensar la distancia" aumenta la fatiga sin mejorar la participación.

### Daily Scrum

**Problema real:** El caso lo dice: "se vuelven mecánicas y excesivamente breves". Degenera en reporte secuencial sin inspección ni adaptación. Neeley observa que en videollamadas "it's more difficult for team members to know when to speak up".

**Señales de degradación:** Todos dicen "no tengo bloqueos" sistemáticamente. Dura 5 minutos para 7 personas. Cámaras apagadas. Nadie pregunta sobre lo que otros reportan.

**Ajuste remoto:** Estructura deliberada con "baton passing" (Neeley, Cap. 5). Preguntas provocativas del SM ("¿alguien cambió de opinión sobre algo?"). Elemento de conexión humana, no solo técnica.

**Práctica contraproducente:** Reemplazarla por reporte escrito en Slack elimina la única oportunidad síncrona de inspección. Usarla como mecanismo de control gerencial genera el comportamiento mecánico observado.

### Sprint Review

**Problema real:** La Scrum Guide advierte "avoid limiting it to a presentation", pero la videollamada favorece exactamente eso: compartir pantalla mientras stakeholders permanecen en mute. Se pierde el carácter de "working session".

**Señales de degradación:** Stakeholders no preguntan. Feedback superficial ("se ve bien"). El Product Backlog no se ajusta como resultado.

**Ajuste remoto:** Compartir el incremento funcionando con acceso previo para que stakeholders lo prueben antes. Sesión síncrona enfocada en reacciones y decisiones. Encuestas anónimas en tiempo real (Neeley, Cap. 5).

**Práctica contraproducente:** Grabar la Review "para quien no pueda asistir" elimina la interacción que le da valor.

### Sprint Retrospective

**Problema real:** La ceremonia más vulnerable. Requiere honestidad sobre dinámicas interpersonales, pero Edmondson demuestra que "85% of respondents reported at least one occasion when they felt unable to raise a concern with their bosses". Cuando gerencia exige "mantener la misma velocidad", criticar el proceso equivale a criticar decisiones gerenciales.

**Señales de degradación:** Mismas acciones de mejora sprint tras sprint. Solo temas técnicos, nunca interpersonales. Dura menos de lo prescrito.

**Ajuste remoto:** Retroalimentación anónima previa con nubes de palabras. Sección explícita de bienestar como tema central. El SM modela vulnerabilidad: Edmondson recomienda que líderes admitan sus propios errores para activar seguridad psicológica.

**Práctica contraproducente:** Usar la Retro solo para "celebrar logros" crea positivismo tóxico. Registrarla en documento accesible por gerencia destruye la confidencialidad.

---

## III. Estimaciones de Esfuerzo

### Por qué el remoto las degrada

Las estimaciones dependen del *conocimiento compartido tácito*. La Scrum Guide establece que la confianza en las estimaciones crece con conocimiento de "past performance, upcoming capacity, and Definition of Done". Este conocimiento se construye con interacciones continuas que Neeley llama "natural awareness by proximity" y que Hackman cuantifica: "60% of team success depends on prework" —las interacciones informales SON ese prework. El cambio a remoto invalida parcialmente la experiencia acumulada del equipo.

### Factores agravantes

- **Comunicación asincrónica:** Cuando un developer estima 3 y otro 13, la conversación que resuelve esa brecha se fragmenta, pierde contexto, y se resuelve por compromiso numérico en lugar de comprensión.  
- **IA generativa:** Introduce sobreconfianza ("la IA genera el 70% del código") sin contabilizar revisión, debugging ni riesgo arquitectónico. Agrawal et al. (2022): la IA proporciona predicción, pero el juicio contextual sigue siendo responsabilidad humana.  
- **Diferencias horarias:** Comprimen las ventanas de discusión, favoreciendo estimaciones superficiales sobre deliberadas.  
- **Fatiga digital:** Una Planning de 8 horas por videollamada es cognitivamente insostenible. Edmondson cita neurociencia: la fatiga "diverts resources from parts of the brain that manage working memory and process new information".  
- **Menor interacción informal:** Sin las calibraciones espontáneas de pasillo, las estimaciones se basan en información incompleta.

### Métricas: útiles vs. ilusorias

**Útiles:** Cycle time (tiempo real inicio-entrega), ratio de re-estimación mid-sprint, tracking de "trabajo invisible" (debugging de IA, comunicación, reuniones no planificadas).

**Ilusorias:** Velocity como KPI gerencial (incentiva inflar estimaciones). Horas de conexión (confunde presencia con productividad). Story points sin contexto de calidad ni valor.

### Por qué la presión empeora todo

La gerencia exige "mantener la misma velocidad". Esto activa un ciclo destructivo: presión → estimaciones artificialmente bajas → trabajo apresurado sin validación → deuda técnica y errores ocultos (porque reportarlos implicaría admitir que la velocidad era ilusoria) → métricas aparentemente normales → gerencia refuerza la presión. Es exactamente la *build trap* de Perri y el "avoidable failure" de Edmondson.

La afirmación del Director de Operaciones —"si las ceremonias ocurren y se entregan funcionalidades, SCRUM funciona"— confunde **actividad visible con colaboración real**, **entrega de funcionalidades con generación de valor**, y **cumplimiento de rituales con práctica efectiva**. La Scrum Guide es taxativa: "Artifacts that have low transparency can lead to decisions that diminish value and increase risk" y "Inspection without transparency is misleading and wasteful". Las ceremonias sin seguridad psicológica son cáscaras vacías que producen la ilusión de agilidad mientras la organización se deteriora.

---

### Referencias

- Schwaber, K. & Sutherland, J. (2020). *The Scrum Guide*.  
- Neeley, T. (2021). *Remote Work Revolution: Succeeding From Anywhere*. HarperCollins.  
- Edmondson, A. C. (2019). *The Fearless Organization*. John Wiley & Sons.  
- Perri, M. (2018). *Escaping the Build Trap*. O'Reilly Media.  
- Agrawal, A., Gans, J. & Goldfarb, A. (2022). *Power and Prediction*. Harvard Business Review Press.

