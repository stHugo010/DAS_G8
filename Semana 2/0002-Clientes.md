---
status: proposed
date: 2024-11-06
decision-makers: Jorge y Omar
consulted: Shania y Gonzalo
informed: Rubén y Hugo
---

# Módulo Clientes

## Contexto y enunciado del problema

El sistema requiere un módulo que permite acceder a los datos personales de los clientes.

## Factores de decisión

* RF2.1 Acceso a datos de clientes: El sistema permitirá a los usuarios autorizados consultar la base de datos de Clientes a través del módulo Clientes.

## Opciones consideradas

* REST
* Eventos

## Resultado de la decisión

Opción elegida: "REST", porque es la opción adecuada para un CRUD que permitirá el acceso controlado y seguro a los datos de los clientes.

### Consecuencias

* Bueno, porque facilita implementaciones más robustas (e.g. de seguridad, lógica de negocios y caché) para el acceso a los datos de los clientes.
* Bueno, porque facilita el acceso frecuente a los datos de los clientes.
* Malo, porque requiere un diseño general del sistema más complejo y preciso puesto que el resto de módulos no necesariamente utilizarán REST.

## Pros y Cons de las opciones

### REST

* Bueno, porque facilita implementaciones más robustas (e.g. de seguridad, lógica de negocios y caché) para el acceso a los datos de los clientes.
* Bueno, porque facilita el acceso frecuente a los datos de los clientes.
* Malo, porque requiere un diseño general del sistema más complejo y preciso puesto que el resto de módulos no necesariamente utilizarán REST.

### Eventos

* Bueno, porque está más en línea con el resto de módulos.
* Malo, porque no es la mejor opción para un CRUD.
* Malo, porque se desaprovecharían las ventajas de eventos en cuanto a comunicación entre módulos.
* Malo, porque añade complejidad innecesaria al módulo.
