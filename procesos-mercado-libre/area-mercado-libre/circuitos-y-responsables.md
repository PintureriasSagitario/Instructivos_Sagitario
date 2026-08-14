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

👉 Transferencia de la empresa 28 a la 32

***

### 2 · Devoluciones

Arranca en el depósito con la mercadería física y termina con la recepción en el sistema. Participan tres personas.

<table><thead><tr><th width="97">Paso</th><th>Qué se hace</th><th>Responsable</th></tr></thead><tbody><tr><td>1</td><td>Recibe la devolución con las etiquetas de venta, verifica el estado y transfiere al Dep 28 o al Dep 50</td><td><strong>Nahuel Richard</strong></td></tr><tr><td>2</td><td>Fotografía las etiquetas ya clasificadas e informa lo recibido por un grupo de wspp y a Natalia.</td><td><strong>Nahuel Richard</strong></td></tr><tr><td>3</td><td>Genera la devolución (NC) y elimina el recibo del autómata</td><td><strong>Cristian,Fernanda y Carmen</strong></td></tr><tr><td>4</td><td>Recepciona en el depósito donde transfirió Nahuel, el 28 o el 50</td><td><strong>Natalia Riado</strong></td></tr></tbody></table>

**La bifurcación:** buen estado → Dep 28 · mal estado → Dep 50 con usuario DEVOLUCI. Se decide en el depósito, no en el sistema.

> ⚠️ **El aviso del paso 2 es el disparador.** Francisco y Natalia no pueden avanzar hasta que Nahuel informe lo recibido, así que ese mensaje es parte del circuito y no una cortesía.

👉 Devoluciones y notas de crédito

***

### 3 · Circuito Full

La mercadería que Mercado Libre retira para Full pasa al Depósito 332 y después se verifica que haya ingresado.

<table><thead><tr><th width="81">Paso</th><th>Qué se hace</th><th>Responsable</th></tr></thead><tbody><tr><td>1</td><td>Transfiere del Dep 28 al Dep 332 lo que ML retiró para Full, y avisa a Francisco por mail con la transferencia adjunta</td><td><strong>Andrea</strong></td></tr><tr><td>2</td><td>Corrobora en Mercado Libre Full que los productos figuren bien</td><td><strong>Francisco Peña</strong></td></tr><tr><td>3</td><td>Gestiona el regreso al Dep 28 de lo que no está apto para la venta, y desde ahí se clasifica al depósito de devolución si corresponde</td><td><strong>Francisco Peña</strong></td></tr></tbody></table>

**La facturación de las ventas Full** —nota de venta, recibo y remito-factura— la genera el **autómata**, igual que en el circuito de facturación.

> 💡 **El mail con la transferencia adjunta** es lo que le permite a Francisco controlar contra algo. Sin ese adjunto, el paso 2 no se puede hacer.

👉 Transferencia al Depósito Full · Verificación del ingreso a Full

***

### 4 · Refacturar de Factura A a Factura B

Para los casos en que el cliente se niega a pagar las percepciones.

<table><thead><tr><th width="103">Paso</th><th>Qué se hace</th><th>Responsable</th></tr></thead><tbody><tr><td>1</td><td>Correr la query de percepciones pendientes y exportar el listado</td><td><em>a asignar</em></td></tr><tr><td>2</td><td>Reclamarle al cliente que abone, con un plazo</td><td><em>a asignar</em></td></tr><tr><td>3</td><td>Si no paga o se niega, refacturar como Factura B</td><td><em>a asignar</em></td></tr></tbody></table>

> ⚠️ **Refacturar es el último recurso, no el paso siguiente.** Primero se le reclama al cliente. Si paga, la factura A queda como está.

**Cambio de fondo:** a partir de la implementación de este circuito, **las ventas del día se facturan en el día**. Ya no se factura al día siguiente.

👉 Query de percepciones pendientes · Refacturar de Factura A a Factura B

***

### 5 · Cancelaciones antes del despacho

La venta se cancela y la mercadería todavía no salió de Hudson. La devolución se hace siempre; lo único que cambia es si hay que transferir la mercadería de vuelta al Dep 28.

<table><thead><tr><th width="104">Paso</th><th width="280">Qué se hace</th><th>Responsable</th></tr></thead><tbody><tr><td>1</td><td>El recibo y el remito-factura se generan automáticamente</td><td>Autómata</td></tr><tr><td>2</td><td>Hace la devolución en Presea</td><td><em>a asignar</em></td></tr><tr><td>3</td><td>Si ya se había transferido del 28 al 32, transfiere del 32 al 28</td><td><em>a asignar</em></td></tr></tbody></table>

> ⚠️ **Si no se había hecho la transferencia de ida, no hay nada más que hacer.** Transferir del 32 al 28 sin que se hubiera hecho la ida genera una diferencia de stock en los dos depósitos.

👉 Está al final de Devoluciones y notas de crédito

***

### 📞 Consultas y reclamos de clientes

Cobertura por horario, a asignar en cada canal.

| Canal                                 | Mañana      | Tarde       |
| ------------------------------------- | ----------- | ----------- |
| Real Trends                           | _a asignar_ | _a asignar_ |
| Mercado Libre                         | _a asignar_ | _a asignar_ |
| Redes sociales (Instagram y Facebook) | _a asignar_ | _a asignar_ |
| Página web                            | _a asignar_ | _a asignar_ |
| WhatsApp de reclamos                  | _a asignar_ | _a asignar_ |

Una misma persona puede cubrir más de un canal, pero cada casillero necesita un nombre.

***

### 🔎 Control diario

**Verificar todos los días que el autómata haya facturado correctamente.** Responsable _a asignar_.
