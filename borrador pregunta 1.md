# Análisis de Modelos de Desarrollo de Software - Parcial I

Este documento presenta la propuesta de selección de modelos tradicionales para tres casos específicos de desarrollo de software en la UCAB, justificando cada decisión bajo criterios de gestión de riesgos, capacidad del equipo y naturaleza de los requisitos.

---

## Caso I: Sistema de Evaluación de Servicios

### 1. Modelo Seleccionado
**Modelo de Entrega Incremental**.

### 2. Justificación Técnica
* **Conveniencia:** Permite realizar una entrega funcional en el plazo crítico de 6 semanas. Al segmentar el sistema en incrementos, los directivos pueden visualizar resultados rápidamente, lo que asegura la continuidad del presupuesto. Es ideal para el equipo de programadores junior, ya que les permite concentrarse en metas pequeñas y alcanzables.
* **Control de Riesgos:** Mitiga la **incertidumbre financiera y política**. Al entregar valor de forma temprana, se evita que el proyecto sea percibido como un "gasto sin resultados". También permite ajustar las métricas de evaluación entre incrementos.
* **Modelo Descartado:** **Modelo en Cascada (Waterfall)**. Se descarta por su rigidez; obligaría a documentar todo antes de programar, consumiendo las 6 semanas sin mostrar código funcional.
* **Consecuencia de error:** Cancelación del proyecto por falta de tangibilidad o entrega de un sistema con métricas ya obsoletas por falta de feedback temprano.

---

## Caso II: Sistema de Contabilidad para la Administración

### 1. Modelo Seleccionado
**Modelo en V (Validación y Verificación)**.

### 2. Justificación Técnica
* **Conveniencia:** El dominio contable es altamente regulado y estático. El Modelo en V garantiza que cada requisito legal (asientos, balances, impuestos) tenga una fase de prueba correspondiente. Se alinea con la cultura del equipo, que es "extremadamente metódico" y prefiere definiciones claras antes del desarrollo.
* **Control de Riesgos:** Controla la **integridad legal y fiscal**. Un error en este sistema no es solo un fallo de software, sino un riesgo de multas y auditorías fallidas para la universidad.
* **Modelo Descartado:** **Prototipado Evolutivo**. A pesar de la sugerencia del Director de TI sobre la "flexibilidad", este modelo se descarta porque la contabilidad no debe "evolucionar" sobre la marcha; las leyes son fijas. Un enfoque demasiado flexible podría comprometer la consistencia de los datos financieros.
* **Consecuencia de error:** Sanciones legales, pérdida de integridad en la migración del sistema *legacy* o descuadres financieros críticos.

---

## Caso III: Sistema Inteligente de Planificación de Viajes Sostenibles

### 1. Modelo Seleccionado
**Modelo en Espiral**.

### 2. Justificación Técnica
* **Conveniencia:** Es el modelo por excelencia para la **gestión de riesgos**. Dada la incertidumbre técnica (algoritmos de IA) y de mercado (modelo startup), la espiral permite avanzar en ciclos de prototipado, análisis de riesgos y validación con inversores.
* **Control de Riesgos:** Controla el **riesgo de inversión fallida**. Obliga a realizar un análisis de riesgos antes de pasar a la siguiente fase, permitiendo "abortar" el proyecto si el algoritmo no es viable o si el mercado no responde.
* **Modelo Descartado:** **Prototipado Puro**. Se descarta porque los inversores exigen "evidencia técnica sólida". El prototipado puro suele centrarse solo en la interfaz y descuida la arquitectura robusta necesaria para una startup escalable.
* **Consecuencia de error:** Quiebra total de la iniciativa (startup) tras haber consumido toda la inversión en un producto que el mercado no necesita o que técnicamente no funciona.

---

## Análisis de Probabilidad de Fracaso

**Proyecto con mayor riesgo:** **Caso III (Viajes Sostenibles)**.

**Razonamiento:**
A diferencia de los casos internos de la universidad, el Caso III depende de **validación de mercado externa** y de la viabilidad de **tecnologías experimentales (IA)**. La presión de los inversores por "rapidez" contra la necesidad de "evidencia sólida" crea un conflicto organizacional que, sumado a la incertidumbre del dominio, eleva la probabilidad de fracaso significativamente por encima de los sistemas administrativos.