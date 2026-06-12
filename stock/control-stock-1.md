---
description: >-
  Este instructivo explica cómo realizar los controles de stock de los productos
  que nos figuran en stock negativo.
---

# Control de Stock - Productos en negativo

Este control sirve para detectar productos en **stock negativo** (cantidad menor a cero en sistema). Traemos **todos los productos de la sucursal** y los ordenamos por cantidad para ver primero los que están en negativo y poder corregirlos.

### Parte 1 — Descargar el Excel de stock

**Ruta**: `Productos → Depósitos → Stock xArt. y deposito`

{% hint style="danger" %}
IMPORTANTE: Desde este listado no nos trae los productos que estan en 0, solo los que al menos tenemos 1 y los que figuran en negativo.
{% endhint %}

<figure><img src="../.gitbook/assets/image (153).png" alt=""><figcaption></figcaption></figure>

2. Nos abre la ventana de filtros: Lo dejamos con los filtros que tienen y le damos aceptar.

<figure><img src="../.gitbook/assets/image (165).png" alt="" width="385"><figcaption></figcaption></figure>

2. Nos abre una pantalla con todos los productos que tenemos en stock.

![image.png](../.gitbook/assets/Control_de_Stock__image_2.png)

3. Para controlar los negativos necesitamos filtrar por los menores a 0, apretamos el icono del Filtro <img src="../.gitbook/assets/image (169).png" alt="" data-size="original"> y nos abre una ventana con lo que necesitamos filtrar:\
   1\. Seleccionar el campo cantidad y damos enter:

<figure><img src="../.gitbook/assets/image (176).png" alt="" width="421"><figcaption></figcaption></figure>

3. Selecicionamos donde dice "MENOR (<)" y le damos enter:

<figure><img src="../.gitbook/assets/image (177).png" alt="" width="427"><figcaption></figcaption></figure>

3. Abajo en el campo filtro lo unico que ponemos es "0" y le damos enter.

<figure><img src="../.gitbook/assets/image (175).png" alt="" width="422"><figcaption></figcaption></figure>

4. Nos pregunta ¿Desea agregar otra condicion? le ponemos NO.
5. Ahora solo en pantalla nos aparecen los productos que son menores a 0, osea que estan en negativo.

<figure><img src="../.gitbook/assets/image (168).png" alt="" width="563"><figcaption></figcaption></figure>

***

<h4 align="center"><strong>Descargar Productos a un Excel</strong></h4>

1. Para descargarlo, hacé clic en las **tres moneditas con la flecha azul** ![](<../.gitbook/assets/image (161).png>) y volcá el archivo.

<figure><img src="../.gitbook/assets/image (178).png" alt="" width="563"><figcaption></figcaption></figure>

Guardar como excel: Seleccioná formato **Excel**, elegí la carpeta donde guardarlo con el ícono de carpeta y ponele un **nombre obligatoriamente** (si no, el archivo no se guarda).

![image.png](../.gitbook/assets/Control_de_Stock__image_5.png)

3. Abrir el archivo descargado:El archivo descargado aparece con este formato:

<figure><img src="../.gitbook/assets/image (179).png" alt="" width="563"><figcaption></figcaption></figure>

{% hint style="warning" %}
El excel se descarga tal cual lo vimos en sistema.\
En el caso de que este mismo archivo lo quieran subir al sistema se tiene que modificar la columna cantidad, con la cantidad REAL que tenemos en la sucursal.
{% endhint %}

***

### Parte 2 — Importar el archivo de stock corregido

📌IMPORTANTE: **Importante:** para poder subir el archivo con las cantidades reales, las columnas tienen que quedar en este orden: **Código – Detalle – Depósito – Cantidad** _(LA CANTIDAD REAL QUE TENGO EN LA SUCU)_

<figure><img src="../.gitbook/assets/image (99).png" alt=""><figcaption></figcaption></figure>

1\. Ingresar al control de stock:\
En Presea, ir a **Productos → Stock → Control de Stock**.

<figure><img src="../.gitbook/assets/image (157).png" alt=""><figcaption></figcaption></figure>

2. Las 2 primeras leyendas aceptamos con enter y avanzamos.

<figure><img src="../.gitbook/assets/image (159).png" alt="" width="511"><figcaption></figcaption></figure>

3. En la parte de productos es que podemos importar el excel que ya completamos con las cantidades reales anteriormente.&#x20;
4. Subir el excel: Apretamos “Ctrl + B” y nos abre un recuadro. Seleccionamos el  icono de la carpeta, y buscamos el archivo. \
   En tipo de archivo va: “XLSX” y tildamos donde dice "La primera fila es cabezera" \
   Importar.

<figure><img src="../.gitbook/assets/image (162).png" alt=""><figcaption></figcaption></figure>

5.  Si necesitamos cargar un producto que no figuraba en el listado, lo hacemos manualmente:\
    CODIGO: Lo podemos ingresar manualmente o buscarlo con F6.\
    DEPOSITO: El número de mi sucursal tambien se puede buscar con F6.\
    CANTIDAD: La cantidad real que tengo en sistema<br>

    <figure><img src="../.gitbook/assets/image (163).png" alt="" width="509"><figcaption></figcaption></figure>



6. Con Escape confirmamos el control de stock.

<figure><img src="../.gitbook/assets/image (164).png" alt="" width="231"><figcaption></figcaption></figure>

✅ Este control se va a guardar en la cola de impresión, hay que descargarlo y pasarlo a Caro y/o Ale de Pedidos para poder hacer los ajustes.

{% hint style="warning" %}
Apenas terminamos de generar el control de Stock pasarlo en el momento, para que si vendemos algo en el transcurso, no se modifiquen las cantidades.
{% endhint %}

7. **Una vez que nos dan el ok de que se concilio el control de stock, chequear al menos 3 productos para ver si se arreglo como solicitamos!!**
