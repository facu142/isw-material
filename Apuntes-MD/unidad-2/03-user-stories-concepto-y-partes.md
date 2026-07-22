# 03 — User Stories: Concepto y Partes

> Págs. 49-54 del apunte. Cubre el concepto de user story, las 3 C (Tarjeta, Conversación, Confirmación), las porciones verticales y los proxies.

## Concepto

> Una **historia de usuario** (*user story*) describe una **funcionalidad que será valiosa para un usuario o comprador** de un sistema o software. *(Addison-Wesley)*

- Son básicamente técnicas que utilizamos para trabajar con los **requerimientos ágiles**.
- Se las llama *stories* porque se supone que **contás una historia**: lo que se escribe en la tarjeta no es lo importante, lo que **hablás** sí.
- Son un **token para una conversación**: como *"como usuario quiero iniciar sesión en Google"*, es un puntapié para que al leerla se desate una conversación.
- **Reducen** un montón la documentación y la burocracia.
- Son escritas por el **Product Owner**.

### Características multipropósito

Una user story es, al mismo tiempo:

- Una **necesidad del usuario**.
- Una **descripción del producto**.
- Un **ítem de planificación**.
- Un **token para una conversación**.
- Un **mecanismo para diferir** una conversación.

---

## Las 3 C: Tarjeta, Conversación, Confirmación

### 1. Tarjeta

> La parte visible, donde escribimos la historia. Está compuesta por:

- **Frase verbal**: una frase resumen a modo de título.
- **Frase principal**: nombre de rol - actividad - valor de negocio.
- **Criterios de aceptación**: los límites para la user story; lo que el PO quiere para que sea aceptada.

> *Ejemplo*: "Registro de usuario".

Criterios de aceptación típicos:
- El sistema debe permitir registrarse con un correo único.
- Se debe mostrar un mensaje de confirmación al registrarse.
- El correo debe ser validado para asegurar que es válido.

### Forma de expresar una user story

```
Como <nombre del rol>, yo puedo <actividad> de forma tal que <valor de negocio que recibo>
```

> *Ejemplo*: "Como conductor quiero buscar un destino a partir de una calle y altura para poder llegar al lugar deseado sin perderme".

### 2. Conversación

> La parte **más importante** de las user stories. **No queda guardada en ningún lado**, porque según los principios ágiles el mejor medio de comunicación es **cara a cara**.

- La conversación **reemplaza** a la documentación exhaustiva.

### 3. Confirmación

> Comprende la definición de las **pruebas de aceptación**, necesarias para que el PO me acepte la user story como válida.

- Las pruebas de aceptación son las que se entiende que va a hacer el PO y los usuarios cuando se entregue la funcionalidad lista.
- Se especifican: si fallan o si pasan.

---

## Pruebas de aceptación

> Son **declaraciones de intención de que hay que probar**. Estas pruebas nacen de las **confirmaciones**; de las conversaciones que se dan.

---

## User Stories: Porciones Verticales

> Lo que tienen las user stories es que hacen un **corte vertical a la arquitectura**: tocan temas que van desde la **interfaz de usuario** hasta la **base de datos**, pasando por la **capa lógica de negocios**.

Si las user stories cortaran a la arquitectura de manera **horizontal**, serían incapaces de dar valor al cliente.

### Ejemplo (e-commerce)

- **Porción Horizontal**: tarea que solo se enfoca en una capa del sistema, como *"crear la tabla de productos en la base de datos"* o *"diseñar la interfaz para agregar productos al carrito"*. **Importantes, pero no aportan valor directo al usuario final** por sí solas.
- **Porción Vertical**: *"como usuario, quiero agregar un producto al carrito para comprarlo más tarde"*. Implica trabajo en la **base de datos** (almacenar el carrito), en la **lógica de negocio** (manejar el proceso) y en la **interfaz** (que el usuario pueda realizar la acción). **Funcionalidad completa** que proporciona valor al usuario.

---

## Usuarios representantes (Proxies)

> Cuando desarrollamos software, no siempre podemos hablar directamente con los usuarios finales (si son miles, o si son clientes externos). Por eso, en la planificación, ciertas personas actúan como **"representantes" (proxies)** de esos usuarios. Su rol es **transmitir las necesidades, expectativas y contextos reales** de quienes usarán el sistema.

### Proxies típicos

- Gerentes de usuario.
- Gerentes de desarrollo.
- Alguien del grupo de marketing.
- Vendedores.
- Expertos del dominio.
- Clientes.
- Capacitadores y personal de soporte.

> **El product owner hace referencia a roles de negocio, no a roles técnicos**. O sea, estaría mal poner: analista en diseño, programador C++, dev ops.

---

## Criterios de aceptación (revisited)

Información concreta que sirve para saber si lo que implementamos es correcto o no.

- **Definen límites** para una user story.
- Ayudan a que el equipo tenga una **visión compartida** de la US.
- Ayudan a developers y testers a **derivar las pruebas**.
- Ayudan a los developers a saber **cuándo parar** de agregar funcionalidad.

### ¿Cómo son los buenos criterios de aceptación?

- Definen una **intención**, no una solución.
- Son **independientes de la implementación**.
- Son relativamente de **alto nivel**, no es necesario escribir cada detalle.

---

## Criterios de Aceptación vs. Pruebas de Aceptación (no son lo mismo)

> Es una confusión muy común: **no son lo mismo**, aunque están relacionados. Uno **define qué** hay que validar; el otro **define cómo** se valida.

| Concepto | Qué es | Quién lo define | Cuándo se hace | Naturaleza |
|---|---|---|---|---|
| **Criterio de Aceptación (CA)** | **Condición** que debe cumplir la historia para ser aceptada. | El **PO** lo negocia con el equipo. | **Antes** de desarrollar. | **Declarativo** (qué se valida). |
| **Prueba de Aceptación (PA)** | **Test que verifica** que un CA se cumple. | El **equipo** la diseña e implementa. | **Durante y después** del desarrollo. | **Ejecutable** (cómo se valida). |

> **Relación**: la PA es la **materialización** del CA. Cada PA se corresponde con uno o más CA. Si el CA falla, la PA falla. **Las PA son la Confirmación de las 3 C**.

### Ejemplo propio (login)

> **User story**: "Como usuario quiero iniciar sesión con email y contraseña para acceder a mi cuenta".

> **Criterios de aceptación** (qué):
> - CA1: El usuario puede iniciar sesión con email y contraseña correctos.
> - CA2: El sistema rechaza contraseñas incorrectas con un mensaje de error claro.
> - CA3: Tras 3 intentos fallidos, la cuenta se bloquea por 15 minutos.

> **Pruebas de aceptación** (cómo):
> - PA1: Ingresar email válido + contraseña válida → redirige al home. (Verifica CA1)
> - PA2: Ingresar email válido + contraseña inválida → muestra error "contraseña incorrecta". (Verifica CA2)
> - PA3: Ingresar 3 veces contraseña inválida → cuenta bloqueada por 15 min. (Verifica CA3)

> **Cómo se ve la diferencia**: el **CA1** dice *qué* debe pasar (login exitoso con credenciales correctas). La **PA1** dice *cómo* verificarlo (ingresar credenciales y ver si redirige). **Múltiples PA pueden verificar un mismo CA** (ej. login con email, con username, con Google, etc. verifican todos el CA1).

### Analogía (medicina)

> El **CA** es *"la presión arterial debe estar por debajo de 120/80"*. La **PA** es el procedimiento real: *"tomar la presión con el tensiómetro 3 veces y verificar que el promedio da menos de 120/80"*. **El CA dice qué; la PA dice cómo**.

### Resumen en una frase

> **Criterio de Aceptación = QUÉ validar. Prueba de Aceptación = CÓMO validar.**

### Errores comunes

- **Confundirlos**: pensar que un CA es lo mismo que una PA, o que las PA "son" los CA. **No**: un CA es una **declaración**; una PA es un **test ejecutable**.
- **CA como test**: escribir el CA como si fuera un test (*"hacer clic en el botón X y ver Y"*). El CA debe definir la **condición**, no el **procedimiento**.
- **PA como CA**: definir la PA sin un CA detrás (*"probar 100 veces"*). Toda PA debe estar **trazada a un CA**.

---

## Chivo para el oral

1. **Concepto**: una historia = una funcionalidad valiosa para un usuario. **Token para una conversación**.
2. **Forma**: "Como `<rol>`, yo puedo `<actividad>` de forma tal que `<valor de negocio>`".
3. **Las 3 C**:
   - **Tarjeta**: lo que se escribe, con **criterios de aceptación** (qué validar).
   - **Conversación**: la parte más importante. Cara a cara, no se documenta.
   - **Confirmación**: las **pruebas de aceptación** (cómo validar).
4. **Porciones Verticales**: las user stories cortan la arquitectura en vertical (de UI a BD). Si fueran horizontales, no darían valor.
5. **Proxies**: cuando no se puede hablar con el usuario real, hay representantes. El PO es un proxy de negocio (no técnico).
6. **CA vs PA**: el **criterio de aceptación** define **qué** validar (condición). La **prueba de aceptación** define **cómo** validar (test ejecutable). **Múltiples PA pueden verificar un mismo CA**. Analogía médica: el CA es "presión < 120/80", la PA es el procedimiento del tensiómetro.
7. **Cerrá con la idea**: las user stories son **multipropósito** (requisito, item de planning, conversación) porque su función principal es **desencadenar la conversación**.

> **Si te preguntan "¿cuál es la parte más importante de una user story?"** → **la conversación**. Lo escrito en la tarjeta es solo el puntapié.

> **Si te preguntan "¿cuál es la diferencia entre criterio de aceptación y prueba de aceptación?"** → El **criterio de aceptación** es la **condición** que debe cumplirse (qué validar). Lo define el **PO** antes de desarrollar. La **prueba de aceptación** es el **test ejecutable** que verifica que el criterio se cumple (cómo validar). La diseña el **equipo** durante el desarrollo. **Múltiples PA pueden verificar un mismo CA**. Las PA son la **Confirmación** de las 3 C. Analogía médica: el CA es "presión < 120/80", la PA es el procedimiento del tensiómetro.
