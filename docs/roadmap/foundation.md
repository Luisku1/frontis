# Plan de cimentación

## Etapa 0 — Definición

- Cerrar actor principal, tipo de negocio inicial y primer flujo vendible.
- Escribir mapa de dominios y glosario.
- Definir roles, permisos y límites por organización/sede.
- Elegir el primer vertical con criterios de aceptación.
- Registrar ADR de autenticación, tenancy y disponibilidad.

## Etapa 1 — Plataforma mínima

- Inicializar pnpm, Turborepo y configuración TypeScript.
- Crear web y API con health checks.
- Configurar PostgreSQL, migraciones y datos de desarrollo.
- Implementar identidad, organización, sede y membresía.
- Agregar CI para tipos, lint, pruebas y build.
- Definir manejo de secretos y ambientes.

## Etapa 2 — Primer vertical

Recomendación: crear una reserva interna desde un calendario de sede, con validación de disponibilidad y trazabilidad. No incluir todavía POS completo; relacionar el cobro sólo cuando sus reglas estén definidas.

## Etapa 3 — Operación comercial

- Ticket de POS independiente.
- Pagos y conciliación.
- Turno y cierre de caja.
- Movimientos básicos de inventario.

## Puertas de calidad

Cada etapa exige aislamiento entre tenants, pruebas de reglas críticas, migraciones reproducibles, observabilidad mínima y documentación de decisiones.
