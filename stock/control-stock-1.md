---
description: Este instructivo explica cómo realizar los controles de stock por sucursal.
---

# Copy of Control de Stock

Descargar el Excel con todos los productos de cada proveedor facilita el control: en lugar de copiar los códigos a mano y calcular las diferencias entre lo físico y lo que figura en sistema, solo hay que completar el Excel con la **cantidad real física** que tenemos en la sucursal.



**Ruta**: `Productos → Depósitos → Stock xArt. y deposito`

{% hint style="danger" %}
IMPORTANTE: Desde este listado no nos trae los productos que estan en 0, solo los que al menos tenemos 1 y los que figuran en negativo.
{% endhint %}

<figure><img src="../.gitbook/assets/image (153).png" alt=""><figcaption></figcaption></figure>

2. Nos abre la ventana de filtros donde tenemos 2 opciones:

* **Filtrar por proveedor:** tildá el campo **Prov. de Stock** y con **F6** buscá por nombre de proveedor. Sirve para controlar una sola fábrica en particular.
* **Dejarlo vacío (sin tildar):** trae **todos** los productos de la sucursal. Esta opción sirve para controlar los negativos.

<figure><img src="../.gitbook/assets/image (154).png" alt="" width="380"><figcaption></figcaption></figure>

3. Nos abre una pantalla con todos los productos que tenemos stock positivo y negativo (En este listado no salen los productos con cantidad 0).

![image.png](../.gitbook/assets/Control_de_Stock__image_2.png)

4. En el caso que querramos descargar/ver solo los negativos. podemos ordenarlo por cantidad. Le damos click a "Cantidad", y nos abre la siguiente ventana - Desmarcamos el campo "Agrupar" y le damos Aceptar.

![image.png](../.gitbook/assets/Control_de_Stock__image_3.png)

5. Revisar los negativos:\
   Ahora que están ordenados por cantidad, yendo hacia arriba de todo podemos ver los productos en negativo y controlarlos.
6. Para descargarlo en un Excel vamos a ir a esas tres moneditas con la flecha azul y volcamos el archivo.

![image.png](../.gitbook/assets/Control_de_Stock__image_4.png)

7. Para guardarlo seleccionamos formato Excel, en el icono de la carpeta elegimos en donde guardarlo y hay que ponerle nombre sí o sí. Si no el archivo no se va a guardar.

![image.png](../.gitbook/assets/Control_de_Stock__image_5.png)

8. Abrimos el archivo que descargamos que va a aparecer con este formato

![image.png](../.gitbook/assets/Control_de_Stock__image_6.png)

### Importar archivo de Stock arreglado:

📌Para poder subir el archivo con las cantidades reales, tienen que quedar en este orden. Código – Detalle – Deposito - Cantidad

<figure><img src="../.gitbook/assets/image (99).png" alt=""><figcaption></figcaption></figure>

1. Para cargar este archivo hay que ir a presea y desde Productos – Stock – Control de Stock.

Con Enter avanzamos y cuando llegamos a la parte del listado tenemos dos opciones. Cargar el archivo con las cantidades modificadas o buscar el producto y cargarlos manualmente. En el caso de que se tenga que subir un archivo, cuando llegamos a la parte de la lista apretamos “Ctrl + B” Nos tiene que aparecer un recuadro y con el icono de la carpeta, buscamos el archivo. En tipo de archivo va: “XLSX” y nombre de la hoja “Hoja1” y después lo importamos.

![image.png](../.gitbook/assets/Control_de_Stock__image_8.png)

![image.png](../.gitbook/assets/Control_de_Stock__image_9.png)

2. Confirmamos vuelco y con Escape confirmamos el control de stock.

✅ Este control se va a guardar en la cola de impresión, hay que descargarlo y pasarlo a administración para poder hacer los ajustes.
