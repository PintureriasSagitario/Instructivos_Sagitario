---
description: Control de que el autómata haya facturado todo.
---

# Control de NV pendientes de facutar.

### ¿Para qué sirve?

Para **corroborar que no haya quedado nada sin facturar**. Devuelve el listado de las notas de venta que ya están procesadas pero que el autómata no facturó.

> ⏰ **Cuándo se hace.** El autómata corre **dos veces por día, a las 13:00 y a las 15:00**, con las ventas del día y con lo que haya quedado pendiente de días anteriores.
>
> El control se hace **una hora después de cada corrida**, o sea alrededor de las 14:00 y de las 16:00. **Son dos controles por día, no uno.**

## Paso a paso

### 1 · Entrar a la consulta

Ir a **Ventas → Pedidos → Consultas → NV MELI PENDIENTES FACTURAR**.

<figure><img src="../../.gitbook/assets/image (237).png" alt="" width="247"><figcaption></figcaption></figure>

### 2 · Los filtros

Se pueden dejar como están (Si lo dejamos asi va a traer todo), o filtrar por **desde la fecha / hasta la fecha**.

<figure><img src="../../.gitbook/assets/image (239).png" alt=""><figcaption></figcaption></figure>

### 3 · Leer el listado

Abre un listado con todos los **números de nota de venta ya procesada que no se facturaron**.

<figure><img src="../../.gitbook/assets/image (240).png" alt="" width="563"><figcaption></figcaption></figure>

***

#### ¿Cómo se lee el resultado?

• En el listado solo pueden quedar algunas pendientes del día (Las que entraron mientras el autómata estaba corriendo) Pero nunca deberían quedar del día anterior. \
• Si hay de días anteriores es porque no se controlo a tiempo y algo del proceso fallo.

### ¿Por qué pueden aparecer sin facturar?

<details>

<summary>1 · Se trabó el autómata por error de correlatividad</summary>

Pasa cuando AFIP está caído. En ese caso hay que seguir el instructivo de errores:\
👉 [Error de Correlatividad](https://pinturerias-sagitario.gitbook.io/instructivos_sagitario/errores-presea/error-correlatividad)

</details>

<details>

<summary>2 · Cambiaron el número de vendedor de la nota de venta</summary>

⚠️ **El autómata solo factura las notas de venta del vendedor 117.** \
Si a alguna le cambiaron el vendedor, queda sin facturar.

</details>

<details>

<summary>3 · Falló el autómata por otro motivo</summary>

Avisar a **Camí** y/o a **Fede**.

</details>



