---
status: proposed
date: 2024-11-06
decision-makers: Jorge y Omar
consulted: Shania y Gonzalo
informed: Rubén y Hugo
---

# 0002-Módulo-Clientes

## Context and Problem Statement

El sistema requiere un módulo que permite acceder a los datos personales de los clientes.

## Decision Drivers

* RF2.1 Acceso a datos de clientes: El sistema permitirá a los usuarios autorizados consultar la base de datos de Clientes a través del módulo Clientes.

## Considered Options

* REST
* Eventos

## Decision Outcome

Opción elegida: "REST", porque es la opción adecuada para un CRUD que permitirá el acceso controlado y seguro a los datos de los clientes.

## Pros and Cons of the Options

### REST

* Bueno, porque facilita implementaciones más robustas (e.g. de seguridad, lógica de negocios y caché) para el acceso a los datos de los clientes.
* Bueno, porque facilita el acceso frecuente a los datos de los clientes.
* Malo, porque requiere un diseño general del sistema más complejo y preciso puesto que el resto de módulos no necesariamente utilizarán REST.

### Eventos

* Bueno, porque está más en línea con el resto de módulos.
* Malo, porque no es la mejor opción para un CRUD.
* Malo, porque se desaprovecharían las ventajas de eventos en cuanto a comunicación entre módulos.
* Malo, porque añade complejidad innecesaria al módulo.
