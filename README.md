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
  - Dominio: Valores predefinidos multievaluados(Fecha de ingreso, Volumen de compra mensual, bonificaciones) con bonificación en función al volumen de compras mensual seguiendo el programa de Tajinaste Plus
  - Ejemplo
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
  -  **ID:** Identificación del vivero.
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
  
