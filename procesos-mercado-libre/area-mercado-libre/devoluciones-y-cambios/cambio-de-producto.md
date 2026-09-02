---
description: Cuando el producto ya fue facturado y hay que reemplazarlo por otro.
---

# Cambio de producto

### ¿Para qué sirve?

Se usa cuando el producto **ya fue facturado** —tiene **REMITO-FACTURA**— y por algún motivo hay que cambiarlo: porque la sucursal envió otro, porque no había disponible, o cualquier otra razón.

No se corrige la factura original. El circuito tiene tres pasos: **se devuelve el producto que se cambia, se genera una nota de venta nueva por el producto que va, y se factura esa nota de venta.**

> ⚠️ **La devolución es solo del producto que cambia.** Si la factura tenía varios productos, los demás quedan como están. Por eso el paso 1 se hace con F5.

***

## Paso a paso

### 1 · Hacer la devolución del producto que se cambia

Ir a **Ventas → Comprobantes → Devoluciones**.

Al volcar la factura aparecen todos sus productos, En este caso vemos que la factura tiene 3 productos, pero solo necesitamos refacturar 1.

<figure><img src="../../../.gitbook/assets/image (255).png" alt="" width="557"><figcaption></figcaption></figure>

Con **F5** hay que **eliminar los que NO se anulan**, dejando únicamente el que se está cambiando.

<figure><img src="../../../.gitbook/assets/image (257).png" alt="" width="563"><figcaption></figcaption></figure>

Después se graba la devolución.

***

### 2 · Generar la nota de venta nueva

Ir a **Ventas → Pedidos → Ingreso de notas de venta**.

Ingresar el o los productos que van en lugar del anterior.

{% hint style="info" %}
Facturarlos al precio que el cliente paga, incluyendo un descuento o una diferencia mayor si corresponde.
{% endhint %}

***

### 3 · Generar el remito-factura

Ir a **Ventas → Pedidos → Despachos → c/Remito → Factura x nro.**

Se vuelca por número de nota de venta, o se busca por número de cliente con **F6**.

En **Despacho completo** va **S**.

<figure><img src="../../../.gitbook/assets/image (256).png" alt=""><figcaption></figcaption></figure>

Y se confirma el remito-factura.



***

### 4. Si se cobra una diferencia o se devuelve dinero, hay que eliminar el recibo y hacerlo por el importe correcto.

***

## Verificación final

En la historia del cliente tienen que quedar los tres comprobantes:

* El **remito-factura original**
* La **Devolución** del producto que se cambió
* El **remito-factura nuevo** del producto que va

Si los importes coinciden, el saldo del cliente queda en cero.

***
