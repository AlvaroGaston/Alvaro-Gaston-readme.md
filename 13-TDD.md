EJEMPLO PRÁCTICO DE TDD: UN SISTEMA BANCARIO SIMPLE

**Etapa 1: La primera prueba (El ciclo Rojo)**

- **Objetivo:** Queremos una clase `CuentaBancaria`. Lo primero es asegurarnos de que al crear una cuenta, su saldo inicial sea 0.
- **Acción:** Escribimos la prueba _antes_ que el código.

```javascript
// --- PRUEBAS (CuentaBancaria.test.js) ---
test("Una nueva cuenta debe tener saldo 0", () => {
  const cuenta = new CuentaBancaria("Alvaro");
  expect(cuenta.saldo).toBe(0);
});
```

- **Resultado:** Si corremos la prueba ahora, falla (ROJO), porque `CuentaBancaria` no existe.

**Etapa 2: El código mínimo para pasar (El ciclo Verde)**

- **Objetivo:** Escribir el código más simple posible para que la prueba anterior pase.
- **Acción:** Creamos la clase.

```javascript
// --- CÓDIGO (CuentaBancaria.js) ---
class CuentaBancaria {
  constructor(titular) {
    this.titular = titular;
    this.saldo = 0;
  }
}
```

- **Resultado:** Corremos la prueba de nuevo. Ahora pasa (VERDE).

**Etapa 3: Refactorización y expansión (El ciclo completo)**

- **Objetivo:** Ahora que tenemos una base que funciona, repetimos el ciclo para cada nueva funcionalidad (depositar, retirar, etc.) y para los casos borde (intentar retirar más dinero del que hay, etc.).
- **Acción:** Se agregan más pruebas, una por una, y se escribe el código necesario para que pasen.

```javascript
// --- CÓDIGO FINAL (CuentaBancaria.js) ---
class CuentaBancaria {
  constructor(titular) {
    this.titular = titular;
    this.saldo = 0;
  }
  depositar(cantidad) {
    if (cantidad <= 0)
      throw new Error("El monto a depositar debe ser positivo");
    this.saldo += cantidad;
  }
  retirar(cantidad) {
    if (cantidad <= 0) throw new Error("El monto a retirar debe ser positivo");
    if (cantidad > this.saldo) throw new Error("Fondos insuficientes");
    this.saldo -= cantidad;
  }
  transferir(cantidad, cuentaDestino) {
    this.retirar(cantidad);
    cuentaDestino.depositar(cantidad);
  }
}

// --- PRUEBAS FINALES (CuentaBancaria.test.js) ---
describe("Sistema de Cuenta Bancaria con TDD", () => {
  let cuenta;
  beforeEach(() => {
    cuenta = new CuentaBancaria("Alvaro");
  });

  test("Debe crear una cuenta con titular y saldo 0", () => {
    expect(cuenta.titular).toBe("Alvaro");
    expect(cuenta.saldo).toBe(0);
  });
  test("Debe sumar el monto correcto al depositar", () => {
    cuenta.depositar(100);
    expect(cuenta.saldo).toBe(100);
  });
  test("Debe restar el monto correcto al retirar", () => {
    cuenta.depositar(100);
    cuenta.retirar(30);
    expect(cuenta.saldo).toBe(70);
  });

  test("Debe transferir fondos entre cuentas", () => {
    const destino = new CuentaBancaria("Destino");
    cuenta.depositar(100);
    cuenta.transferir(40, destino);
    expect(cuenta.saldo).toBe(60);
    expect(destino.saldo).toBe(40);
  });

  // Pruebas de casos borde y errores
  test("Debe lanzar un error si se intenta retirar más del saldo disponible", () => {
    expect(() => cuenta.retirar(100)).toThrow("Fondos insuficientes");
  });
  test("Debe lanzar un error si se deposita un monto negativo o cero", () => {
    expect(() => cuenta.depositar(-50)).toThrow(
      "El monto a depositar debe ser positivo",
    );
  });
  test("Debe lanzar un error si se retira un monto negativo o cero", () => {
    expect(() => cuenta.retirar(0)).toThrow(
      "El monto a retirar debe ser positivo",
    );
  });
});
```

**Conclusión del proceso TDD:**
El resultado es un código robusto donde cada línea de lógica de negocio está protegida por una prueba. Esto nos da la confianza para hacer cambios a futuro, sabiendo que si rompemos algo, las pruebas nos avisarán inmediatamente. El comando `npm test` se convierte en nuestra red de seguridad.
