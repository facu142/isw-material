# 13 — Métricas de Software

> Págs. 33-35 del apunte + presentación 05. Es la **introducción al tema** (lo que se vuelve a tratar con más profundidad en la unidad 12 de la unidad 2). Cubre los 3 dominios, las métricas básicas, el monitoreo y control, y la cita de Brooks.

> **Nota de coherencia**: este archivo es la **introducción conceptual** al tema. Para el **tratamiento completo** (incluyendo métricas por enfoque tradicional/ágil/Lean, DRE, epifenómenos, GQM y muchos ejemplos para el oral), ver `Apuntes-MD/unidad-2/12-metricas-agiles.md`.

---

## Concepto

> Las **métricas** son **medidas numéricas o porcentajes** que aportan **visibilidad** sobre el proyecto. Son útiles para saber si nuestro proyecto está **en línea con lo planificado** o si se está **desviando**.

> El dominio de las métricas de software se divide en **3 grandes grupos** (proceso, proyecto, producto). En la **unidad 2** se agrega un cuarto dominio: **personas**, porque el software lo hacen personas y su satisfacción/carga de trabajo también se mide.

> *"No se puede controlar, gestionar ni mejorar lo que no se mide."* — Lord Kelvin (citado en la unidad 2)

> **Definición formal (IEEE)**: medida cuantitativa del grado en el que un sistema, componente o proceso posee un atributo determinado. Esta definición es la que se usa en la bibliografía (Pressman, Sommerville).

### Métrica vs. Indicador

> Es importante **no confundir** estos dos términos, aunque suelen usarse como sinónimos en el lenguaje cotidiano.

| Concepto | Qué es | Características |
|---|---|---|
| **Métrica** | Es el **número crudo** que se mide directamente. | **Objetivo, cuantificable, único**. Ej: "30 defectos graves en producción". |
| **Indicador** | Es una **métrica compuesta o comparada** que **aporta contexto** para tomar decisiones. | **Relativo, comparativo, derivado**. Ej: "30 defectos graves en producción (vs. 10 esperados → 300%)" o "tasa de defectos = 3 por KLOC". |

> **Relación**: la métrica es el **dato base**; el indicador es la **señal accionable** que se construye a partir de la métrica. **El indicador da información para decidir**.

#### Ejemplo propio (métrica vs. indicador)

> - **Métrica**: "El sistema tuvo **45 defectos** en el último release".
> - **Indicador**: "El sistema tuvo **45 defectos**, que representan **un desvío del 200%** respecto a los 15 que esperábamos. **Indicador = ROJO**, hay que investigar".

> Es como en medicina: la **métrica** es la presión arterial (120/80 mmHg), y el **indicador** es saber si eso es **normal o alto** comparado con los valores de referencia. El número solo no dice nada; necesita contexto.

> **Conexión con la unidad 2**: en la unidad 12 se profundiza este concepto y se ve cómo construir **indicadores** a partir de **métricas** (ej. DRE, tasa de defectos, % de cobertura).

### Estimación vs. Métrica

> Es común preguntarse: *"¿por qué se estima lo mismo que se mide? ¿tamaño, esfuerzo, calendario?"*. **Sí, se mira lo mismo**, pero en **momentos distintos** y con **propósitos distintos**.

| | **Estimación** | **Métrica** |
|---|---|---|
| **Cuándo se hace** | **Antes** de hacer el trabajo (mirando hacia adelante). | **Después** de hacer el trabajo (mirando hacia atrás). |
| **Propósito** | Predecir cuánto va a llevar. | Medir cuánto llevó realmente. |
| **Base** | Suposiciones, experiencia, analogía, datos históricos. | Datos reales del proyecto. |
| **Naturaleza** | **Subjetiva**, aproximada, con incertidumbre. | **Objetiva**, cuantificable. |
| **Resultado** | "Estimamos que el proyecto va a llevar **200 horas**". | "El proyecto llevó **250 horas**". |

> **Cómo se conectan**: con el tiempo, las **métricas alimentan las próximas estimaciones**. Si en 5 proyectos mediste que tu equipo tarda **25% más** de lo estimado, el próximo proyecto vas a estimar con un colchón del 25%.

> **Conexión con Brooks**: *"los proyectos se retrasan de a un día por vez"*. Esto aplica a **las dos cosas**: a la **estimación** (cada día subestimás 1 hora → en 100 días son 100 horas extra) y a la **métrica** (los pequeños desvíos se acumulan hasta hacer explotar el plan).

> **Conexión con la unidad 2**: el **desvío** (que vimos en la sección de Tiempo) es donde **estimación y métrica se encuentran**: `Desvío = (Real - Planificado) / Planificado × 100`. El "Planificado" es estimación, el "Real" es métrica, y el desvío en sí es un **indicador**.

---

---

## Los 3 dominios de métricas

### 1. Métricas de proceso

> Saber, en términos de la **organización**, la manera en la que estamos trabajando.

- **Porcentaje de proyectos que terminan a tiempo** vs. los que terminan con desvío.
- Las métricas de proceso son una **despersonalización** de las métricas del proyecto → todas las métricas que son del proyecto también lo son del proceso.

> *Ejemplo*: tomás métricas de las desviaciones de los últimos 10 proyectos y notás que el desvío promedio es de un 30% respecto a lo planificado. Esto refleja que el proceso está **siendo mal implementado o mal entendido**. Como no se analiza un proyecto en particular, sino que se los **despersonaliza** llevándolos a un nivel más superior, es una **métrica de proceso**.

### 2. Métricas de proyecto

> Permiten saber si un proyecto de software en ejecución se está cumpliendo de acuerdo a lo planificado o no.

```
(Tiempo Real / Tiempo Planificado) × 100
```

> Esto sirve para saber si el tiempo de duración del proyecto está en línea con lo planificado.

### 3. Métricas de producto

> Directamente relacionadas con el **producto de software** que estamos construyendo.

- Están muy relacionadas con **métricas de defectos**.

> Las métricas del proyecto **se consolidan** para crear **métricas de proceso** que sean públicas para toda la organización del software.

---

## Métricas básicas para un proyecto de software

| Métrica | Pertenece a | Dominio |
|---|---|---|
| **Tamaño del producto** | Producto. | Producto. |
| **Esfuerzo** | Proyecto. | Proyecto. |
| **Tiempo (calendario)** | Proyecto. | Proyecto. |
| **Defecto** | Producto. | Producto. |

> Un aspecto **clave** a la hora de tomar métricas es **mantenerlo simple**. El esfuerzo tiene que ser el menor posible.

> **Cómo se complementan las 4**: el **tamaño** te dice cuánto hay que construir, el **esfuerzo** cuánto trabajo lleva, el **tiempo** cuándo se entrega y los **defectos** qué tan bien se hizo.

---

## Ejemplo sencillo: Tiempo (calendario)

> Esto nos sirve para entender a qué nos referimos con despersonalización.

> Supongamos que tomás métricas de las desviaciones de los últimos 10 proyectos y notás que el desvío promedio es de un 30% con respecto a lo planificado. Esto refleja que el proceso está siendo mal implementado o mal entendido. Es una **métrica de proceso** porque no se analiza un proyecto particular, sino que se los **despersonaliza** a un nivel más superior.

```
(T.real - T.planificado) / T.planificado × 100 = Desvío porcentual
```

## Ejemplo sencillo: Esfuerzo

> Mismo concepto: las desviaciones de esfuerzo a lo largo de muchos proyectos se consolidan en una **métrica de proceso** que dice cómo funciona la organización en su conjunto.

---

## Métricas por nivel organizacional

> Cada nivel de la organización mira **métricas distintas** según lo que necesita controlar. Esto se ve en la unidad 2 con más detalle (es el "sueño del pibe" de la cátedra).

### Desarrollador

- Esfuerzo.
- Esfuerzo y duración estimada y actual de una tarea.
- % de cobertura por el unit test.
- Número y tipo de defectos encontrados en el unit test.
- Número y tipo de defectos encontrados en revisión por pares.

### Equipo de desarrollo

- Tamaño del producto.
- Duración estimada y actual entre hitos importantes.
- Niveles de staffing actuales y estimados.
- Nro. de tareas planificadas y completadas.
- Distribución del esfuerzo.
- Status de requerimientos.
- **Volatilidad de requerimientos**: % de requerimientos que cambiaron sobre el total.
- Nro. de defectos en integración y prueba de sistemas.
- Nro. de defectos en peer reviews.
- Status de distribución de defectos.
- % de test ejecutados.

### Organización

- Tiempo calendario.
- Performance actual y planificada de esfuerzo.
- Performance actual y planificada de presupuesto.
- Precisión de estimaciones en schedule y esfuerzo.
- **Defectos en release**.

> **Cómo memorizar el "sueño del pibe"**:
> - **Desarrollador** mira **su** trabajo (esfuerzo, unit tests).
> - **Equipo** mira **el proyecto** (tareas, staffing, defectos internos).
> - **Organización** mira **el proceso** (presupuesto, schedule, defectos en release).

---

## Monitoreo y Control

> El monitoreo y control, que es para lo que usamos las métricas, tiene que ver con ir **comparando lo planificado y lo real**.

- La línea perfecta entre lo planificado y lo real no existe, suele estar **algo dibujado**.
- De esto se encarga el **líder de proyecto**.

> En el libro *The Mythical Man-Month* (Fred Brooks) se habla de que **los proyectos se retrasan 1 día a la vez**. Justamente si tenemos una buena planificación y buenas métricas, un desvío **no será difícil de corregir** si es tomado a tiempo.

> *"Como se atrasa un proyecto: de a un día por vez."* — Fred Brooks.

> **Conexión con la unidad 2**: en ágil, este concepto se traduce a que **la velocidad no es constante** — puede oscilar (sprint 7 = 4 puntos, sprint 8 = 43). Por eso, **detectar desvíos temprano** es clave para corregirlos antes de que sea tarde.

---

## Mantenerlo simple

> *"Si estás a millas de distancia de tu destino, no tiene sentido medir en milímetros."*

Preguntas antes de tomar una métrica:

- ¿Nos da más información que la que tenemos ahora?
- ¿Es esta información de beneficio práctico?
- ¿Nos dice lo que queremos saber?

> Si la respuesta a alguna es **no**, descartala.

> **Conexión con la unidad 2**: el costo de recolección es fundamental. Si definimos 100 métricas complejas que nadie usa, **el costo de obtenerlas supera el beneficio** → es **desperdicio Lean**. Las métricas deben ser simples, objetivas e intuitivas.

---

## ¿Para qué se usan las estimaciones, las métricas y los riesgos?

> Sirven para el **monitoreo y control** del proyecto:

- Comparar lo planificado y lo real.
- Detectar desvíos temprano.
- Corregir el rumbo antes de que sea tarde.
- Comunicar el estado del proyecto a los stakeholders.

---

## Diferencia con métricas en otros enfoques (preview de la unidad 2)

> En la **unidad 2** se retoman las métricas con foco en los **3 enfoques** de gestión. Esta es la **tabla resumen** (vista en detalle en el archivo de la unidad 12):

| Enfoque | Métricas típicas |
|---|---|
| **Tradicional** | Esfuerzo, Tiempo, Costos, Defectos, Tamaño (LOC o PF). |
| **Ágil (Scrum)** | Velocidad, Capacidad, Running Tested Features (RTF). |
| **Lean (Kanban)** | Lead Time, Cycle Time, Touch Time, Eficiencia del Proceso. |

> **Conexión con la unidad 3**: en SCM (gestión de configuración) también hay métricas (auditorías PCA/FCA, densidad de defectos, etc.).

---

## Chivo para el oral

1. **Concepto**: medidas numéricas que dan **visibilidad** sobre el proyecto.
2. **3 dominios** (se agrega **Personas** en la unidad 2):
   - **Proceso** (organización, despersonalizadas).
   - **Proyecto** (¿se está cumpliendo lo planificado?).
   - **Producto** (tamaño, defectos).
3. **Métricas básicas**: tamaño, esfuerzo, tiempo, defectos.
4. **Mantenerlo simple**: si no aporta información nueva y útil, no la tomes.
5. **Monitoreo y control**: comparar planificado vs. real. **Es responsabilidad del líder**.
6. **Brooks**: *"de a un día por vez"*. Si tenés buenas métricas, un desvío pequeño se corrige a tiempo.
7. **Sueño del pibe**: desarrollador (esfuerzo/unit tests) → equipo (tareas/staffing) → organización (presupuesto/release).
8. **Cerrá con la idea**: las métricas son el insumo del monitoreo. Sin métricas, no podés controlar nada.

> **Si te preguntan "¿qué es una métrica de proceso vs. de proyecto?"** → la de **proyecto** analiza **un proyecto particular** (¿se está cumpliendo este plan?); la de **proceso** analiza **muchos proyectos despersonalizados** (¿cómo funciona la organización en su conjunto?).

> **Si te preguntan "¿cuáles son las métricas básicas de un proyecto?"** → las 4: **Tamaño** (producto), **Esfuerzo** (proyecto), **Tiempo** (proyecto), **Defectos** (producto).

> **Si te preguntan "¿qué es la volatilidad de requerimientos?"** → el porcentaje de requerimientos que **cambian** sobre el total. Una volatilidad alta significa mucho retrabajo y poca estabilidad del plan. La mira el **equipo de desarrollo**.

> **Si te preguntan "¿qué dijo Brooks sobre los atrasos?"** → *"los proyectos se atrasan de a un día por vez"*. Si tenés buenas métricas, podés detectar el desvío temprano y corregirlo antes de que sea tarde.

> **Si te preguntan "¿cuál es la diferencia entre métrica e indicador?"** → la **métrica** es el **número crudo** que se mide (ej. "30 defectos graves"). El **indicador** es la **señal accionable** que se construye a partir de la métrica, dándole contexto (ej. "30 defectos vs. 10 esperados → 200% → ROJO"). La métrica es el dato, el indicador es la alarma. Analogía: la métrica es la presión arterial, el indicador es saber si es normal o alta.

> **Si te preguntan "¿por qué se estima y se mide lo mismo (tamaño, esfuerzo, tiempo)?"** → **no es lo mismo**, aunque el objeto sea el mismo. La **estimación** se hace **antes** (es una predicción subjetiva, ej. "va a llevar 200 horas"). La **métrica** se hace **después** (es la medición real, ej. "llevó 250 horas"). Se conectan a través del **desvío** `(Real - Planificado) / Planificado × 100`, que es un **indicador**. Y con el tiempo, **las métricas mejoran las próximas estimaciones** (si siempre mediste 25% más de lo estimado, el próximo proyecto estimás con un colchón del 25%). Analogía: la estimación es el pronóstico del tiempo, la métrica es lo que terminó lloviendo, el indicador es el desvío.
