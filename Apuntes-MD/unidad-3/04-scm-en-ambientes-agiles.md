# 04 — SCM en Ambientes Ágiles

> Págs. 163-164 del apunte. Cubre las diferencias entre SCM tradicional y SCM ágil, y la trazabilidad automática.

## El cambio de enfoque

> En las metodologías ágiles, la gestión de configuración **cambia el enfoque**: ya que la misma es de **utilidad** para los miembros del equipo de desarrollo, y no al revés.

> En ágil, **la SCM está al servicio del equipo**, no el equipo al servicio de la SCM.

---

## Características de SCM ágil

### 1. No hay auditorías formales

> Los equipos ágiles son **autoorganizados**, por lo que las **Auditorías de configuración no son una actividad propia** de la gestión de configuración en los ambientes ágiles.

> En su lugar, se usan prácticas como **peer reviews** y **revisiones técnicas** que se cubren en la unidad 4.

### 2. No hay comité de control de cambios

> El **comité de control de cambios desaparece**, porque ahora no tenemos una estructura rígida como lo establecen los procesos definidos. Los equipos **se autorregulan**.

- Los cambios se gestionan de forma más liviana, dentro del flujo del sprint.
- Se confía en la **comunicación cara a cara** del equipo.

### 3. SCM responde a los cambios

> Dada la naturaleza de los requerimientos ágiles, la SCM **responde a los cambios** en lugar de evitarlos.

- Cambio es **bienvenido**, no combatido.

### 4. Automatización y transparencia

- **Esforzarse por ser transparente y sin fricción**, automatizando tanto como sea posible.
- **Coordinación y automatización frecuente y rápida**.
- **Eliminar el desperdicio**: no agregar nada más que valor.
- **Documentación Lean y Trazabilidad**.
- **Feedback continuo y visible** sobre calidad, estabilidad e integridad.

---

## Trazabilidad: tradicional vs. ágil

| Enfoque | Cómo se hace |
|---|---|
| **Tradicional** (Documentación manual) | Se generan informes formales y rastreo detallado a través de herramientas especializadas. |
| **Ágil** (Trazabilidad automática) | Se gestiona mediante **herramientas integradas** como **Git, Jira, Azure DevOps**, etc. |

> En ágil, la trazabilidad se obtiene **como subproducto** del uso de las herramientas, no como un proceso manual separado.

### Ejemplo: trazabilidad automática

- **Git**: cada commit tiene autor, fecha, mensaje, branch, archivos modificados. Esto da **trazabilidad de código**.
- **Jira**: cada issue tiene estado, asignado, linked branches, linked commits. Esto da **trazabilidad de tareas**.
- **Git + Jira integrados**: cada branch se vincula con un ticket, y cada commit referencia el ticket. Esto da **trazabilidad end-to-end** automática.

> En Scrum, además, la **DoD** y los **eventos** (Sprint Review) hacen las veces de "auditoría" sin necesidad de un comité formal.

---

## Comparación Tradicional vs. Ágil

| Aspecto | Tradicional | Ágil |
|---|---|---|
| **Auditorías** | Sí, formales e independientes. | No, reemplazadas por peer reviews. |
| **Comité de cambios** | Sí, formal y con representantes. | No, equipo se autorregula. |
| **Trazabilidad** | Manual, informes formales. | **Automática**, vía herramientas. |
| **Respuesta al cambio** | Evitar cambios. | **Aceptar y responder** al cambio. |
| **Documentación** | Exhaustiva. | **Lean**, lo justo y necesario. |
| **Integración** | Manual, al final. | **Continua** (CI/CD). |

---

## Relación con el agilismo

- **Transparencia**: la trazabilidad automática hace visible el estado del proyecto.
- **Inspección**: las prácticas de CI permiten inspeccionar el código en cada cambio.
- **Adaptación**: si un cambio rompe algo, se detecta y corrige rápido.
- **Iteración**: cada sprint es una mini-línea base que se revisa y se libera.

---

## Chivo para el oral

1. **Cambio de enfoque**: en ágil, la SCM **sirve al equipo**, no al revés. Se eliminan las rigideces del tradicional.
2. **Desaparecen**:
   - Las **auditorías formales** (reemplazadas por peer reviews).
   - El **comité de control de cambios** (autorregulación del equipo).
3. **Aparecen / se mantienen**:
   - **Trazabilidad automática** (Git, Jira, Azure DevOps).
   - **Respuesta al cambio** (en vez de evitarlo).
   - **Automatización** y feedback continuo.
   - **Documentación Lean**.
4. **Cerrá con la idea**: en ágil, SCM es **automatizada, transparente, sin fricción** y enfocada en **responder al cambio**, no en evitarlo. Las herramientas hacen el trabajo pesado.

> **Si te preguntan "¿cómo se hace la trazabilidad en ágil sin documentación manual?"** → se obtiene **automáticamente** de las herramientas: Git sabe qué commit modificó qué archivo, Jira sabe qué ticket está en qué estado y quién lo trabaja, y la integración entre ambos da trazabilidad **end-to-end sin escribir un solo informe manual**.
