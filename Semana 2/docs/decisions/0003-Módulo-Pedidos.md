---
status: proposed
date: 2024-11-06
decision-makers: Jorge y Omar
consulted: Shania y Gonzalo
informed: Rubén y Hugo
---

# 0003-Módulo-Pedidos

## Context and Problem Statement

El sistema requiere un módulo permite a los clientes realizar pedidos de los productos a la empresa. Si un cliente intenta realizar un pedido se le permite un número máximo de 3 de intentos. Las prestaciones y escalabilidad del sistema van a depender del número de pedidos por hora. El sistema de pedidos pasa siempre por una cadena de tres fases: Preprocesado del pedido, autorización y aceptación, de manera que no es posible pasar a un estado sino se procesado correctamente el estado anterior.

## Decision Drivers

* RF3.3 Preprocesado de pedidos: El módulo Pedidos comenzará los pedidos con su preprocesado. 
* RF3.4 Autorización de pedidos: El módulo Pedidos, tras el preprocesado, debe recibir el contenido del pedido, autorizarlo y notificar al módulo Pagos.
* RF3.5 Aceptación de pedidos: El sistema, tras la autorización y la conformación de pago, registra el pedido en la base de datos y manda un mensaje de éxito al cliente.

## Considered Options

* Eventos
* REST

## Decision Outcome

Opción elegida: "Eventos", porque es la opción adecuada para un sistema que requiere una comunicación entre módulos y una secuencia de pasos para la realización de un pedido.

## Pros and Cons of the Options

### Eventos

* Bueno, porque facilita el desarrollo paso a paso de los pedidos.
* Bueno, porque es el estilo de comunicación que se adecua a la comunicación entre módulos necesaria para gestionar los pedidos.

### REST

* Bueno, porque facilita una creación directa de pedidos.
* Malo, porque al ser una arquitectura sin estados no es óptima para la gestión secuencial de los pedidos.
* Malo, porque no es la opción adecuada para la comunicación entre módulos necesaria para gestionar los pedidos.
