# OTOMKT — sistema de diseño

OTOMKT es la plataforma de control de gestión para equipos de marketing: junta facturas, budget, paid media, influencers y medios offline, y responde cuánto se gastó, cuánto queda y cuánto cuesta cada cliente. Este sistema existe para que esas respuestas se lean en un vistazo, en modo claro y oscuro.

## Principios

1. **El número primero.** Cada pantalla abre con los números que importan, grandes y con cifras tabulares. El resto (gráficos, tablas, acciones) explica esos números.
2. **Un acento, muchos grises.** La interfaz es neutra y fría. El lima `brand` aparece poco: botón principal, marca, ítem activo. Si todo resalta, nada resalta.
3. **El color significa algo.** Verde y rojo solo dicen bueno o malo para el negocio, siempre con ícono y texto. Los colores de serie identifican plataformas y canales, y no cambian entre pantallas.
4. **Comparar siempre.** Ningún número aparece sin referencia: contra el budget, el objetivo, el mes anterior o el promedio.
5. **Densidad cómoda.** Tarjetas con aire (20px de padding) y tablas compactas (filas de 44px). Lo que se escanea va en tabla; lo que se decide va en tarjeta.

## Voz

- Español rioplatense, directo y corto: "Quedan US$ 89,000 del año", no "Usted dispone de un remanente presupuestario".
- Los títulos nombran la cosa ("Budget vs. gasto real"); los subtítulos dicen la conclusión ("US$ 911,000 de US$ 1,000,000 a la fecha").
- Botones con verbo + objeto: "Aplicar en Google Ads", "Generar contrato", "Elegir canal".
- Oto, el asesor, habla en primera persona solo dentro de sus recomendaciones y respuestas.

## Color

Los tokens son semánticos y tienen tema claro (primero) y oscuro. Se usan por rol, nunca por valor.

| Rol | Tokens | Regla |
| --- | --- | --- |
| Fondos | `canvas`, `surface`, `surface-sunken` | La app es `canvas`; todo lo que tiene datos va sobre `surface`. |
| Texto | `text-primary`, `text-secondary`, `text-tertiary` | Números y títulos en primary; etiquetas en secondary; ejes y notas en tertiary. |
| Marca | `brand`, `on-brand`, `brand-soft` | Lima solo como relleno, con texto `on-brand`. Nunca texto lima sobre fondo claro. |
| Estado | `positive*`, `negative*`, `warning*`, `info-soft` | Bueno, malo, atención, en proceso. Con ícono y palabra. |
| Datos | `series-1` … `series-5` | Orden fijo: azul, naranja, aqua, amarillo, magenta. Más de 5 series se agrupan en "Otros". |
| Gráficos | `chart-grid`, `chart-track`, `chart-target` | Grilla recesiva; objetivos y budget en punteada `chart-target`. |
| Navegación | `nav`, `nav-text`, `nav-hover` | Barra lateral oscura en los dos temas. |

El modo oscuro no es una inversión: los fondos suben en tres escalones (`canvas` → `surface` → `surface-sunken`), las sombras casi desaparecen y los colores de serie tienen su propio paso para el fondo oscuro. Todo texto cumple 4,5:1 en los dos temas.

## Tipografía

Una sola familia, **Geist**, con cifras tabulares para que los números se alineen en columna y no "salten" al actualizarse. **Geist Mono** solo para direcciones, IDs de factura y de campaña, nunca para importes.

- Números: `num-hero` (40), `num-kpi` (30), `num-md` (20), `num-table` (14). Peso 600, tracking negativo en los grandes.
- Títulos: `title-page` (28), `title-section` (18), `title-card` (15).
- Texto: `body` (14), `body-sm` (13), `label` (12), `overline` (11, mayúsculas).

## Formato de números

- Sistema numérico de Estados Unidos: coma para los miles y punto para los decimales (`5,860`, `1.6%`).
- Montos siempre en dólares, completos y sin abreviar, con prefijo `US$`: `US$ 911,000`, `US$ 1,200,000`, `US$ 27,400`. Nunca K ni M.
- Montos sin decimales salvo los que los necesitan para leerse, como el CPM (`US$ 2.50`).
- Porcentajes: una decimal debajo de 10% (`1.6%`), enteros desde 10% (`16%`).
- Signo menos tipográfico (−) en variaciones y desvíos.
- Sin dato: guion largo (—) o "Sin dato", nunca 0.

## Layout

- Barra lateral de 240px + contenido de hasta 1,240px, centrado.
- Grilla de 12 columnas con gutter de 24px (16px en móvil). Las filas de tarjetas usan 4, 2 o 1 columnas según el ancho.
- Orden de cada pantalla: título y control de período → fila de KPIs → gráficos → tablas → acciones y recomendaciones.
- Espaciado en escala de 4: `space-1` (4) a `space-12` (48).
- Radios: `radius-md` (10) para controles, `radius-lg` (16) para tarjetas, `radius-full` para badges y pistas.

## Gráficos

- Barras finas con extremo redondeado de 4px apoyadas en cero; líneas de 2px con área al 12% y el último punto marcado.
- Un eje Y por gráfico. Grilla horizontal tenue, sin eje vertical dibujado.
- Leyenda arriba a la derecha cuando hay dos o más series; tooltip en cada barra o punto.
- Budget y objetivos siempre en punteada `chart-target`.

## Accesibilidad

- Contraste de texto ≥ 4.5:1 en los dos temas; los estados nunca dependen solo del color.
- Foco de teclado visible: anillo `focus` de 2px con 2px de separación.
- Objetivos táctiles de al menos 32px en tablas densas y 40px en el resto.
- Los gráficos tienen `aria-label` con la conclusión, y los datos también están en una tabla o tooltip.

## Cómo usarlo

Cargá `tokens.css` (variables `--canvas`, `--text-primary`, `--series-1`, `--space-5`, `--radius-lg`, `--font-sans`…) y `components/bundle.css`, que trae las clases `oto-*`: `oto-card`, `oto-kpi-strip`, `oto-kpi`, `oto-delta`, `oto-badge`, `oto-btn`, `oto-seg`, `oto-table`, `oto-bar`, `oto-meter`, `oto-nav`, `oto-input`, `oto-insight`, `oto-mono`, `oto-chart`, `oto-legend`. El tema oscuro se activa con `data-theme="dark"` en el elemento raíz. Los componentes son HTML y CSS; no requieren JavaScript.
