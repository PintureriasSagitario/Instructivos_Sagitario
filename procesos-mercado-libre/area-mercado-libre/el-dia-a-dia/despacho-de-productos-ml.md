---
description: >-
  Transferencia de la empresa 28 a la empresa 32. Despacho de las ventas de
  Mercado Libre.
---

# Despacho de Productos ML

***

#### ¿Para qué sirve?

Pasa al **depósito 32** la mercadería de las ventas de Mercado Libre que se van a despachar, para que quede separada del stock general del depósito 28.

Los productos se cargan **escaneando el código de barras**, uno por uno, directamente sobre la grilla de la transferencia. No hay carga manual ni planilla intermedia.

***

## Antes de la transferencia

### 1 · Bajar de Mercado Libre el listado de ventas y las etiquetas

Se descargan desde Mercado Libre y **se imprimen**.

> 💡 **El listado impreso no es solo para el depósito:** es el papel contra el que se controla la transferencia en el paso 5. Sin él no se puede verificar que se haya escaneado lo correcto.

### 2 · El depósito prepara los pedidos

Con las etiquetas y el listado, el depósito arma los pedidos y **lleva los productos al puesto de escaneo**.

***

## La transferencia en Presea

### 3 · Entrar a la pantalla de transferencia

Ir a **Productos → Depósitos → Transf. entre empresas**.

<figure><img src="../../../.gitbook/assets/image (210).png" alt=""><figcaption></figcaption></figure>

### 4 · Escanear los productos por código de barras

Se escanea cada producto directamente sobre la grilla. **Cada pistoleo carga un renglón**: el escaneo es la carga de la transferencia, no un paso previo.

<figure><img src="../../../.gitbook/assets/image (211).png" alt="" width="563"><figcaption></figcaption></figure>

### 5 · Controlar la grilla contra el listado impreso

**Antes de grabar**, comparar lo que quedó cargado en la grilla con el listado de ventas del paso 1. Tienen que coincidir los productos y las cantidades.

**Es el único momento del circuito en que un error se detecta antes de que la mercadería salga.**

> ⚠️ **Si la grilla no coincide con el listado**
>
> * **Falta un producto:** no está preparado o no se escaneó. Verificar con el depósito antes de seguir.
> * **Sobra un producto:** se escaneó algo que no corresponde a estas ventas. Quitar el renglón de la grilla.
> * **La cantidad no coincide:** se pistoleó dos veces el mismo producto, o falta una unidad. Corregir la cantidad en la grilla.
>
> **No grabar la transferencia hasta que coincida.** Una vez grabada, corregirla implica una transferencia nueva en sentido contrario.

### 6 · Dar ESC para cerrar la carga

Una vez que están todos los productos cargados y controlados, dar **ESC**.

### 7 · Empresa y depósito de entrada

Va a preguntar **EMPRESA DEPÓSITO DE ENTRADA**: va la **32**. Y después el **PASSWORD DEPÓSITO DE ENTRADA**, que también es **32**.

<figure><img src="../../../.gitbook/assets/image (212).png" alt=""><figcaption></figcaption></figure>

> 💡 El password va enmascarado con asteriscos, pero **al lado el sistema muestra el nombre del depósito**. Leerlo antes de confirmar: si no dice el depósito de Mercado Libre, el password está mal.

### 8 · Observaciones

Al dar **ESC** pide una observación. Conviene poner un **dato identificatorio** de la tanda —por ejemplo la fecha y el turno— para poder encontrar esta transferencia después.

### 9 · Confirmar la transferencia

Confirmar y listo.

***

## Después de la transferencia

### 10 · Entregar el remito de transferencia al depósito

Con ese remito, **Nahuel Richard** controla los bultos que Mercado Libre viene a retirar de la colecta. Es el último control del circuito de facturación.

> ℹ️ **No se recepciona en el Depósito 32.** La transferencia no requiere recepción del otro lado. El circuito de facturación termina cuando Mercado Libre retira la mercadería.

***

> ⚠️ **No confundir con la transferencia a Full.** Las dos salen del 28 y usan la misma pantalla, pero el destino lo define el password: **32** para el despacho diario, **332** para Full. Ver Transferencia al Depósito Full.
