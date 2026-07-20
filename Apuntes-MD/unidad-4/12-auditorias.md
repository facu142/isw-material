# 12 — Auditorías de Software

> Págs. 233-240 del apunte. Cubre el concepto, los tipos (PCA, FCA, de Proyecto), el proceso, las técnicas y las métricas.

## Concepto

> Las auditorías son **evaluaciones independientes** (realizadas por un grupo de personas **ajenas al equipo** de trabajo) de los productos o procesos de software, para asegurar el cumplimiento con estándares, lineamientos, especificaciones y procedimientos, basada en un **criterio objetivo**.

> A diferencia de las revisiones técnicas, las auditorías buscan la **máxima objetividad**, lograda cuando la evaluación la realiza alguien que **no pertenece al proyecto**.

Son un instrumento para el **Aseguramiento de la Calidad en el Software**.

> Las auditorías se pueden realizar tanto a nivel de **producto** como de **proyecto** (revisiones técnicas también).

---

## Tipos de Auditorías

### 1. Auditoría Física de Configuración (PCA)

- Asegura que lo indicado para cada **ítem de configuración** (IC) en la **línea base** se haya alcanzado según el plan de configuración, contra lo que tengo en el repositorio.
- Con respecto al código, se compara al mismo con la **documentación de soporte**.
- **Nivel general**: se compara el código con la documentación de soporte y se verifica que sea consistente.
- **Verificación**: asegura que el producto cumple con los objetivos preestablecidos definidos en la documentación de líneas base. Todas las funciones son llevadas a cabo con éxito y los test cases tengan status "ok" o consten como "problemas reportados" en la nota de release.

### 2. Auditoría Funcional de Configuración (FCA)

> Evaluación independiente de los productos de software, controlando que la **funcionalidad y performance reales** de cada IC sean consistentes con la **especificación de requerimientos**.

- **Valida** que el producto a construir sea consistente con los requerimientos identificados en la ERS.
- Se usa una **matriz de rastreabilidad** para encontrar dónde se implementa cada requerimiento.
- **Validación**: el problema es resuelto de manera apropiada de manera que el usuario obtenga el producto correcto.

![Auditoría Funcional de Configuración vs Física](imgs/p236_img1.png)

> La **FCA** valida que el producto construido cumple los **requerimientos** (usando la matriz de rastreabilidad). La **PCA** valida que el producto construido es consistente con la **documentación** (código vs. docs).

### 3. Auditorías de Proyecto

- **Valida el cumplimiento del proceso de desarrollo**. Verifica que el proyecto se ha ejecutado con el proceso que se dijo que se iba a ejecutar.
- ¿Dónde está definido qué proceso voy a usar? → En el **plan del proyecto**.
- Se llevan a cabo de acuerdo al **PACS** (Plan de Aseguramiento de Calidad de Software).
- El PACS debería indicar quién es el responsable de realizarlas.
- Las inspecciones de software y las revisiones de la documentación de diseño y prueba deberían incluirse en esta auditoría.
- El objetivo es **verificar objetivamente la consistencia del producto** a medida que evoluciona a lo largo del proceso de desarrollo.

#### Ejemplo: proyecto con metodología tradicional (waterfall o modelo en V)

Se auditan los **roles**:
- ¿Quién es el líder del proyecto?
- ¿El líder hace lo que tiene que hacer?
- ¿Cuáles son los roles definidos?

Se audita la **documentación**:
- Requerimientos → ERS.
- Diseño → SDD (Software Design Document).
- ¿Cada requisito de la ERS tiene **trazabilidad** hacia el diseño, código y pruebas?

---

## Roles de la Auditoría

### Gerente de SQA
- Prepara el plan de auditorías.
- Calcula el costo.
- Asigna recursos.
- Es responsable de **resolver las no-conformidades**.

### Auditor
- Acuerda la fecha de la auditoría.
- Comunica el **alcance**.
- Recolecta y analiza la **evidencia objetiva** relevante y suficiente para tomar conclusiones.
- Realiza la auditoría.
- Prepara el reporte.
- Realiza el **seguimiento** de los planes de acción acordados con el auditado.

### Auditado
- Suele ser el **líder del proyecto**.
- Acuerda la fecha.
- Participa en la auditoría.
- **Proporciona evidencia** al auditor.
- Contesta al reporte.
- Propone el **plan de acción** para las deficiencias citadas.
- Comunica el cumplimiento del plan de acción.

---

## Proceso de Auditoría

1. **Planificación y Preparación**: el auditado solicita la auditoría, se coordina fecha, participantes y se proporciona documentación preliminar.
2. **Ejecución**: el auditor hace preguntas, el auditado responde, el auditor solicita evidencia. Se completa un **checklist** en paralelo.
3. **Generación de Reporte**: se analizan resultados y se genera un **reporte preliminar** (después se entrega el final en una fecha determinada).
4. **Seguimiento**: se analizan las desviaciones y el auditor genera un **plan de acción** para corregirlas.

---

## Técnicas Utilizadas en Auditorías

### Checklists

> El contenido general de un checklist incluye:

- Fecha de auditoría.
- Lista de auditados.
- Nombre del auditor.
- Nombre del proyecto.
- Fase actual del proyecto (si aplica).
- Objetivo y alcance de la auditoría.
- Lista de preguntas.

### Muestreo

> Consiste en seleccionar una **muestra representativa** de los productos y/o procesos a auditar.

### Revisión de registros

Análisis de los registros documentales del proyecto.

### Herramientas automatizadas

Software que facilita la auditoría (análisis estático, métricas, etc.).

---

## Análisis y Reporte de Resultados

### Contenido del reporte

- Identificación de la auditoría.
- Fecha de la auditoría.
- Auditor.
- Auditados.
- Nombre del proyecto auditado.
- Fase actual del proyecto.
- Lista de resultados.
- Comentarios.
- **Solicitud de planes de acción**.

### Tipos de resultados

| Resultado | Significado | Acción |
|---|---|---|
| **Buenas prácticas** | Práctica/procedimiento/instrucción que se ha desarrollado **mucho mejor** de lo esperado. | Reservar para cuando el auditado: (1) estableció un sistema efectivo, (2) desarrolló alto grado de conocimiento y cooperación interna, (3) adoptó una práctica superior a cualquier otra. |
| **Desviaciones** | Requieren **plan de acción** por parte del auditado. | Cualquier disconformidad del producto respecto de sus requerimientos, falta de control para satisfacerlos, o desviación al proceso definido que cause incertidumbre sobre la calidad. |
| **Observaciones** | Condiciones que **deberían mejorarse** pero **no requieren plan de acción**. | Opinión sobre condición incumplida, práctica a mejorar, condición que puede devenir en desviación futura. |

### Ejemplos de preguntas para auditoría de planificación

![Ejemplos de preguntas - Planificación de Proyectos](imgs/p238_img1.png)

- ¿Existe un plan de proyecto?
- ¿Está actualizado?
- ¿Existe un responsable para cada actividad?
- ¿Se han asignado recursos para las actividades de soporte?
- ¿Están disponibles los planes para todos los involucrados?

El auditor debe asegurarse de que:
- Los planes estén basados en los requerimientos.
- Las actividades planificadas se hayan llevado a cabo.
- Todos los involucrados estén comprometidos con la última versión de los planes.
- Los cambios a los planes se hayan aprobado por todos los involucrados.
- La decisión de esos cambios se haya documentado oportunamente.
- Se hayan identificado y comunicado los **riesgos** del proyecto.

---

## Métricas de Auditoría

> Cada organización deberá establecer las métricas más apropiadas. Algunos ejemplos:

- **Esfuerzo por auditoría**.
- **Cantidad de desviaciones**.
- **Duración de auditoría**.
- **Cantidad de desviaciones clasificadas por área de proceso de CMMI**.

---

## Diferencia clave: Revisiones vs. Auditorías

| Aspecto | Revisión técnica (peer review) | Auditoría |
|---|---|---|
| Quién | Colegas del equipo | Personas **externas** al equipo |
| Objetividad | Alta | **Máxima** (la independencia es el valor central) |
| Frecuencia | Continua (diaria, por iteración) | Programada (periódica) |
| Proceso | Formal o informal | Siempre formal |
| Artefactos | Cualquier artefacto | Productos, procesos, documentación |
| Métricas | Recomendadas (en formales) | Siempre |
| Cultura | "No se juzga al autor" | Independiente y objetiva |

> En ágil se prefieren las **revisiones técnicas** para evitar traer auditores externos, que pueden chocar con la autoorganización del equipo.

---

## Chivo para el oral

1. **Concepto**: evaluaciones **independientes** (personas ajenas al equipo) de productos o procesos, con criterio objetivo.
2. **Tres tipos**:
   - **PCA** (física): compara producto con documentación.
   - **FCA** (funcional): compara producto con requerimientos (matriz de rastreabilidad).
   - **De proyecto**: verifica cumplimiento del proceso definido en el plan.
3. **Roles**: gerente de SQA (planifica), auditor (evalúa), auditado (generalmente el líder del proyecto, proporciona evidencia).
4. **Proceso**: Planificación → Ejecución → Reporte → Seguimiento.
5. **Resultados**: buenas prácticas (elogio), **desviaciones** (requieren plan de acción), observaciones (sugerencia, sin plan).
6. **Diferencia con peer review**: la auditoría es **externa e independiente**; la revisión es entre colegas. Ágil prefiere la segunda.
7. **Cerrá con la idea**: la auditoría es el instrumento de **máxima objetividad** porque la realiza alguien sin compromiso con el proyecto.

> **Si te preguntan "¿qué es una no-conformidad?"** → una **desviación** que resulta en disconformidad del producto respecto de sus requerimientos, o falta de control para satisfacerlos. Requiere plan de acción.
