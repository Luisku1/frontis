# Cimentación de arquitectura

## Decisión inicial

Frontis partirá como monolito modular en un monorepo. La unidad de despliegue puede separarse entre web y API, pero las reglas de negocio permanecen organizadas por dominio y no por capa técnica global.

## Topología objetivo

```text
apps/
  web/          # Next.js: experiencia web y BFF sólo si se documenta
  api/          # NestJS/Fastify: casos de uso, autorización y contratos
packages/
  contracts/    # Esquemas y tipos públicos sin lógica de infraestructura
  database/     # Esquema, migraciones y adaptadores de persistencia
  config/       # Configuración compartida de tooling
  ui/           # Componentes visuales reutilizables, sin reglas de negocio
docs/
  adr/          # Decisiones duraderas
```

Los módulos de dominio vivirán primero dentro de la API. Sólo se extraerán como paquetes cuando exista un consumidor o límite real que lo justifique.

## Reglas transversales

### Multi-tenancy

- El contexto de organización se resuelve en servidor desde una membresía autenticada.
- Toda consulta operativa queda delimitada por organización; la sede es un límite adicional.
- Índices y restricciones incluyen el tenant cuando la unicidad es local.
- Las pruebas deben intentar acceso cruzado entre tenants.

### Dinero

- Importes en unidades menores enteras o tipo decimal definido.
- Moneda explícita.
- Pagos y webhooks idempotentes.
- Ventas cerradas no se reescriben: se corrigen con eventos o documentos compensatorios.

### Tiempo y reservaciones

- Instantes persistidos en UTC.
- Zona horaria IANA por sede.
- La prevención de doble reserva debe apoyarse en una garantía transaccional de base de datos, no sólo en una consulta previa.
- Políticas de cancelación y tolerancia son configuración versionable.

### Inventario y caja

- Existencias derivadas de movimientos.
- Cada movimiento registra causa, actor, sede y referencia.
- Los cierres de caja son snapshots auditables; ajustes posteriores quedan separados.

## Integraciones

Supabase, Mercado Pago, Redis y otros proveedores se conectan detrás de adaptadores. El dominio no depende de SDKs externos. Todo webhook conserva identificador del proveedor, estado de procesamiento e historial de reintentos.

## ADR requeridos antes del scaffolding completo

1. Estrategia de autenticación y autorización multi-tenant.
2. Garantía de exclusión para horarios.
3. Modelo monetario e impuestos.
4. Despliegue inicial y ambientes.
5. Estrategia de contratos entre web y API.
