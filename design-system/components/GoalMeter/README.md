# GoalMeter

Compara lo conseguido contra un objetivo y contra el ritmo esperado a la fecha.

- Pista `chart-track`, relleno `series-1`, marca de ritmo de 2px en `chart-target`.
- El badge de arriba dice el estado en palabras: "En ritmo", "390 debajo del ritmo", "Objetivo cumplido".
- El pie dice el % conseguido y lo que falta por período. El medidor no se pinta de rojo: el estado lo lleva el badge.
- `role="img"` con un `aria-label` que diga los tres números.
