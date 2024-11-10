# Requerimientos Funcionales

| Número | Nombre                                              | Descripción                                                                                                                                                       |
|--------|-----------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF1.1  | Arquitectura de microservicios                      | El sistema presentará una arquitectura basada en microservicios adaptando los módulos de la empresa.                                                             |
| RF1.2  | Componente Gateway                                  | El sistema contará con un Gateway que facilite y centralice el acceso a los distintos módulos.                                                                   |
| RF1.3  | Peticiones HTTP/REST                                | El sistema recibirá peticiones HTTP/REST de los usuarios que serán gestionadas por el Gateway.                                                                   |
| RF2.1  | Acceso a datos de clientes                          | El sistema permitirá a los usuarios autorizados consultar la base de datos de Clientes a través del módulo Clientes.                                             |
| RF2.2  | Gestión de clientes                                 | El sistema permitirá gestionar los datos de los clientes (crear, modificar y eliminar).                                                                          |
| RF3.1  | Acceso a datos de pedidos                           | El sistema permitirá al módulo Pedidos acceder a la base de datos de Pedidos.                                                                                    |
| RF3.2  | Pedido procesado en tres fases                      | El módulo Pedidos pasará por tres fases ordenadas para la gestión de un pedido y la comunicación con el módulo Pagos.                                            |
| RF3.3  | Preprocesado de pedidos                             | El módulo Pedidos comenzará los pedidos con su preprocesado.                                                                                                     |
| RF3.4  | Autorización de pedidos                             | El módulo Pedidos, tras el preprocesado, deberá recibir el contenido del pedido, autorizarlo y notificar al módulo Pagos.                                        |
| RF3.5  | Aceptación de pedidos                               | El sistema, tras la autorización y la conformación de pago, registrará el pedido en la base de datos y manda un mensaje de éxito al cliente.                     |
| RF3.6  | Restricción de intentos                             | El sistema deberá limitar el número de intentos de pedido a tres por cliente.                                                                                    |
| RF4.1  | Decisión de rutas                                   | El módulo Reparto y Rutas deberá elegir la ruta adecuada para cada repartidor entre las generadas por dos algoritmos de optimización.                            |
| RF4.2  | Gestionar reparto                                   | El módulo Reparto y Rutas recibirá un aviso cuando un repartidor comience a repartir y le enviará la información de su ruta.                                     |
| RF4.3  | Recalcular ruta por incidencia                      | El módulo de Reparto y Rutas deberá recibir notificaciones del módulo de Incidencias sobre eventos que afecten a la ruta y notificar a los repartidores.        |
| RF5.1  | Acceso a datos del pedido                           | El sistema permitirá a los usuarios autorizados consultar los datos pertinentes a su pedido.                                                                     |
| RF5.2  | Seguimiento del pedido                              | El módulo Estadísticas recibirá la información de la ubicación en tiempo real del pedido, cuando este se encuentre en la ruta de transporte.                     |
| RF5.3  | Almacenamiento de información de entrega de pedidos | El sistema permitirá al módulo Estadísticas acceso a las bases de datos para actualizar la información de los pedidos respecto a entrega y recepción.             |
| RF5.4  | Escucha de incidencias                              | El módulo Estadísticas recibirá del módulo de Incidencias los problemas que afecten al reparto.                                                                  |
| RF6.1  | Recepción de incidencias en las rutas de reparto    | El módulo Incidencias recibirá alertas sobre problemas en las rutas de reparto, como accidentes de los camiones.                                                 |
| RF6.2  | Procesado de incidencias                            | El módulo Incidencias se encargará de procesar la información en una incidencia para el resto de los módulos.                                                    |
| RF6.3  | Comunicación con Reparto y Rutas, y Estadísticas    | El módulo Incidencias enviará la información al módulo Reparto y Rutas, y al módulo Estadísticas para modificaciones pertinentes.                                |
| RF7.1  | Realización de transacciones mediante pasarela de pago | El módulo Pagos se encargará de realizar transacciones de forma segura mediante la utilización de la pasarela de pago STRIPE.                                  |
| RF7.2  | Almacenamiento de datos de pago                     | El sistema permitirá al módulo Pagos acceso a la base de datos para almacenar los datos de pago de los clientes.                                                 |
| RF7.3  | Comunicación con pedidos                            | El módulo de Pagos recibirá la información del módulo de Pedidos, establecerá conexión entre el cliente y la plataforma de pago y comunicará el resultado.      |