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

## Chivo para el oral

1. **Concepto**: una historia = una funcionalidad valiosa para un usuario. **Token para una conversación**.
2. **Forma**: "Como `<rol>`, yo puedo `<actividad>` de forma tal que `<valor de negocio>`".
3. **Las 3 C**:
   - **Tarjeta**: lo que se escribe, con criterios de aceptación.
   - **Conversación**: la parte más importante. Cara a cara, no se documenta.
   - **Confirmación**: las pruebas de aceptación.
4. **Porciones Verticales**: las user stories cortan la arquitectura en vertical (de UI a BD). Si fueran horizontales, no darían valor.
5. **Proxies**: cuando no se puede hablar con el usuario real, hay representantes. El PO es un proxy de negocio (no técnico).
6. **Cerrá con la idea**: las user stories son **multipropósito** (requisito, item de planning, conversación) porque su función principal es **desencadenar la conversación**.

> **Si te preguntan "¿cuál es la parte más importante de una user story?"** → **la conversación**. Lo escrito en la tarjeta es solo el puntapié.
