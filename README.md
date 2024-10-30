## MI PRIMER DER - EXCALIDRAW
![image](https://github.com/user-attachments/assets/cc01f4a4-3acf-404a-af70-6036922d2a7e)


## DESARROLLO TEORICO - PRESENTACIÓN
https://www.canva.com/design/DAGU3XvVhrI/LJ90pXHF-jiMnAlSKxnazw/edit?utm_content=DAGU3XvVhrI&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton

## DER - WORKBENCH 
![image](https://github.com/user-attachments/assets/8501eac6-c2a7-449c-9d16-d58ab83fa9d5)

## DOCUMENTACIÓN -  El Cuervo PetShop

## Descripción
Este proyecto está diseñado para gestionar las operaciones de ventas, compras y postventa de **El Cuervo PetShop**. La base de datos permite almacenar y organizar información de clientes, proveedores, vendedores, productos, y reclamos postventa. Su estructura facilita la administración del inventario, la auditoría de transacciones, y el seguimiento de interacciones con clientes.

---

## Tablas
### 1. **proveedores**
   - **Descripción:** Almacena datos de los proveedores de productos.
   - **Columnas Principales:**
     - `id_proveedor`: Identificador único del proveedor.
     - `forma_de_pago`: Tipo de pago acordado con el proveedor.
   - **Relaciones:** Referencia `productos` y `categoria_de_producto`.
   - **Problema que Resuelve:** Centraliza los datos de proveedores para facilitar las compras y el seguimiento de pedidos.

### 2. **productos**
   - **Descripción:** Contiene información de cada producto, incluyendo su categoría, precio, y cantidad disponible.
   - **Columnas Principales:**
     - `id_producto`: Identificador único del producto.
     - `nombre_producto`: Nombre descriptivo del producto.
   - **Relaciones:** Referencia `facturas_de_compra` y `categoria_de_producto`. Referenciado en `detalle_de_compra`, `proveedores`, `stock`, y `detalle_de_venta`.
   - **Problema que Resuelve:** Facilita el control y la actualización del inventario de productos, junto con la categorización y costos asociados.

### 3. **stock**
   - **Descripción:** Almacena información sobre la cantidad de productos disponibles en cada centro de almacenamiento.
   - **Columnas Principales:**
     - `id_stock`: Identificador único del stock.
   - **Relaciones:** Referencia `productos` y `centro_de_almacenamiento`.
   - **Problema que Resuelve:** Facilita la administración de los niveles de stock y permite rastrear la ubicación de productos en los distintos centros de almacenamiento.
   
### 4. **detalle_de_compra**
   - **Descripción:** Almacena detalles de cada compra, incluyendo el producto, cantidad y subtotal.
   - **Columnas Principales:**
     - `id_detalle_compra`: Identificador único del detalle de compra.
   - **Relaciones:** Referencia `productos` y `facturas_de_compra`.
   - **Problema que Resuelve:** Proporciona un desglose detallado de las compras, permitiendo un control detallado de inventario y costos.
     
### 5. **facturas_de_compra**
   - **Descripción:** Almacena detalles de las facturas de compra, incluyendo el proveedor, fecha de compra, monto bruto, impuestos y monto neto.
   - **Columnas Principales:**
     - `id_numero_de_factura_de_compra`: Identificador único para cada factura de compra.
     - `nombre_proveedor`: Nombre del proveedor asociado a la factura.
     - `fecha_compra`: Fecha en la que se realizó la compra.
   - **Relaciones:** Referenciada en la tabla `productos` y `detalle_de_compra`.
   - **Problema que Resuelve:** Facilita el control y la auditoría de las compras realizadas, manteniendo un registro detallado de cada factura para gestionar costos y stock.
     
### 6. **ventas**
   - **Descripción:** Registra cada venta realizada, incluyendo el cliente, vendedor, producto y el monto total.
   - **Columnas Principales:**
     - `id_venta`: Identificador único de la venta.
   - **Relaciones:** Referencia `cliente`, `vendedor`, `categoria_de_producto`, y `facturas_de_venta`.
   - **Problema que Resuelve:** Permite llevar un control detallado de las ventas, identificando el cliente y el vendedor asociados, así como la categoría del producto.
     
### 7. **vendedor**
   - **Descripción:** Almacena la información sobre los vendedores, incluyendo nombre, estado y cantidad de ventas.
   - **Columnas Principales:**
     - `id_vendedor`: Identificador único del vendedor.
     - `nombre_vendedor`: Nombre del vendedor.
   - **Relaciones:** Referenciado en la tabla `ventas`.
   - **Problema que Resuelve:** Ayuda a gestionar y evaluar el desempeño de cada vendedor individualmente y permite segmentar las ventas realizadas por cada uno.

### 8. **cliente**
   - **Descripción:** Almacena los datos de los clientes, como nombre, fecha de nacimiento, dirección, email, estado del cliente, etc.
   - **Columnas Principales:**
     - `id_cliente`: Identificador único del cliente.
     - `nombre_cliente`: Nombre del cliente.
     - `estado`: Estado de pagos del cliente (DEUDOR o A TIEMPO).
   - **Relaciones:** Referenciado en la tabla `ventas`.
   - **Problema que Resuelve:** Permite mantener un historial y una clasificación de los clientes basada en su estado, facilitando el seguimiento y la fidelización de clientes.

### 9. **facturas_de_venta**
   - **Descripción:** Almacena las facturas de venta generadas para cada transacción.
   - **Columnas Principales:**
     - `id_num_factura_venta`: Identificador único de la factura de venta.
   - **Relaciones:** Referenciado en la tabla `ventas`.
   - **Problema que Resuelve:** Facilita el registro y la verificación de ventas realizadas, proporcionando un control administrativo.

### 10. **categoria_de_producto**
   - **Descripción:** Define las categorías de productos disponibles en la tienda.
   - **Columnas Principales:**
     - `id_categoria_de_producto`: Identificador único para la categoría del producto.
     - `categoria_de_producto`: Enumera las categorías posibles (alimento, accesorios, etc.).
   - **Relaciones:** Referenciado en `productos`, `ventas`, y `proveedores`.
   - **Problema que Resuelve:** Organiza los productos en categorías, facilitando la gestión del inventario y el análisis de ventas por categoría de producto.

### 11. **centro_de_almacenamiento**
   - **Descripción:** Almacena información sobre los centros de almacenamiento.
   - **Columnas Principales:**
     - `id_centro_de_almacenamiento`: Identificador único del centro de almacenamiento.
   - **Relaciones:** Referenciado en la tabla `stock`.
   - **Problema que Resuelve:** Permite gestionar el inventario en diferentes ubicaciones de almacenamiento, optimizando la logística de stock.

### 12. **postventa**
   - **Descripción:** Almacena información sobre reclamos de postventa.
   - **Columnas Principales:**
     - `id_reclamo`: Identificador único del reclamo.
     - `tipo_de_reclamo`: Tipo de problema reportado (producto defectuoso, retraso, etc.).
   - **Relaciones:** Referencia `ventas`.
   - **Problema que Resuelve:** Facilita el seguimiento y la gestión de los reclamos para mejorar el servicio postventa.

### 13. **detalle_de_venta**
   - **Descripción:** Almacena detalles de los productos vendidos en cada transacción.
   - **Columnas Principales:**
     - `id_detalle_de_venta`: Identificador único del detalle de venta.
   - **Relaciones:** Referencia `ventas`, `productos`, y `facturas_de_venta`.
   - **Problema que Resuelve:** Ofrece un desglose detallado de cada venta, permitiendo analizar las ventas por producto y tipo de venta (online o física).


