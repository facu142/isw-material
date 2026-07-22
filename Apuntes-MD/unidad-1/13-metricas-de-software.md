# 13 — Métricas de Software

> Págs. 33-35 del apunte + presentación 05. Es la **introducción al tema**. Para el **tratamiento completo** (métricas por enfoque tradicional/ágil/Lean, DRE, epifenómenos, GQM y muchos ejemplos para el oral), ver `Apuntes-MD/unidad-2/12-metricas-agiles.md`.

---

## Concepto

> Las **métricas** son **medidas numéricas o porcentajes** que aportan **visibilidad** sobre el proyecto. Son útiles para saber si nuestro proyecto está **en línea con lo planificado** o si se está **desviando**.

> **Definición formal (IEEE, citada por Pressman)**: medida cuantitativa del grado en el que un sistema, componente o proceso posee un atributo determinado.

> *"No se puede controlar, gestionar ni mejorar lo que no se mide."* — Lord Kelvin

El dominio de las métricas de software se divide en **3 grandes grupos** (proceso, proyecto, producto). En la **unidad 2** se agrega un cuarto dominio: **personas** (ver sección 2.4 del archivo de unidad 2).

---

## Los 3 dominios de métricas

| Dominio | Qué mide | Perspectiva | Ejemplo |
|---|---|---|---|
| **Proceso** | Cómo trabaja la **organización** en su conjunto. | Estratégica, largo plazo, despersonalizada. | "En los últimos 10 proyectos el desvío promedio fue 30%". |
| **Proyecto** | Si un proyecto en ejecución se está cumpliendo. | Táctica, corto plazo, atribuida a un proyecto. | `(Tiempo Real / Tiempo Planificado) × 100`. |
| **Producto** | Características del software en sí. | Tamaño, defectos, calidad. | Cantidad de defectos por severidad. |

> Las métricas del proyecto **se consolidan** (despersonalizándolas) para crear **métricas de proceso** que sean públicas para toda la organización.

> **Analogía**: si un paciente tiene la **presión en 120/80** (métrica de producto), el hospital mide el **promedio de presión de sus pacientes** (métrica de proceso) para saber si la **población general** está bien.

---

## Métrica vs. Indicador vs. Estimación

> Tres conceptos que suelen confundirse. Es importante no mezclarlos.

| Concepto | Qué es | Cuándo |
|---|---|---|
| **Métrica** | El **número crudo** que se mide directamente. | **Después** (mirando hacia atrás). |
| **Indicador** | Una **métrica con contexto** (umbral, comparación, ratio). | Cuando querés **decidir**. |
| **Estimación** | La **predicción** de cuánto va a llevar. | **Antes** (mirando hacia adelante). |

> **Relación entre los 3**: la **estimación** se hace antes; la **métrica** se hace después; el **desvío** entre ambas es un **indicador**. Con el tiempo, **las métricas mejoran las próximas estimaciones**.

> **Cómo se conectan** (analogía meteorológica): estimación = pronóstico, métrica = lo que llovió, indicador = desvío. Si siempre mediste 25% más de lo estimado, el próximo proyecto estimás con un colchón del 25%.

> **Conexión con Brooks**: *"los proyectos se retrasan de a un día por vez"*. Esto aplica a **las dos cosas** (estimación y métrica): cada día que subestimás 1 hora se acumula; cada pequeño desvío se acumula hasta hacer explotar el plan.

---

## Métricas básicas para un proyecto de software

| Métrica | Pregunta que responde | Dominio |
|---|---|---|
| **Tamaño del producto** | ¿Cuánto tengo que construir? | Producto. |
| **Esfuerzo** | ¿Cuánto trabajo lleva? | Proyecto. |
| **Tiempo (calendario)** | ¿Cuándo lo entrego? | Proyecto. |
| **Defecto** | ¿Qué tan bien lo estoy haciendo? | Producto. |

> **Cómo se complementan**: tamaño + esfuerzo + tiempo dan el **plan**; los defectos miden la **calidad** del resultado.

> **Limitación de LOC** (líneas de código): es difícil de estimar antes de codificar y depende del lenguaje. Mejor **Puntos de Función** (agnósticos al lenguaje) o **Puntos de Historia** (en ágil).

> **Métricas por nivel organizacional** (el "sueño del pibe" de la cátedra):
> - **Desarrollador** → su trabajo (esfuerzo, unit tests, peer review).
> - **Equipo** → el proyecto (tareas, staffing, **volatilidad de requerimientos**, defectos internos).
> - **Organización** → el proceso (presupuesto, schedule, **defectos en release**).

---

## Monitoreo y Control

> El monitoreo y control tiene que ver con ir **comparando lo planificado y lo real**. De esto se encarga el **líder de proyecto**.

> *"Como se atrasa un proyecto: de a un día por vez."* — Fred Brooks (*The Mythical Man-Month*)

> **El desvío** es donde estimación y métrica se encuentran: `Desvío = (Real - Planificado) / Planificado × 100`. Es un **indicador** que dispara acciones.

---

## Mantenerlo simple

> *"Si estás a millas de distancia de tu destino, no tiene sentido medir en milímetros."*

Preguntas antes de tomar una métrica:
- ¿Nos da más información que la que tenemos ahora?
- ¿Es esta información de beneficio práctico?
- ¿Nos dice lo que queremos saber?

> Si la respuesta a alguna es **no**, descartala. **El costo de recolectar la métrica no puede superar al beneficio de usarla**.

---

## Diferencia con métricas en otros enfoques (preview de la unidad 2)

| Enfoque | Métricas típicas |
|---|---|
| **Tradicional** | Esfuerzo, Tiempo, Costos, Defectos, Tamaño (LOC o PF). |
| **Ágil (Scrum)** | Velocidad, Capacidad, Running Tested Features (RTF). |
| **Lean (Kanban)** | Lead Time, Cycle Time, Touch Time, Eficiencia del Proceso. |

> **Conexión con la unidad 3**: en SCM también hay métricas (auditorías PCA/FCA, densidad de defectos).

---

## Chivo para el oral

1. **Concepto**: medidas numéricas que dan **visibilidad** sobre el proyecto.
2. **3 dominios** (se agrega **Personas** en la unidad 2): **Proceso** (despersonalizadas), **Proyecto** (atribuidas a un proyecto), **Producto** (tamaño/defectos).
3. **Métricas básicas**: tamaño, esfuerzo, tiempo, defectos. El LOC no sirve bien, mejor PF o Puntos de Historia.
4. **Métrica vs Indicador vs Estimación**: métrica = el dato, indicador = el dato con contexto, estimación = el pronóstico.
5. **Mantenerlo simple**: si no aporta información nueva y útil, no la tomes.
6. **Monitoreo y control**: comparar planificado vs. real. **Es responsabilidad del líder**.
7. **Brooks**: *"de a un día por vez"*. Si tenés buenas métricas, un desvío pequeño se corrige a tiempo.
8. **Sueño del pibe**: desarrollador (esfuerzo/unit tests) → equipo (tareas/staffing) → organización (presupuesto/release).
9. **Cerrá con la idea**: las métricas son el insumo del monitoreo. Sin métricas, no podés controlar nada.

> **Si te preguntan "¿qué es una métrica de proceso vs. de proyecto?"** → la de **proyecto** analiza un proyecto particular (¿se cumple este plan?); la de **proceso** analiza muchos proyectos despersonalizados (¿cómo funciona la organización?).

> **Si te preguntan "¿cuál es la diferencia entre métrica e indicador?"** → la métrica es el **número crudo** (ej. "30 defectos graves"). El indicador es la **señal accionable** con contexto (ej. "30 vs. 10 esperados → 200% → ROJO"). Métrica = dato, indicador = alarma. Analogía: la métrica es la presión arterial, el indicador es saber si es normal o alta.

> **Si te preguntan "¿por qué se estima y se mide lo mismo?"** → no es lo mismo, aunque el objeto lo sea. La estimación se hace **antes** (predicción subjetiva), la métrica se hace **después** (medición real). Se conectan por el **desvío**, que es un indicador. Y las métricas **mejoran las próximas estimaciones**.

> **Si te preguntan "¿qué dijo Brooks sobre los atrasos?"** → *"los proyectos se atrasan de a un día por vez"*. Si tenés buenas métricas, podés detectar el desvío temprano y corregirlo antes de que sea tarde.
