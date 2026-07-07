# Resolución del Ejercicio 17: Estimación de Costos (Método COSMIC)

**Objetivo del Proyecto:** Desarrollar una aplicación web para la gestión eficiente y segura de finanzas personales.

## Consideraciones Previas y Criterio de Clasificación

Para cumplir con la instrucción de clasificar las interacciones en Pequeña (S), Mediana (M) o Grande (L), y basándonos en que cada movimiento funcional (Entrada, Salida, Lectura, Escritura) equivale a 1 punto COSMIC (PFC), establecemos la siguiente escala de estimación:

- **Pequeña (S):** ~3 movimientos de datos (Ej: Entrada + Escritura + Salida). Valor = **3 PFC**.
- **Mediana (M):** ~5 movimientos de datos (Ej: Entrada + 2 Lecturas + Escritura + Salida). Valor = **5 PFC**.
- **Grande (L):** ~7 movimientos de datos o más (Ej: múltiples validaciones, lecturas y escrituras cruzadas). Valor = **7 PFC**.

---

## Pasos 1, 2 y 3: Identificación, Clasificación y Cálculo del Tamaño Funcional

A continuación se analizan los requisitos funcionales del usuario (FUR) para extraer los procesos funcionales y calcular su tamaño.

### 1. Gestión de cuentas bancarias

| Requisito / Interacción Funcional | Clasificación | Justificación de Movimientos Estimados                                                                              |  PFC   |
| :-------------------------------- | :-----------: | :------------------------------------------------------------------------------------------------------------------ | :----: |
| Creación y edición de cuentas     |     **S**     | Entrada de datos, Escritura en BD, Salida (confirmación)                                                            |   3    |
| Visualizar saldo e historial      |     **M**     | Entrada (búsqueda/filtro), Lectura (saldo), Lectura (historial), Salida (pantalla)                                  |   5    |
| Realizar transferencias           |     **L**     | Entrada (datos), Lectura (origen), Lectura (destino), Escritura (débito), Escritura (crédito), Salida (comprobante) |   7    |
| Descargar historial (CSV/PDF)     |     **S**     | Entrada (solicitud), Lectura (datos), Salida (archivo generado)                                                     |   3    |
| **Subtotal Módulo 1**             |               |                                                                                                                     | **18** |

### 2. Gestión de ingresos y gastos

| Requisito / Interacción Funcional | Clasificación | Justificación de Movimientos Estimados                                 |  PFC   |
| :-------------------------------- | :-----------: | :--------------------------------------------------------------------- | :----: |
| Creación y edición                |     **S**     | Entrada (monto/fecha), Escritura (registro), Salida (confirmación)     |   3    |
| Categorizar ingresos/gastos       |     **S**     | Entrada (selección), Escritura (actualización), Salida                 |   3    |
| Visualizar gráficos y reportes    |     **M**     | Entrada (filtros), Lectura (agrupada), Salida (renderizado de gráfico) |   5    |
| Establecer presupuestos           |     **S**     | Entrada (categoría/monto), Escritura (límite), Salida                  |   3    |
| **Subtotal Módulo 2**             |               |                                                                        | **14** |

### 3. Gestión de deudas

| Requisito / Interacción Funcional        | Clasificación | Justificación de Movimientos Estimados                              |  PFC   |
| :--------------------------------------- | :-----------: | :------------------------------------------------------------------ | :----: |
| Crear/editar deudas (monto, tasa, plazo) |     **M**     | Entrada (múltiples variables), Escritura, Salida (confirmación)     |   5    |
| Calendario de pagos y simulaciones       |     **L**     | Entrada (escenarios), Lectura (deuda), Salidas (cálculos múltiples) |   7    |
| Informes de progreso                     |     **M**     | Entrada (consulta), Lectura (pagos vs total), Salida (reporte)      |   5    |
| **Subtotal Módulo 3**                    |               |                                                                     | **17** |

**Tamaño Funcional Total del Proyecto (X):** 18 + 14 + 17 = **49 PFC**.

---

## Pasos 4, 5, 6 y 7: Estimación de Esfuerzo, Duración y Costos

### Paso 4: Obtener el costo por punto de función (CPFC)

Tomando como referencia la región de **Rosario, Argentina**, el costo de un equipo de desarrollo estándar (Ssr/Sr) se calcula basándose en salarios y costos operativos en dólares (para mantener la estabilidad de la estimación).

- Costo mensual estimado de un equipo pequeño-mediano: ~$4,500 USD.
- Productividad promedio estimada: 30 PFC/mes.
- _Cálculo CPFC:_ $4,500 / 30 = $150 USD por PFC.
- **Y = 150 USD**

### Paso 5: Determinar la cantidad de PFC por mes

Se conformará un equipo de **Z = 3 personas** (1 Desarrollador Full-Stack, 1 Analista QA, 1 Líder de Proyecto/Diseñador).

- Basado en la experiencia empírica de un equipo de este tamaño, se estima una capacidad de desarrollo constante.
- **W = 30 PFC / mes**

### Paso 6: Calcular la duración del proyecto

Se divide el tamaño funcional total (X) por la capacidad mensual del equipo (W).

- _Fórmula:_ X / W
- _Cálculo:_ 49 PFC / 30 PFC/mes = 1.63 meses.
- **A = 1.63 meses** (Aproximadamente 7 semanas de trabajo).

### Paso 7: Estimar el costo total

Se multiplica el tamaño funcional total (X) por el costo unitario de cada punto de función (Y).

- _Fórmula:_ Costo = Tamaño del software x Costo por punto de función.
- _Cálculo:_ 49 PFC x 150 USD
- **B = 7.350 USD**

---

## Resumen Final de Resultados

| Variable | Descripción                            | Valor Estimado |
| :------- | :------------------------------------- | :------------- |
| **X**    | Puntos de Función COSMIC (PFC) Totales | **49 PFC**     |
| **Y**    | Costo por Punto de Función (CPFC)      | **150 USD**    |
| **Z**    | Tamaño del Equipo de Desarrollo        | **3 personas** |
| **W**    | Cantidad de PFC producidos por mes     | **30 PFC/mes** |
| **A**    | Duración Estimada del Proyecto         | **1.63 meses** |
| **B**    | Costo Total del Proyecto               | **7.350 USD**  |
