# Requisitos funcionales

| Número | Nombre                                          | Descripción                                                                                                                       |
| ------ | ----------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| RF1    | Arquitectura basada en microservicios           | El sistema cuenta con una arquitectura basada en microservicios.                                                                  |
| RF2    | Capa de cliente                                 | El sistema cuenta con una capa de cliente.                                                                                        |
| RF3    | Tipos de cliente                                | Los clientes se dividen en clientes de PC y clientes de móvil.                                                                    |
| RF4    | Capa de datos                                   | El sistema cuenta con una capa de acceso a datos.                                                                                 |
| RF5    | Componente Gateway                              | El sistema cuenta con un Gateway. Los clientes se conectan al sistema a través del Gateway mediante protocolos HTTP/REST.         |
| RF6    | Diferenciación de clientes                      | El componente Gateway diferencia entre los clientes PC y los clientes móvil.                                                      |
| RF7    | Módulo Clientes                                 | La lógica de negocio cuenta con un módulo crítico Clientes.                                                                       |
| RF7.1  | Funcionalidad del módulo Clientes               | El módulo Clientes accede a datos personales de los clientes.                                                                     |
| RF8    | Módulo Pedidos                                  | La lógica de negocio cuenta con un módulo crítico Pedidos.                                                                        |
| RF8.1  | Funcionalidad del módulo Pedidos                | El módulo Pedidos permite a los clientes realizar pedidos de los productos a la empresa.                                          |
| RF8.2  | Límite de intentos de pedido                    | El módulo Pedidos limita a los clientes el número de intentos de pedido a 3 por sesión.                                           |
| RF9    | Módulo Reparto                                  | La lógica de negocio cuenta con un módulo Reparto.                                                                                |
| RF9.1  | Funcionalidad del módulo Reparto                | El módulo Reparto gestiona el reparto de productos a los clientes asignando a cada camión una ruta predefinida.                   |
| RF9.2  | Generación de rutas para el reparto             | El módulo Reparto genera las rutas mediante un algoritmo de planificación de rutas basado en técnicas de investigación operativa. |
| RF10   | Módulo Estadísticas                             | La lógica de negocio cuenta con un módulo no crítico Estadísticas.                                                                |
| RF10.1 | Funcionalidad del módulo Estadísticas           | El módulo Estadísticas proporciona información sobre el estado de los pedidos y la situación en tiempo real de los camiones.      |
| RF10.2 | Informar sobre estado del pedido a los clientes | El módulo Estadísticas proporciona información a los clientes del estado de sus pedidos.                                          |
| RF11   | Módulo Noticias                                 | La lógica de negocio cuenta con un módulo no crítico Noticias.                                                                    |
| RF11.1 | Funcionalidad del módulo Noticias               | El módulo Noticias permite a los clientes subscribirse a noticias sobre el estado de los pedidos y del estado del reparto.        |
| RF12   | Módulo Pagos                                    | La lógica de negocio cuenta con un módulo crítico Pagos.                                                                          |
| RF12.1 | Funcionalidad del módulo Pagos                  | El módulo Pagos establece una pasarela de pago externa para garantizar los pagos.                                                 |
| RF13   | Capa de seguridad                               | El sistema cuenta con una capa crítica de Seguridad paralela a las demás.                                                         |
| RF14   | Acceso seguro para clientes                     | La capa de Seguridad proporciona un acceso seguro para los clientes.                                                              |
| RF14.1 | Solicitar usuario y clave a clientes            | La capa de Seguridad solicita a los clientes usuario y clave para el acceso al sistema.                                           |
| RF14.2 | Solicitar doble factor de autentificación       | La capa de Seguridad solicita a los clientes el uso de un doble factor de autentificación.                                        |
| RF15   | Acceso seguro a pasarela de pago                | La capa de Seguridad cuenta con un acceso seguro a la pasarela de pago.                                                           |
| RF15.1 | Encriptación de los datos de la tarjeta         | La capa de Seguridad encripta los datos de las tarjetas usadas para el pago por el cliente.                                       |
| RF15.2 | Temporizador para el pago                       | La capa de Seguridad proporciona un temporizador que limita el tiempo para realizar el pago.                                      |
