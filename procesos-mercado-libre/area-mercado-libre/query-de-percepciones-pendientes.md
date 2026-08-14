---
description: Detectar qué facturas A tienen percepciones en deuda.
---

# Query de Percepciones Pendientes

***

#### ¿Para qué sirve?

Devuelve el listado de las **facturas A que quedaron con saldo en deuda** porque el cliente no pagó las percepciones.

Es el paso de detección del circuito de refacturación: primero se corre la query para saber cuáles son, después se le reclama a cada cliente, y solo si no paga se refactura.

***

## Correr la query

### 1 · Abrir la query desde el ícono de Querys

El ícono son las **moneditas amarillas**. Desde ahí ir a la carpeta **Ventas Online** y después a la query **PERCEP.PENDIENTES FAC A**.

<figure><img src="../../.gitbook/assets/image (216).png" alt="" width="563"><figcaption></figcaption></figure>

### 2 · Ingresar el filtro por fecha

La query pide un rango de fechas antes de mostrar los resultados.

<figure><img src="../../.gitbook/assets/image (217).png" alt="" width="326"><figcaption></figcaption></figure>

### 3 · Leer el listado

Abre el listado de todas las facturas con saldo en deuda, con **fecha, número de cliente, nombre, número de factura e importe**.

<figure><img src="../../.gitbook/assets/image (218).png" alt="" width="563"><figcaption></figcaption></figure>

***

## Exportar a Excel

### 4 · Exportar desde las flechitas

Arriba a la derecha están las **flechitas de exportación**. Conviene exportar siempre, para poder llevar el control de qué facturas ya se refacturaron y cuáles no.

<figure><img src="../../.gitbook/assets/image (219).png" alt="" width="563"><figcaption></figcaption></figure>

### 5 · Elegir ruta, nombre y formato

En la ventana que se abre hay que completar tres cosas:

* **La ruta** donde se guarda el archivo.
* **El nombre** del archivo, al final de la ruta.
* **El tipo de archivo**, que siempre es **XLSX**.

<figure><img src="../../.gitbook/assets/image (220).png" alt="" width="293"><figcaption></figcaption></figure>

> ⚠️ **Guardarlo siempre en el mismo lugar.** Si se guarda en el escritorio y después se arrastra a la carpeta compartida, tarde o temprano alguno queda solo en el escritorio de una máquina. Conviene **guardarlo directo en la carpeta compartida** y usar siempre el mismo criterio de nombre, por ejemplo `PERCEP_PENDIENTES_AAAA-MM-DD`. Así se puede ver la evolución y no se pisan entre sí.

### 6 · Aceptar

Se genera el Excel en la ruta elegida.

***

## Qué hacer con el listado

> ⚠️ **Refacturar no es el paso siguiente: es el último recurso.** Primero se le reclama al cliente que abone las percepciones.

### 7 · Reclamar el pago de las percepciones

Se contacta al cliente para que abone lo que quedó en deuda y **se le da un plazo** para hacerlo.

### 8 · Esperar el plazo y ver qué pasa

De ahí salen dos caminos:

* **El cliente paga:** la factura A queda como está. No se refactura nada.
* **No paga o se niega a pagar:** recién ahí se refactura como Factura B.

### 9 · Refacturar solo los casos que no se resolvieron

Seguir el instructivo de refacturación. La query dice **cuáles**; ese instructivo dice **cómo**.

👉 [Refacturar de Factura A a Factura B](refacturar-de-fac.a-a-fac.b.md)

***

> ⚠️ **Usar el Excel para seguir los plazos.** Como hay un plazo en el medio, el Excel exportado no es solo un listado: es la hoja de seguimiento. Conviene agregarle tres columnas a mano:
>
> * **Fecha de reclamo** — cuándo se le avisó al cliente.
> * **Vence el plazo** — hasta cuándo tiene para pagar.
> * **Estado** — pagó, refacturada, o pendiente de vencimiento.
>
> Sin esas columnas, de una corrida a la otra no se distingue una factura recién detectada de una que ya está reclamada y esperando el plazo. Y la factura va a seguir apareciendo en la query hasta que se pague o se refacture.
