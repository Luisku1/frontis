# Frontis

SaaS multinegocio para administrar centros deportivos: reservaciones de canchas y operación de punto de venta desde una misma plataforma.

## Estado

Proyecto en cimentación. Antes de implementar funcionalidades se documentarán alcance, límites de dominio y decisiones de arquitectura.

## Principios

- Reservaciones, ventas, caja e inventario son dominios distintos, aunque colaboran.
- Una reserva no es una venta. Pueden relacionarse sin compartir ciclo de vida.
- Arquitectura inicial: monolito modular dentro de un monorepo.
- TypeScript de extremo a extremo y contratos explícitos.
- Multi-tenant desde el modelo y la autorización, no como adaptación posterior.
- PWA preparada para evolución offline; el MVP no promete operación offline completa.
- Todo cambio debe preservar trazabilidad financiera y de inventario.

## Stack base propuesto

- Monorepo: pnpm + Turborepo
- Web: Next.js, React, Tailwind CSS y shadcn/ui
- Datos de cliente: TanStack Query
- Formularios: React Hook Form + Zod
- API: NestJS sobre Fastify
- Contrato: REST + OpenAPI
- Persistencia: PostgreSQL administrado con Supabase y Drizzle ORM
- Servicios: Supabase Auth, Realtime y Storage
- Procesamiento asíncrono: Redis + BullMQ cuando el caso de uso lo justifique
- Pagos: Mercado Pago México
- Calidad: Vitest, Playwright y Testcontainers
- Observabilidad: Sentry y OpenTelemetry
- Móvil: Expo como evolución futura

El stack queda sujeto a ADR antes de introducir cada dependencia.

## Documentación

- [Contexto de producto](docs/product/context.md)
- [Arquitectura inicial](docs/architecture/foundation.md)
- [Plan de cimentación](docs/roadmap/foundation.md)
- [Reglas para agentes](AGENTS.md)

## Desarrollo local

El scaffolding ejecutable se agregará en la siguiente etapa, después de cerrar el alcance del primer vertical. Esto evita crear infraestructura ficticia o dependencias prematuras.
