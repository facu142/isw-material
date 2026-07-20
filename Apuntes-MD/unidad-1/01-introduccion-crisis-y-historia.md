# 01 — Introducción: Crisis del Software e Historia

> Págs. 1-3 del apunte + presentación 00. Cubre qué es software, la crisis del software, las estadísticas de Standish, la línea de tiempo de la IS, y por qué "saber programar no es suficiente".

## ¿Qué es software?

> Software es un set de **programas y la documentación que los acompaña** (Margaret Hamilton mostrando el código fuente del Apollo es el ejemplo clásico de qué es un producto de software).

Existen **tres tipos básicos de software**:

- **System software** (de sistema).
- **Utilitarios** (herramientas).
- **Software de aplicación**.

> Es importante entender que el software es un **esfuerzo intelectual humano**. La creación de software depende de las personalidades e intelectos de los miembros del equipo que lo crean. Un proceso que entrega gran software para un equipo puede fallar completamente con otro.

---

## La Crisis del Software

> La **crisis del software** surge en los años 60 y 70 cuando se empezaron a evidenciar graves problemas en el desarrollo de software. El término fue planteado en la **conferencia de la OTAN en 1968** por **Friedrich Bauer**, quien recalcó la dificultad para generar software libre de defectos, fácilmente comprensible y verificable.

### Causas principales

- El **hardware avanzó muchísimo** (debido al avance de los circuitos integrados) mientras que el software se quedó atrás, porque es una **actividad humana**.
- **Demandas crecientes**: a medida que la tecnología y las técnicas de desarrollo evolucionan, la demanda de sistemas más grandes y complejos aumenta.
- Se utilizaban **metodologías ad hoc**, que carecían de rigor estructural y no podían gestionar sistemas cada vez más grandes y críticos.

> **¿Qué es una metodología ad hoc?** Prácticas de desarrollo improvisadas, informales, que dependían de la experiencia individual. Cada equipo desarrollaba a su manera, sin procesos bien definidos.

### Problemas típicos

- **Retrasos en la entrega**: los desarrollos se extendían más allá de los plazos.
- **Sobrecostes**: presupuestos subestimados, a menudo duplicados o triplicados.
- **Calidad deficiente**: software plagado de errores, mal rendimiento, mala experiencia de usuario.
- **Mantenibilidad limitada**: difícil de modificar por falta de documentación, técnicas no sistemáticas, poca modularidad.

---

## ¿Cómo estamos hoy?

El avance de la Ingeniería de Software como disciplina ha permitido abordar muchos de estos desafíos con metodologías, herramientas y técnicas más avanzadas. Algunos avances que ayudaron a gestionar la crisis:

- **Entornos integrados de desarrollo** (IDE).
- **Testing**.
- **SCM y lenguajes como Git**.

---

## ¿Cuándo nos va bien? (Standish)

El *CHAOS Report* de Standish Group muestra que el éxito de los proyectos se explica por:

| Factor | % |
|---|---|
| Involucramiento del usuario | 15,9% |
| Apoyo de la gerencia | 13,0% |
| Enunciado claro de los requerimientos | 9,6% |
| Planeamiento adecuado | 8,2% |
| Expectativas realistas | 7,7% |
| Hitos intermedios | 7,7% |
| Personas competentes | 7,2% |

## ¿Cuándo nos va mal?

| Factor | % |
|---|---|
| Requerimientos incompletos | 13,1% |
| Falta de involucramiento del usuario | 12,4% |
| Falta de recursos | 10,6% |
| Expectativas poco realistas | 9,3% |
| Falta de apoyo de la gerencia | 8,7% |
| Requerimientos cambiantes | 8,1% |

> **Lo que entregamos ≠ las especificaciones ≠ el presupuesto.** Los 3 ejes se desbalancean constantemente.

> **Conclusión**: **saber programar NO es suficiente**.

---

## Línea de tiempo de la IS

| Año | Hito |
|---|---|
| **1968** | Nace el término "crisis del software" — Conferencia de la **NATO**. |
| **1975** | *The Mythical Man-Month* — **Frederick Brooks**. |
| **1978** | Tom DeMarco introduce **Structured Analysis**. |
| **80s** | Primeros grandes errores de software conocidos. |
| **1987** | *No Silver Bullet* (**Brooks**). Características esenciales del software. |
| **1989** | *Managing the Software Process* — **Watts Humphrey**. |
| **1990** | Internet / Object Oriented. |
| **1991** | **CMM 1.0**. |
| **1993** | CMM 1.1. |
| **2000** | **CMMI 1.0**. |
| **2001** | **Manifiesto Ágil** (Snowbird, Utah). |
| **2003** | **Lean Software Development**. |

---

## SEBoK — Cuerpo de Conocimiento de la IS

- *Software Engineering Body of Knowledge*.
- **Versión 3.0 del 2014** de la **IEEE**.
- Está conformado por **15 áreas de conocimiento**.

> Es el equivalente al PMBOK pero para la ingeniería de software: define qué debe saber un ingeniero de software.

---

## Chivo para el oral

1. **Arrancá con la definición de software**: "es un set de programas y la documentación que los acompaña" (los 3 tipos: sistema, utilitarios, aplicación).
2. **Crisis del software**: definida por **Bauer en 1968 en la NATO**. Tres causas: el hardware avanzó más que el software (es humano-intensivo), demandas crecientes, y metodologías ad hoc.
3. **Contraste con hoy**: IDEs, testing, SCM/Git ayudaron a gestionar la crisis.
4. **Standish**: mencioná las estadísticas clave (involucramiento del usuario 15,9% como principal causa de éxito; requerimientos incompletos 13,1% como principal causa de fracaso).
5. **Línea de tiempo**: arrancá con 1968 NATO y terminá con 2001 Manifiesto Ágil.
6. **Cerrá con SEBoK**: 15 áreas, IEEE 2014.

> **Si te preguntan "¿qué es la crisis del software?"** → un conjunto de problemas (retrasos, sobrecostes, mala calidad, baja mantenibilidad) que aparecieron en los 60/70 y que motivaron la creación de la IS como disciplina.
