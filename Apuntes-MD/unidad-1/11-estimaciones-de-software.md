# 11 — Estimaciones de Software

> Págs. 30 + 35 del apunte + presentación 05. Cubre las 5 estimaciones en el orden recomendado (tamaño, esfuerzo, calendario, costo, recursos críticos).

## Concepto

> En un proyecto de desarrollo de software, se trata de **estimar para predecir el valor de un elemento** relacionado con el proyecto o con el producto: el tiempo que va a llevar, el costo, cuántas personas se necesitan, etc.

> En un enfoque **tradicional**, esta estimación es realizada únicamente por el **líder de proyecto**. En la metodología tradicional existe un **orden definido y recomendado** para realizar las estimaciones.

---

## El orden de las estimaciones (tradicional)

> En la gestión tradicional, se plantea una secuencia de estimaciones con el siguiente orden:

1. **Tamaño** (lo primero).
2. **Esfuerzo**.
3. **Calendario**.
4. **Costo**.
5. **Recursos críticos** (lo último).

> El tamaño es la más importante porque **influye en los otros aspectos** (esfuerzo, costo, tiempo de calendario).

---

## 1. Tamaño

> Definir el **producto a construir**. Esta estimación es una de las más importantes porque **influye en otros aspectos** como el esfuerzo, el costo, el tiempo de calendario, etc.

### Ejemplos de cómo medir el tamaño

- **Líneas de código** (así se hacía antes; es un método **muy pobre**).
- **Por casos de uso / requerimientos** (un poco más sofisticado).

> La **lógica de la cascada de estimaciones**: el tamaño define el esfuerzo, el esfuerzo define el calendario, el calendario y el esfuerzo definen el costo.

---

## 2. Esfuerzo

> Medido en **horas-persona lineales** (no se tienen en cuenta las horas de ocio).

- Es la cantidad de trabajo total necesario para completar el producto.
- Se calcula a partir del tamaño (más tamaño = más esfuerzo, en general).

---

## 3. Calendario

> Determinar **qué días y qué horas se trabaja**, y **cuántas personas van a trabajar**.

- Es necesario para darle al cliente una idea de **cuánto tiempo se va a demorar** la finalización del proyecto.
- Una vez que tenés el esfuerzo (horas-persona), podés estimar el calendario dividiendo por la cantidad de personas y los días laborables.

---

## 4. Costo

> De forma similar a la estimación de la duración, la estimación de **costos depende directamente del tamaño y del esfuerzo** que se necesite para el desarrollo. Por eso es **lo último que se estima**.

- Es muy útil para darle una idea al cliente del **costo aproximado** del proyecto.

---

## 5. Recursos críticos

> Identificar los **recursos clave** (humanos o técnicos) que pueden ser cuello de botella o que son especialmente difíciles de conseguir.

---

## Orden de las estimaciones (resumen visual)

```
Tamaño (qué construir)
    ↓
Esfuerzo (cuánto trabajo)
    ↓
Calendario (cuánto tiempo)
    ↓
Costo (cuánto dinero)
    ↓
Recursos críticos (qué hace falta asegurar)
```

> **Cada estimación depende de la anterior**. Por eso se estima en cascada.

---

## Nota sobre las técnicas de estimación

> Con respecto a las técnicas de estimación no las vamos a nombrar ahora porque no tiene sentido: **más adelante en el resumen se las explica con mayor profundidad**.

> Las técnicas se verán con más detalle en la unidad 2 (estimaciones ágiles, Planning Poker, Wideband Delphi, etc.).

---

## Chivo para el oral

1. **Concepto**: estimar es **predecir valores** relacionados con el proyecto o producto (tiempo, costo, gente).
2. **Orden de estimación** (en cascada):
   - **Tamaño** primero (lo más importante, define todo lo demás). Opciones: líneas de código (pobre) o casos de uso/requerimientos (mejor).
   - **Esfuerzo** segundo: horas-persona lineales.
   - **Calendario** tercero: días y horas de trabajo, cantidad de personas.
   - **Costo** cuarto: depende del tamaño y esfuerzo.
   - **Recursos críticos** al final.
3. **Enfoque tradicional**: lo hace **solo el líder de proyecto**.
4. **Cerrá con la idea**: cada estimación depende de la anterior. **Si cambia el tamaño, cambian todas las demás**. Por eso el tamaño es la primera y la más crítica.

> **Si te preguntan "¿por qué se estima el tamaño primero?"** → porque el tamaño **define el esfuerzo, el esfuerzo define el calendario, y el calendario y el esfuerzo definen el costo**. Si no sabés qué construir, no podés saber cuánto cuesta ni cuánto tarda.
