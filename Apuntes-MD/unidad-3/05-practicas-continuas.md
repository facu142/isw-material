# 05 — Prácticas Continuas (CI / CD)

> Págs. 164-166 del apunte + transcripción de clase grabada. Cubre la Integración Continua, la Entrega Continua, el Despliegue Continuo y las estrategias de despliegue (Blue-Green, Canary).

## Introducción

> Las **prácticas continuas** vienen a ser como una **evolución de SCM**, que ya apuntan a una **automatización completa**.

> Las 3 prácticas continuas son: **Integración Continua**, **Entrega Continua** y **Despliegue Continuo**.

---

## 1. Integración Continua (CI)

> Práctica de desarrollo que promueve que los desarrolladores adopten la costumbre de **integrar su código a un repositorio compartido varias veces al día**.

- Cada integración es verificada por **pruebas automatizadas**.
- Permite al equipo **detectar problemas de manera temprana** (al integrar frecuentemente, es más fácil detectar y corregir errores).

> **Lo que busca CI** (según la clase): **integrar continuamente** los diferentes componentes de un producto que pueden estar siendo trabajados por **diferentes miembros del equipo** o hasta por **diferentes equipos** que participan del mismo producto.

### El servidor de integración continua

> CI **requiere de un servidor de integración continua**, que es el lugar donde cada una de las **ramas de desarrollo** del repositorio y cada uno de los componentes finalmente hacen la operación de **merge** y se **automatizan las pruebas unitarias** para garantizar que, una vez integrado, **no se rompe nada** a nivel unitario.

### Flujo

1. Cada desarrollador realiza **pruebas unitarias** en su entorno local (idealmente automatizadas, idealmente con TDD).
2. Cuando sabe que su código funciona, lo sube al **repositorio de integración** (merge de su rama).
3. El **servidor de CI** corre las **pruebas unitarias automatizadas** sobre el producto integrado.
4. Si todo pasa, se genera el **empaquetado (release) de forma automatizada**.
5. Sobre ese release se ejecutan las **pruebas de aceptación de forma manual**.

> **TDD** + **CI** = combinación natural: escribís el test, lo hacés pasar, subís el código, los tests de CI verifican la integración.

> **Punto clave de la clase**: en CI el pipeline **termina en el empaquetado**. El objetivo es producir un release sano; el despliegue a producción **no forma parte** de CI.

---

## 2. Entrega Continua (Continuous Delivery)

> Disciplina en la que el software se construye de tal manera que **puede ser liberado en producción en cualquier momento**.

- Hay una serie de pruebas que verifican que el código subido se integra correctamente al sistema.
- **No implica que se libere** cada vez que hay un cambio.
- Solo ocurre si el **responsable de negocio** (PO) **decide pasar a producción**: hay un **componente humano** en la decisión.
- Pero **en cualquier caso, la versión está lista** de inmediato.

> **Diferencia clave con CI**: en CI solo se verifica que el código se integra. En entrega continua, además se garantiza que la versión está **lista para producción** (aunque no se despliegue).

### Detalle de la clase: dónde termina el pipeline

> En entrega continua, el pipeline **no produce el despliegue a producción**: su objetivo es **terminar en el empaquetado**. Sobre ese empaquetado se ejecutan las **pruebas de aceptación de forma manual** y, finalmente, con un **proceso independiente** se pone ese release en producción.

- El pipeline puede tener un **"botoncito"** (un disparador manual) que permite **desatar el despliegue**, pero ese paso es **manual y sujeto a que las pruebas de aceptación se hayan ejecutado manualmente**.
- **Ojo con el matiz**: en entrega continua el **proceso de deploy puede estar automatizado** (apretar un botón), pero **se dispara de forma manual**. No es lo mismo que el despliegue continuo, donde el deploy está **dentro del pipeline** y se dispara solo.
- En la práctica, el deploy manual puede ser desde apretar un botón hasta **llevar el paquete a un servidor de aplicaciones / contenedor** (Tomcat, réplicas, etc.) y actualizarlo a mano.

---

## 3. Despliegue Continuo (Continuous Deployment)

> Consiste en **poner en producción** el producto directamente. A diferencia de la entrega continua, **no existe la intervención humana** para desplegar.

- Se utilizan **pipelines** que contienen una serie de **pasos en un orden determinado** para que la instalación sea satisfactoria.
- Si los tests pasan, el código va a producción automáticamente.

### La condición para llegar al despliegue continuo (de la clase)

> Solo los **equipos maduros** llegan al despliegue continuo: son los que lograron **automatizar las pruebas de aceptación** (además de las unitarias y las de integración).

- Cuando una feature está terminada → se desata la integración continua → culmina en **pruebas de aceptación automatizadas** → si todo sale bien y no se rompe nada → **automáticamente se desata el despliegue a producción**.
- Es **lo más rápido posible** para llevar una feature al cliente y ponerla a prueba en un entorno productivo.

### Pipeline

```
[Construcción] → [Tests unitarios] → [Empaquetado] → [Tests de aceptación] → [Producción]
     auto              auto               auto         auto (solo en CD)      auto
```

---

## Comparación visual: CI / Entrega Continua / Despliegue Continuo

![Comparación CI, Entrega Continua, Despliegue Continuo](imgs/p164_img1.png)

| Práctica | Construcción | Tests unitarios | Despliegue (entorno) | Tests de aceptación | **Producción** |
|---|---|---|---|---|---|
| **CI** | Automático | Automático | Automático | Automático | **No incluido** |
| **Entrega continua** | Automático | Automático | Automático | Automático | **Manual** (decisión de negocio) |
| **Despliegue continuo** | Automático | Automático | Automático | Automático | **Automático** |

> La diferencia es **qué pasa con el último paso**: en CI no se llega a producción, en entrega continua se llega pero con decisión humana, en despliegue continuo se llega sin intervención.

### Regla mnemotécnica

> **CI** = "cada commit se integra".
> **Entrega Continua** = "la versión siempre está lista".
> **Despliegue Continuo** = "la versión va sola a producción".

---

## El componente más importante: automatizar las pruebas

> **Pregunta de la clase**: ¿cuál es el componente más importante para poder realizar cualquiera de estas prácticas continuas? → **La automatización de las pruebas** (no solo las de aceptación: las pruebas **en general**).

Las pruebas automatizadas le dan al producto el **aseguramiento de calidad** necesario en dos niveles:

- **Unitario**: que cada uno de los componentes que se integran produce un **release sano**, que cumple con las especificaciones internas del producto.
- **Aceptación**: que ese producto **corresponde y satisface los requerimientos de los clientes**.

### Las 2 trampas (muy preguntables en el oral)

1. **Automatizar no alcanza si el producto es malo**: *"yo tranquilamente puedo crear un script que haga el deploy a producción y puedo hacer deploy a producción de **basura que no funciona**"*. Automatizar el deploy sin pruebas no sirve de nada.

2. **Automatizar no alcanza si las pruebas son malas**: *"tranquilamente podríamos automatizar pruebas y que el conjunto de nuestros tests sea **cero**... un pipeline que corre derecho, y si tengo cero pruebas, no me sirve de nada"*. No es solo la automatización: necesitás un **buen conjunto de pruebas** que te asegure que si el pipeline corre, produce un producto sano que va a funcionar correctamente en producción.

> **Resumen**: la palabra clave es **automatizar las pruebas**, pero con dos condiciones: que las pruebas **existan** y que estén **bien hechas**.

---

## El rol DevOps

> A nivel conceptual las prácticas continuas **no son nuevas**, pero **no todas las empresas las implementan**.

- El rol que hace la **automatización de los procesos de deploy** es de los **más difíciles de encontrar** en la industria.
- Está más ligado a la parte de **infraestructura**: construir los **pipelines** para la integración continua, armar las integraciones para el deploy.
- Son perfiles **poco distribuidos** pero que **ayudan muchísimo** a la calidad y a poder **entregar rápidamente un producto en el que tenés confianza**.

---

## Estrategias de despliegue continuo

### 1. Blue-Green Deployment

> Técnica donde mantenes **dos entornos de producción idénticos**:

- **Blue**: la versión actual en producción.
- **Green**: la nueva versión que quieres desplegar.

**Funcionamiento**:
- Desplegás la nueva versión en Green.
- Hacés todas las pruebas que necesites en Green sin afectar a los usuarios.
- Cuando estás listo, **redireccionás el tráfico** del entorno Blue al Green por medio de un **balanceador de cargas**.
- Si hay problemas, volvés a apuntar el balanceador a Blue (**rollback instantáneo**).

> **Ventaja**: rollback trivial, sin downtime.

### 2. Canary Deployment

> La nueva versión del producto se va **liberando de manera gradual** a un subconjunto de usuarios, como un **lanzamiento por etapas**.

**Funcionamiento**:
1. La nueva versión (v2) es desplegada a solo el **5%** de los usuarios.
2. Observamos cómo se comporta: errores, rendimiento, feedback.
3. Si va bien, incrementamos el porcentaje: **25% → 50% → 100%**.
4. Si hay problemas, podemos **detener o revertir** el despliegue fácilmente.

> **Ventaja**: permite ir obteniendo **feedback de manera gradual** y **monitorear** cómo funciona. Si hay problemas, se hace rollback antes de que afecte a todos los usuarios.

### Comparación

| Estrategia | Cambio | Rollback | Audiencia |
|---|---|---|---|
| **Blue-Green** | Instantáneo (cambio de balanceador). | Instantáneo. | 100% de los usuarios. |
| **Canary** | Gradual (% incremental). | Rápido (parar despliegue). | Subconjunto creciente. |

---

## Relación con SCM y agile

Las prácticas continuas son la **materialización** del agilismo en la ingeniería de software:

- **CI** = **integración frecuente** + tests automatizados → elimina el "integration hell".
- **Entrega Continua** = la versión **siempre está lista** → reduce la latencia del feedback.
- **Despliegue Continuo** = automatización completa → minimiza el riesgo y el tiempo al mercado.

> Conectar con la **Pirámide de Testing** de la unidad 4: las prácticas continuas permiten correr muchos tests en poco tiempo porque están automatizados.

---

## Chivo para el oral

1. **3 prácticas continuas**: CI, Entrega Continua, Despliegue Continuo. Son una **evolución de SCM** hacia la automatización completa.
2. **CI (Integración Continua)**: integrar al repositorio compartido **varias veces al día**. Requiere un **servidor de CI** donde se mergean las ramas y corren los tests unitarios automatizados. **El pipeline termina en el empaquetado**; no incluye producción.
3. **Entrega Continua**: la versión **siempre está lista** para producción, pero el paso a producción es **decisión humana** (PO). El deploy puede estar automatizado pero **se dispara manualmente** (botón). Las pruebas de aceptación son **manuales**.
4. **Despliegue Continuo**: la versión va a producción **automáticamente**. Solo para **equipos maduros** que lograron **automatizar las pruebas de aceptación**.
5. **Componente más importante**: **automatizar las pruebas** (en general). Trampas: podés automatizar el deploy de **basura que no funciona**, o tener un pipeline con **cero tests** que corre derecho. Necesitás un **buen conjunto de pruebas**.
6. **Rol DevOps**: automatiza los procesos de deploy, construye pipelines. Difícil de encontrar, ligado a infraestructura, muy valioso.
7. **Estrategias**:
   - **Blue-Green**: dos entornos idénticos, redireccionás el tráfico. **Rollback instantáneo**.
   - **Canary**: despliegue gradual a un % de usuarios. **Feedback incremental**.
8. **Cerrá con la idea**: las prácticas continuas son el **eslabón final** entre el agilismo y la operación real. Permiten entregar valor al usuario de forma **frecuente, segura y automatizada**.

---

## Respuestas modelo para preguntas frecuentes

### ¿Cuál es la diferencia entre CI y Entrega Continua?
> En **CI** solo se valida que el código se integra con el resto: el servidor de CI mergea las ramas, corre los tests unitarios automatizados y genera el empaquetado. El pipeline **termina ahí**. En **Entrega Continua**, además, se garantiza que la versión está **lista para ir a producción** en cualquier momento, aunque el despliegue sigue siendo una **decisión humana** (las pruebas de aceptación se hacen manualmente y alguien dispara el deploy).

### ¿Cuál es la diferencia entre Entrega Continua y Despliegue Continuo?
> En **Entrega Continua** el despliegue a producción es **manual**: puede ser apretar un botón, pero un humano decide cuándo, después de correr las pruebas de aceptación manualmente. En **Despliegue Continuo** el despliegue es **automático**: solo lo logran **equipos maduros** que automatizaron las pruebas de aceptación; si todo el pipeline pasa, la feature va sola a producción sin intervención humana.

### ¿Cuál es el componente más importante de las prácticas continuas?
> **La automatización de las pruebas** (en general, no solo las de aceptación). Pero con dos trampas: podés automatizar el deploy de **basura que no funciona**, y podés tener un pipeline con **cero tests** que corre perfecto pero no asegura nada. La clave es tener un **buen conjunto de pruebas** automatizadas que garanticen que si el pipeline pasa, el producto en producción funciona correctamente y satisface los requerimientos del cliente.

### ¿Qué es un pipeline?
> Es un **conjunto ordenado de pasos** que se ejecutan automáticamente: construcción → pruebas unitarias → empaquetado → pruebas de aceptación → (eventualmente) despliegue. En CI termina en el empaquetado; en entrega continua el deploy se dispara manual; en despliegue continuo el deploy está dentro del pipeline.

### ¿Qué hace el rol DevOps?
> Automatiza los **procesos de deploy**: construye los **pipelines** de integración continua y arma las integraciones para el despliegue. Está ligado a **infraestructura**, es un perfil **difícil de encontrar** en la industria, y aporta muchísimo a la calidad y a la velocidad de entrega.
