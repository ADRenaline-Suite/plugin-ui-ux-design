---
name: define-appearance
description: Fija la dirección visual de la interfaz en un moodboard y el kit de interfaz con sus tokens. Si no se selecciona un kit, se usa el preset plain. Úsalo cuando alguien pregunta cómo se ve la interfaz, o pide los componentes o los tokens de diseño.
---

<p align="right">Idioma:&emsp;<a href="SKILL.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../README.es.md)

# Definir la apariencia

Produce el moodboard o el kit de interfaz. El kit gobierna el mock y el handoff. Si el producto ya tiene un kit, parte de ese y no inventes otro. Si no lo tiene, usa un preset de [references/presets.es.md](references/presets.es.md). Cuando no se selecciona ninguno, el preset es `plain`.

Fuente de los tokens: Design Tokens Format Module 2025.10 y Color Module 2025.10 (W3C Design Tokens Community Group, Final Community Group Report, 28 de octubre de 2025). Son estables y no son un estándar del W3C. No cites un borrador posterior. Los componentes siguen el kit de interfaz del producto. Atomic Design (Brad Frost) es solo un modelo de agrupación posible cuando el producto todavía no tiene el suyo. El moodboard no tiene un estándar único en las fuentes: registra referencias, color, tipo y tono aplicados a pantallas.

## Antes de escribir

1. Si este turno viene de un comando, la pieza ya está fijada.
2. Lee solo `references/<piece>.md` de la pieza que pidieron. No leas referencias de otro skill. Para el kit de interfaz, lee también `references/presets.md` y el preset que selecciona.
3. Plataforma: web, o la guía nativa (Apple Human Interface Guidelines, Material Design 3, Fluent 2). Si la guía contradice al kit, dilo y sigue el kit.
4. Temas: solo los que el producto tiene (light, dark, variantes de marca). No añadas un tema. Los cinco presets son solo light.
5. Para el kit de interfaz, sigue `references/presets.md`. Un kit `accepted` del producto gana. Los valores escritos en este turno ganan a un preset. Un preset nombrado se copia tal cual. Si no se selecciona ninguno, usa `plain` y dilo, y nombra `dense`, `material-3`, `hig` y `fluent-2`. No inventes una paleta.
6. No dibujes el flujo ni audites WCAG. No escribas HTML ni código de interfaz.

| Pedido | Pieza | Referencia |
| --- | --- | --- |
| Dirección visual | moodboard | [references/moodboard.es.md](references/moodboard.es.md) |
| Componentes, tokens y reglas | kit de interfaz | [references/ui-kit.es.md](references/ui-kit.es.md) |

## Idioma

Las instrucciones siguen en inglés. Escribe el artefacto en el idioma del pedido. Si el pedido nombra un idioma, usa ese. Si no, usa el idioma en el que está escrito el pedido. Conserva los nombres que la persona ya usó. Traduce los encabezados de la plantilla de la referencia y mantén los mismos campos. El tipo en el nombre del archivo sigue el id de pieza en inglés (`moodboard`, `ui-kit`). `$description` de un token sigue el idioma del artefacto. Las columnas de `STATUS.md` siguen `N`, `archivo`, `estado`, `sustituye`, `notas`. La respuesta usa ese mismo idioma, incluido el bloque Assumed cuando se aplicó una plantilla y las tres partes cuando un prerrequisito todavía detiene la entrega. Los prompts de la referencia están en inglés: muéstralos en el idioma del pedido y conserva los nombres de comando.

## Cuando falta un prerrequisito

Un prerrequisito se cumple con un archivo `accepted` de esa pieza, o con el dato escrito en este turno. La referencia de la pieza nombra cada prerrequisito, la plantilla que lo llena, el estado que esa plantilla deja, el comando que lo sustituye y el comando que regenera esta pieza.

Usa las fuentes en este orden: un archivo `accepted`, luego el dato escrito en este turno, luego la plantilla. No apliques una plantilla cuando existe una fuente más alta.

Cuando la referencia da una plantilla, escribe los archivos. En el mismo turno, escribe también las piezas anteriores que esa referencia dice escribir, cada una con su `<NNN>`, y solo esas. No escribas una pieza que este pedido no necesita.

En el Markdown, añade un encabezado `Assumed`, traducido al idioma del pedido. Una línea por plantilla: el hueco, el id de la plantilla y el valor usado. Las `notas` de `STATUS.md` de esa fila listan los ids de plantilla (`assumed: plain, linear-three`).

Después de la carpeta, los archivos, el `N` y el estado, cierra con este bloque, en el idioma del pedido. Una línea por plantilla. Omite el bloque cuando no se asumió nada.

```text
Assumed automatically (there was no accepted file and this message did not bring it):
- <gap>: template <id> (<value used>). Change it with <command>. Regenerate with <command>.
```

Una plantilla que la referencia marca `accepted` deja la entrega `accepted`. Una plantilla que la referencia marca `proposed` la deja `proposed`. Cada línea dice que el valor es un punto de partida, tomado automáticamente, y que no es un dato de la persona, de una investigación ni de otro plugin.

Si la referencia no da plantilla y no se detiene, escribe el artefacto como dice y, al cerrar, nombra el comando que llena el hueco. Di que el blanco se dejó a propósito y que no se inventó nada para él.

Dos comprobaciones siguen deteniendo la entrega. No escribas archivos de esa pieza. Responde solo con esto, en el idioma del pedido:

1. «Falta:» y los nombres que faltan.
2. «En un mensaje:» y el único prompt de la referencia. Rellénalo con lo que la persona ya dijo. Donde falte un valor, deja el hueco (`#…`, `<task>`).
3. «O, en este orden:» y los comandos anteriores que todavía faltan, en el orden de la referencia, cada uno con su prompt. Omite este bloque si no hay un comando anterior. Omite los comandos cuyo prerrequisito ya está cumplido.

Esas dos son una captura o una URL para `/uiux-implementation-review`, y un kit de interfaz del producto para `/uiux-consistency` (un kit `accepted`, o tokens en este turno). La consistencia también se detiene cuando no existe una pantalla `accepted` y este turno no describe una. No dibujes una pantalla para compararla, y no compares contra el preset `plain`.

No inventes texto, notas de accesibilidad, filas de prueba, cifras de HEART, una decisión elegida, el nombre o la biografía de una persona, ni una paleta. Esos huecos se quedan en blanco, o usan la plantilla que la referencia nombra, y la entrega se queda en el estado que la referencia nombra.

## Entrega

La carpeta es `ui-ux-design/` en la raíz del proyecto. Si `.cursor/adrenaline.json` tiene `outputDirs["plugin-ui-ux-design"]` con una ruta relativa, sin `..` y no absoluta, usa esa ruta. Si falta el archivo, la clave o una ruta válida, usa `ui-ux-design/` y, en el último caso, dilo. Crea la carpeta si no existe. No escribas fuera de ella. No elijas la carpeta de otro plugin.

`<NNN>` es el siguiente entero libre, de tres dígitos, y no se reutiliza. El moodboard es `<NNN>-moodboard-<topic>.md` más un SVG por pantalla de ejemplo, `<NNN>-moodboard-<topic>-<screen>.svg`. El kit de interfaz es `<NNN>-ui-kit-<topic>.md` y `<NNN>-ui-kit-<topic>.tokens.json`. La misma entrega, el mismo `<NNN>`.

Mantén `<folder>/STATUS.md` con las columnas `N`, `archivo`, `estado`, `sustituye` y `notas`. Los estados son `proposed`, `accepted`, `deprecated` y `superseded`. Al elegir qué seguir, el orden es `accepted`, luego `proposed`, luego `deprecated`, luego `superseded`.

Mantén `<folder>/ORIGIN.json` junto a `STATUS.md`. No es un archivo `<NNN>` y no tiene fila en `STATUS.md`. Escríbelo cuando se crea la carpeta. En una entrega posterior, vuelve a escribirlo solo si falta o si un campo difiere. Los campos son `suite` `ADRenaline-Suite`, `plugin` `plugin-ui-ux-design`, `repository` `https://github.com/ADRenaline-Suite/plugin-ui-ux-design` y `convention` `adr-001`. El marcador nombra la carpeta. No dice que cada archivo de dentro siga sin cambios.

Si el tema ya tiene un archivo:

- La persona pide cambiar esa entrega: edita los mismos archivos, conserva el `<NNN>` y déjalo `accepted`.
- La persona pide un reemplazo o una decisión nueva sobre el mismo tema: toma el siguiente `<NNN>`, marca la fila anterior `superseded` (`sustituye` apunta al `N` nuevo) y deja la fila nueva `accepted`.
- En otro caso: el siguiente `<NNN>` y una fila `accepted`.

Una entrega nueva es `accepted`. Es `proposed` si la persona pide un borrador, el kit no cubre los temas que el producto ya tiene, o el moodboard usó la plantilla `neutral`. Cuando el kit viene de un preset, `notas` nombra el id del preset (`plain`, `dense`, `material-3`, `hig`, `fluent-2`). Al cerrar, di la carpeta, los archivos, el `N`, el estado y, si se usó `plain` porque no se seleccionó ninguno, los otros cuatro presets en el bloque Assumed.

## Terminado

Antes de cerrar, evalúa esta lista y la lista `## Terminado` de la referencia de esta situación. Un comando fija la situación: usa la referencia que ese comando nombra. Cada ítem es cierto, o corriges la entrega en este turno. No dejes un archivo que falle un ítem. No lo marques `accepted` mientras un ítem falle. Una plantilla que la referencia nombra se aplica y se registra bajo Assumed; la entrega usa el estado que esa referencia nombra. Un prerrequisito que todavía detiene la entrega no es una lista fallida: sigue «Cuando falta un prerrequisito» y no escribas archivos de esa pieza.

- La situación de este turno es la única que se escribe, salvo que el pedido pidiera dos. Cada entrega tiene su `<NNN>`.
- Los archivos están solo en la carpeta de salida, nombrados como dice Entrega. `<NNN>` no se reutiliza. `STATUS.md` coincide con los archivos y con el estado que esta situación permite. Un hueco que la referencia deja como `proposed` se queda `proposed`.
- `ORIGIN.json` está en la carpeta de salida. Sus cuatro campos coinciden con este plugin. No tiene fila en `STATUS.md`.
- El idioma del artefacto coincide con el pedido. Las columnas de `STATUS.md` siguen `N`, `archivo`, `estado`, `sustituye`, `notas`.
- Cada campo que la plantilla exige está lleno. No queda un marcador (`#…`, `<task>`, `TBD`, lorem ipsum). Un campo que la referencia manda dejar en blanco hasta que lleguen los datos está en blanco a propósito, y el estado es el que la referencia nombra.
- No se añadió nada que este skill prohíbe. La referencia nombra qué queda fuera.
- La respuesta nombra la carpeta, los archivos, el `N` y el estado. Si se aplicó una plantilla, la respuesta termina con el bloque Assumed, una línea por plantilla, nombrando el comando que lo cambia y el comando que regenera esta pieza. Un blanco dejado a propósito nombra el comando que lo llena.

## Ejemplo

Entrada: «Kit de interfaz de la tienda.» Nada más. Todavía no hay un kit `accepted`.

Salida: `012-ui-kit-shop.md` y `012-ui-kit-shop.tokens.json`, copiados del preset `plain`. La respuesta dice que se usó `plain` porque no se seleccionó ninguno, y nombra `dense`, `material-3`, `hig` y `fluent-2`.

Entrada: «Kit de interfaz mínimo de la tienda, tema claro. Azul de acción #0066cc, fondo blanco, texto casi negro, espacio de 16 px.»

Salida: los mismos dos archivos, a partir de esos valores, no de un preset. Los valores no se corrigen hacia `plain`.
