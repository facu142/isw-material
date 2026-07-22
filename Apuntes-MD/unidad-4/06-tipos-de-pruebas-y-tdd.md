# 06 — Tipos de Pruebas y TDD

> Págs. 186-188 del apunte + transcripción de clase de testing. Cubre smoke test, sanity test, testing funcional, testing no funcional, y TDD con el ciclo Red-Green-Refactor.

## Smoke Test

> Es una **primera corrida** de los tests de sistema que provee cierto aseguramiento de que el software no provoca una **falla catastrófica**. Son pruebas **muy superficiales**.

Lo que se suele probar:

- ¿La aplicación arranca?
- ¿Se puede iniciar sesión?
- ¿Carga la pantalla principal?
- ¿Responde el backend?
- ¿Se conecta a la base de datos?
- ¿No hay errores fatales?

> Es un **filtro rápido** antes de invertir tiempo en tests más profundos. Se hace muchas veces con la **primera versión** del producto: una corrida rápida por todo el software, **sin escenarios alternativos ni casos rebuscados**, solo para ver que no haya nada catastrófico.

## Sanity Test

> **No es lo mismo que el smoke test** (la profe lo aclaró explícitamente en clase).

| | **Smoke Test** | **Sanity Test** |
|---|---|---|
| **Qué verifica** | Que no haya **fallas catastróficas** (el software "prende"). | Que se corran todos los tests y las **funcionalidades básicas no tengan fallas críticas**. |
| **Profundidad** | Más superficial. | Un poco más profundo: confirma que lo básico sigue sano. |
| **Cuándo** | Primera versión / build nuevo. | Después de cambios, para confirmar que lo esencial no se rompió. |

> **Mnemotecnia**: *smoke* = "¿prende sin explotar?"; *sanity* = "¿lo básico sigue cuerdo?".

---

## Testing Funcional

- Las pruebas se basan en **funciones y características** del sistema (descritas en documentos o entendidas por los testers) y su **interoperabilidad** con sistemas específicos.
- **Basado en requerimientos**.
- **Basado en los procesos de negocio**.
- Evidentemente deriva de **requerimientos funcionales**.

> **Ejemplo**: en una aplicación bancaria, las pruebas funcionales verificarán si los usuarios pueden realizar correctamente transacciones (transferencias, pagos, consultas de saldo, etc.).

> **De la clase**: es el tipo de prueba **más fácil** porque, si los requerimientos están bien planteados, el caso de prueba **deriva casi automáticamente** de ellos.

---

## Testing No Funcional

- Es la prueba de **cómo funciona** el sistema, no de **qué hace**.
- Los requerimientos no funcionales son **tan importantes** como los funcionales.

> **De la clase**: acá es donde toma especial importancia que el **ambiente de prueba sea lo más parecido posible a producción** (para probar stress, portabilidad, fiabilidad). Y ojo: los requerimientos no funcionales **van mucho más allá del código** — tienen que ver con el **ambiente, las condiciones de ejecución y hasta el equipamiento**.
- Tipos de pruebas no funcionales:

| Tipo | Qué analiza |
|---|---|
| **Performance** | Tiempo de respuesta y concurrencia. |
| **Carga** | Comportamiento de los dispositivos de hardware (procesadores, memorias, etc.). |
| **Stress** | Se fuerza al sistema a fallar, sometiéndolo a condiciones más allá de las normales. |
| **Usabilidad** | Si es cómodo de utilizar para el usuario. |
| **Portabilidad** | Se prueba en distintos entornos. |

> Estos tipos se corresponden con los cuadrantes del testing ágil (ver [07-testing-agil.md](07-testing-agil.md)).

---

## TDD — Test Driven Development

> Proceso en el que nos enfocamos en **construir primero la prueba unitaria** cuando tenemos los requerimientos, y **luego codear el componente**. Básicamente, **se escribe código a partir de la ejecución de casos de prueba**.

### Ciclo Red-Green-Refactor

1. 🔴 **Rojo**: escribís un caso de prueba basado en una funcionalidad que querés implementar. Al principio, este test **fallará** porque aún no escribiste el código.
2. 🟢 **Verde**: escribís el **código mínimo** necesario para que la prueba pase.
3. ♻️ **Refactorizar**: mejorás el código para hacerlo más limpio y eficiente, **sin que las pruebas dejen de pasar**.

```javascript
// 1. ROJO - escribo el test
test('sumar(2, 3) debe ser 5', () => {
  expect(sumar(2, 3)).toBe(5);  // sumar no existe, falla
});

// 2. VERDE - escribo el código mínimo
function sumar(a, b) {
  return a + b;  // ahora pasa
}

// 3. REFACTOR - mejoro (ejemplo, sumar manejo de tipos)
function sumar(a, b) {
  if (typeof a !== 'number' || typeof b !== 'number') {
    throw new Error('Ambos argumentos deben ser números');
  }
  return a + b;
}
```

### Beneficio clave

El feedback es **inmediato**: sabés en todo momento si lo que acabás de codear cumple con lo que el test esperaba. Esto conecta con el principio de testing ágil: **reducir la latencia del feedback**.

---

## Chivo para el oral

1. **Smoke**: primera corrida, superficial, filtra fallas catastróficas. Listá las preguntas típicas (arranca, login, pantalla principal, BD, etc).
2. **Sanity ≠ Smoke**: smoke es "¿prende sin explotar?"; sanity es "¿las funcionalidades básicas siguen sanas tras correr todos los tests?". (La profe lo aclaró: NO son lo mismo.)
3. **Funcional**: "qué hace". Deriva de requerimientos funcionales, basado en procesos de negocio. El más fácil: deriva casi automáticamente de los requerimientos.
4. **No funcional**: "cómo funciona". Performance, carga, stress, usabilidad, portabilidad. Necesita ambiente lo más parecido a producción; los RNF van más allá del código (ambiente, equipamiento).
5. **TDD**: ciclo Red-Green-Refactor, en ese orden. Test primero, código mínimo, refactor sin romper nada.
6. **Cerrá con la conexión**: TDD encaja con el principio ágil de **testing temprano** y **reducir latencia del feedback**.

> **Si te preguntan la diferencia entre funcional y no funcional** → funcional verifica **qué** hace (transferencia, pago, etc); no funcional verifica **cómo** lo hace (qué tan rápido, cuántos usuarios soporta, etc).

> **Si te preguntan la diferencia entre smoke y sanity** → smoke es una corrida superficial que verifica que no haya **fallas catastróficas** (típicamente en la primera versión). Sanity verifica que, corriendo todos los tests, las **funcionalidades básicas no tengan fallas críticas**. La profe remarcó que **no son lo mismo**.
