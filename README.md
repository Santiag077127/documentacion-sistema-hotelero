# Lineamientos Técnicos

# 🏨 Sistema Hotelero - Planteamiento General

## 📌 Objetivo
Desarrollar un sistema hotelero que permita gestionar:

- Clientes
- Habitaciones
- Reservas
- Check-in / Check-out
- Facturación
- Inventario y servicios
- Mantenimiento
- Seguridad (roles y permisos)

---

# ⚙️ Definition of Ready (DoR)

Antes de iniciar cualquier historia o tarea debe cumplirse lo siguiente:

## ✔️ Backlog definido
- Historias de usuario claras
- Priorización de tareas
- Uso de herramientas (Trello, Jira)

---

## ✔️ Datos poblados (Seed / Mock Data)
- Base de datos con datos iniciales
- Sin datos rotos
- Integridad referencial garantizada

---

## ✔️ Historias de usuario (DDL - DML)
- DDL: creación de tablas
- DML: operaciones sobre datos

---

## ✔️ Roles y permisos (DCL)
- Definición clara de accesos
- Seguridad desde el inicio

---

## ✔️ Herramientas
- Control de versiones (Git)
- Gestión de tareas

---

## ✔️ Convenciones
- Código en inglés
- Uso de Conventional Commits

---

## ✔️ Base de datos
- ❌ No insertar datos manualmente
- ✅ Uso de migraciones (Liquibase)
- ✅ Trazabilidad (trace)

---

# ✅ Definition of Done (DoD)

Una tarea se considera finalizada cuando se cumple todo lo siguiente:

## 🚀 Desarrollo y funcionalidad
  - La funcionalidad se implementó según los criterios de aceptación
  - El código sigue las convenciones del proyecto
## 🗂️ Migraciones y datos
  - Las migraciones Liquibase necesarias están creadas y revisadas
  - Las migraciones se aplicaron con éxito en el entorno de prueba
  - Los datos resultantes son consistentes y mantienen integridad referencial
## 🧪 Pruebas y validación
  - Se ejecutaron pruebas unitarias, de integración o de aceptación relevantes
  - La funcionalidad fue validada en el entorno local
  - No hay errores críticos abiertos relacionados con el cambio
## 📝 Revisión y documentación
  - El cambio está listo para revisión o ya fue revisado
  - La documentación relacionada se actualizó si es necesario
## 📦 Entrega y control de versiones
  - Se generó un commit claro y descriptivo (Conventional Commits)
  - La rama está lista para integración al flujo principal
  - No existen cambios manuales en la base de datos fuera de migraciones
  - Se verificó la posibilidad de rollback si aplica

---

# 🧠 TRIAGE

Proceso de:

- Clasificar
- Priorizar
- Asignar tareas o bugs

## Ejemplo

- 🔴 Crítico: Login no funciona
- 🟡 Medio: Error en reservas
- 🟢 Bajo: Error visual

---

# 🧑‍💻 Convenciones de Desarrollo

## Código
- Todo en inglés

Ejemplo:

user
booking
room


---

## Commits (Conventional Commits)

Ejemplos:

feat: add reservation module
fix: validate check-in date
refactor: improve query performance


---

# 🛡️ Roles del Sistema

## 👑 Administrador
Permisos:
- DDL (estructura BD)
- DML (datos)
- Gestión de usuarios
- Asignación de roles
- Acceso total

---

## 🧑‍💼 Recepcionista
Permisos:
- Crear reservas
- Registrar clientes
- Check-in / Check-out
- Consultar disponibilidad

Restricciones:
- No gestiona BD
- No administra roles

---

## 💰 Cajero / Facturación
Permisos:
- Generar facturas
- Registrar pagos
- Consultar ventas

---

## 🧹 Mantenimiento
Permisos:
- Gestionar estado de habitaciones
- Registrar mantenimientos

---

## 📦 Inventario
Permisos:
- Gestión de productos
- Control de stock
- Registro de ventas

---

## 🧑 Cliente (Opcional)
Permisos:
- Ver habitaciones
- Reservar
- Cancelar reservas

---

# 🗄️ Estructura General de la Base de Datos

## 🧍 Personas
- cliente
- persona
- usuario

---

## 🔐 Seguridad
- rol
- permiso
- usuario_rol
- rol_permiso

---

## 🏨 Hotel
- habitacion
- tipo_habitacion
- estado_habitacion
- sede

---

## 📅 Reservas
- reserva_habitacion
- cancelacion_habitacion
- disponibilidad_habitacion

---

## 🛎️ Estadia
- estadia
- check_in
- check_out

---

## 💳 Facturación
- factura
- pre_factura
- pago_parcial
- detalle_compra

---

## 📦 Inventario
- producto
- servicio
- proveedor

---

## 🛠️ Mantenimiento
- mantenimiento_habitacion
- mantenimiento_uso
- mantenimiento_remodelacion

---

# ⚠️ Reglas del Proyecto

- ❌ No modificar BD manualmente
- ✅ Usar migraciones (Liquibase)
- ❌ No permitir datos rotos
- ✅ Mantener integridad referencial
- ✅ Commits claros y en inglés
- ✅ Uso de triage

---

# 🚀 Conclusión

Este sistema:

- Tiene una base de datos robusta
- Maneja múltiples módulos
- Implementa seguridad por roles
- Sigue buenas prácticas de desarrollo

👉 Escalable a nivel empresarial