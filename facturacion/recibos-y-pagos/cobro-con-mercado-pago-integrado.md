---
description: Cobro con QR y tarjetas desde el Lapos de Mercado Pago
---

# Cobro con MP - Integrado

* Cargá el ticket como de costumbre. Cuando llegues a la parte de **pagos**, seguí estos pasos:

#### 1. Elegí la forma de cobro

Arriba a la izquierda aparecen 4 cuadrados con el símbolo de Mercado Pago. Para cobrar usás los siguientes:

* **Logo de MP:** <img src="../../.gitbook/assets/image (189).png" alt="" data-size="line"> envía la orden al Lapos de MP para que aparezca el cobro.
* **Logo de QR:** <img src="../../.gitbook/assets/QR.jpg" alt="" data-size="line"> para que el cliente escanee el QR ya impreso y le aparezca el monto exacto.

<figure><img src="../../.gitbook/assets/image (190).png" alt=""><figcaption></figcaption></figure>

> ℹ️ Los otros dos cuadrados se usan para **anulaciones**, no para el cobro de la venta.

#### 2. El sistema queda esperando el pago

Al elegir cualquiera de las dos formas, aparece un cartel avisando que el sistema queda a la espera de que se cobre. Con **F10** se cancela.

<figure><img src="../../.gitbook/assets/image (191).png" alt=""><figcaption></figcaption></figure>

#### 3. Cobro en el Lapos de MP

Si elegiste el Lapos de MP, en el equipo vas a ver esto. El cliente **elige cómo pagar (tarjeta o código QR) y completa el pago en el Lapos**.

<div><figure><img src="../../.gitbook/assets/image (192).png" alt="" width="375"><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (193).png" alt="" width="375"><figcaption></figcaption></figure></div>

#### 4. Cierre del pago en el sistema

Una vez cobrado, en el sistema aparece directamente el cuadro de observación para cerrar el pago.

{% hint style="warning" %}
\
📌**IMPORTANTE:**\
Con esta integración, el sistema **detecta automáticamente si la venta tuvo o no descuento y realiza la Nota de Crédito correspondiente**. Ya no hay que seleccionar a mano si fue con descuento o no.
{% endhint %}

