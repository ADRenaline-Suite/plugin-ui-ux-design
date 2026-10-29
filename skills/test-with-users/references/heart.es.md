<p align="right">Idioma:&emsp;<a href="heart.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Probar con personas](../SKILL.es.md)

# HEART

Fuente: Rodden, Hutchinson y Fu (2010), Measuring the User Experience on a Large Scale (CHI 2010). El proceso es metas, señales y métricas. Complementa la investigación con personas. No la sustituye. No es una prueba de usabilidad.

## Qué fija

Para un producto ya lanzado, qué meta de experiencia se persigue, qué señal la mostraría y qué métrica la contaría.

## Dimensiones

Solo las que la persona quiere trabajar. Los nombres son los del artículo:

| Dimensión | Pregunta |
| --- | --- |
| Happiness | Qué actitud tiene la persona que lo usa |
| Engagement | Cuánto se involucra |
| Adoption | Cuántas personas nuevas empiezan a usarlo |
| Retention | Cuántas vuelven |
| Task success | Si completan la tarea |

## Cómo hacerlo

1. Si el producto no está lanzado, no inventes cifras de uso. Deja la entrega `proposed` y di que HEART espera al lanzamiento. Ofrece el plan de la prueba de usabilidad si lo que quieren es medir la tarea ahora.
2. Cada fila tiene una meta (para qué), una señal (qué conducta o actitud la delata) y una métrica (cómo se contaría). La persona aporta el umbral. Si no hay umbral, la fila se queda sin número y preguntas.
3. No diseñes el evento, el código ni el panel. La instrumentación pertenece al área de frontend. No uses Core Web Vitals como si fueran HEART.
4. El éxito de la tarea de HEART no sustituye la tasa de éxito de una prueba: uno es el producto en uso, el otro es una sesión.

## Plantilla

```markdown
# HEART — <product>

- Launched: yes | no (this delivery stays proposed)
- Source: Rodden, Hutchinson, and Fu (2010). It does not replace the usability test.
- Instrumentation: outside this plugin.

| Dimension | Goal | Signal | Metric | Threshold |
| --- | --- | --- | --- | --- |
```

## Ejemplo

Producto lanzado. Task success. Meta: la persona que paga sabe si el cargo se realizó. Señal: no reintenta el mismo pedido. Métrica: proporción de pedidos con un solo intento de cargo. La persona escribe el umbral. Este archivo no define el evento de analítica.

## Prerrequisitos

- **Producto lanzado.** Si todavía no está lanzado, la entrega se queda `proposed`. No se inventan cifras de uso. El cierre dice que HEART espera al lanzamiento y que las cifras no se rellenaron. Comando anterior: `/uiux-usability-test`. Regenera con `/uiux-heart` cuando el producto esté lanzado.

## Indicaciones

En un mensaje:

```text
/uiux-heart of payment.
The product is already launched.
Task success. Goal: the person paying knows whether the charge went through.
Signal: they do not retry the same order.
Metric: share of orders with a single charge attempt. Threshold: <you supply it>.
```

En orden, omitiendo los que ya están cumplidos:

```text
/uiux-usability-test of pay with a card.
The task is pay with a card.
Five people who have already bought in the shop take part.
```

## Terminado

- Si el producto no está lanzado, la entrega es `proposed`, no se inventó ninguna cifra de uso, y la respuesta dice que HEART espera al lanzamiento.
- Cada fila que pidió la persona tiene una meta, una señal y una métrica. Un umbral que falta se queda en blanco. No se inventó ningún umbral.
- No se diseñó ningún evento, código, panel ni métrica de Core Web Vitals. El archivo dice que no sustituye la prueba de usabilidad.
