<p align="right">Idioma:&emsp;<a href="wireframe.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Especificar una pantalla](../SKILL.es.md)

# Wireframe

Fuente: el orden de fidelidad de este plugin. Tamaños de ventana: los del producto, o Material Design 3 si el producto no tiene.

## Qué fija

La jerarquía y la disposición de una pantalla, por tamaño de ventana. Qué va primero, qué se apila y qué se parte en columnas.

## Qué deja abierto

El estilo visual: color de marca, tipografía final, elevación.

## Cómo hacerlo

1. Escala de grises, igual que el sketch. Esta vez los bloques tienen jerarquía: un título, el contenido, la acción principal. El orden de lectura es de arriba abajo y, en los idiomas de izquierda a derecha, de izquierda a derecha.
2. El Markdown describe la disposición de cada tamaño de ventana. El SVG vuelve a dibujar un tamaño de ventana solo cuando cambia la disposición.
3. Incluye una cadena larga en al menos un bloque, para ver el salto de línea. Si una cadena corta puede traducirse, reserva espacio para 200–300% (W3C Internationalization, Text size in translation). Si el producto necesita RTL, un marco con `direction="rtl"` en el grupo SVG.
4. Lista los estados. Dibuja los que cambian la disposición, en especial el error, que conserva lo que se escribió.
5. Todavía sin color de marca y sin medidas para construir. Las medidas pertenecen al handoff.

## Plantilla Markdown

```markdown
# Wireframe — <screen>

- Tarea o caso de uso:
- Plataforma:
- Tamaños de ventana: <los del producto, o Material Design 3>
- Estados, y cuáles cambian la disposición:
- Cadena larga de prueba:
- Expansión al traducir:
- RTL: sí, en el marco <nombre> | no aplica
- SVG: `<NNN>-wireframe-<topic>-<screen>.svg`

## Disposición por tamaño de ventana

| Tamaño de ventana | Disposición |
| --- | --- |
```

## Ejemplo

Pago, web, Material Design 3. Compact: monto, formulario y «Pagar» en una columna. Expanded: resumen a la izquierda y formulario a la derecha. Error añade el aviso encima del formulario y no borra el número de tarjeta. Large y extra-large solo ensanchan la disposición expanded; el Markdown lo dice y el SVG no los repite.

## Prerrequisitos

- **Tarea.** Un análisis de tareas `accepted`, o la tarea de este turno. Si no existe ninguno, escribe el análisis de tareas en este turno con la plantilla `single-task`. Estado de ese archivo: `accepted`. Este wireframe se queda `accepted`. Cambia la tarea con `/uiux-tasks`. Regenera este wireframe con `/uiux-wireframe`.

## Indicaciones

En un mensaje:

```text
/uiux-wireframe de la pantalla de pago.
La tarea es pagar con tarjeta.
Plataforma: web.
```

En orden, omitiendo los que ya se cumplieron:

```text
/uiux-tasks
La meta es pagar un pedido con tarjeta. Tareas: revisar el monto, ingresar la tarjeta, confirmar.
```

## Terminado

- La jerarquía y la disposición están fijas por tamaño de ventana. La tarea está nombrada, incluida la plantilla `single-task` cuando se escribió en este turno. Los tamaños de ventana son los del producto, o Material Design 3 si el producto no tiene. Un tamaño de ventana que solo crece se nombra en el Markdown y no se vuelve a dibujar.
- El SVG se queda en escala de grises. Al menos un bloque tiene una cadena larga. La expansión al traducir se reserva cuando una cadena corta puede traducirse. RTL es un marco solo si el producto lo necesita.
- Se dibujan los estados que cambian la disposición, incluido el error, que conserva lo que se escribió. El color de marca y las medidas para construir están ausentes.
