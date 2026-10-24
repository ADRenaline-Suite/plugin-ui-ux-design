# HEART

Fuente: Rodden, Hutchinson y Fu (2010), Measuring the User Experience on a Large Scale (CHI 2010). El proceso es objetivos, señales y métricas. Complementa la investigación con usuarios. No la sustituye. No es un test de usabilidad.

## Qué fija

Para un producto ya lanzado, qué objetivo de experiencia se persigue, qué señal lo mostraría y qué métrica lo contaría.

## Dimensiones

Solo las que el usuario quiera trabajar. Los nombres son los del artículo:

| Dimensión | Pregunta |
| --- | --- |
| Happiness | Qué actitud tiene quien lo usa |
| Engagement | Cuánto se involucra |
| Adoption | Cuántas personas nuevas empiezan a usarlo |
| Retention | Cuántas vuelven |
| Task success | Si completan la tarea |

## Cómo hacerlo

1. Si el producto no está lanzado, no inventes cifras de uso. Deja la entrega `proposed` y di que HEART espera al lanzamiento. Ofrece el plan de test de usabilidad si lo que quieren es medir la tarea ahora.
2. Cada fila tiene un objetivo (para qué), una señal (qué comportamiento o actitud lo delata) y una métrica (cómo se contaría). El umbral lo da el usuario. Si no hay umbral, la fila queda sin número y se pregunta.
3. No diseñes el evento, el código ni el tablero. La instrumentación es del área de frontend. No uses Core Web Vitals como si fueran HEART.
4. Task success de HEART no reemplaza la tasa de éxito de un test: uno es de producto en uso, el otro es de una sesión.

## Plantilla

```markdown
# HEART — <producto>

- Lanzado: sí | no (esta entrega queda proposed)
- Fuente: Rodden, Hutchinson y Fu (2010). No sustituye al test de usabilidad.
- Instrumentación: fuera de este plugin.

| Dimensión | Objetivo | Señal | Métrica | Umbral |
| --- | --- | --- | --- | --- |
```

## Ejemplo

Producto lanzado. Task success. Objetivo: quien paga sabe si el cargo quedó hecho. Señal: no vuelve a intentar el mismo pedido. Métrica: proporción de pedidos con un solo intento de cobro. El umbral lo escribe el usuario. Este archivo no define el evento de analítica.
