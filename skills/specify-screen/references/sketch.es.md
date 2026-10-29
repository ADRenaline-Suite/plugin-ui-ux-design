<p align="right">Idioma:&emsp;<a href="sketch.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Especificar una pantalla](../SKILL.es.md)

# Sketch

Fuente: el orden de fidelidad de este plugin. El sketch fija la idea. Todavía no es la especificación.

## Qué fija

La idea de la pantalla y sus bloques. Un bloque es una zona con un nombre (monto, formulario, acción).

## Qué deja abierto

Medida, color, texto final y estilo.

## Cómo hacerlo

1. Un SVG por pantalla, en escala de grises (`#f4f4f4`, `#ffffff`, trazo `#222`). Rectángulos y etiquetas. Sin iconos de marca y sin la tipografía final.
2. Dibuja el estado ideal. Agrega un marco por cada estado que cambia los bloques. El Markdown lista ideal, vacío, carga, parcial, error y éxito, y dice cuáles no aplican.
3. Las etiquetas son las palabras que la persona ya usó. Si una etiqueta todavía no existe, usa el nombre de la subtarea, no un texto de interfaz inventado.
4. No anotes píxeles. No enlaces pantallas: eso es el prototipo.

## Plantilla Markdown

```markdown
# Sketch — <screen>

- Tarea o caso de uso:
- Plataforma:
- Estados: ideal, vacío, carga, parcial, error, éxito. No aplican: <cuáles, y por qué>
- SVG: `<NNN>-sketch-<topic>-<screen>.svg`
- Dejado abierto: medida, color, texto final
```

## Ejemplo

Pantalla de pago. Bloques del estado ideal: monto, datos de la tarjeta, acción «Pagar». Estado de error: los mismos bloques más un aviso, y los datos de la tarjeta siguen rellenos. Vacío no aplica: el monto llega del pedido.

## Prerrequisitos

- **Tarea.** Un análisis de tareas `accepted`, o la tarea de este turno. Si no existe ninguno, escribe el análisis de tareas en este turno con la plantilla `single-task` (una tarea nombrada a partir del pedido; las subtareas son ingresar los datos, confirmar y ver el resultado). Estado de ese archivo: `accepted`. Este sketch se queda `accepted`. Cambia la tarea con `/uiux-tasks`. Regenera este sketch con `/uiux-sketch`.

## Indicaciones

En un mensaje:

```text
/uiux-sketch de la pantalla de pago.
La tarea es pagar con tarjeta.
```

En orden, omitiendo los que ya se cumplieron:

```text
/uiux-tasks
La meta es pagar un pedido con tarjeta. Tareas: revisar el monto, ingresar la tarjeta, confirmar.
```

## Terminado

- La tarea o el caso de uso está nombrado, a partir de un análisis accepted, de este turno o de la plantilla `single-task`. Cuando se usó la plantilla, Assumed lo dice. El SVG está en escala de grises, un archivo por pantalla, con rectángulos y etiquetas. Sin iconos de marca, sin tipografía final, sin medidas en píxeles, sin enlaces a otras pantallas.
- Están listados ideal, vacío, carga, parcial, error y éxito. Un estado que no aplica dice por qué. Un estado que cambia los bloques tiene un marco. El error conserva lo que se escribió.
- Las etiquetas son palabras que la persona ya usó, o el nombre de la subtarea. Sin texto de interfaz nuevo.
- Lo dejado abierto sigue siendo medida, color y texto final.
