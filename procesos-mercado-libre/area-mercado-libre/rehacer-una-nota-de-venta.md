---
description: >-
  Cuando hay que ingresar una nota de venta desde cero, o rehacer una porque la
  venta pide envío a domicilio.
---

# Rehacer una nota de venta

### ¿Para qué sirve?

Cuando la venta **pide envío a domicilio**, hay que cargar los datos de entrega en la nota de venta. Como esos datos no estaban al momento de la venta, hay que rehacer la facturación para que salgan en el comprobante.

**La primera pregunta define todo el circuito:** ¿la venta ya fue facturada o todavía no?

***

## Caso A · Todavía NO fue facturado

### 1 · Modificar la nota de venta

Poner **nuestro número de vendedor** y cargar los **datos de entrega**.

> ⚠️ **Cambiar el vendedor es lo que evita que el autómata la facture.** El autómata solo factura las notas de venta del vendedor **117**. Poniendo el nuestro, queda fuera de su alcance y podemos facturarla a mano con los datos de entrega ya cargados.

### 2 · Facturar desde C/factura y recibo x nro

Ir al ítem **C/factura y recibo x nro.**

<figure><img src="../../.gitbook/assets/image (1).png" alt="" width="187"><figcaption></figcaption></figure>

### 3 · La parte de pagos, según si el recibo ya existe

| Situación                                     | Qué hacer en pagos                                                                         |
| --------------------------------------------- | ------------------------------------------------------------------------------------------ |
| **El recibo ya fue generado por el autómata** | Dejar el medio de pago vacio, así lo envía a cuenta y lo compensa con el recibo ya cargado |
| **El recibo todavía no fue generado**         | Ingresar **MP (4000)** y el **n° de operación**                                            |

> ⚠️ **Si el recibo ya existe y no se ponen los pagos en 0, se duplica el cobro.** Quedarían dos recibos por la misma venta y el cliente con saldo a favor.

***

## Caso B · Ya fue todo facturado

Acá no se puede modificar: hay que deshacer y volver a hacer.

### 1 · Hacer la devolución

Anula la facturación existente.

👉 [Devoluciones y notas de crédito](devolucion-nota-de-credito.md)

### 2 · Generar la nota de venta desde cero

Ventas - Pedidos - Ingreso de nota de venta\
Con los datos de entrega ya cargados.

### 3 · Facturarla desde C/factura y recibo x nro

El mismo ítem del Caso A, con el mismo criterio para la parte de pagos.

***

> 💡 **Esta nota de venta va a aparecer en el control diario.** Al sacarla del vendedor 117, el autómata no la factura, así que va a salir en la consulta de **NV pendientes de facturar** hasta que se facture a mano. Es esperado, no es un error — pero conviene facturarla en el día para que no quede dando vueltas en ese listado.
>
> 👉 [NV pendientes de facturar](control-de-nv-pendientes-de-facturar..md)

***
