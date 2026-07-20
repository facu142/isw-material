# 03 — Disciplinas de la Ingeniería de Software

> Págs. 4-5 del apunte + presentación 00. Cubre las 3 macro-disciplinas que componen la IS: técnicas, de gestión y de soporte.

## Las 3 macro-disciplinas

La Ingeniería de Software se compone de **tres grandes grupos de disciplinas** que, trabajando en conjunto, permiten obtener un producto de software de calidad.

---

### 1. Disciplinas Técnicas (orientadas al producto)

> Actividades que **aportan al desarrollo del software como producto**. Producen los artefactos centrales: requerimientos, código, pruebas, documentación, despliegue.

| Disciplina | Qué hace |
|---|---|
| **Toma de requerimientos** | Recopilar las necesidades del cliente y los usuarios. |
| **Análisis de requerimientos** | Refinar, negociar y documentar los requerimientos. |
| **Diseño de software** | Definir la arquitectura, componentes, interfaces y datos. |
| **Implementación** | Codificar el software. |
| **Prueba de software** | Verificar que cumple con los requerimientos. |
| **Despliegue** | Poner el software en producción. |
| **Documentación** | Generar manuales, guías, ERS, SDD, etc. |
| **Capacitación a usuarios** | Entrenar a los usuarios en el uso del producto. |

> **Sinónimo común en la cátedra**: "las disciplinas técnicas son las que construyen el producto".

---

### 2. Disciplinas de Gestión

> Actividades de **planificación, monitoreo y control** del proyecto de desarrollo. Gestionan los recursos, el tiempo, el alcance y los riesgos.

Ejemplos:

- **Planificación de proyecto** (alcance, estimación, riesgos, recursos, calendarización).
- **Monitoreo y control de proyectos** (métricas, reuniones de seguimiento, informes).

> *Ejemplo*: dentro del marco Lean, tenemos a **Kanban**, que utiliza tableros para monitorear el proyecto.

---

### 3. Disciplinas de Soporte (transversales)

> Son **transversales a los procesos** de software. Permiten **verificar la integridad y la calidad** del producto. No construyen producto, pero garantizan que lo construido sea confiable y mantenible.

| Disciplina | Qué hace |
|---|---|
| **Gestión de Configuración de Software (SCM)** | Versionado, líneas base, control de cambios. |
| **Toma de métricas** | Medir proceso, proyecto y producto. |
| **Aseguramiento de la calidad (QA)** | Verificar cumplimiento de estándares y procesos. |
| **Calidad en el producto** | Atributos del producto (funcionalidad, performance, etc.). |
| **Calidad en el proceso** | Madurez y capacidad del proceso. |
| **Pruebas de software (Testing)** | Verificación y validación. |

> **Las disciplinas de soporte son transversales**: aplican a todo el ciclo de vida y a todas las disciplinas técnicas.

---

## Relación entre los 3 grupos

```
Disciplinas Técnicas ──→ construyen el PRODUCTO
Disciplinas de Gestión ──→ controlan el PROYECTO
Disciplinas de Soporte  ──→ aseguran la CALIDAD de ambos
```

> Las tres dimensiones son **complementarias** y necesarias. Un equipo sin gestión se desorganiza; un equipo sin soporte entrega producto de baja calidad; un equipo solo de soporte no entrega nada.

---

## Chivo para el oral

1. **Las 3 macro-disciplinas**: técnicas, de gestión, de soporte. Repetí esta clasificación en voz alta como mantra.
2. **Técnicas**: son las que producen el producto. Mencioná 2-3 (requerimientos, diseño, prueba, despliegue).
3. **Gestión**: planificación + monitoreo/control. Ejemplo: Kanban.
4. **Soporte**: SCM, métricas, QA, testing. **Transversales**, aplican a todo.
5. **Cerrá con la idea**: sin las 3 no hay producto de calidad. Una empresa que solo hace testing sin gestión va a fallar; una que solo hace gestión sin soporte también.

> **Si te preguntan "¿cuáles son las disciplinas técnicas?"** → las que producen el producto: requerimientos, análisis, diseño, implementación, prueba, despliegue, documentación, capacitación.
> **Si te preguntan "¿cuáles son las de soporte?"** → SCM, métricas, aseguramiento de calidad, calidad (de proceso y producto), testing. **La clave es que son transversales**.
