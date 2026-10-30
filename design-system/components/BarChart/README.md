# BarChart

Compara una magnitud entre meses o categorías, con el budget u objetivo como línea de referencia.

- Barras finas (la mitad de la banda), extremo superior redondeado 4px y apoyadas en cero. Un solo color: `series-1`. Una barra que excede el budget pasa a `negative`.
- Referencia (budget, objetivo) en línea punteada `chart-target` de 1.5px.
- Grilla horizontal `chart-grid`, 3 o 4 líneas. Sin eje vertical dibujado. Textos de eje en `text-tertiary` 11px con cifras tabulares.
- Leyenda arriba a la derecha, nunca debajo. Tooltip por barra con mes, valor, referencia y diferencia.
- Un solo eje Y. Dos medidas de distinta escala van en dos gráficos.
