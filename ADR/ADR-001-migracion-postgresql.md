# ADR 001 - migracion a postgresql

## contexto
El proyecto actual usa un esquema de base de datos diseñado para mysql. La migracion a postgresql busca aprovechar caracteristicas avanzadas, mejorar la solidez de operaciones transaccionales y reducir el costo de mantenimiento a largo plazo.

## decision
Se adopta postgresql como motor de base de datos para el sistema de gestion hotelera.

## razones
- rendimiento: postgresql ofrece optimizaciones fuertes en consultas complejas, indices avanzados y planificacion de consultas con estadisticas robustas.
- tipos de datos avanzados: postgresql soporta tipos como uuid, jsonb, timestamp con zona horaria, arrays y checks complejos de forma nativa.
- consistencia y seguridad: el manejo de transacciones en postgresql es maduro, con aislamiento serializable y bloqueo de filas eficientes.
- soporte de comunidad: postgresql es un proyecto open source con una comunidad amplia y estable, lo que facilita soporte tecnico, actualizaciones y compatibilidad con herramientas modernas.
- portabilidad: postgresql se integra bien con contenedores, servicios en la nube y herramientas devops, lo que acelera la migracion y la infraestructura.

## consecuencias
- el esquema debe convertirse de sintaxis mysql a sintaxis postgresql.
- se requiere ajustar el backend para compatibilidad con tipos como uuid, boolean y timestamp.
- la gestion de actualizaciones automáticas de campos como updated_at puede necesitar triggers o logica de aplicacion adicional.
- se mejora la capacidad de escalar la base de datos y de soportar consultas analiticas sin depender de extensiones propietarias de mysql.

## alternativas consideradas
- seguir con mysql: reduce el esfuerzo inicial, pero mantiene limitaciones de tipos y menor flexibilidad para datos estructurados.
- usar maria db: compatible con mysql, pero no aporta la misma madurez en tipos complejos ni la misma comunidad que postgresql.
- usar sqlite: no es apropiado para el alcance transaccional y multiusuario del sistema.
