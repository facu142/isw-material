# 03 — Actividades de SCM

> Págs. 159-163 del apunte. Cubre la identificación, el control de cambios, las auditorías, los informes de estado y la matriz de trazabilidad.

## 1. Identificación de Ítems de Configuración

> Esto implica una **identificación unívoca** para cada ítem. Implica:

- Definir **políticas, reglas de nombrado y versionado**.
- Definir la **estructura del repositorio**.
- Definir la **ubicación de los ítems** en la estructura.

> Los ICs se clasifican según su **ciclo de vida**: de producto (viven con el producto), de proyecto, de iteración.

*(Detalle en el archivo [02-items-de-configuracion.md](02-items-de-configuracion.md))*

---

## 2. Control de Cambios

> Una vez definida la **línea base**, no es posible cambiarla sin antes pasar por un **proceso formal de control de cambios**. El control se hace sobre los ICs que pertenecen a la línea base, ya que todos los trabajadores del software los tienen como referencia.

> Para esto se recurre al **comité de control de cambios**.

### Proceso formal (5 pasos)

1. **Se recibe una propuesta de cambio** sobre una línea base determinada (no sobre un ítem específico).
2. El **comité de control de cambios** realiza un **análisis de impacto** del cambio:
   - Esfuerzo técnico.
   - Impacto en la gestión de recursos.
   - Efectos secundarios.
   - Impacto global sobre funcionalidad y arquitectura.
3. Si se autoriza la propuesta, se genera una **orden de cambio** que define:
   - Lo que se va a realizar.
   - Las restricciones a tener en cuenta.
   - Los criterios para revisar y auditar.
4. Luego de realizado el cambio, el **comité vuelve a intervenir** para **aprobar la modificación de la línea base** y marcarla como línea base nuevamente (revisión de partes).
5. Finalmente se **notifica a los interesados** los cambios realizados sobre la línea base.

### Comité de control de cambios

Formado por **representantes de todas las áreas** involucradas en el desarrollo:

- Análisis.
- Diseño.
- Implementación.
- Testing.
- Otros interesados.

---

## 3. Auditorías de Configuración de Software

> Las **auditorías** son **evaluaciones independientes** (realizadas por un grupo de personas **ajenas al equipo**) de los productos o procesos de software, para asegurar el cumplimiento con estándares, lineamientos, especificaciones y procedimientos, basada en un **criterio objetivo**.

> **Es muy importante notar que la auditoría se realiza en torno a una línea base**.

Son un instrumento para el **Aseguramiento de Calidad en el Software**.

### Tipos de auditoría

#### Auditoría Física de Configuración (PCA)

> En la auditoría física se verifica la **integridad del repositorio**: que los ICs se encuentren ubicados allí en el **lugar correcto**.

- **Verificación**: asegura que un producto cumple con los objetivos preestablecidos, definidos en la documentación de líneas base.
  - Todas las funciones son llevadas a cabo con éxito.
  - Los test cases tengan status "ok" o consten como "problemas reportados" en la nota de release.

#### Auditoría Funcional de Configuración (FCA)

> Se valida que el **producto construido es el correcto**. Se contrastan los ICs contra los **requerimientos** para ver si estamos construyendo un producto correcto.

- Valida que el producto sea consistente con los requerimientos identificados en la **ERS**.
- Se usa una **matriz de rastreabilidad** para encontrar dónde se implementa cada requerimiento.
- **Validación**: el problema es resuelto de manera apropiada de manera que el usuario obtenga el producto correcto.

### Comparación PCA vs. FCA

![Comparación PCA y FCA](imgs/p161_img1.png)

| Tipo | Compara | Objetivo |
|---|---|---|
| **PCA** (Auditoría Física) | Producto construido ↔ Documentación. | **Consistencia con la documentación**. |
| **FCA** (Auditoría Funcional) | Producto construido ↔ Requerimientos. | **Consistencia con los requerimientos** (usando la matriz de rastreabilidad). |

---

## Matriz de Trazabilidad de Requerimientos

> Herramienta para **rastrear** los requerimientos a lo largo de todo el ciclo de vida del software.

### Ejemplo de matriz

| ID | Requisito | Casos de uso | Casos de prueba | Ítems de configuración | Estado |
|---|---|---|---|---|---|
| REQ-001 | El usuario debe poder iniciar sesión | CU-01 | TC-001, TC-002 | login.js, authController.java, config.yaml | **Implementado** |
| REQ-002 | El sistema debe bloquear al usuario tras 3 intentos fallidos | CU-02 | TC-003 | securityService.java, login.js | **En desarrollo** |

> Con esta matriz, ante un cambio en un requerimiento, podemos **ubicar inmediatamente** todos los artefactos afectados.

---

## 4. Informes de Estado

> La principal razón para usar informes de estado es **aportar visibilidad** acerca de la gestión de configuración, para **tomar decisiones**.

### Ejemplos de informes

- **Inventario**: lista todos los ICs con su estado en el repositorio en un momento de tiempo.
- **Solicitudes de cambio atendidas**: cantidad de solicitudes de cambio gestionadas en un periodo.
- **Contenido de una línea base**: lista los ICs que componen una línea base específica.

---

## Resumen de actividades

| Actividad | Objetivo | Salida |
|---|---|---|
| **Identificación** | Identificar unívocamente los ICs. | Repositorio estructurado con nombres y versiones. |
| **Control de cambios** | Gestionar formalmente los cambios a líneas base. | Órdenes de cambio aprobadas y nuevas líneas base. |
| **Auditorías** | Verificar cumplimiento con estándares. | Reportes de auditoría (PCA, FCA). |
| **Informes** | Visibilidad para tomar decisiones. | Informes de estado. |

---

## Chivo para el oral

1. **4 actividades**: identificación, control de cambios, auditorías, informes de estado.
2. **Control de cambios**: una vez definida la **línea base**, todo cambio pasa por un **comité**. Proceso de 5 pasos: propuesta → análisis de impacto → orden de cambio → revisión → notificación.
3. **Comité**: representantes de todas las áreas (análisis, diseño, implementación, testing, otros).
4. **Auditorías**: independientes, alrededor de una **línea base**.
   - **PCA** (física): producto vs. documentación.
   - **FCA** (funcional): producto vs. requerimientos (con matriz de rastreabilidad).
5. **Matriz de trazabilidad**: tabla que vincula cada requerimiento con sus casos de uso, tests, ICs y estado.
6. **Informes**: inventario, solicitudes de cambio, contenido de líneas base.
7. **Cerrá con la idea**: SCM no es solo control de versiones. Es el **conjunto de actividades** que asegura que los cambios sean formales, rastreables y auditables.

> **Si te preguntan "¿cuál es la diferencia entre PCA y FCA?"** → **PCA** compara el producto con la **documentación** (¿está donde dice la doc?); **FCA** compara el producto con los **requerimientos** (¿hace lo que el cliente necesita?). Las dos juntas dan la auditoría completa.
