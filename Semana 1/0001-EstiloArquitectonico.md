---
# These are optional metadata elements. Feel free to remove any of them.
status: "{proposed | rejected | accepted | deprecated | … | superseded by ADR-0123"
date: {YYYY-MM-DD when the decision was last updated}
decision-makers: {list everyone involved in the decision}
consulted: {list everyone whose opinions are sought (typically subject-matter experts); and with whom there is a two-way communication}
informed: {list everyone who is kept up-to-date on progress; and with whom there is a one-way communication}
---

# {short title, representative of solved problem and found solution}

## Migración de monolito a microservicios para compañia de productos alimenticios

Una compañía de productos alimenticios pretende migrar la arquitectura de un sistema monolítico a una basada en microservicios de manera que la arquitectura sea menos rígida. La arquitectura existente cuenta con una parte de clientes PC y móvil que acceden a los datos de la empresa alojados en 2 BBDD SQL (Clientes, Pedidos). La BBDD de Clientes contiene datos de clientes y pagos mientras que la BBDD de Pedidos se encarga de almacenar los datos restantes. El acceso actual se pretende que sea sustituido por protocolos HTTP/REST mediante un componente Gateway adecuado el cual facilita el acceso desde los clientes PC y móvil. La lógica de negocio de la empresa cuenta con los siguientes módulos con diferentes grados decriticidad.

- Clientes (crítico): Este componente permite a acceder los datos de personales de los clientes.
- Pedidos (semi crítico): Este módulo permite a los clientes realizar pedidos de los productos a la empresa. Si un cliente intenta realizar un pedido se le permite un número máximo de 3 de intentos. Las prestaciones y escalabilidad del sistema van a depender del número de pedidos por hora. El sistema de pedidos pasa siempre por una cadena de tres fases: Preprocesado del pedido, autorización y aceptación, de manera que no es posible pasar a un estado sino se procesado correctamente el estado anterior.
- Reparto y rutas (Crítico): Este componente complejo cuenta con una gran funcionalidad que es necesario desacoplar y gestiona el reparto de las flotas de transporte a los clientes y las rutas de los camiones. La gestión cuenta con 2 algoritmos de optimización que se seleccionan en función de la demora del camión.
- Estadísticas (no crítico): El sistema cuenta con un módulo de estadísticas que proporciona información valiosa sobre el estado de los pedidos y la situación en tiempo real de los camiones. Las estadísticas proporcionan también información de clientes.
- Incidencias (semi crítico): Este módulo reporta a los gestores de las rutas cualquier tipo de incidencia (camión averiado, reparto no realizado, etc.)
- Pagos (crítico): Este componente es una pasarela de pago externa que proporciona la empresa STRIPE (<http://stripe.com>) para garantizar la seguridad de los pagos y la compatibilidad con otros clientes.

Asimismo, la gestión de los pedidos debe proporcionar una forma de gestionar todas las peticiones de los pedidos de clientes y gestionar las incidencias en el reparto.

La nueva arquitectura debe contar con los elementos software y/o tecnología adecuados para poder ejecutar los microservicios.

## Factores de decisión

* Los clientes deben poder acceder de forma segura a su información guardada en ambas bases de datos de la empresa
* Acceso por protoclos HTTP/REST
* Modularización para adaptación a microservicios
* Los pedidos pasan por tres estados ordenados
* Escalabilidad del sistema de pedidos
* Manejo de incidencias en repartos y gestión de rutas
* Conexión en tiempo real con los camiones y ubicación actualizada de los pedidos
* La conexión con STRIPE
* Diferencias en criticidad de los módulos

## Opciones consideradas

* REST
* De eventos
* Orientada a servicios

## Resultado de la decisión

Chosen option: "{title of option 1}", because {justification. e.g., only option, which meets k.o. criterion decision driver | which resolves force {force} | … | comes out best (see below)}.

<!-- This is an optional element. Feel free to remove. -->
### Consecuencias

* Good, because {positive consequence, e.g., improvement of one or more desired qualities, …}
* Bad, because {negative consequence, e.g., compromising one or more desired qualities, …}
* … <!-- numbers of consequences can vary -->

<!-- This is an optional element. Feel free to remove. -->
### Confirmación

{Describe how the implementation of/compliance with the ADR can/will be confirmed. Is the chosen design and its implementation in line with the decision? E.g., a design/code review or a test with a library such as ArchUnit can help validate this. Note that although we classify this element as optional, it is included in many ADRs.}

<!-- This is an optional element. Feel free to remove. -->
## Pros y Cons de las opciones

### {title of option 1}

<!-- This is an optional element. Feel free to remove. -->
{example | description | pointer to more information | …}

* Good, because {argument a}
* Good, because {argument b}
<!-- use "neutral" if the given argument weights neither for good nor bad -->
* Neutral, because {argument c}
* Bad, because {argument d}
* … <!-- numbers of pros and cons can vary -->

### {title of other option}

{example | description | pointer to more information | …}

* Good, because {argument a}
* Good, because {argument b}
* Neutral, because {argument c}
* Bad, because {argument d}
* …

<!-- This is an optional element. Feel free to remove. -->
## Más información

{You might want to provide additional evidence/confidence for the decision outcome here and/or document the team agreement on the decision and/or define when/how this decision the decision should be realized and if/when it should be re-visited. Links to other decisions and resources might appear here as well.}