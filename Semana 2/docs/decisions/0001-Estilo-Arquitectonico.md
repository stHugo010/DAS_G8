---
status: proposed
date: 2024-11-06
decision-makers: Jorge y Omar 
consulted: Shania y Gonzalo
informed: Rubén y Hugo
---

# 0001-Estilo-Arquitectonico

## Context and Problem Statement

El sistema deberá implementar al menos 6 modulos que encapsularán la lógica de negocio de la empresa. Estos módulos son: Clientes, Pedidos, Reparto y rutas, Estadísticas, Incidencias y Pagos. 

## Decision Drivers

* RF1.1 Arquitectura de Microservicios: El sistema presentará una arquitectura basada en microservicios adaptando los módulos de la empresa.
* RF1.2 Componente Gateway: El sistema debe contar con un Gateway que facilite y centralice el acceso a los distintos módulos.
* RF1.3 Peticiones HTTP/REST: El sistema recibirá peticiones HTTP/REST de los usuarios que serán gestionadas por el Gateway.
* RF3.2 Pedido procesado en tres fases: El módulo Pedidos pasará por tres fases ordenadas para la gestión de un pedido y la comunicación con el módulo Pagos.
* RF
* RF

## Considered Options

* REST
* Eventos
* Híbrida REST-Eventos

## Decision Outcome

Opción elegida "Híbrida REST-Eventos", porque es la opción que se ajusta de mejor manera a las necesidades de los diferentes módulos, utilizando las ventajas que proporciona REST para las operaciones CRUD y el uso de la plataforma STRIPE, mientras que los eventos permiten la comunicación entre los módulos utilizando un nuevo gestor de eventos e igualmente facilita una conexión en tiempo real entre usuarios y módulos. El componente Gateway se encargará de gestionar las peticiones HTTP/REST y redirigirlas al módulo REST correspondiente o crear un evento en el gestor.

## Pros and Cons of the Options

### REST

* Bueno, porque facilita la comunicación entre los módulos
* Bueno, porque permite la conexión en tiempo real entre usuarios y módulos
* Bueno, porque permite la gestión de peticiones HTTP/REST
* Bueno, porque facilita la conexión con la plataforma STRIPE
* Bueno, porque facilita el uso de operaciones CRUD
* Malo, porque requiere un diseño general del sistema más complejo y preciso

### {title of other option}

{example | description | pointer to more information | …}

* Good, because {argument a}
* Good, because {argument b}
* Neutral, because {argument c}
* Bad, because {argument d}
* …