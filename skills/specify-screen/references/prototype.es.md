<p align="right">Idioma:&emsp;<a href="prototype.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Especificar una pantalla](../SKILL.es.md)

# Prototipo

Fuente: el orden de fidelidad de este plugin. El prototipo es el camino, no la especificación para construir.

## Qué fija

El camino de una tarea a través de las pantallas. Se abre en el navegador.

## Qué deja abierto

Medidas, tokens anotados y requisitos de accesibilidad. Eso se queda en el handoff.

## Cómo hacerlo

1. Parte de las pantallas ya dibujadas: el mock si está `accepted`; si no, el wireframe. Si no existe ninguno y este turno no trae los bloques, escribe un wireframe en este turno con la plantilla `task-blocks` (un bloque por subtarea, más la acción principal). Vuelve a dibujar cada pantalla en su SVG de prototipo y añade los enlaces. No reescribas un archivo de mock que ya existe.
2. Un SVG por pantalla. Enlaza con `<a href="<file.svg>">` alrededor de la zona que se activa. La ruta es relativa, al SVG hermano de la misma entrega. Sin JavaScript.
3. El primer SVG es el inicio del camino. El Markdown dice cuál abrir.
4. Cada destino existe. Si una acción no tiene pantalla, deja esa zona sin enlace y marca la entrega `proposed`. No inventes el destino.
5. Incluye el estado de error cuando la tarea puede fallar, como SVG propio si es otra vista, o como marco enlazado dentro de la misma pantalla si el error no cambia de archivo. El enlace «reintentar» vuelve a la pantalla donde están los datos.
6. El camino no es un diagrama UML. Si hace falta una máquina de estados, pídesela a `plugin-uml-diagrams`.

## Plantilla Markdown

```markdown
# Prototipo — <path>

- Tarea o caso de uso:
- Abrir primero: `<NNN>-prototype-<topic>-<screen>.svg`
- Origen visual: mock <N> | wireframe <N>

## Enlaces

| Pantalla | Acción | Destino |
| --- | --- | --- |
```

## Ejemplo

`001-prototype-pay-payment.svg` enlaza «Pagar» con `001-prototype-pay-result.svg`. «Reintentar» en el resultado de error vuelve a `001-prototype-pay-payment.svg`. El SVG de pago se abre en el navegador.

## Prerrequisitos

- **Tarea.** Un análisis de tareas `accepted`, o la tarea de este turno. Si no existe ninguno, escríbela con la plantilla `single-task`. Estado: `accepted`. Cámbiala con `/uiux-tasks`. Regenera este prototipo con `/uiux-prototype`.
- **Camino.** Un flujo de usuario `accepted`, o el camino de este turno. Si no existe ninguno, escríbelo con la plantilla `linear-three` (las mismas reglas de pantallas que el mock). Estado: `accepted`. Cámbialo con `/uiux-user-flow`. Regenera este prototipo con `/uiux-prototype`.
- **Pantalla dibujada.** Un mock `accepted`, o un wireframe `accepted`, o los bloques de la pantalla en este turno. Si no existe ninguno, escribe un wireframe en este turno con la plantilla `task-blocks`: un bloque por subtarea de la tarea, más la acción principal. Estado: `accepted`. Cámbialo con `/uiux-wireframe` o `/uiux-mock`. Regenera este prototipo con `/uiux-prototype`.

## Indicaciones

En un mensaje:

```text
/uiux-prototype del pago.
La tarea es pagar con tarjeta.
El camino es carrito, pago, resultado. Si el cobro falla, vuelve al pago con los datos todavía rellenos.
Pantalla de pago: monto, tarjeta y un botón Pagar. Sin kit de interfaz: haz primero el wireframe en este turno.
Si debe verse como el mock, incluye el kit.
Kit de interfaz: preset plain. Otros presets: dense, material-3, hig, fluent-2.
```

En orden, omitiendo los que ya se cumplieron:

```text
/uiux-tasks
La meta es pagar un pedido con tarjeta. Tareas: revisar el monto, ingresar la tarjeta, confirmar.
```

```text
/uiux-user-flow para pagar con tarjeta.
La tarea es pagar con tarjeta.
Pantallas: carrito, pago, resultado. Si el cobro falla, vuelve al pago con los datos todavía rellenos.
```

```text
/uiux-wireframe de la pantalla de pago.
La tarea es pagar con tarjeta.
Plataforma: web.
```

```text
/uiux-prototype del pago.
La tarea es pagar con tarjeta.
El camino es carrito, pago, resultado. Si el cobro falla, vuelve al pago con los datos todavía rellenos.
```

## Terminado

- El camino se abre en el navegador. Cada pantalla es su propio SVG. Los enlaces son `<a href>` a un SVG hermano de este mismo `<NNN>`. No hay JavaScript. Un wireframe escrito en este turno a partir de la plantilla `task-blocks` se nombra bajo Assumed.
- El Markdown nombra el archivo que se abre primero. Cada destino enlazado existe. Una zona sin destino queda sin enlace y la entrega queda en `proposed`.
- El error de una tarea que puede fallar está incluido, y reintentar vuelve a la pantalla que tiene los datos.
- Las medidas, los tokens y las notas de accesibilidad están ausentes. No es un diagrama UML. No se reescribió el archivo de mock o de wireframe.
