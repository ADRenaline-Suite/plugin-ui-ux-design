<p align="right">Idioma:&emsp;<a href="mock.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Especificar una pantalla](../SKILL.es.md)

# Mock

Fuente: el kit de interfaz del producto. Los tokens escritos en este turno siguen el Design Tokens Format Module 2025.10; el archivo de tokens lo produce `define-appearance`, no este manual. Tamaños de ventana: los del producto, o Material Design 3.

## Qué fija

La apariencia visual de una pantalla, con los tokens del kit de interfaz y por tema.

## Qué deja abierto

El camino hacia otras pantallas y la especificación para construir (medidas anotadas, comportamiento, accesibilidad). Eso es el prototipo y el handoff.

## Cómo hacerlo

1. El camino tiene que estar decidido: un flujo de usuario `accepted`, o el camino de este turno. Si no existe ninguno, escribe el flujo de usuario en este turno con la plantilla `linear-three`.
2. Usa los tokens del kit de interfaz `accepted`. Si no hay kit, escríbelo con `define-appearance` y después el mock. Un preset nombrado o los tokens de este turno lo eligen. Si no llega ninguno, el kit es el preset `plain`. No inventes una paleta.
3. Un marco por tema en el estado ideal (claro, oscuro, variante de marca), solo los temas que el producto tiene. No añadas modo oscuro si el producto no lo tiene.
4. Texto real, de la persona o de `plugin-ux-writing`. Si falta el texto final, usa las etiquetas ya acordadas y dilo en el Markdown; no escribas microtextos nuevos.
5. Dibuja los estados que cambian la apariencia. El error conserva lo que se escribió y muestra qué falló.
6. El SVG usa los colores del kit en `fill` y `stroke`. Todavía sin acotaciones: las dimensiones pertenecen al handoff.

## Plantilla Markdown

```markdown
# Mock — <screen>

- Tarea o caso de uso:
- Camino decidido: <archivo de flujo de usuario, o "descrito en este turno">
- Kit de interfaz: <archivo accepted> | preset <id> | tokens de este turno
- Temas:
- Plataforma y tamaños de ventana:
- Estados dibujados:
- Origen del texto: quien pide | plugin-ux-writing | etiquetas acordadas, el texto final todavía falta
- SVG: `<NNN>-mock-<topic>-<screen>.svg`
```

## Ejemplo

Mock de pago en el tema claro, con el color de acción y el tipo del kit de la tienda. El estado de error usa el color de error del kit, el aviso «El cobro no se realizó» si `plugin-ux-writing` ya lo dio, y los campos de la tarjeta siguen rellenos. El camino al resultado está en el flujo de usuario accepted; este mock no lo enlaza.

## Prerrequisitos

- **Tarea.** Un análisis de tareas `accepted`, o la tarea de este turno. Si no existe ninguno, escríbela en este turno con la plantilla `single-task`. Estado: `accepted`. Cámbiala con `/uiux-tasks`. Regenera este mock con `/uiux-mock`.
- **Camino.** Un flujo de usuario `accepted`, o el camino de este turno. Si no existe ninguno, escribe el flujo de usuario en este turno con la plantilla `linear-three`: las pantallas nombradas en el pedido, en ese orden; una sola pantalla se vuelve esa pantalla y luego un resultado, y el error vuelve a ella con los datos conservados; si no se nombra ninguna pantalla, queda formulario, espera, resultado. Un pago o una acción irreversible (pagar, borrar, enviar, publicar, comprar, transferir) inserta una pantalla de confirmación antes del resultado. Estado: `accepted`. Cámbialo con `/uiux-user-flow`. Regenera este mock con `/uiux-mock`.
- **Kit de interfaz.** Un kit `accepted`, un preset nombrado o los tokens de este turno. Si no llega ninguno, escribe el preset `plain` con `define-appearance` y después el mock. Estado: `accepted`. Cámbialo con `/uiux-ui-kit`. Regenera este mock con `/uiux-mock`. No inventes una paleta.

## Indicaciones

En un mensaje:

```text
/uiux-mock de la pantalla de pago.
La tarea es pagar con tarjeta.
El camino es carrito, pago, resultado. Si el cobro falla, vuelve al pago con los datos todavía rellenos.
Kit de interfaz: preset plain. Otros presets: dense, material-3, hig, fluent-2.
```

El kit de interfaz no está en este orden. Cuando falta, el preset `plain` se escribe con el mock.

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

## Terminado

- El camino es un flujo de usuario accepted, el camino de este turno, o la plantilla `linear-three` escrita en este turno. La línea del kit de interfaz nombra un kit accepted, un id de preset o tokens de este turno. Si no se seleccionó ninguno, el kit es el preset `plain`, escrito por `define-appearance` antes de este archivo. No se inventó una paleta. Cada plantilla usada queda bajo Assumed.
- Los temas son solo los que el producto tiene. Se dibujan los estados que cambian la apariencia. El error conserva lo que se escribió y muestra qué falló.
- El texto viene de la persona, de `plugin-ux-writing` o de etiquetas acordadas, y la línea de origen dice cuál. Sin microtextos nuevos.
- El SVG usa colores del kit. No hay acotaciones ni enlaces a otras pantallas.
