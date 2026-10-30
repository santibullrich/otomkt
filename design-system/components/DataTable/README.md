# DataTable

Tabla para comparar canales, campañas, facturas o perfiles con números alineados que se leen en columna.

- Números a la derecha con cifras tabulares; texto a la izquierda. Encabezados en `label` y `text-secondary`.
- Filas de 44px (12px arriba y abajo), divisores `border`, hover `surface-sunken`. Sin cebra.
- Agrupar con `.oto-group` (estilo `overline`) en vez de repetir la categoría en cada fila.
- La barra de ejecución (`.oto-bar`) muestra el % del budget: `series-1` hasta 100%, `negative` con `.is-over` cuando se pasa, y siempre el % escrito al lado.
- Total en `tfoot` con peso 600 y borde superior `border-strong`.
- Dentro de `.oto-table-wrap` para que en móvil scrollee la tabla y no la página. La primera columna nombra la fila; el resto se ordena de lo más leído a lo menos.
