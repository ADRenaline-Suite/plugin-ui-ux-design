<p align="right">Idioma:&emsp;<a href="handoff.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Especificar una pantalla](../SKILL.es.md)

# Handoff

Fuente: la práctica de este plugin. No hay un estándar único de handoff. Basta para construir la pantalla sin adivinar: medidas, estados, texto, comportamiento por tamaño de ventana y notas de accesibilidad. La revisión de implementación usa esta entrega como criterio, junto con el kit de interfaz.

## Qué fija

Todo lo que quien construye la pantalla tendría que adivinar.

## Qué deja abierto

Nada de la pantalla. El código queda fuera de este plugin.

## Cómo hacerlo

1. Parte del mock `accepted`. Si no hay uno, escribe la tarea (`single-task` si hace falta), el flujo de usuario (`linear-three` si hace falta), el kit (preset `plain` si no se selecciona ninguno) y el mock en este turno, y después el handoff. El handoff se queda `proposed` cuando ese mock se asumió. El SVG del handoff es el mock con acotaciones: líneas de cota (trazo discontinuo) y el valor medido. La unidad es la del kit de interfaz (`px` o `rem` en los tokens). No inventes una medida que el kit no tiene: si falta, anótala como hueco y deja la entrega en `proposed`.
2. El Markdown describe el comportamiento por tamaño de ventana: qué se muestra, qué se apila, qué se mueve. Repite un marco en el SVG solo cuando cambia la disposición.
3. Texto: pídeselo a `plugin-ux-writing` (microtextos, errores, vacío, carga, éxito, confirmaciones). Si la persona ya lo pegó, úsalo y cita el origen. No lo escribas aquí. Si falta, la entrega se queda `proposed` y lista los huecos.
4. Notas de accesibilidad: pídeselas a `plugin-accessibility` (orden de foco, encabezados, regiones, nombres accesibles, texto alternativo). Inclúyelas tal como se dieron, cada una con el criterio WCAG que ese plugin nombró. No corras la auditoría. Si faltan, la entrega se queda `proposed`.
5. Estados: ideal, vacío, carga, parcial, error y éxito; sin permiso y sin conexión cuando aplican. En el error, lo que se escribió se conserva. Cada estado dice qué es visible y qué hace la acción principal.
6. Comprobación de contenido: una cadena larga y la expansión al traducir. RTL si el producto lo necesita. La traducción en sí queda fuera de alcance.
7. Los temas del producto, con los tokens de cada uno.

## Plantilla Markdown

```markdown
# Handoff — <screen>

- Tarea o caso de uso:
- Kit de interfaz:
- Mock de origen:
- Plataforma y tamaños de ventana:
- Temas:
- SVG con acotaciones: `<NNN>-handoff-<topic>-<screen>.svg`
- Origen del texto:
- Origen de las notas de accesibilidad:
- Estado de esta entrega: accepted | proposed (falta: )

## Comportamiento por tamaño de ventana

| Tamaño de ventana | Qué cambia |
| --- | --- |

## Estados

| Estado | Qué es visible | Acción principal | Conserva lo escrito |
| --- | --- | --- | --- |

## Texto

| Elemento | Texto | Origen |
| --- | --- | --- |

## Accesibilidad

| Nota | Elemento | Criterio |
| --- | --- | --- |

## Medidas

| Elemento | Medida | Token |
| --- | --- | --- |
```

## Ejemplo

Handoff de pago. La distancia entre el monto y el formulario es el token `space.stack`. El error muestra el texto que dio `plugin-ux-writing` y no borra la tarjeta. El orden de foco es el que anotó `plugin-accessibility`. Si ese plugin no está en la sesión, la nota se le pide a la persona y, hasta que llegue, la fila de `STATUS.md` se queda `proposed`.

## Prerrequisitos

- **Mock.** Un mock `accepted`, o uno escrito en este turno. Si falta, escribe primero la tarea, el camino, el kit y el mock. La tarea es la plantilla `single-task` cuando no está dicha. El camino es la plantilla `linear-three` cuando no está dicho. El kit es el kit `accepted`, el preset nombrado, los tokens de este turno o el preset `plain`. Estado de este handoff: `proposed` cuando ese mock se asumió en este turno, y también cuando faltan el texto o las notas. Cambia el mock con `/uiux-mock`. Regenera este handoff con `/uiux-handoff`.
- **Kit de interfaz.** Un kit `accepted`, un preset nombrado o los tokens de este turno. Si no llega ninguno, escribe el preset `plain` con `define-appearance` antes del handoff. Una medida que el kit no tiene sigue siendo un hueco. Estado: `accepted` para el kit. Cámbialo con `/uiux-ui-kit`. Regenera este handoff con `/uiux-handoff`.
- **Texto.** Pegado por quien pide el handoff, o dado por `plugin-ux-writing`. No hay plantilla. La celda se queda en blanco. La entrega se queda `proposed`. No se inventó nada. Pega el texto y regenera con `/uiux-handoff`.
- **Notas de accesibilidad.** Pegadas por quien pide el handoff, o dadas por `plugin-accessibility`. No hay plantilla. La celda se queda en blanco. La entrega se queda `proposed`. No se inventó nada. Pega las notas y regenera con `/uiux-handoff`.

## Indicaciones

En un mensaje:

```text
/uiux-handoff de la pantalla de pago.
La tarea es pagar con tarjeta.
El camino es carrito, pago, resultado. Si el cobro falla, vuelve al pago con los datos todavía rellenos.
Kit de interfaz: preset plain. Otros presets: dense, material-3, hig, fluent-2.
Texto: pégalo aquí, o se le pide a plugin-ux-writing y el handoff se queda en proposed.
Notas de accesibilidad: pégalas aquí, o se le piden a plugin-accessibility y el handoff se queda en proposed.
```

El kit de interfaz no está en este orden. Cuando falta, el preset `plain` se escribe con el handoff.

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
/uiux-mock de la pantalla de pago.
La tarea es pagar con tarjeta.
El camino es carrito, pago, resultado. Si el cobro falla, vuelve al pago con los datos todavía rellenos.
```

```text
/uiux-handoff de la pantalla de pago.
La tarea es pagar con tarjeta.
El camino es carrito, pago, resultado. Si el cobro falla, vuelve al pago con los datos todavía rellenos.
```

## Terminado

- El SVG es el mock accepted más las acotaciones. Cada medida es un token que el kit tiene. Una medida que falta es un hueco, y la entrega queda en `proposed`.
- Están las tablas de comportamiento por tamaño de ventana, estados, texto, accesibilidad y medidas. El error conserva lo que se escribió. Un estado que no aplica dice por qué.
- El texto y las notas de accesibilidad se citan de la persona, de `plugin-ux-writing` o de `plugin-accessibility`. Si falta alguno, la celda se queda en blanco, la entrega queda en `proposed` y se listan los huecos. No se escribieron aquí y no se auditó WCAG. Un mock asumido en este turno también deja el handoff en `proposed`, y Assumed nombra las plantillas.
- Las comprobaciones de cadena larga y de expansión al traducir están en el archivo. RTL se incluye solo si el producto lo necesita. Sin HTML.
