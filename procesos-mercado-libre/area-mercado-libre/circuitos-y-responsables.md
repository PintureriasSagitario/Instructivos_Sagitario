---
description: >-
  Los cinco circuitos del área y quién responde por cada paso. El detalle de
  cómo se hace cada uno está en su propio instructivo.
---

# Circuitos y responsables:

💡 **Un solo responsable por paso.** Cuando una tarea la ejecutan dos personas según el día, uno de los dos responde por que esté hecha.

### 📍 Los depósitos

<table><thead><tr><th width="110">Depósito</th><th>Para qué se usa</th></tr></thead><tbody><tr><td><strong>28</strong></td><td>General — Hudson</td></tr><tr><td><strong>32</strong></td><td>Mercado Libre</td></tr><tr><td><strong>50</strong></td><td>Devoluciones en mal estado (usuario DEVOLUCI)</td></tr><tr><td><strong>332</strong></td><td>Full, dentro de la empresa 32</td></tr></tbody></table>

***

### 1 · Facturación y despacho

Desde que se factura la venta hasta que Mercado Libre retira los bultos de la colecta.

<table><thead><tr><th width="93">Paso</th><th>Qué se hace</th><th>Responsable</th></tr></thead><tbody><tr><td>1</td><td>Factura la venta (recibo, nota de venta, remito-factura)</td><td>Autómata</td></tr><tr><td>2</td><td>Imprime las etiquetas y el resumen de productos a preparar (listado de ventas)</td><td><strong>Andrea</strong></td></tr><tr><td>3</td><td>Prepara los pedidos y lleva los productos a escanear</td><td><strong>Depósito Hudson</strong></td></tr><tr><td>4</td><td>Transfiere del Dep 28 al Dep 32 lo escaneado, controlando contra el listado impreso</td><td><strong>Andrea</strong></td></tr><tr><td>5</td><td>Con el remito de transferencia, controla los bultos que se retiran de la colecta</td><td><strong>Nahuel Richard</strong></td></tr></tbody></table>

> ⚠️ **El doble control del paso 4 es lo que sostiene el circuito.** Lo escaneado tiene que coincidir con el listado impreso en el paso 2. Si no coincide, se detecta antes de transferir.

**No se recepciona en el Dep 32.** El circuito termina cuando Mercado Libre retira.

👉 [Transferencia de la empresa 28 a la 32](despacho-de-productos-ml.md)

***

### 2 · Devoluciones

Arranca en el depósito con la mercadería física y termina con la recepción en el sistema. Participan tres personas.

<table><thead><tr><th width="97">Paso</th><th width="253">Qué se hace</th><th>Responsable</th></tr></thead><tbody><tr><td>1</td><td>Escanea las etiquetas de los productos de devoluciones y genera un Excel sheet donde detalla cuales son las ventas.</td><td><strong>Francisco Pena</strong></td></tr><tr><td>2</td><td>Genera la devolución (NC), elimina el recibo del autómata y completan el Excel sheet con el n° de devolucion de Presea.</td><td><em>a asignar</em></td></tr><tr><td>3</td><td>Verifica el estado de los productos y transfiere al Dep 28 o al Dep 50 - e informa a Natialia Riado.</td><td><strong>Nahuel Richard</strong></td></tr><tr><td>4</td><td>Recepciona en el depósito donde transfirió Nahuel, el 28 o el 50</td><td><strong>Natalia Riado</strong></td></tr></tbody></table>

**La bifurcación:** buen estado → Dep 28 · mal estado → Dep 50 con usuario DEVOLUCI. Se decide en el depósito, no en el sistema.

> ⚠️ **Completar el Excel Sheet** tanto por Francisco y los vendedores, es lo que permite llevar un control, de las NC ya realizadas y las que aun estan pendientes.\
> \
> ⚠️ **El aviso del paso 3 es importante.** Natalia no pueden avanzar hasta que Nahuel informe lo recibido, así que ese mensaje es parte del circuito.

👉 [Devoluciones y notas de crédito](devolucion-nota-de-credito.md)

***

### 3 · Refacturar de Factura A a Factura B

Para los casos en que el cliente se niega a pagar las percepciones.

<table><thead><tr><th width="103">Paso</th><th>Qué se hace</th><th>Responsable</th></tr></thead><tbody><tr><td>1</td><td>Correr la query de percepciones pendientes y exportar el listado. Actualizar Excel Sheet</td><td><strong>Cristian,Fernanda y Carmen</strong></td></tr><tr><td>2</td><td>Reclamarle al cliente que abone, con un plazo</td><td><strong>Cristian,Fernanda y Carmen</strong></td></tr><tr><td>3</td><td>Si no paga o se niega, refacturar como Factura B</td><td><strong>Cristian,Fernanda y Carmen</strong></td></tr><tr><td>4</td><td>Anotar en Excel Sheet, Fecha de reclamo, quien lo reclamo y si fue abonado o refacturado.</td><td><strong>Cristian,Fernanda y Carmen</strong></td></tr></tbody></table>

> ⚠️ **Refacturar es el último recurso, no el paso siguiente.** Primero se le reclama al cliente. Si paga, la factura A queda como está.\
> \
> ⚠️ **Completar el Excel Sheet**, es lo que permite llevar un control, de los reclamos ya realizados, la refacturación o si el cliente ya abono.

**Cambio de fondo:** a partir de la implementación de este circuito, **las ventas del día se facturan en el día**. Ya no se factura al día siguiente.

👉 [Query de percepciones pendientes ](query-de-percepciones-pendientes.md)· [Refacturar de Factura A a Factura B](refacturar-de-fac.a-a-fac.b.md)

***

### 4 · Cancelaciones antes del despacho

La venta se cancela y la mercadería todavía no salió de Hudson. La devolución se hace siempre; lo único que cambia es si hay que transferir la mercadería de vuelta al Dep 28.

<table><thead><tr><th width="104">Paso</th><th width="280">Qué se hace</th><th>Responsable</th></tr></thead><tbody><tr><td>1</td><td>El recibo y el remito-factura se generan automáticamente</td><td>Autómata</td></tr><tr><td>2</td><td>Hace la devolución en Presea</td><td><em>a asignar</em></td></tr><tr><td>3</td><td>Si ya se había transferido del 28 al 32, transfiere del 32 al 28</td><td><em>a asignar</em></td></tr></tbody></table>

> ⚠️ **Si no se había hecho la transferencia de ida, no hay nada más que hacer.** Transferir del 32 al 28 sin que se hubiera hecho la ida genera una diferencia de stock en los dos depósitos. Averiguar con Deposito el estado de esta venta.

👉 [Está al final de Devoluciones y notas de crédito](devolucion-nota-de-credito.md)

***

***

### 5 · Despachos desde otras sucursales

Cuando una venta de Mercado Libre se despacha desde una sucursal en lugar del depósito de Hudson.

| Paso | Qué se hace                                              | Responsable        |
| ---- | -------------------------------------------------------- | ------------------ |
| 1    | La sucursal entrega la mercadería y transfiere al Dep 32 | **Sucursal**       |
| 2    | Se recepciona la transferencia en el Dep 32              | **Cristian Ortiz** |

> ⚠️ **Esta es la excepción al "no se recepciona en el Dep 32".** Lo que transfiere Andrea desde el 28 en el despacho diario **no** se recepciona. Lo que llega transferido desde otra sucursal, **sí.**

👉 [Recepción en el Depósito 32](recepcion-de-deposito-32.md)

***

### 6 · Circuito Full

La mercadería que Mercado Libre retira para Full pasa al Depósito 332 y después se verifica que haya ingresado.

<table><thead><tr><th width="81">Paso</th><th>Qué se hace</th><th>Responsable</th></tr></thead><tbody><tr><td>1</td><td>Transfiere del Dep 28 al Dep 332 lo que ML retiró para Full, y avisa a Francisco por mail con la transferencia adjunta</td><td><strong>Andrea</strong></td></tr><tr><td>2</td><td>Corrobora en Mercado Libre Full que los productos figuren bien</td><td><strong>Francisco Peña</strong></td></tr><tr><td>3</td><td>Gestiona el regreso al Dep 28 de lo que no está apto para la venta, y desde ahí se clasifica al depósito de devolución si corresponde</td><td><strong>Francisco Peña</strong></td></tr></tbody></table>

**La facturación de las ventas Full** —nota de venta, recibo y remito-factura— la genera el **autómata**, igual que en el circuito de facturación.

> 💡 **El mail con la transferencia adjunta** es lo que le permite a Francisco controlar contra algo. Sin ese adjunto, el paso 2 no se puede hacer.

👉 [Transferencia al Depósito Full · Verificación del ingreso a Full](transferencia-deposito-full.md)

***

### RESPONSABLES A DEFINIR:

### 1. 📞 Consultas y reclamos de clientes

Cobertura por horario, a asignar en cada canal.

| Canal                                 | Mañana      | Tarde       |
| ------------------------------------- | ----------- | ----------- |
| Real Trends                           | _a asignar_ | _a asignar_ |
| Mercado Libre                         | _a asignar_ | _a asignar_ |
| Redes sociales (Instagram y Facebook) | _a asignar_ | _a asignar_ |
| Página web                            | _a asignar_ | _a asignar_ |
| WhatsApp de reclamos                  | _a asignar_ | _a asignar_ |

Una misma persona puede cubrir más de un canal.

***

### 2. 🔎 Control diario de Facturación

[**Verificar todos los días que el autómata haya facturado correctamente.** ](control-de-nv-pendientes-de-facturar..md)

💡 **Controlar que no queden notas de venta pendientes, de facturar o de despachar.**

Responsable: _a asginar_

***

### 3. Devoluciones

Genera la devolución (NC), elimina el recibo del autómata y completan el Excel sheet con el n° de devolucion de Presea.\
\
Responsable: _a asignar_

***

### 4. Refacturar de A a B

Para los casos en que el cliente se niega a pagar las percepciones.\
\
Responsable: _a asignar_

***

### 5. Cuentas Corrientes empresa 32:

Verificar que no quede saldo a favor ni en deuda de los clientes de ML.\
\
_&#x52;esponsable: a asignar_
