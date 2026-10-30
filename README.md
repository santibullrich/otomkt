# OTOMKT — On Top Of Marketing

Plataforma de control de gestión para equipos de marketing. Junta en un solo lugar el gasto, el budget, los clientes conseguidos y las facturas, para que el equipo deje de armar scorecards a mano y se enfoque en la estrategia.

## Estado

Prototipo navegable con datos de ejemplo. Todavía no lee facturas reales ni se conecta a las plataformas de publicidad.

## Estructura

| Carpeta | Qué hay |
| --- | --- |
| `app/index.html` | El prototipo completo en un solo archivo HTML. Abrilo en el navegador. |
| `design-system/` | Sistema de diseño: `tokens.json` (colores claro y oscuro, tipografía, espaciado, radios), `components/bundle.css` (clases `oto-*`) y una carpeta por componente con su guía y vista previa. Empezá por `design-system/README.md`. |

## Secciones de la app

- **Dashboard:** clientes, gasto y CAC totales; clientes del año y del mes contra lo proyectado; budget vs. gasto real; resultados por canal.
- **Paid Media:** gasto, clientes y CAC por plataforma; campañas; recomendaciones de Oto aplicables (simuladas).
- **Influencers y streaming:** tabla de perfiles con contacto, alcance, costo y CAC; contratos generados con AI; preguntas a Oto por perfil.
- **Medios offline:** inversión por campaña en TV, radio y vía pública, con impactos y CPM.
- **Budget:** proyección editable de gasto y clientes nuevos por canal y por mes, y gráficos de proyectado vs. real.
- **Facturas:** estado de pago, vencimientos y consulta a finanzas por las vencidas.
- **Conexiones:** correos donde llegan las facturas, correo de finanzas y plataformas de paid media.

## Notas

- Montos en dólares, completos y con formato de Estados Unidos (`US$ 911,000`).
- La generación de contratos y las preguntas a Oto usan la AI de Claude cuando la app se abre como artifact en claude.ai; abierta localmente, esas funciones avisan que no están disponibles.
- Las ediciones del budget, los correos y el tema claro u oscuro se guardan en el navegador (localStorage).
