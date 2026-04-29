# Cancelación de Nota de Venta

Usá el siguiente asistente para saber exactamente qué pasos seguir según el estado de la nota de venta:

<div>
<style>
.wiz * { box-sizing: border-box; }
.wiz { padding: 1.25rem; font-family: sans-serif; }
.wiz .bc { display:flex; gap:6px; align-items:center; margin-bottom:1.25rem; flex-wrap:wrap; }
.wiz .bc-item { font-size:12px; color:#666; padding:3px 10px; border-radius:12px; background:#f0f0f0; }
.wiz .bc-sep { color:#aaa; font-size:12px; }
.wiz .question { font-size:16px; font-weight:600; color:#1a1a1a; margin-bottom:1rem; line-height:1.4; }
.wiz .note { font-size:13px; color:#92400e; background:#fffbeb; border-left:3px solid #f59e0b; padding:10px 14px; border-radius:0 8px 8px 0; margin-bottom:1rem; line-height:1.6; }
.wiz .warn-note { font-size:13px; color:#991b1b; background:#fef2f2; border-left:3px solid #ef4444; padding:10px 14px; border-radius:0 8px 8px 0; margin-bottom:1rem; line-height:1.6; }
.wiz .opts { display:flex; flex-direction:column; gap:10px; }
.wiz .opt { text-align:left; padding:14px 16px; border:1.5px solid #e0e0e0; border-radius:10px; background:#fff; color:#1a1a1a; font-size:14px; cursor:pointer; font-family:sans-serif; transition:border-color .15s, background .15s; width:100%; }
.wiz .opt:hover { border-color:#aaa; background:#f9f9f9; }
.wiz .result-card { background:#f0fdf4; border:1.5px solid #86efac; border-radius:12px; padding:1.25rem; }
.wiz .result-title { font-size:15px; font-weight:600; color:#166534; margin-bottom:0.75rem; }
.wiz .step-row { display:flex; align-items:flex-start; gap:10px; background:#fff; padding:10px 14px; border-radius:8px; margin-bottom:8px; font-size:13px; color:#1a1a1a; line-height:1.5; }
.wiz .step-num { min-width:22px; height:22px; border-radius:50%; background:#dcfce7; color:#166534; font-size:11px; font-weight:600; display:flex; align-items:center; justify-content:center; flex-shrink:0; margin-top:1px; }
.wiz .path { font-weight:600; color:#166534; font-family:monospace; font-size:12px; }
.wiz .warn { font-size:12px; color:#92400e; background:#fffbeb; padding:8px 12px; border-radius:8px; margin-top:10px; line-height:1.5; }
.wiz .tip { font-size:12px; color:#1e40af; background:#eff6ff; padding:8px 12px; border-radius:8px; margin-top:10px; line-height:1.5; }
.wiz .back-btn { margin-top:1rem; padding:8px 16px; background:transparent; border:1.5px solid #e0e0e0; border-radius:8px; font-size:13px; cursor:pointer; color:#666; font-family:sans-serif; transition:all .15s; }
.wiz .back-btn:hover { color:#1a1a1a; border-color:#aaa; }
.wiz .link-btn { display:inline-block; margin-top:1rem; padding:8px 16px; background:#1e40af; color:#fff; border-radius:8px; font-size:13px; text-decoration:none; }
</style>
<div class="wiz">
  <div id="ndv-bc" class="bc"></div>
  <div id="ndv-screen"></div>
</div>
<script>
(function(){
const S = {
  start: {
    q: '¿Cuál es el estado de la nota de venta?',
    tip: '💡 Si no sabés el estado, consultá la Trazabilidad NDV desde el ícono superior de Presea.',
    opts: [
      { label: '📄 No facturada y no despachada', to: 'nf' },
      { label: '🧾 Facturada, sin despachar (Sin Remito)', to: 'f_nd' },
      { label: '📦 Facturada y despachada (Con Remito)', to: 'f_d' },
    ]
  },
  nf: {
    q: '¿Se cancela en su totalidad o solo algunos productos?',
    opts: [
      { label: 'Cancelación total', to: 'r_baja' },
      { label: 'Solo algunos productos', to: 'r_mod' },
    ]
  },
  f_nd: {
    q: '¿Se cancela en su totalidad o solo algunos productos?',
    note: '⚠️ PRIMERO hacé la Nota de Crédito x Nro de Factura\nRuta: Ventas → Comprobantes → Notas de Crédito x nro. Factura\nCuando el sistema pregunte "¿Actualiza nota de venta?" → ingresá una S',
    opts: [
      { label: 'Cancelación total', to: 'r_baja' },
      { label: 'Solo algunos productos', to: 'r_mod_f' },
    ]
  },
  f_d: {
    q: '¿Qué quiere hacer el cliente?',
    warn: '⚠️ En este caso la nota de venta NO se puede modificar y queda sin uso.\nCuando el sistema pregunte "¿Actualiza nota de venta?" → ingresá una N\nLa devolución SIEMPRE debe hacerse en la sucursal donde el cliente compró.',
    opts: [
      { label: '💰 Dejar el dinero a favor', to: 'r_dev' },
      { label: '🔄 Cambiar por otro producto (cualquier sucursal)', to: 'r_ticket' },
    ]
  },
  r_baja: {
    result: {
      title: 'Dar de baja la nota de venta',
      steps: [
        ['Ir a:', 'Ventas → Pedidos → Bajas'],
        ['Filtrar por cliente o número de nota de venta', null],
        ['Pararse sobre la NDV que queremos anular y tocar el botón superior derecho', null],
        ['Dar ESCAPE para confirmar la eliminación', null],
      ]
    }
  },
  r_mod: {
    result: {
      title: 'Modificar la nota de venta',
      steps: [
        ['Ir a:', 'Ventas → Pedidos → Modificaciones'],
        ['Buscar el cliente y seleccionar la nota de venta', null],
        ['Eliminar los productos cancelados o modificar la cantidad', null],
        ['Agregar observación si es necesario y confirmar', null],
      ],
      tip: '💡 La NDV modificada queda en la cola de impresión.'
    }
  },
  r_mod_f: {
    result: {
      title: 'Modificar la nota de venta',
      steps: [
        ['Ya hiciste la Nota de Crédito con Actualiza NDV = S. Ahora ir a:', 'Ventas → Pedidos → Modificaciones'],
        ['Buscar el cliente y seleccionar la NDV', null],
        ['Cambiar la cantidad o eliminar el producto cancelado', null],
        ['Confirmar la modificación', null],
      ],
      tip: '💡 La NDV modificada queda en la cola de impresión.'
    }
  },
  r_dev: {
    result: {
      title: 'Hacer la devolución (Con Remito)',
      steps: [
        ['Ir a:', 'Ventas → Comprobantes → Devoluciones'],
        ['Seleccionar el cliente y la lista de precios con la que se hizo la NDV', null],
        ['Completar la información y en "Actualiza nota de venta" poner: N', null],
        ['En la ventana de productos usar CTRL+B para traer las facturas (NO cargar manualmente)', null],
        ['Al dar ESCAPE asociar la nota de crédito con la factura correspondiente', null],
        ['Confirmar: ✅ Tilde verde = NC total de facturas A | ❌ Cruz roja = facturas B o NC parcial de A', null],
      ],
      warn: '⚠️ Debe realizarse en la sucursal donde el cliente compró.'
    }
  },
  r_ticket: {
    result: {
      title: 'Hacer un ticket de cambio',
      steps: [
        ['Ir a:', 'Ventas → Comprobantes → Tickets'],
        ['Buscar el cliente e ingresar número de vendedor', null],
        ['Cargar el producto que DEVUELVE con cantidad en NEGATIVO', null],
        ['Cargar el producto NUEVO que se lleva con cantidad en POSITIVO', null],
        ['Ir a la solapa VALORES (ESCAPE) y registrar el medio de pago por la diferencia', null],
        ['Confirmar con ESCAPE', null],
      ],
      warn: '⚠️ El producto que se lleva debe ser de IGUAL o MAYOR valor que el devuelto.'
    }
  }
};
const BC = { start:'Estado NDV', nf:'No facturada', f_nd:'Facturada s/despacho', f_d:'Facturada y despachada' };
let stack=[], curr='start';
function render(){
  const step=S[curr];
  const bcEl=document.getElementById('ndv-bc');
  const items=['Inicio',...stack.map(s=>BC[s]).filter(Boolean)];
  bcEl.innerHTML=items.map((l,i)=>`<span class="bc-item">${l}</span>${i<items.length-1?'<span class="bc-sep">›</span>':''}`).join('');
  const scr=document.getElementById('ndv-screen');
  if(step.result){
    const r=step.result;
    scr.innerHTML=`<div class="result-card"><div class="result-title">✓ ${r.title}</div>${r.steps.map(([t,p],i)=>`<div class="step-row"><span class="step-num">${i+1}</span><span>${t}${p?` <span class="path">${p}</span>`:''}</span></div>`).join('')}${r.warn?`<div class="warn">${r.warn}</div>`:''}${r.tip?`<div class="tip">${r.tip}</div>`:''}</div><button class="back-btn" onclick="ndvReset()">↩ Consultar otro caso</button>`;
  } else {
    scr.innerHTML=`${step.warn?`<div class="warn-note">${step.warn}</div>`:''}${step.note?`<div class="note">${step.note}</div>`:''}${step.tip?`<div class="tip">${step.tip}</div>`:''}
<div class="question">${step.q}</div><div class="opts">${step.opts.map(o=>`<button class="opt" onclick="ndvGo('${o.to}')">${o.label}</button>`).join('')}</div>${stack.length?`<button class="back-btn" onclick="ndvBack()">← Volver</button>`:''}`;
  }
}
window.ndvGo=function(n){stack.push(curr);curr=n;render();};
window.ndvBack=function(){curr=stack.pop();render();};
window.ndvReset=function(){stack=[];curr='start';render();};
render();
})();
</script>
</div>

---

## Instructivos detallados por caso

---

### 1️⃣ Bajas — Cancelación total (No facturada / No despachada)

Este ítem lo usamos cuando necesitamos eliminar una nota de venta para que no quede pendiente ni de facturar ni de despachar.

**Ruta:** `Ventas → Pedidos → Bajas`

**Pasos:**

1. Ir a Ventas - Pedidos - Bajas

2. Se abre un cuadro para filtrar. Se puede filtrar por **cliente**, número de nota de venta o fecha.

3. Nos trae todas las NDV. Nos paramos sobre la que queremos anular y tocamos el botón de arriba a la derecha.

4. Le damos **ESCAPE** y ya queda eliminada la nota de venta. ✅

---

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

---

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
> - **✅ Tilde Verde:** Nota de crédito TOTAL de facturas A
> - **❌ Cruz Roja:** Siempre que sean facturas B y nota de crédito PARCIAL de facturas A

✅ Queda grabada la nota de crédito en la historia del cliente.

> 💡 Si se cancela la NDV en su **totalidad** → ir a **Bajas**. Si se cancelan **algunos productos** → ir a **Modificación NDV**.

---

### 4️⃣ Devolución — Facturada y despachada (Con Remito)

Se usa cuando la factura fue emitida desde una nota de venta y **SÍ** se despachó. Genera una nota de crédito y devuelve los productos al stock.

**Ruta:** `Ventas → Comprobantes → Devoluciones`

> ⚠️ **La devolución SIEMPRE debe hacerse en la sucursal donde el cliente compró.**

**Pasos:**

1. Ir a Ventas - Comprobantes - Devoluciones.

2. Seleccionamos el cliente. Se abre un cuadro pidiendo la **lista de precios** con la que se hizo la NDV. Ver las columnas desde/hasta para identificar la correcta.

3. Completamos la información y en **"Actualiza nota de venta"** ponemos **N**.

4. Se abre la ventana de productos. Tocar **CTRL + B** para traer las facturas del cliente.

   > ⚠️ Es muy importante que NO carguemos los productos manualmente.

5. Al dar ESCAPE, el sistema pide que **asociemos la nota de crédito con una factura**. Este paso es obligatorio, sino no graba la NC.

6. Confirmamos. Nos sale el cuadro:
   - **✅ Tilde Verde:** Nota de crédito TOTAL de facturas A
   - **❌ Cruz Roja:** Facturas B o nota de crédito PARCIAL de facturas A

✅ Queda la Devolución en la historia del cliente.

---

### 5️⃣ Ticket de cambio — El cliente quiere cambiar de producto

Se usa cuando el cliente quiere cambiar el producto por otro. Se hace un Ticket poniendo en **negativo** lo que devuelve y en **positivo** lo que se lleva.

**Ruta:** `Ventas → Comprobantes → Tickets`

> ⚠️ **El producto nuevo que se lleva debe ser de IGUAL o MAYOR valor que el devuelto.**
> El cambio se puede hacer en **cualquier sucursal**.

**Pasos:**

1. Ir a Ventas - Comprobantes - Tickets.

2. Ingresar el código del cliente o buscarlo con **F6** por nombre.

3. Ingresar el número de vendedor y confirmar con ENTER.

4. En la pantalla de productos:
   - Cargar el **producto que DEVUELVE** con cantidad en **NEGATIVO** (ej: -1)
   - Cargar el **producto NUEVO** que se lleva con cantidad en **POSITIVO** (ej: 1)

5. Con **ESCAPE** ir a la solapa **VALORES** para registrar el medio de pago por la diferencia.

6. Confirmar con ESCAPE. ✅

**Ejemplo:**

> Un cliente devuelve RECUBLOCK 3EN1 01 L (1 unidad) y lleva AGORESTE ACCENT 8E (1 unidad) de mayor valor. En el Ticket se carga:
> - RECUBLOCK 3EN1 01 L → cantidad: **-1** (negativo)
> - AGORESTE ACCENT 8E → cantidad: **1** (positivo)
> - El cliente abona la diferencia por el medio de pago que corresponda.

---

> 💡 **¿No sabés en qué estado está la nota de venta?**
> Consultá la **Trazabilidad NDV** desde el ícono superior de Presea → Notas de Venta → Trazabilidad. Filtrá por fecha, cliente y número de NDV.
