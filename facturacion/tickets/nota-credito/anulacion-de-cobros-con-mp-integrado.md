---
description: >-
  Con la integración de Mercado Pago, al hacer una Nota de Crédito por Reversión
  de un ticket que se cobró por MP, el sistema también devuelve la plata al
  cliente.
---

# 📌 Anulación de cobros con MP Integrado

⚠️ **La reversión es total.** El sistema revierte el pago completo, así que esto **no sirve para devolver una parte del ticket**.

***

### 1 · Generar la [nota de crédito por reversión](reversion-total.md)

Se hace **como de costumbre**, sin ningún cambio. Al dar `Esc` para grabarla, el sistema abre esta ventana:

<figure><img src="../../../.gitbook/assets/image (289).png" alt="" width="245"><figcaption></figcaption></figure>

Leé la ventana antes de seguir: ahí está la **fecha y la hora exactas del cobro** que se va a revertir. Ese es el dato que te sirve para encontrar la operación correcta en Mercado Pago.

***

### 2 · Buscar el N° de operación en Mercado Pago

Entrá a la cuenta de Mercado Pago de la sucursal y ubicá el cobro **usando la fecha y hora que mostró la ventana del sistema**. Al abrir la operación, abajo de todo aparece **N.° de operación**: ese es el número que hay que copiar.

<figure><img src="../../../.gitbook/assets/image (290).png" alt="" width="398"><figcaption></figcaption></figure>

> ⚠️ **Antes de copiar el número, verificá que coincidan el importe y la fecha/hora** con lo que dice la ventana del sistema. Si no coinciden, es otra operación.

***

### 3 · Pegar el número y aceptar

Pegá el N° de operación en el recuadro y confirmá con **Aceptar**.

El cliente recibe el reintegro **en el mismo medio con el que pagó**:

* Si pagó con **dinero en cuenta de MP** → vuelve a su cuenta de Mercado Pago.
* Si pagó con **tarjeta a través de MP** → vuelve a esa tarjeta.

No hay que hacer nada más: la devolución queda hecha junto con la nota de crédito.

***

> ⚠️ **Si no encontrás la operación en Mercado Pago, no adivines.** Cancelá y consultá a Oficina de Administración antes de seguir. Un número de operación equivocado revierte el cobro de otra venta.

> 📝 Como toda nota de crédito, esta también tiene que quedar **observada y firmada** en el momento, con la causa de la devolución. Ver _Notas de crédito: observar y firmar_.
