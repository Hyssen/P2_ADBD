# MODELO ENTIDAD/RELACIÓN. VIVEROS
- Airam Herrera Plasencia
- Enrique Hernández Cabrera
## Descripción de las entidades definidas
Entidades Definidas:
### Cliente
Atributos:
- **NIF:** Número de identificación fiscal del cliente.
- Dominio: Cadena alfanumérica con un formato específico, como 12345678X.
- Ejemplo: 98765432A
- **Nombre:** Nombre del cliente.
- Dominio: Cadena de texto alfabética. No puede estar vacía.
- Ejemplo: Juan Pérez
- **Fidelizado**
- Dominio: Valores predefinidos multievaluados(Fecha de ingreso, Volumen de compra mensual) con bonificación en función al volumen de compras mensual seguiendo el programa de Tajinaste Plus
- Ejemplo 07/10/2024 300 Uds
### Pedidos
Atributos:
- **Código pedido:** Còdigo del pedido.
- Dominio: Cadena alfanúmerica con un formato específico.
- Ejemplo: 05124512345
- **Importe:** Importe total del pedido.
- Dominio: Número entero positivo que indica la cantidad de dinero a pagar.
- Ejemplo: 9.99 EUR
- **Fecha Pedido:** Fecha en la que se hace el pedido.
- Dominio: Cadena del tipo que representa una fecha válida.
- Ejemplo: 07/10/2024
- **Nombre cliente:** Nombre del cliente
- Dominio: Cadena de texto alfabética. No puede estar vacía.
- Ejemplo: Juan Antonio
- **Forma Pago** Forma de pagar el pedido
- Dominio: Valores limitados, (Efectivo, Domicialización, transferencia bancaria, Tarjeta)
- Ejemplo: Tarjeta
### Vivero
Atributos:
- **ID:** Identificación del vivero.
- Dominio: Cadena númerica. No se puede repetir y no puede estar vacía.
- Ejemplo: 3.
- **Nombre:** Nombre del vivero.
- Dominio: Cadena de texto alfabética.
- Ejemplo: Plantas de interior.
- **Georreferencia:** Posicionamiento espacial del vivero.
- Dominio: Cadena sumando las coordenadas de latitud y longitud
- Ejemplo: 28.472, -16.332.  
### Productos
Atributos:
- **Código Producto:** Código asignado a un producto.
- Dominio: Cadena de texto alfanúmerica que no se puede repetir.
- Ejemplo: M3214567124.
- **Nombre:** Nombre del producto.
- Dominio: Cadena de texto alfabética.
- Ejemplo: Pera.
- **Tipo**: Tipo de cultivo.
- Dominio: Cadena de texto alfabética que se refiere a un dominio específico de cultivo según su uso.
- Ejemplo: Consumo.
- **Unidades totales:** Cantidad de producto que existe en el momento.
- Dominio: Valor de número entero el cual es calculado según la resta del stock y las unidades vendidas.
- Ejemplo: 500 Uds. 
### Zona
Atributos:
- **Código de zona:** Identificación de la zona.
- Dominio: Cadena alfanúmerica. No se puede repetir y no puede estar vacía.
- Ejemplo: A23.
- **Nombre:** Nombre de la zona.
- Dominio: Cadena de texto alfabética.
- Ejemplo: Almacen.
- **Georreferencia:** Posicionamiento espacial de la zona.
- Dominio: Cadena sumando las coordenadas de latitud y longitud
- Ejemplo: 28.472, -16.332.
### Empleado
Atributos:
- **NIF:** Número de identificación fiscal del Empleado.
- Dominio: Cadena alfanumérica con un formato específico, como 12345678X.
- Ejemplo: 98765432A
- **Nombre:** Nombre del empleado.
- Dominio: Cadena de texto alfabética. No puede estar vacía.
- Ejemplo: Roberto Calvo
- **Seguridad social:** Identifica al empleado con sus relaciones de la seguridad social.
- Dominio: Cadena numérica con un formato específico de 12 dígitos.
- 345127859202.
## Relaciones Definidas:
### Cliente encarga pedido
Cardinalidad: Un cliente puede encargar muchos pedidos (1,N), y un pedido solo puede ser encargado por un cliente (N,1).
Descripción: Relación entre clientes y pedidos, indicando qué pedidos ha realizado cada cliente.

### Pedido Está Compuesto por Productos
Cardinalidad: Un pedido puede estar compuesto por muchos productos (1,N), y un producto puede estar en muchos pedidos (N,N).
Descripción: Relación entre pedidos y productos, mostrando los productos que están incluidos en cada pedido.

### Empleado Gestiona Pedido
Cardinalidad: Un empleado puede gestionar muchos pedidos (1,N), y un pedido solo puede ser gestionado por un empleado (N,1).
Descripción: Relación entre empleados y pedidos, indicando qué pedidos han sido gestionados por cada empleado.

### Vivero Ofrece Producto
Cardinalidad: Un vivero puede ofrecer muchos productos (1,N), y un producto puede ser ofrecido por muchos viveros (N,N).
Descripción: Relación entre viveros y productos, mostrando qué productos están disponibles en cada vivero.

### Empleado Gestiona Vivero
Cardinalidad: Un empleado gestiona un solo vivero a la vez (N,1), y un vivero puede ser gestionado por muchos empleados a lo largo del tiempo (1,N).
Descripción: Relación entre empleados y viveros, reflejando qué empleados están a cargo de gestionar cada vivero.

### Zona Es Trabajada por Empleado
Cardinalidad: Una zona puede ser trabajada por muchos empleados a lo largo del tiempo (1,N), y un empleado solo puede trabajar en una zona a la vez (N,1).
Descripción: Relación entre zonas de viveros y empleados, mostrando qué empleados han trabajado en cada zona.

### Zona Forma Parte de Vivero
Cardinalidad: Un vivero puede tener muchas zonas (1,N), y una zona pertenece a un solo vivero (N,1).
Descripción: Relación entre viveros y sus zonas, mostrando cómo se dividen las áreas dentro de cada vivero.

### Producto Está en Zona
Cardinalidad: Un producto puede estar en muchas zonas (N,N), y una zona puede contener muchos productos (N,N).
Descripción: Relación entre productos y zonas, indicando qué productos están almacenados o expuestos en cada zona.

## Restricciones Semánticas Propuestas:
- No pueden haber cantidades negativas en los produtos: Impide que en el stock no hayan números negativos.
- No se pueden vender productos con un stock total de 0: Para garantizar la veracidad del pedido no se puede vender un producto cuyo stock sea igual a 0.
- El precio del producto no puede ser negativo: Se debe asegurar que el preciode cualquier producto  sea un valor positivo.
- No se puede repetir la fecha: La época en que trabaja un empleado no debe repetirse.

