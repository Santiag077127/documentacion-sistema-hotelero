# ADR 002 - implementacion de uuid

## contexto
El esquema original usa ids incrementales autogenerados en mysql. Para postgresql se propone usar uuid como llave primaria en todas las tablas.

## decision
Se implementa uuid como llave primaria en las tablas del modelo de datos, en lugar de ids enteros autoincrementales.

## razones
- seguridad: los uuid no son predecibles, lo que reduce el riesgo de enumeracion de recursos y facilita el diseño de apis seguras.
- escalabilidad: uuid permite generar identificadores de forma distribuida sin coordinar un contador global, lo que mejora la flexibilidad para replicacion y microservicios.
- desacoplamiento del backend: al usar uuid el frontend o servicios externos pueden generar ids si es necesario, sin depender de una insercion previa en la base de datos.
- compatibilidad con postgresql: postgresql maneja uuid de forma nativa y puede generar valores con extensiones como pgcrypto.

## consecuencias
- todas las columnas de llave primaria se convierten a tipo uuid con valor por defecto gen_random_uuid().
- las llaves foraneas tambien se ajustan a uuid para mantener integridad referencial.
- los campos de auditoria created_by, updated_by y deleted_by deben usar uuid en lugar de bigint.
- puede requerirse adaptacion en la capa de datos y en el mapeo objeto-relacional para soportar uuid.

## consideraciones adicionales
- el uso de uuid no impide crear indices unicos ni constraints, pero la estrategia de particion y ordenamiento cambia frente a enteros secuenciales.
- para consultas basadas en fechas o relaciones se recomienda crear indices explicitos en columnas foraneas y campos de referencia.
