# Contexto de producto

## Visión

Frontis será un SaaS para negocios que rentan canchas deportivas. Además de administrar disponibilidad y reservaciones, funcionará como punto de venta para aumentar su valor operativo: cobros, caja, productos y existencias del establecimiento.

## Resultado para el negocio

Una operación puede conocer qué cancha está disponible, quién reservó, qué se cobró, qué se vendió y cómo cerró la caja sin reconciliar herramientas aisladas.

## Dominios iniciales

| Dominio | Responsabilidad |
| --- | --- |
| Identidad y tenancy | Organizaciones, sedes, usuarios, membresías y permisos |
| Reservaciones | Canchas, horarios, disponibilidad, reservas y políticas |
| POS | Catálogo vendible, tickets, partidas, descuentos y devoluciones |
| Pagos | Intenciones, confirmaciones, conciliación y reembolsos |
| Caja | Turnos, entradas, salidas, arqueos y cierres |
| Inventario | Existencias, movimientos, ajustes y costo |
| Clientes | Perfil operativo e historial permitido |

## Límites esenciales

- Una reserva bloquea capacidad temporal; una venta registra una transacción comercial.
- El pago es evidencia financiera relacionada con una reserva o venta, no su estado interno.
- La caja explica custodia de dinero; no reemplaza ventas ni pagos.
- El inventario se modifica mediante movimientos trazables, nunca editando existencias sin causa.
- Toda entidad operativa pertenece a una organización y, cuando corresponda, a una sede.

## Alcance por definir antes del primer vertical

- Tipo inicial de centro deportivo y reglas de duración.
- Canales de reserva: personal, cliente final o ambos.
- Roles del MVP y alcance por sede.
- Métodos de pago y necesidad de facturación.
- Productos físicos incluidos en el POS.
- Flujo mínimo de caja e inventario.
- Mercado objetivo inicial y modelo de cobro de Frontis.

## Fuera de compromiso actual

- Aplicación móvil nativa.
- Operación offline completa.
- Automatizaciones avanzadas de marketing.
- Contabilidad formal o facturación, hasta definir requisitos.
