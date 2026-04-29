# 📌 Cancelación de NDV (Guía completa)

Usá el siguiente asistente para saber exactamente qué pasos seguir según el estado de la nota de venta:

{% embed url="https://pintureriassagitario.github.io/Instructivos_Sagitario/widget-cancelacion-ndv.html" %}

***

## Instructivos detallados por caso

***

### 1️⃣ Bajas — Cancelación total (No facturada / No despachada)

Este ítem lo usamos cuando necesitamos eliminar una nota de venta para que no quede pendiente ni de facturar ni de despachar.

**Ruta:** `Ventas → Pedidos → Bajas`

**Pasos:**

1. Ir a Ventas - Pedidos - Bajas
2. Se abre un cuadro para filtrar. Se puede filtrar por **cliente**, número de nota de venta o fecha.
3. Nos trae todas las NDV. Nos paramos sobre la que queremos anular y tocamos el botón de arriba a la derecha.
4. Le damos **ESCAPE** y ya queda eliminada la nota de venta. ✅

***

### 2️⃣ Modificación NDV — Cancelación de algunos productos

Las notas de venta confirmadas se pueden modificar: descuentos, productos, dirección o cantidades.

**Ruta:** `Ventas → Pedidos → Modificaciones`

**Pasos:**

1. Ir a Ventas - Pedidos - Modificaciones.
2. Buscamos el cliente y seleccionamos la nota de venta que queremos modificar.
3. Nos deja modificar las condiciones de venta y descuentos. También podemos **agregar o eliminar productos**.
4. Podemos agregar una observación y luego confirmamos la modificación.

> 📌 La nota de venta modificada queda guardada en la cola de impresión.

✅ Ya queda guardada la NDV con las modificaciones y podemos levantar la factura y el recibo correspondiente.

***

### 3️⃣ Nota de Crédito x Nro de Factura — Facturada sin despachar (Sin Remito)

Se usa cuando hicimos la factura pero **NO** se despachó. No mueve el stock.

**Ruta:** `Ventas → Comprobantes → Notas de Crédito x nro. Factura`

**Pasos:**

1. Ir a Ventas - Comprobantes - Notas de Crédito x nro. Factura.
2. Poner el número de factura o con **F6** buscar al cliente y seleccionar la factura.
3. Una vez seleccionada la factura, el sistema pregunta **"¿Actualiza nota de venta?"** → poner **S**
4. Se abren todos los productos y cantidades facturados. Si solo necesitamos devolver algunos productos, los que **NO** vamos a anular los ponemos en **0**.
5. Con ESCAPE confirmamos la nota de crédito.

> ⚠️ Nos va a salir un cuadro importante:
>
> * **✅ Tilde Verde:** Nota de crédito TOTAL de facturas A
> * **❌ Cruz Roja:** Siempre que sean facturas B y nota de crédito PARCIAL de facturas A

✅ Queda grabada la nota de crédito en la historia del cliente.

> 💡 Si se cancela la NDV en su **totalidad** → ir a **Bajas**. Si se cancelan **algunos productos** → ir a **Modificación NDV**.

***

### 4️⃣ Devolución — Facturada y despachada (Con Remito)

Se usa cuando la factura fue emitida desde una nota de venta y **SÍ** se despachó. Genera una nota de crédito y devuelve los productos al stock.

**Ruta:** `Ventas → Comprobantes → Devoluciones`

> ⚠️ **La devolución SIEMPRE debe hacerse en la sucursal donde el cliente compró.**

**Pasos:**

1. Ir a Ventas - Comprobantes - Devoluciones.
2. Seleccionamos el cliente. Se abre un cuadro pidiendo la **lista de precios** con la que se hizo la NDV. Ver las columnas desde/hasta para identificar la correcta.
3. Completamos la información y en **"Actualiza nota de venta"** ponemos **N**.
4.  Se abre la ventana de productos. Tocar **CTRL + B** para traer las facturas del cliente.

    > ⚠️ Es muy importante que NO carguemos los productos manualmente.
5. Al dar ESCAPE, el sistema pide que **asociemos la nota de crédito con una factura**. Este paso es obligatorio, sino no graba la NC.
6. Confirmamos. Nos sale el cuadro:
   * **✅ Tilde Verde:** Nota de crédito TOTAL de facturas A
   * **❌ Cruz Roja:** Facturas B o nota de crédito PARCIAL de facturas A

✅ Queda la Devolución en la historia del cliente.

***

### 5️⃣ Ticket de cambio — El cliente quiere cambiar de producto

Se usa cuando el cliente quiere cambiar el producto por otro. Se hace un Ticket poniendo en **negativo** lo que devuelve y en **positivo** lo que se lleva.

**Ruta:** `Ventas → Comprobantes → Tickets`

> ⚠️ **El producto nuevo que se lleva debe ser de IGUAL o MAYOR valor que el devuelto.** El cambio se puede hacer en **cualquier sucursal**.

**Pasos:**

1. Ir a Ventas - Comprobantes - Tickets.
2. Ingresar el código del cliente o buscarlo con **F6** por nombre.
3. Ingresar el número de vendedor y confirmar con ENTER.
4. En la pantalla de productos:
   * Cargar el **producto que DEVUELVE** con cantidad en **NEGATIVO** (ej: -1)
   * Cargar el **producto NUEVO** que se lleva con cantidad en **POSITIVO** (ej: 1)
5. Con **ESCAPE** ir a la solapa **VALORES** para registrar el medio de pago por la diferencia.
6. Confirmar con ESCAPE. ✅

**Ejemplo:**

> Un cliente devuelve RECUBLOCK 3EN1 01 L (1 unidad) y lleva AGORESTE ACCENT 8E (1 unidad) de mayor valor. En el Ticket se carga:
>
> * RECUBLOCK 3EN1 01 L → cantidad: **-1** (negativo)
> * AGORESTE ACCENT 8E → cantidad: **1** (positivo)
> * El cliente abona la diferencia por el medio de pago que corresponda.

***

> 💡 **¿No sabés en qué estado está la nota de venta?** Consultá la **Trazabilidad NDV** desde el ícono superior de Presea → Notas de Venta → Trazabilidad. Filtrá por fecha, cliente y número de NDV.
