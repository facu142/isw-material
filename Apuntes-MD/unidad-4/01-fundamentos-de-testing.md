# 01 — Fundamentos de Testing

> Págs. 167-170 del apunte. Cubre el concepto de testing, la visión tradicional, los principios, y la diferencia entre error y defecto.

## Contexto: dónde encaja el testing en la calidad

![Aseguramiento de la calidad de software](imgs/p167_img1.png)

El testing es **una de las tareas del Aseguramiento de Calidad de Software**, junto con el control de calidad del proceso y del producto. La calidad se obtiene a lo largo de todo el desarrollo, y una buena SCM (administración de configuración) es el puntapié inicial.

---

## Concepto

> Proceso mediante el cual se somete a un software o un componente a condiciones específicas con el fin de determinar y demostrar si el mismo es válido o no en función de los requerimientos especificados.

---

## Visión del testing (la apropiada)

- Es un proceso **destructivo**: se busca encontrar defectos (cuya presencia se asume) en el código.
- Hay que ir con **actitud negativa**, intentando demostrar que algo es incorrecto.
- **Testing exitoso** = el que encuentra defectos.
- Representa entre el **30% y el 50%** del costo del producto.
- El testing **NO asegura** que el producto sea de calidad (ni la agrega), ni que el proceso por el que se desarrolló sea de calidad.

> Aclaremos: el testing no es calidad de producto ni de proceso; solo garantiza que el producto sea **confiable**.

---

## ¿Cuánto testing es suficiente?

El **testing exhaustivo es imposible** por la cantidad de tiempo que requiere. El momento de dejar de testear depende del **nivel de riesgo o costo** asociado al proyecto. Los riesgos permiten definir prioridades: qué se testea primero y con qué esfuerzo.

El **Criterio de Aceptación** resuelve cuándo una fase de testing se considera completada. Se puede definir en términos de:

- Costos.
- % de test corridos sin fallas.
- No hay defectos de una determinada severidad.

---

## Relación con el ciclo de vida

Lo ideal es testear **lo más temprano posible** para abaratar costos. No hace falta tener código para empezar a testear: con la historia de usuario o los requerimientos ya alcanza.

> Hay modelos (como cascada) que lo implementan en fases tardías, con consecuencias negativas.

---

## Mitos sobre el testing

- "El testing es una etapa que comienza al terminar de codificar." ❌
- "El testing es probar que el software funciona." ❌
- "Testing = Calidad de producto." ❌
- "Testing = Calidad de proceso." ❌
- "El tester es el enemigo del programador." ❌

> Aunque hagas un testing excelente, con 0 errores, el producto puede seguir teniendo fallas de calidad porque la calidad es **subjetiva** y depende de varios factores, como la experiencia de usuario.

---

## Principios del Testing

| # | Principio | Explicación |
|---|---|---|
| 1 | El testing muestra la **presencia** de defectos | El propósito es encontrar defectos, no probar que el software está libre de ellos. |
| 2 | El testing **exhaustivo** es imposible | No se pueden probar todas las combinaciones de entradas, condiciones y resultados. |
| 3 | **Testing temprano** | Debe comenzar lo antes posible (idealmente en la fase de requisitos). Detectar temprano reduce costos. |
| 4 | **Principio de Pareto** | Los defectos se concentran en pocos módulos o áreas (regla 80/20). |
| 5 | **Paradoja del pesticida** | Si se usan siempre los mismos tests, con el tiempo dejarán de encontrar nuevos defectos. |
| 6 | **Dependiente del contexto** | Las técnicas dependen del tipo de sistema (un sistema bancario requiere pruebas más rigurosas que uno de entretenimiento). |
| 7 | **Falacia de la ausencia de errores** | Aunque no se encuentren errores, el software puede no satisfacer las necesidades del cliente. |
| 8 | **Evitar probar el propio código** | Los programadores tienen sesgo personal hacia su trabajo. |

---

## Errores y defectos

La diferencia está en el **momento en que se detectan** y se solucionan:

- **Error**: se descubre en la misma etapa en la que se está trabajando.
- **Defecto**: es un error que **no se descubrió en su etapa** y se trasladó a etapas posteriores.

> Lo que el testing busca son **defectos**.

### Clasificación de defectos

| Dimensión | Categorías |
|---|---|
| **Severidad** (gravedad) | Bloqueante · Crítico · Mayor · Menor · Cosmético |
| **Prioridad** (urgencia) | Urgente · Alta · Media · Baja |

> **Ojo**: severidad ≠ prioridad. Un defecto cosmético (ej. error de ortografía) puede tener **alta prioridad** para la empresa (no quiere quedar como analfabeta en su web).

---

## Chivo para el oral

1. **Concepto + visión**: arrancá con la definición y dejá claro que es un proceso **destructivo** y que un testing exitoso es el que **encuentra defectos**.
2. **Aclaración clave**: el testing **no es calidad**, solo garantiza confiabilidad.
3. **Principios**: nombrá los 7-8 más importantes (exhaustivo imposible, temprano, pareto, falacia, contexto).
4. **Error vs. defecto**: la diferencia es **cuándo se descubre**. El testing busca defectos.
5. **Cerrá con severidad ≠ prioridad** (ejemplo de la ortografía) — un clásico de pregunta trampa.

> Si te preguntan **"¿el testing asegura calidad?"** → no, y agregá por qué: la calidad es subjetiva, depende del usuario, de las expectativas, etc.
