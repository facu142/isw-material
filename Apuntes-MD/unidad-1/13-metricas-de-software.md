# 13 — Métricas de Software

> Págs. 33-35 del apunte + presentación 05. Cubre los 3 dominios de las métricas, las métricas básicas, el monitoreo y control, y la cita de Brooks.

## Concepto

> Las **métricas** son **medidas numéricas o porcentajes** que aportan **visibilidad** sobre el proyecto. Son útiles para saber si nuestro proyecto está **en línea con lo planificado** o si se está **desviando**.

> El dominio de las métricas de software se divide en **3 grandes grupos**.

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

| Métrica | Pertenece a |
|---|---|
| **Tamaño del producto** | Producto |
| **Esfuerzo** | Proyecto |
| **Tiempo (calendario)** | Proyecto |
| **Defecto** | Producto |

> Un aspecto **clave** a la hora de tomar métricas es **mantenerlo simple**. El esfuerzo tiene que ser el menor posible.

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
- Volatilidad de requerimientos.
- Nro. de defectos en integración y prueba de sistemas.
- Nro. de defectos en peer reviews.
- Status de distribución de defectos.
- % de test ejecutados.

### Organización

- Tiempo calendario.
- Performance actual y planificada de esfuerzo.
- Performance actual y planificada de presupuesto.
- Precisión de estimaciones en schedule y esfuerzo.
- Defectos en release.

---

## Monitoreo y Control

> El monitoreo y control, que es para lo que usamos las métricas, tiene que ver con ir **comparando lo planificado y lo real**.

- La línea perfecta entre lo planificado y lo real no existe, suele estar **algo dibujado**.
- De esto se encarga el **líder de proyecto**.

> En el libro *The Mythical Man-Month* (Fred Brooks) se habla de que **los proyectos se retrasan 1 día a la vez**. Justamente si tenemos una buena planificación y buenas métricas, un desvío **no será difícil de corregir** si es tomado a tiempo.

> *"Como se atrasa un proyecto: de a un día por vez."* — Fred Brooks.

---

## Mantenerlo simple

> *"Si estás a millas de distancia de tu destino, no tiene sentido medir en milímetros."*

Preguntas antes de tomar una métrica:

- ¿Nos da más información que la que tenemos ahora?
- ¿Es esta información de beneficio práctico?
- ¿Nos dice lo que queremos saber?

> Si la respuesta a alguna es **no**, descartala.

---

## ¿Para qué se usan las estimaciones, las métricas y los riesgos?

> Sirven para el **monitoreo y control** del proyecto:

- Comparar lo planificado y lo real.
- Detectar desvíos temprano.
- Corregir el rumbo antes de que sea tarde.
- Comunicar el estado del proyecto a los stakeholders.

---

## Chivo para el oral

1. **Concepto**: medidas numéricas que dan **visibilidad** sobre el proyecto.
2. **3 dominios**:
   - **Proceso** (organización, despersonalizadas).
   - **Proyecto** (¿se está cumpliendo lo planificado?).
   - **Producto** (tamaño, defectos).
3. **Métricas básicas**: tamaño, esfuerzo, tiempo, defectos.
4. **Mantenerlo simple**: si no aporta información nueva y útil, no la tomes.
5. **Monitoreo y control**: comparar planificado vs. real. **Es responsabilidad del líder**.
6. **Brooks**: *"de a un día por vez"*. Si tenés buenas métricas, un desvío pequeño se corrige a tiempo.
7. **Cerrá con la idea**: las métricas son el insumo del monitoreo. Sin métricas, no podés controlar nada.

> **Si te preguntan "¿qué es una métrica de proceso vs. de proyecto?"** → la de **proyecto** analiza **un proyecto particular** (¿se está cumpliendo este plan?); la de **proceso** analiza **muchos proyectos** despersonalizados (¿cómo funciona la organización en su conjunto?).
