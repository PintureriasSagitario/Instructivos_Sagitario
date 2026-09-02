---
description: >-
  Cuando el cliente devuelve el producto en una sucursal que no es Hudson y
  quiere que le devuelvan el dinero.
---

# Devolución de producto en otra sucursal

### ¿Para qué sirve?

Se usa cuando el cliente **devolvió un producto en otra sucursal** —no en Hudson— y **no quiere llevarse otra cosa**: quiere el reintegro del dinero.

El circuito tiene tres partes, y las tres son necesarias:

1. **La devolución**, que anula la facturación de ese producto.
2. **El recibo**, que hay que rehacer por el importe correcto para que la cuenta del cliente quede en cero.
3. **La transferencia a la sucursal**, porque el producto quedó físicamente allá pero el sistema lo ingresó al Depósito 32.

> ⚠️ **Si falta el paso 3, el stock queda mal.** El producto figura en nuestro Depósito 32 y físicamente está en la otra sucursal.

***

## Paso a paso

### 1 · Hacer la devolución del producto devuelto

Ir a **Ventas → Comprobantes → Devoluciones**.

Al volcar la factura aparecen todos sus productos. En el ejemplo la factura tiene **3 productos** y solo hay que devolver **1**: con **F5** se eliminan los que no se devuelven.

<figure><img src="../../.gitbook/assets/image (259).png" alt="" width="563"><figcaption></figcaption></figure>

**Detallar en observaciones qué pasó con ese producto.**

<figure><img src="../../.gitbook/assets/image (260).png" alt="" width="563"><figcaption></figcaption></figure>

Y se graba la devolución.

### 2 · Anular el recibo y generarlo por el importe correcto

El recibo original cubría toda la factura. Como una parte se devolvió, hay que **eliminarlo y volver a cargarlo por la diferencia**: lo que el cliente efectivamente pagó y se queda.

<figure><img src="../../.gitbook/assets/image (262).png" alt="" width="407"><figcaption></figcaption></figure>

En el ejemplo, el recibo original era por **$174.258,74** y al cliente se le devolvieron **$166.859,74**. El recibo nuevo va por la diferencia.

> ⚠️ **Verificar que la cuenta del cliente quede en $0.** Es la forma de confirmar que el importe del recibo nuevo es el correcto. Si queda saldo a favor o en deuda, el recibo se cargó por un importe equivocado.

<figure><img src="../../.gitbook/assets/image (263).png" alt="" width="436"><figcaption></figcaption></figure>

### 3 · Transferir el producto a la sucursal donde lo devolvió

Cuando se genera la devolución, **el producto ingresa al Depósito 32**. Pero el cliente lo dejó en otra sucursal, así que hay que transferirlo: para que salga de nuestro stock y entre en el de ellos.

Ir a **Productos → Depósitos → Transferencias entre locales**.

<figure><img src="../../.gitbook/assets/image (264).png" alt="" width="192"><figcaption></figcaption></figure>

**Password depósito de salida = 32** · **COT = N**

Se abre la ventana para ingresar el código del producto y la cantidad.

<figure><img src="../../.gitbook/assets/image (265).png" alt="" width="563"><figcaption></figcaption></figure>

Al dar **ESC** pregunta a qué sucursal transferir. Se puede buscar con **F6** — en el ejemplo es **26\_JUNIN** — y pide confirmar que ese depósito sea el correcto.

<figure><img src="../../.gitbook/assets/image (266).png" alt="" width="437"><figcaption></figcaption></figure>

Se confirma, y **en observaciones se coloca a qué venta corresponde** esa transferencia.

<figure><img src="../../.gitbook/assets/image (267).png" alt="" width="293"><figcaption></figcaption></figure>

### 4 · Pasarle el remito a la sucursal

La transferencia genera un **REMITO**. Hay que **pasárselo a la sucursal** para que ellos recepcionen esa mercadería.

<figure><img src="../../.gitbook/assets/image (268).png" alt="" width="474"><figcaption></figcaption></figure>

> 💡 **El circuito no termina hasta que la sucursal recepciona.** Mientras no lo hagan, la mercadería queda en tránsito y no aparece en el stock de ninguno de los dos.

***

## Verificación final

* La factura original y la **nota de crédito** del producto devuelto, en la historia del cliente.
* El **recibo nuevo** por el importe correcto, con la cuenta del cliente en **$0**.
* La **transferencia al depósito de la sucursal**, con el remito entregado.

***

> ℹ️ Es la misma pantalla de **Transferencias entre locales** que se usa para clasificar las devoluciones al Dep 28 o al Dep 50. Siempre sale del Depósito 32; lo único que cambia es que acá el destino es el depósito de una sucursal.
