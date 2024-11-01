# Requerimientos Funcionales

## Sistema

### RF1.1: Comunicación del sistema con la base de datos de clientes

**Descripción:** El sistema debe tener conexión constante con la base de datos que almacena toda la información de los clientes, como datos personales y pagos realizados.

### RF1.2: Comunicación del sistema con la base de datos de los pedidos

**Descripción:** El sistema debe tener conexión constante con la base de datos que almacena toda la información de los pedidos realizados.

## Módulo de Clientes

### RF2.1: Consultar datos personales

**Descripción:** Los clientes pueden consultar los datos personales que se almacenan en el sistema.

## Módulo de Pedidos

### RF3.1: Realizar pedidos

**Descripción:** Los clientes pueden realizar pedidos de los productos de la empresa. Los clientes tendrán tres intentos como máximo para conseguir terminar el pedido con éxito.

### RF3.2: Preprocesar pedidos

**Descripción:** El sistema debe preparar los nuevos pedidos antes de que estos pasen a fases posteriores, realizando acciones esenciales como preparar documentación, verificar la información o asignar recursos.

### RF3.3: Autorizar pedidos

**Descripción:** El sistema debe comprobar que toda la información es correcta y el procesado ha sido planeado correctamente para después autorizar la compra del producto y pedir aceptación de la misma.

### RF3.4: Aceptar pedidos

**Descripción:** El sistema debe pedir aceptación de la compra a los clientes. Si esta tiene lugar, el sistema procede a preparar el pedido.

## Módulo de Estadísticas

### RF4.1: Informar del estado de los pedidos

**Descripción:** El sistema almacena y puede mostrar toda la información relacionada con los pedidos, como el estado de realización del mismo, su progreso en la ruta de transporte localizando el camión que transporta el producto y la información necesaria de los clientes que han realizado la compra.

## Módulo de Incidencias

### RF5.1: Reportar incidencias en las rutas

**Descripción:** El sistema debe obtener las posibles incidencias que ocurran en las rutas de transporte de los pedidos para así notificar en tiempo real a los distintos encargados de dichas rutas de posibles modificaciones o dificultades.

## Módulo de Pagos

### RF6.1: Realizar transacciones mediante pasarela de pago

**Descripción:** El sistema permitirá a los clientes realizar transacciones de pago de los productos mediante la pasarela de pago *STRIPE*.