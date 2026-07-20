# 02 — Casos de Prueba

> Págs. 171-174 del apunte. Cubre la definición, las partes, un ejemplo, y las técnicas de derivación (clases de equivalencia y valores límite).

## Definición

> Un **caso de prueba** es un conjunto de condiciones o variables que permiten determinar si el software (o una parte) está funcionando correctamente.

## Partes de un caso de prueba

| Parte | Qué define |
|---|---|
| **Objetivo** | La característica del sistema a comprobar. |
| **Datos de entrada y de ambiente** | Datos a introducir al sistema, con el sistema en condiciones preestablecidas. |
| **Comportamiento esperado** | La salida o acción esperada, según los requerimientos. |

---

## Ejemplo de caso de prueba

| ID | Prioridad | Nombre | Precondiciones | Pasos | Resultado esperado |
|---|---|---|---|---|---|
| 1 | Media | Taxis libres filtrados por barrio | · Usuario "Carlos" registrado y logueado con perfil de administrador.<br>· Software configurado con ubicación, radio en Córdoba.<br>· Barrios de Córdoba cargados (Nueva Córdoba, El Cerro, Alta Córdoba, etc).<br>· Hay taxis conectados, libres, en Alta Córdoba, patente AF925ED. | 1. El admin selecciona "ver mapa de taxis".<br>2. Selecciona el barrio "Alta Córdoba".<br>3. Selecciona filtro de estado "libre". | El sistema muestra un mapa de Córdoba con zoom en Alta Córdoba, visualizando el taxi libre con patente AF925ED. |

---

## El problema: ¿cuántos casos de prueba defino?

> No se puede identificar o definir casos de prueba de manera infinita, ni de manera exploratoria o según lo que se me ocurra. Se necesita un mecanismo que permita **definir la menor cantidad de casos cubriendo el testing de forma holística**.

---

## Clases de equivalencia y valores límite

Los **bugs se esconden en las esquinas y se congregan en los límites**.

> **Ejemplo**: en una compra con valor mínimo $0 y máximo $100.000, conviene aprobar con valores esquina: **$100.000, $0, $1, $100.001, $100.000,32**. **No tiene sentido** probar $43.534.

### Partición de equivalencias

Se identifican **clases de equivalencia** (de entrada y de salida) que definen subconjuntos de datos válidos o no. Luego se toman representantes de cada clase.

> **Ejemplo (de la imagen del apunte)**: para un campo "Duración" con rango 10-25 y fracciones 0,5 ó 0:

| Condición | Clase | Casos |
|---|---|---|
| ≥10 y ≤25 con fracción 0, 5 ó 0 | Válida | 10, 20, 25 |
| ≥10 y ≤25 con fracción **distinta** de 0, 5 ó 0 | Inválida | 10,3 |
| Entero <10 o >25 | Inválida | 11 |
| Otro valor | Inválida | 12 |
| No ingresa valor | Inválida | 13 |

### Análisis de valores límite

Es una herramienta **dentro** de la partición de equivalencias: usar los **bordes** de cada clase para definir los casos de prueba (mínimo, mínimo-1, máximo, máximo+1).

---

## De dónde derivar los casos de prueba

> Cuanto más documentado está el software, más fácil es derivar un caso de prueba. Si el proyecto tiene puro código y casi nada escrito en la ERS, derivar casos se complica.

![Derivación de casos de prueba](imgs/p173_img2.png)

Los casos se pueden derivar desde:
- Documentos del cliente.
- Información de relevamiento.
- Requerimientos.
- Especificaciones de programación.
- El código mismo.

---

## Ciclo de Prueba

> Es la **ejecución de un conjunto de casos de prueba en una versión determinada** del producto. Generalmente se tienen **2 ciclos**; el primero se llama **ciclo 0**. El ciclo 0 siempre es **manual** (allí se configura todo) y a partir del **ciclo 1** ya se pueden automatizar las pruebas.

---

## Regresión

> Al concluir un ciclo de pruebas y reemplazarse la versión del sistema, debe realizarse una **verificación total de la nueva versión**, a fin de prevenir la introducción de nuevos defectos al intentar solucionar los detectados.

> "Volve a revisar todo antes de realizar un nuevo ciclo de test, ya que al solucionar un error es probable que hayan aparecido 1 o dos más."

---

## Chivo para el oral

1. **Definí qué es un caso de prueba** y sus 3 partes (objetivo, datos, comportamiento esperado).
2. **Mostrá el ejemplo** de la tabla (Taxis / Alta Córdoba / AF925ED) — es muy gráfico.
3. **Explicá el problema**: no se puede probar infinito, hay que derivar con criterio.
4. **Conectá con clases de equivalencia y valores límite**: los bugs están en los bordes. Mencioná la tabla del campo Duración.
5. **Cerrá con regresión** y por qué es importante antes de un nuevo ciclo.

> **Tip**: si te preguntan "¿por qué los valores límite?" → porque la mayoría de los errores de programación (off-by-one, comparaciones con `<` en vez de `<=`, etc.) caen en los bordes de los rangos válidos.
