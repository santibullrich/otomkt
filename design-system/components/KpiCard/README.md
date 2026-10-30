# KpiCard

Muestra una métrica con su etiqueta, el valor grande, la variación y una línea de contexto; es la unidad básica de todo dashboard OTOMKT.

## Anatomía

- `.oto-kpi__label`: qué se mide, en `label` y `text-secondary`. Sin dos puntos.
- `.oto-kpi__value`: el número, estilo `num-kpi`, cifras tabulares. Siempre el número completo, sin K ni M.
- `.oto-kpi__foot`: un `Delta` + contra qué se compara ("vs. septiembre", "del budget anual"). Nunca un delta sin referencia.
- `.oto-kpi__spark` (opcional): la tendencia de los últimos 10 períodos, `series-1` con área al 12%.

## Reglas

- De 3 a 4 KPIs por fila, dentro de `.oto-kpi-strip` (una sola tarjeta dividida por hairlines), no 4 tarjetas sueltas.
- El color del delta dice si el cambio es bueno o malo, no si sube o baja: el CAC que sube es `is-bad`.
- Montos completos en dólares, sin abreviar (`US$ 911,000`, `US$ 1,200,000`); cantidades con coma de miles (`5,860`).
- Lo que la persona provee: etiqueta, valor ya formateado, delta y referencia.
