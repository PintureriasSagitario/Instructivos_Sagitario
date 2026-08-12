---
description: >-
  Nota de crédito sin movimiento de stock, cambio del cliente a Consumidor Final
  y emisión de la Factura B.
---

# Refacturar de Factura A a Factura B:

### ¿Para qué sirve?

Se usa cuando una venta **se facturó como Factura A y tiene que ser Factura B**.

Anula la facturación **sin mover el stock**, porque el producto ya fue entregado y lo único que hay que corregir es el tipo de comprobante. La mercadería no vuelve al depósito.

**Antes de empezar, tener a mano:** el número de la factura A a anular · el número de cliente ·

El circuito tiene tres fases y hay que hacerlas en orden. **Si se saltea la Fase 2, la factura nueva vuelve a salir como A.**

***

## Fase 1 · Hacer la nota de crédito

_Anula la factura A sin devolver la mercadería al stock._

### 1 · Ventas → Comprobantes → Notas créd. x art. s/stock

`[IMAGEN: 01-menu-notas-cred-sin-stock.png]`

> ⚠️ **Es esta opción y no otra.** Tiene que ser **Notas créd. x art. s/stock**. El "s/stock" significa _sin stock_, y es lo que hace que la mercadería no vuelva al depósito. Si se usa "Notas créd x nro. Factura", el stock se mueve y el producto que ya está en manos del cliente vuelve a figurar como disponible.

### 2 · Selección de Sucursal / Talonario

Ingresar el número de talonario del punto de venta. En el ejemplo, **1101**.

`[IMAGEN: 02-seleccion-sucursal-talonario.png]`

El número tiene que estar habilitado en la tabla de numeración.

### 3 · Cargar el número de vendedor

En el campo **Actualiza Nota de venta** poner **N**.

`[IMAGEN: 03-vendedor-actualiza-nota-venta.png]`

### 4 · Traer la factura con CTRL + B

Se abre la ventana de productos. Con **CTRL + B** se abre la lista de facturas para elegir.

`[IMAGEN: 04-ventana-elegir-factura.png]`

### 5 · Enter sobre la factura y después ESC

Los productos quedan volcados en la nota de crédito.

`[IMAGEN: 05-productos-volcados.png]`

### 6 · ESC de nuevo: se abre el cuadro de observaciones

**Aclarar acá que se cambia a factura B.**

`[IMAGEN: 06-observaciones.png]`

### 7 · ESC y confirmar la nota de crédito

Va a aparecer el cuadro **Confirmación de percepciones a calcular**.

`[IMAGEN: 07-confirmacion-percepciones.png]`

> ⚠️ **Siempre devolver las percepciones.** Hay que apretar el **tilde verde**. Si no se devuelven, el cliente queda con una percepción que ya no corresponde a ningún comprobante.

***

## Fase 2 · Pasar el cliente a Consumidor Final

_Sin este paso el sistema va a seguir emitiendo Factura A._

### 8 · Ventas → Clientes → Modificaciones → Datos Básica

`[IMAGEN: 08-menu-clientes-datos-basica.png]`

### 9 · Filtrar por número de cliente y modificar tres campos

| Campo       | Valor nuevo            |                       |
| ----------- | ---------------------- | --------------------- |
| `Tipo_Resp` | **5.0 Cons. Final**    |                       |
| `Tipo_Doc`  | **99 Sin identificar** |                       |
| `CUIT`      | **vacío**              | se borra el contenido |

Así tiene que quedar:

`[IMAGEN: 09-cliente-como-queda.png]`

> ⚠️ **Este cambio es permanente.** Modifica los datos fiscales del cliente en el sistema, no solo esta venta. A partir de acá, todo lo que se le facture a ese cliente va a salir como B. Antes de hacerlo hay que estar seguro de que corresponde.

***

## Fase 3 · Emitir la factura B

_Se refactura la misma nota de venta._

### 10 · Ventas → Comprobantes → Facturas

Seleccionar el punto de venta y cargar el número de cliente y el de vendedor.

`[IMAGEN: 10-menu-comprobantes-facturas.png]`

**Antes de seguir, verificar que arriba ya diga FACTURA B.**

`[IMAGEN: 11-verificar-que-diga-factura-b.png]`

> ⚠️ **Si todavía dice FACTURA A** es porque el cambio de la Fase 2 no quedó guardado. Volver a Clientes y revisar los tres campos antes de continuar, o la factura va a salir mal de nuevo.

### 11 · En la ventana de productos, CTRL + N

Enter sobre la nota de venta que se va a refacturar.

`[IMAGEN: 12-ctrl-n-elegir-nota-de-venta.png]`

> 💡 **Si no sabés cuál es la nota de venta.** En la historia del cliente, pararse sobre la nota de crédito que se acaba de hacer y apretar **F9**. Se abre una ventana con toda la información: casi al final, del lado derecho, aparece el campo **NOTA\_VENTA** con el número.

`[IMAGEN: 13-f9-buscar-nota-de-venta.png]`

### 12 · Una vez volcada, ESC para grabar la factura

`[IMAGEN: 14-factura-b-grabada.png]`

***

## Verificación final

En la historia del cliente tienen que quedar **los tres comprobantes**:

* La factura A original
* La nota de crédito que la anula
* La factura B nueva

Si falta alguno de los tres, el circuito quedó a medias.

`[IMAGEN: 15-historia-del-cliente.png]`
