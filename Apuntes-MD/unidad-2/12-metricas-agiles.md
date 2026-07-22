# 12 — Métricas de Software

> Págs. 138-148 del apunte + presentación "Métricas de Software en los Diferentes Enfoques" + resumen de Facu. Es **el tema del examen final**. Para la **introducción conceptual** del tema, ver `Apuntes-MD/unidad-1/13-metricas-de-software.md`.

---

## 1. Conceptos fundamentales

### 1.1. ¿Qué es una métrica?

> *"No se puede controlar, gestionar ni mejorar lo que no se mide."* — Lord Kelvin

> **Métrica** (IEEE, citada por Pressman): medida cuantitativa del grado en el que un sistema, componente o proceso posee un atributo determinado. Es un **número objetivo** que da **visibilidad** para **tomar decisiones**.

**Las 3 reglas de oro de las métricas**: **objetiva** (número, no opinión), **simple e intuitiva**, **costo razonable**.

> **Trampa**: querer medir *"la cantidad de requerimientos que deberíamos haber identificado"* es **imposible de medir objetivamente** (no podemos contabilizar lo que ni siquiera sabemos que ignoramos). Es **desperdicio Lean**.

### 1.2. Métrica vs. Indicador vs. Estimación

| Concepto | Qué es | Cuándo | Ejemplo |
|---|---|---|---|
| **Métrica** | El **número crudo** que se mide. | **Después** (mirando atrás). | "30 defectos graves en producción". |
| **Indicador** | Una **métrica con contexto** (umbral, comparación, ratio). | Cuando querés **decidir**. | "30 vs. 10 esperados = 200% → ROJO". |
| **Estimación** | La **predicción** de cuánto va a llevar. | **Antes** (mirando adelante). | "Estimamos 200 horas". |

> **Relación**: la estimación se hace **antes**; la métrica se hace **después**; el **desvío** entre ambas es un indicador. Con el tiempo, **las métricas alimentan las próximas estimaciones** (si siempre mediste 25% más, ajustás el próximo proyecto).
>
> **Analogía meteorológica**: estimación = pronóstico, métrica = lo que llovió, indicador = desvío. Analogía médica: métrica = presión arterial, indicador = ¿es normal o alta?

> **Conexión con Brooks**: *"los proyectos se retrasan de a un día por vez"*. Cada día subestimás 1 hora → 100 días = 100 horas extra. La métrica te sirve para **corregir la próxima estimación**.

### 1.3. Ejemplo propio: estimación vs. métrica en un sprint

> **Antes del sprint (estimación)**: capacidad = 140h, velocidad = 40 puntos.
> **Después del sprint (métrica real)**: trabajó 130h, PO aceptó 43 puntos → **desvío = subutilización 7%** (indicador: amarillo).
> **Próximo sprint**: la estimación se ajusta a 43-45 puntos, **alimentada por la métrica** del sprint anterior.

---

## 2. Los dominios de las métricas

> Las métricas de software se dividen en **3 dominios clásicos** (proceso, proyecto, producto) más un **cuarto que se agrega en clase**: **las personas**.

<img src="imgs/metricas_tradicional_portada.png" alt="Metricas en el enfoque tradicional" width="700">

| Dominio | Perspectiva | Característica clave | Ejemplo |
|---|---|---|---|
| **Proceso** | Estratégica, largo plazo. | **Despersonalizada**, pública para toda la org. | "La organización tiene 3 defectos por millón de LOC". |
| **Proyecto** | Táctica, corto plazo. | Atribuida a un proyecto específico. | "Este proyecto tuvo 5 defectos graves en su release 1.0". |
| **Producto** | Características del software. | Evalúa tamaño, defectos, calidad. | LOC, PF, complejidad ciclomática. |
| **Personas** | Cuarto dominio, agregado en clase. | El software lo hacen personas. | Satisfacción, rotación, carga de trabajo. |

> **Estoy midiendo lo mismo, pero el foco de medición es diferente**. Las de proyecto se **consolidan** para crear las de proceso.

### GQM (Goal-Question-Metric)

> Técnica para **derivar métricas desde un objetivo de negocio**: primero el **Goal**, después las **Questions**, después las **Metrics**. Si la métrica no responde una pregunta que sirve al goal, no sirve.

> **Ejemplo**: Goal = "reducir defectos graves en producción". Question = "¿cuántos defectos graves llegaron a producción?". Metric = "cantidad de defectos graves detectados en producción por severidad".

---

## 3. Métricas básicas de un proyecto

<img src="imgs/metricas_4_basicas.png" alt="Las 4 metricas basicas" width="700">

| Métrica | Pregunta que responde | Dominio | Cómo se mide |
|---|---|---|---|
| **Tamaño** | ¿Cuánto tengo que construir? | Producto. | LOC, Puntos de Función, Requerimientos. |
| **Esfuerzo** | ¿Cuánto trabajo lleva? | Proyecto. | Horas-persona. |
| **Tiempo** | ¿Cuándo lo entrego? | Proyecto. | Días calendario. |
| **Defectos** | ¿Qué tan bien lo hice? | Producto. | Por severidad. |

> **Limitación de LOC**: depende del lenguaje (mismo sistema en Java = 50k LOC, en Python = 20k LOC). Mejor **Puntos de Función** (agnósticos al lenguaje, estimables antes de codificar) o **Puntos de Historia** (en ágil).

> **Severidad de defectos**: bloqueante (impide usar) > grave (falla operacional) > menor (incomoda) > cosmético (no afecta funcionalidad). **Contar sin severidad no sirve**.

---

## 4. El "sueño del pibe": métricas por nivel organizacional

<img src="imgs/metricas_sueno_pibe.png" alt="El sueno del pibe" width="700">

| Nivel | Qué mira | Métricas clave |
|---|---|---|
| **Desarrollador** | Su trabajo individual. | Esfuerzo, cobertura de unit test, defectos en unit test/peer review. |
| **Equipo de desarrollo** | El proyecto. | Tareas planificadas/completadas, staffing, **volatilidad de requerimientos**, defectos internos. |
| **Organización** | El proceso. | Tiempo calendario, performance de esfuerzo/presupuesto, **defectos en release**. |

> **Cómo memorizarlo**: Desarrollador → su trabajo. Equipo → el proyecto. Organización → el proceso.

> **Volatilidad de requerimientos** = (requerimientos cambiados / total) × 100. Si en 20 historias 5 cambiaron: volatilidad = 25% → mucho retrabajo, plan inestable.

---

## 5. Métricas por enfoque

> *"En cada enfoque de gestión se miden cosas distintas, pero el objetivo es el mismo: tomar decisiones informadas."*

### 5.1. Enfoque Tradicional (procesos definidos)

Variables robustas: **Tamaño** (LOC o PF), **Esfuerzo, Tiempo, Costos, Defectos** .

### 5.2. Enfoque Ágil (procesos empíricos)

<img src="imgs/metricas_agiles_portada.png" alt="Metricas agiles" width="700">

> **Regla de oro del agilismo**: la medición es una **salida**, no una actividad en sí misma. Medir lo necesario y nada más. *"El software funcionando es la principal medida de progreso"*.

<img src="imgs/metricas_agiles_resumen.png" alt="Las 3 metricas agiles" width="700">

#### 5.2.1. Velocidad

> **Velocidad** = puntos de historia **aceptados** por el PO en un sprint. **No se estima, se calcula**. Es histórica, no predictiva. Es el **pulso** del equipo.

<img src="imgs/metricas_velocidad_grafico.png" alt="Grafico de velocidad" width="700">

> **Cuidado con asumir que es constante**: el equipo puede tener grandes oscilaciones (sprint 7 = 4 puntos, sprint 8 = 43) por historias no terminadas, no aceptadas o cerca de terminarse. **Un pico aislado no significa nada, pero una tendencia sostenida sí**.

#### 5.2.2. Capacidad

> **Capacidad** = trabajo que el equipo **puede comprometerse** a hacer en un sprint. **Sí se estima** (en horas para equipos nuevos, en puntos para maduros). Es como el **combustible en el tanque**: sabés cuánto podés recorrer.

**Tabla de cálculo (del apunte, págs. 146-147):**

| Persona | Días disponibles | Días para otras actividades | Horas por día | Horas de esfuerzo disponibles |
|---|---|---|---|---|
| Jorge | 10 | 2 | 4-7 | 32-56 |
| Betty | 8 | 2 | 5-6 | 30-36 |
| Simón | 8 | 2 | 4-6 | 24-36 |
| Pedro | 9 | 2 | 2-3 | 14-21 |
| Raúl | 10 | 2 | 5-6 | 40-48 |
| **Total** | | | | **140-197 horas** |

> Los sprints 1-2 tienen 240h (equipo base), 3-4 suben a 480h (se sumó alguien), 5-6 bajan a 420h (vacaciones), 7 vuelve a 480h. **Total: 2760h = 335 puntos de historia**.

<img src="imgs/metricas_capacidad_grafico.png" alt="Grafico de capacidad" width="700">

#### 5.2.3. RTF (Running Tested Features)

> **RTF** = cantidad de **features probadas y funcionando** que se entregan por iteración. Es la métrica que **mejor refleja el progreso real** (no el trabajo en curso). Es el **contador de "funcionalidades usables"**.

> **Limitación**: cuenta features sin considerar **tamaño ni complejidad** (igual que contar casos de uso sin contar su complejidad). Si tenés 5 features, no sabés si son 5 features chicas o 1 grande.

<img src="imgs/metricas_rtf_grafico.png" alt="Grafico RTF" width="700">

### 5.3. Enfoque Lean / Kanban (flujo)

> Pone el foco en **medir la eficiencia del proceso de flujo de trabajo**. Las métricas clave son **Lead Time, Cycle Time, Touch Time y Eficiencia del Ciclo de Proceso**.

**Ordenadas de la más grande a la más chica:**
1. **Lead Time** → vista del cliente (lo más grande: desde que pide hasta que recibe).
2. **Cycle Time** → vista del equipo (más chica: desde que arranca hasta que termina).
3. **Touch Time** → tiempo realmente trabajado (la más chica: solo lo que se trabajó).

<img src="imgs/kanban_metricas_clave.png" alt="Kanban - Métricas Clave" width="700">

> El tablero real muestra **Lead Time** (flecha superior, de BACKLOG a COMPLETE) y **Cycle Time** (flecha inferior, de DEV a COMPLETE). **Lead incluye al Cycle + el tiempo de espera en cola**.

#### 5.3.1. Lead Time (LA MÁS GRANDE)

> **Lead Time** = tiempo desde que se **pide un ítem** (entra al backlog) hasta que se **entrega** (final del proceso). Mide el **ritmo de entrega al cliente**.

- Es la métrica que el **cliente ve** y percibe.
- **Es la más grande** porque incluye TODO: espera en cola + trabajo del equipo + entrega.

> **Ejemplo del café**: el cliente pide a las **10:00** y se lo entregan a las **10:15** → **Lead Time = 15 minutos** (todo lo que esperó).

#### 5.3.2. Cycle Time (LA INTERMEDIA)

> **Cycle Time** = tiempo entre el **inicio** y el **final del proceso** para un ítem. Mide el **ritmo de terminación** del equipo.

- Es la métrica que el **equipo controla** (cuánto tardó en producirlo).
- **Es más chica que Lead Time** porque no incluye la espera en cola.
- **Lead Time = Cycle Time + espera en cola**.

> **Ejemplo del café**: el barista arrancó a las **10:05** (5 min después de que el cliente pidió, en cola) y terminó a las **10:12** → **Cycle Time = 7 minutos** (10:05 → 10:12). Los 5 min de cola no cuentan.

#### 5.3.3. Touch Time (LA MÁS CHICA)

> **Touch Time** = tiempo en el cual un ítem fue **realmente trabajado** por el equipo, **dentro del cycle time**. Es lo opuesto a **espera**.

- **Es la métrica más chica** porque solo cuenta tiempo activo sobre el ítem.
- El resto del Cycle Time (lo que no es Touch) es **espera dentro del proceso**: bloqueos, esperas de review, esperas de build.

**La regla clave: Touch ≤ Cycle ≤ Lead**

<img src="imgs/kanban_touch_time.png" alt="Kanban - Touch Time y Eficiencia" width="700">

> Cuanto más nos acerquemos al **Lead Time**, más **espera** hay acumulada. Cuanto más nos acerquemos al **Touch Time**, más **eficiente** es el proceso.

> **Ejemplo de eficiencia**: ítem 25 días en sistema, 2 trabajados → Lead = 25, Cycle = 25, Touch = 2 → **Eficiencia = 2/25 = 8%** → el 92% fue desperdicio (espera).

#### 5.3.4. Eficiencia del Ciclo de Proceso

> **% Eficiencia = Touch Time / Elapsed Time**.

> El **Cycle Time** es el **tiempo que el ítem está en la máquina**; el **Touch Time** es el **tiempo que el operario lo está tocando**. La diferencia es **espera** (desperdicio).

<img src="imgs/metricas_cycle_lead_def.png" alt="Definiciones Cycle Time y Lead Time" width="700">

---

## 6. Métricas orientadas a servicio

> Miden el **servicio** que el sistema le entrega al cliente. Hay 4 conceptos clave:

| Concepto | Definición |
|---|---|
| **Expectativa de nivel de servicio** | Lo que los clientes esperan. |
| **Capacidad del nivel de servicio** | Lo que el sistema puede entregar. |
| **SLA (Acuerdo de nivel de servicio)** | Lo que se **acordó** con el cliente. |
| **Umbral de adecuación** | Lo que el cliente considera **aceptable**. |

> **SLA ≠ Umbral**. El SLA es lo que acordaste, el umbral es lo que el cliente acepta. **Hay que estar siempre dentro del umbral**, aunque estés dentro del SLA.

> **Ejemplo del banco**: SLA = transferencia en <24h. Umbral = <1h (si tarda más, es inaceptable para el cliente). **Hay que estar por debajo de 1h**, no de 24h.

---

## 7. Atributos de calidad y epifenómenos

> Ni la **calidad** ni la **usabilidad** se miden de forma directa. No podemos medir *"litros de usabilidad"*. Hay que recurrir a **epifenómenos**: medir **atributos internos o derivados** cuantificables que se **correlacionan** con el atributo externo (Sommerville, Pressman).

**Epifenómenos típicos para medir usabilidad:**

| Epifenómeno | Por qué se correlaciona |
|---|---|
| Cantidad de clics para una tarea | Menos clics = más fácil. |
| Tiempo en completar una tarea | Más rápido = más intuitivo. |
| Errores del usuario (no del sistema) | Menos errores = más usable. |
| Horas de capacitación necesarias | Menos = más usable. |
| Tasa de abandono en un flujo | Más abandono = menos usable. |

> **Ejemplo**: para medir la usabilidad de un formulario de registro, mido **tasa de éxito** (70%), **tiempo promedio** (3 min), **errores por usuario** (2.3), **pedidos de ayuda** (15/día). Esos números **no son "usabilidad"**, pero me dan una señal.

---

## 8. DRE — Eficiencia en la Remoción del Defecto

> **DRE (Defect Removal Efficiency)** = porcentaje de defectos **detectados antes de llegar al cliente** (en producción).

> **DRE = (Defectos encontrados antes de release / Total de defectos encontrados) × 100**

> **Ejemplo**: en testing se encontraron 80 defectos, en producción 20 → **DRE = 80%** → el equipo detectó el 80% antes de que llegaran al cliente. **Organizaciones de calidad alta (CMMI 5) tienen DRE > 95%**.

> **Analogía del colador**: si dejás pasar mucho (DRE 80%), el colador tiene agujeros. Si pasás poco (DRE 95%), el colador está apretado.

---

## 9. Resumen visual por enfoque

<img src="imgs/metricas_resumen_enfoques.png" alt="Resumen por enfoque" width="700">

| Tradicional | Ágil | Lean (Kanban) |
|---|---|---|
| Esfuerzo | Velocidad | Lead Time |
| Tiempo | Capacidad | Cycle Time |
| Costos | RTF | Touch Time |
| Defectos | | Eficiencia del Proceso |

<img src="imgs/metricas_producto.png" alt="Metricas para producto software" width="700">

> **Métricas de producto**: Tamaño (LOC, PF, Requerimientos) y Defectos (cobertura, severidad, densidad).

---

## 10. Tabla maestra: comparación de métricas

| Métrica | Qué mide | Quién la usa | Tipo |
|---|---|---|---|
| **LOC / PF** | Tamaño. | Tradicional. | Producto. |
| **Esfuerzo** | Horas-persona. | Tradicional. | Proyecto. |
| **Tiempo calendario** | Duración. | Tradicional. | Proyecto. |
| **Costos** | Presupuesto. | Tradicional. | Proyecto. |
| **Defectos** | Por severidad. | Todos. | Producto. |
| **Densidad de defectos** | Por KLOC. | Tradicional. | Producto. |
| **DRE** | % pre-release. | Todos. | Proceso. |
| **Story Points** | Tamaño relativo. | Scrum. | Producto. |
| **Velocity** | Puntos aceptados/sprint. | Scrum. | Proyecto. |
| **Capacidad** | Trabajo posible/sprint. | Scrum. | Proyecto. |
| **RTF** | Features funcionando. | Scrum. | Producto. |
| **Burndown / Burnup** | Restantes / completados. | Scrum/Kanban. | Proyecto. |
| **Lead Time** | Vista del cliente. | Kanban. | Proceso. |
| **Cycle Time** | Vista interna. | Kanban. | Proceso. |
| **Touch Time** | Tiempo trabajado. | Kanban. | Proceso. |
| **Eficiencia de flujo** | Touch / Elapsed. | Kanban. | Proceso. |
| **WIP** | Trabajo en curso. | Kanban. | Proceso. |
| **SLA / Umbral** | Nivel de servicio. | Servicio. | Producto. |

---

## 11. Reglas mnemotécnicas para el oral

1. **4 dominios = 4P**: Proceso / Proyecto / Producto / Personas.
2. **Por enfoque = 3 estrellas**:
   - Tradicional: Esfuerzo + Tiempo + Costos + Defectos.
   - Ágil: **V**elocidad + **C**apacidad + **R**TF.
   - Lean: **L**ead + **C**ycle + **T**ouch + **E**ficiencia.
3. **Touch ≤ Cycle ≤ Lead**: trabalenguas que no se olvida.
4. **Lead = cliente, Cycle = equipo**: el equipo controla Cycle, el cliente sufre Lead.
5. **La velocidad NO se estima, se calcula**: es el pulso histórico, no una promesa.
6. **GQM = Goal → Question → Metric**: si la métrica no responde una pregunta, no sirve.
7. **Métrica vs. Indicador**: métrica = dato, indicador = alarma con contexto.
8. **Estimación vs. Métrica**: estimación = pronóstico, métrica = realidad, indicador = desvío.

---

## 12. Chivo para el oral

### Bloque 1: Conceptos fundamentales

1. **¿Por qué medir?** Porque no se puede controlar lo que no se mide. La métrica es un **número objetivo** que da **visibilidad** para **tomar decisiones**.
2. **4 dominios**: **Proceso** (despersonalizado, estratégico), **Proyecto** (atribuido, táctico), **Producto** (tamaño/defectos), **Personas** (cuarto eje, en clase).
3. **GQM**: derivar métricas de un Goal a través de Questions. Si la métrica no responde una pregunta, no sirve.
4. **Mantenerlo simple**: *"si estás a millas de distancia, no tiene sentido medir en milímetros"*.

### Bloque 2: Métricas básicas

5. **4 métricas básicas**: **Tamaño** (LOC/PF/reqs), **Esfuerzo** (horas-persona), **Tiempo** (calendario), **Defectos** (por severidad).
6. **PF (Puntos de Función)**: agnóstico al lenguaje, estimable antes de codificar. LOC no sirve bien.
7. **Defectos por severidad**: bloqueante, grave, menor, cosmético. Contar sin severidad no sirve.

### Bloque 3: Métricas por enfoque

8. **Tradicional**: Esfuerzo, Tiempo, Costos, Defectos.
9. **Ágil**:
   - **Velocidad**: puntos de historia **aceptados** por el PO. **No se estima, se calcula**. Histórica, no predictiva. Cuidado con las oscilaciones.
   - **Capacidad**: trabajo que el equipo **puede comprometerse**. **Sí se estima** (140-197h en el ejemplo).
   - **RTF**: features probadas y funcionando. Refleja el progreso real. Limitación: no considera tamaño/complejidad.
10. **Lean (Kanban)**: **Lead Time** (vista del cliente), **Cycle Time** (vista del equipo), **Touch Time** (trabajo real), **Eficiencia = Touch / Elapsed**.

### Bloque 4: Diferencias y relaciones

11. **Touch ≤ Cycle ≤ Lead**.
12. **Lead incluye Cycle + espera en cola**.
13. **Velocity mide producto aceptado; Capacity mide producto posible**.
14. **Sueño del pibe**: Desarrollador → su trabajo. Equipo → el proyecto. Organización → el proceso.
15. **Brooks**: *"de a un día por vez"*. Las métricas sirven para detectar el desvío temprano y corregir antes de que sea tarde — también aplica a la **oscilación de la velocidad** en ágil.

### Bloque 5: Conceptos avanzados

16. **Epifenómenos**: la calidad y la usabilidad no se miden directo. Medimos **clics, tiempo de tarea, errores de usuario, capacitación** como proxies.
17. **DRE** = defectos pre-release / total. DRE alto = colador apretado. CMMI 5 → DRE > 95%.
18. **SLA vs. Umbral**: el SLA es lo que acordaste, el **umbral es lo que el cliente considera aceptable**. Hay que estar **siempre dentro del umbral**.

### Frase de cierre

> *"Las métricas de software no son números fríos en un tablero: son el mecanismo fundamental para entender el impacto de nuestras decisiones. Midiendo proceso, proyectos y productos, una organización aprende de sus errores, optimiza su esfuerzo y garantiza software de alta calidad."*

---

## 13. Respuestas modelo para preguntas frecuentes

> **"¿Qué es una métrica?"** → Una **medida cuantitativa** del grado en el que un sistema, componente o proceso posee un atributo. Es un **número objetivo** que da visibilidad para decidir.

> **"¿Diferencia entre métrica, indicador y estimación?"** → **Métrica** = el dato crudo (se mide después). **Indicador** = la métrica con contexto (umbral, comparación, ratio). **Estimación** = la predicción (antes). Se conectan por el **desvío** = `(Real - Planificado) / Planificado × 100`.

> **"¿Métrica de proceso vs. de proyecto?"** → La de **proyecto** es atribuida a un proyecto particular. La de **proceso** es **despersonalizada**, sumada de muchos proyectos, pública para toda la org. Las de proyecto se **consolidan** para crear las de proceso.

> **"¿Qué es la velocidad?"** → Puntos de historia **aceptados** por el PO en un sprint. **No se estima, se calcula**. Es histórica. Cuidado con asumirla constante: puede oscilar mucho (sprint 7 = 4, sprint 8 = 43).

> **"¿Qué es la capacidad?"** → Trabajo que el equipo **puede comprometerse** a hacer en un sprint. **Sí se estima**. Se calcula con la tabla de **días disponibles × horas por día - días de actividades Scrum** (140-197h en el ejemplo).

> **"¿Qué es RTF?"** → **Running Tested Features**: features probadas y funcionando por iteración. Refleja el progreso real. **Limitación**: no considera tamaño ni complejidad.

> **"¿Lead Time vs. Cycle Time?"** → **Lead Time** = vista del **cliente** (pide → recibe, incluye espera en cola). **Cycle Time** = vista **interna** del equipo (arranca → termina). **Lead ≥ Cycle**. Ejemplo del café: Lead = 15 min, Cycle = 7 min, cola = 5 min.

> **"¿Qué es el Touch Time?"** → Tiempo en que el ítem fue **realmente trabajado** dentro del Cycle Time. Es lo opuesto a espera. Si un ítem estuvo 25 días en el sistema pero solo 2 fue trabajado: Touch = 2, **Eficiencia = 8%**.

> **"¿Qué es GQM?"** → **Goal-Question-Metric**: técnica para **derivar métricas desde un objetivo de negocio**. Primero el Goal, después las Questions, después las Metrics. Si una métrica no responde una pregunta que sirve al goal, no sirve.

> **"¿Qué es el DRE?"** → **Defect Removal Efficiency**: % de defectos **detectados antes del release**. DRE = (pre-release / total) × 100. Si en testing 80 y en producción 20, DRE = 80%. **Organizaciones de calidad alta tienen DRE > 95%**.

> **"¿Cómo se mide la usabilidad?"** → **No se mide directamente**. La usabilidad es un **atributo de calidad externo** subjetivo. Se miden **epifenómenos**: clics para una tarea, tiempo de completado, errores del usuario, horas de capacitación, tasa de abandono.

> **"¿Por qué no usar LOC?"** → Porque es **difícil de estimar** antes de codificar y depende del **lenguaje** (mismo sistema en Java 50k LOC, en Python 20k LOC). Mejor **Puntos de Función** o **Puntos de Historia**.

> **"¿SLA y umbral son lo mismo?"** → **No**. El **SLA** es lo que acordaste con el cliente (ej. entrega en 24h). El **umbral** es lo que el cliente considera **aceptable** (ej. si tarda más de 1h es inaceptable). Aunque estés dentro del SLA, si superás el umbral, el servicio es inaceptable. **Hay que estar siempre dentro del umbral**.

> **"¿Por qué se estima y se mide lo mismo (tamaño, esfuerzo, tiempo)?"** → **No es lo mismo**, aunque el objeto lo sea. **Estimación** se hace antes (predicción subjetiva). **Métrica** se hace después (medición real). Se conectan por el **desvío**. Las métricas **mejoran las próximas estimaciones**: si siempre mediste 25% más, ajustás con un colchón.

> **"¿Qué dijo Brooks sobre los atrasos?"** → *"Los proyectos se retrasan de a un día por vez"*. Si tenés buenas métricas, detectás el desvío temprano y lo corregís antes de que sea tarde.
