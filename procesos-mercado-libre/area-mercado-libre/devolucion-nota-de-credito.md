---
description: >-
  Carga de la devolución en Presea, eliminación del recibo del autómata y caso
  de cancelación.
---

# Devolución / Nota de Crédito:

### ¿Qué es una devolución?

Es el comprobante con el que se **anula una venta que ya fue facturada**. Hace dos cosas al mismo tiempo:

* **Emite la nota de crédito al cliente**, que cancela lo que se le había facturado.
* **Reingresa la mercadería al stock** de la Empresa 32.

#### Cuándo se usa:

* Cuando el cliente **devuelve el producto** de una venta de Mercado Libre, sea el pedido completo o solo una parte.
* Cuando la venta **se cancela** antes de que la mercadería salga de Hudson. En ese caso la devolución se hace igual, y se agrega un paso — está al final de esta página.

#### Qué no resuelve la devolución

Estas dos cosas hay que hacerlas aparte, y por eso esta página tiene tres partes:

* **No elimina el recibo** que generó el autómata. Si no se elimina, el cliente queda con dinero a favor que no le corresponde.
* **No mueve la mercadería entre depósitos.** La clasificación y la transferencia al Dep 28 o al Dep 50 son un paso posterior del circuito.

***

### Antes de empezar: verificar el despacho

Verificar que la mercadería fue efectivamente **despachada**: tiene que tener **Remito-Factura** o **Remito**. Se consulta desde la **Historia del cliente**.

Ejemplo: cliente con REMITO:

<figure><img src="../../.gitbook/assets/image (198).png" alt="" width="469"><figcaption></figcaption></figure>

Ejemplo: cliente con REMITO-FACTURA:

<figure><img src="../../.gitbook/assets/image (199).png" alt="" width="469"><figcaption></figcaption></figure>

***

## Cargar la devolución

### 1 · Ingresar al ítem de devoluciones

Ir a **Ventas → Comprobantes → Devoluciones**.

<figure><img src="../../.gitbook/assets/image (201).png" alt="" width="281"><figcaption></figcaption></figure>

Ingresar el **número de cliente**. En el campo **ACTUALIZA NOTAS DE VTA** colocar **N** y dar **ENTER** hasta llegar al ingreso de productos.

<figure><img src="../../.gitbook/assets/image (202).png" alt="" width="504"><figcaption></figcaption></figure>

### 3 · Volcar la factura

**No ingresar los productos manualmente.** Volcar la factura con **CTRL + B**. Se abre la ventana con las facturas: seleccionar con **ENTER** y luego dar **ESC**.

<figure><img src="../../.gitbook/assets/image (203).png" alt="" width="504"><figcaption></figcaption></figure>

### 4 · Confirmar los productos volcados

Aparece la ventana con el producto ya volcado. Confirmar con **ESC**.

<figure><img src="../../.gitbook/assets/image (204).png" alt="" width="504"><figcaption></figcaption></figure>

> ⚠️ **Devolución parcial.** Si la factura tiene más de un producto pero solo se devuelven algunos: eliminar el que no corresponde con **F5** o modificar la cantidad, para que en pantalla quede únicamente lo que efectivamente se devolvió.

### 5 · Confirmar la devolución

Dar **ESC** y confirmar la devolución.

***

## Eliminar el recibo del autómata

El autómata genera un recibo junto con la venta. Al hacer la devolución ese recibo queda sin respaldo, y si no se elimina **el cliente queda con dinero a favor que no le corresponde**.

Son dos partes: primero se desimputa la factura y después se anula el recibo.

### 6 · Desimputar la factura del recibo

Ir a **Ventas → Clientes → Historia de clientes**. Pararse sobre el recibo a eliminar y apretar **F8**: se abre una ventana con las facturas imputadas. Sobre la factura, apretar **F8** de nuevo.

<figure><img src="../../.gitbook/assets/image (205).png" alt="" width="563"><figcaption></figcaption></figure>

Va a pedir la contraseña para desimputar. Es "45"**.** Dar **ENTER** y confirmar la desimputación.

<figure><img src="../../.gitbook/assets/image (206).png" alt="" width="563"><figcaption></figcaption></figure>

### 7 · Anular el recibo

Ir a **Ventas → Comprobantes → Anulaciones**. Colocar el número de cliente y la fecha: se abre una ventana con todos los comprobantes. Dar **ENTER** sobre el recibo que se quiere eliminar.

<figure><img src="../../.gitbook/assets/image (207).png" alt="" width="563"><figcaption></figcaption></figure>

Va a preguntar _"¿deja el recibo pendiente para volver a procesar?"_. Poner **CANCELAR**.

<figure><img src="../../.gitbook/assets/image (208).png" alt="" width="563"><figcaption></figcaption></figure>

Después aparece el cartel para confirmar la anulación: poner **ACEPTAR**.

<figure><img src="../../.gitbook/assets/image (209).png" alt="" width="563"><figcaption></figcaption></figure>

> ⚠️ **Si fue una devolución parcial.** Después de anular el recibo hay que **volver a hacerlo**, por el importe que el cliente efectivamente pagó y se queda. Si no, queda sin registrar el cobro de lo que no se devolvió.

***

## Si la devolución es por una cancelación

Cuando la venta se cancela y la mercadería **todavía no salió de Hudson**. La devolución y la eliminación del recibo se hacen igual que arriba, sin ninguna diferencia. Lo único que se agrega es revisar si hay que transferir la mercadería al Depósito 28.

### 8 · Revisar si ya se había transferido del 28 al 32

| Situación                             | Qué se hace                   |
| ------------------------------------- | ----------------------------- |
| Ya se transfirió del Dep 28 al Dep 32 | **Transferir del 32 al 28**   |
| Todavía no se transfirió              | **No hay nada más que hacer** |

> 💡 Si no sabés si la transferencia ya se hizo, **consultalo con Andrea**: ella es la que transfiere del Dep 28 al Dep 32 cuando se despacha.

### 9 · Transferir del 32 al 28 (solo si corresponde)

Es el **mismo procedimiento de Transferencias entre Locales** que se usa para las devoluciones. Siempre sale del Depósito 32; en este caso entra al Depósito 28, en lugar del 50.

> ⚠️ **No transferir si la ida no se hizo.** Si se transfiere del 32 al 28 sin que se hubiera hecho la transferencia de ida, se genera una diferencia de stock en los dos depósitos. Ante la duda, preguntar antes de hacerla.
