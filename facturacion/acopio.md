---
description: >-
  Circuito completo para registrar un acopio en Presea, desde el cobro
  adelantado hasta la entrega de la mercadería.
---

# Acopio

El acopio es una venta que el cliente paga por adelantado y retira después. El circuito tiene **cuatro pasos** y hay que hacerlos en orden: cada uno depende del anterior.

### 1. Recibo por pago adelantado

Entrá a **Ventas → Comprobantes → Recibos** y marcá la opción **Pago adelantado**.

<figure><img src="../.gitbook/assets/image (269).png" alt="" width="563"><figcaption></figcaption></figure>

#### Observaciones

En el campo de observaciones anotá el **número de la lista de precios**.

<figure><img src="../.gitbook/assets/image (270).png" alt="" width="359"><figcaption></figcaption></figure>

{% hint style="info" %}
Este dato es el que después permite saber con qué precios se armó el acopio. Si no se carga, se pierde la referencia.&#x20;
{% endhint %}

#### Artículos

En la parte de artículos cargá el producto de código `99999999...`, llamado **PRODUCTO GENÉRICO PARA ACOPIOS**.

<figure><img src="../.gitbook/assets/image (272).png" alt="" width="563"><figcaption></figcaption></figure>

{% hint style="warning" %}
Cargá únicamente el producto. **No modifiques nada más** en esta pantalla.
{% endhint %}

#### Pagos

Presioná `ESC` para pasar a la sección de pagos y cargá el monto del acopio en efectivo, o con el medio de pago que el cliente elija.

<figure><img src="../.gitbook/assets/image (274).png" alt="" width="563"><figcaption></figcaption></figure>

Confirmación

Presioná `ESC` de nuevo. El sistema te lleva a la carga de retenciones: como no hay ninguna, volvé a presionar `ESC` y confirmá el recibo.

<figure><img src="../.gitbook/assets/image (275).png" alt="" width="287"><figcaption></figcaption></figure>

{% hint style="info" %}
Al confirmar el recibo, el sistema genera automáticamente **una factura** por ese acopio.&#x20;
{% endhint %}

### ETAPA 2: Cúando el cliente viene a retirar algo de ese acopio.

#### 2. Nota de venta

Entrá a **Ventas → Pedidos → Ingreso Notas de Ventas**.

En el campo **Condición**, buscá con `F6` la opción **Acopio Ventas**.

<figure><img src="../.gitbook/assets/image (276).png" alt=""><figcaption></figcaption></figure>

#### Vincular el recibo

Presioná `Enter` hasta llegar al campo **Pago adelantado**.

<figure><img src="../.gitbook/assets/image (277).png" alt="" width="553"><figcaption></figcaption></figure>

Con `F6`, seleccioná el recibo que hiciste en el paso anterior.

<figure><img src="../.gitbook/assets/image (278).png" alt="" width="506"><figcaption></figcaption></figure>

{% hint style="danger" %}
**Este paso es obligatorio.** Si no seleccionás el recibo, el sistema no descuenta del pago la mercadería que el cliente va a retirar.&#x20;
{% endhint %}

#### Artículos

Cargá los artículos que el cliente se lleva y confirmá la nota de venta.

<figure><img src="../.gitbook/assets/image (279).png" alt="" width="563"><figcaption></figcaption></figure>

#### 3. Preparación grupal

Entrá a **Ventas → Pedidos → Preparación → Preparación Grupal**.

<figure><img src="../.gitbook/assets/image (280).png" alt="" width="326"><figcaption></figcaption></figure>

#### Filtros

Filtrá por **número de cliente** y, si hace falta, por fecha. El resto de los filtros dejalos como están.

<figure><img src="../.gitbook/assets/image (281).png" alt="" width="563"><figcaption></figcaption></figure>

#### Selección

Va a aparecer la nota de venta que acabás de hacer, con un renglón por cada producto.

<figure><img src="../.gitbook/assets/image (282).png" alt="" width="563"><figcaption></figcaption></figure>

Con la **barra espaciadora** seleccioná todos los productos de la misma nota de venta.

<figure><img src="../.gitbook/assets/image (283).png" alt="" width="563"><figcaption></figcaption></figure>

Presioná `ESC` y confirmá la preparación.

#### 4. Despacho con remito y factura

Entrá a **Ventas → Pedidos → Despachos → Grupal c/Remito y Factura**.

<figure><img src="../.gitbook/assets/image (284).png" alt="" width="335"><figcaption></figcaption></figure>

#### Filtros

Filtrá por **número de cliente** y, en el campo **Depós.**, poné el número de tu sucursal. Agregá la fecha si hace falta. El resto de los filtros dejalos como están.

<figure><img src="../.gitbook/assets/image (285).png" alt="" width="563"><figcaption></figcaption></figure>

#### Selección

Va a aparecer la nota de venta.

<figure><img src="../.gitbook/assets/image (286).png" alt="" width="563"><figcaption></figcaption></figure>

Seleccionala con la **barra espaciadora**.

<figure><img src="../.gitbook/assets/image (287).png" alt="" width="563"><figcaption></figcaption></figure>

Presioná `ESC` y confirmá.

## Verificación final

{% hint style="danger" %}
**Es de suma importancia que verifiques este paso.**
{% endhint %}

Al confirmar el despacho, el sistema tiene que generar **dos comprobantes**:

* Una **factura**
* Una **nota de crédito**

> Si falta alguno de los dos, el acopio quedó mal registrado.&#x20;

### Resumen del circuito

| Paso | Dónde                                                    | Qué genera                |
| ---- | -------------------------------------------------------- | ------------------------- |
| 1    | Ventas → Comprobantes → Recibos                          | Recibo + factura          |
| 2    | Ventas → Pedidos → Ingreso Notas de Ventas               | Nota de venta             |
| 3    | Ventas → Pedidos → Preparación → Preparación Grupal      | Preparación confirmada    |
| 4    | Ventas → Pedidos → Despachos → Grupal c/Remito y Factura | Factura + nota de crédito |
