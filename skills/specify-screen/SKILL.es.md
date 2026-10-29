---
name: specify-screen
description: Produce el sketch, el wireframe, el mock, el prototipo o el handoff de una pantalla, de lo menos concreto a lo más concreto. Úsalo cuando alguien pide dibujar o especificar una pantalla para poder construirla.
---

<p align="right">Idioma:&emsp;<a href="SKILL.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../README.es.md)

# Especificar una pantalla

Produce una pantalla. El handoff es la pieza desde la cual se puede construir la pantalla sin adivinar. Este skill cierra esa entrega.

Fuente: ISO 9241-210:2019 (producir soluciones). Estados: Scott Hurff, The UI Stack, más el éxito y, cuando aplican, sin permiso y sin conexión. Tamaños de ventana de respaldo: Material Design 3 (compact &lt;600 dp, medium 600–839, expanded 840–1199, large 1200–1599, extra-large ≥1600), según el ancho de la ventana. Plataforma nativa: Apple Human Interface Guidelines, Material Design 3 o Fluent 2. Expansión del texto: W3C Internationalization, Text size in translation. El texto lo escribe `plugin-ux-writing`. Las notas de accesibilidad las especifica `plugin-accessibility`.

## Antes de dibujar

1. Si este turno viene de un comando, la pieza ya está fija. Si no, elige una de la tabla.
2. Lee solo `references/<piece>.md` de la pieza que pidieron. No leas referencias de otro skill. Excepción: si no hay un kit `accepted`, escribe el kit con `define-appearance` antes del mock o del handoff. Ese skill lee `references/presets.md`. Un preset nombrado o los tokens de este turno eligen el kit. Si no llega ninguno, el kit es el preset `plain`.
3. Cada pantalla nombra la tarea de la persona o el caso de uso que cubre. Si la tarea no está dicha, escríbela en este turno con la plantilla `single-task` y regístrala bajo Assumed.
4. El orden es sketch, wireframe, mock, prototipo, handoff. El sketch y el wireframe siguen siendo opcionales. Escribe una pieza anterior en este turno solo cuando la referencia de la pieza que pidieron dice que esa pieza es necesaria y falta.
5. El mock necesita un camino: un flujo de usuario `accepted`, el camino de este turno, o la plantilla `linear-three` escrita como flujo de usuario en este turno. Si no hay un kit de interfaz `accepted`, escribe uno con `define-appearance` antes del mock: el preset nombrado, los tokens de este turno, o `plain` cuando no se selecciona ninguno. No inventes una paleta. Registra cada plantilla bajo Assumed.
6. Plataforma y tamaños de ventana: los del producto, si existen. Si no hay tamaños de ventana, usa Material Design 3. Si el producto es nativo, sigue la guía de esa plataforma. Si esa guía contradice el kit de interfaz, dilo y sigue el kit.
7. Contenido real, lo que la persona ya dio o lo que dio `plugin-ux-writing`. Sin lorem ipsum. En el wireframe, el mock y el handoff, prueba una cadena larga y la expansión al traducir (una cadena de hasta 10 caracteres puede crecer 200–300%). Si el producto usa escritura de derecha a izquierda, incluye un marco RTL. No traduzcas el producto: la traducción en sí queda fuera de alcance.
8. Temas: si el producto tiene modo claro, modo oscuro o variantes de marca, el mock y el handoff los cubren.
9. Estados de cada pantalla: ideal, vacío, carga, parcial, error y éxito. Cuando aplican, también sin permiso y sin conexión. En el error, lo que la persona escribió se conserva. Si un estado no aplica, el Markdown dice por qué.
10. Un diagrama de actividad o una máquina de estados de la pantalla se le pide a `plugin-uml-diagrams`. No lo dibujes aquí.
11. No escribas HTML ni código de interfaz.

| Pedido | Pieza | Referencia |
| --- | --- | --- |
| Idea y bloques | sketch | [references/sketch.es.md](references/sketch.es.md) |
| Jerarquía y disposición | wireframe | [references/wireframe.es.md](references/wireframe.es.md) |
| Apariencia visual | mock | [references/mock.es.md](references/mock.es.md) |
| Camino entre pantallas | prototype | [references/prototype.es.md](references/prototype.es.md) |
| Especificación para construir | handoff | [references/handoff.es.md](references/handoff.es.md) |

| Pieza | Qué fija | Qué deja abierto |
| --- | --- | --- |
| Sketch | Idea y bloques | Medida, color, texto final |
| Wireframe | Jerarquía y disposición por tamaño de ventana | Estilo visual |
| Mock | Apariencia visual de una pantalla, por tema | Interacción entre pantallas |
| Prototipo | Camino que se abre en el navegador | Especificación para construir |
| Handoff | Medidas, estados, texto, comportamiento, notas de accesibilidad | — |

## SVG

Uno por pantalla. SVG 1.1, con `xmlns="http://www.w3.org/2000/svg"`, un `viewBox` y un rectángulo de fondo. Texto en `<text>`, `font-family="system-ui, Segoe UI, sans-serif"`. Sin imágenes externas, sin scripts y sin `foreignObject`.

Dentro de ese archivo, un marco por estado que cambia lo visible. Un tamaño de ventana se vuelve a dibujar solo cuando cambia la disposición (columnas, qué se muestra, qué se apila). Si solo crece, el Markdown lo dice y el marco no se repite. Los temas son marcos del estado ideal cuando cambian el color o el tipo. Cada marco tiene una etiqueta (`Ideal · Compacto`, `Error · Oscuro`). Esas etiquetas siguen el idioma del artefacto.

El Markdown es `<NNN>-<type>-<topic>.md`. Cada SVG es `<NNN>-<type>-<topic>-<screen>.svg`. La misma entrega, el mismo `<NNN>`.

## Idioma

Las instrucciones se quedan en inglés. Escribe el artefacto en el idioma del pedido. Si el pedido nombra un idioma, usa ese. Si no, usa el idioma en el que está escrito el pedido. Conserva los nombres que la persona ya usó. Traduce los encabezados de la plantilla de la referencia y mantén los mismos campos. El tipo en el nombre del archivo sigue siendo el id de la pieza en inglés (`sketch`, `wireframe`, `mock`, `prototype`, `handoff`). Las columnas de `STATUS.md` siguen `N`, `archivo`, `estado`, `sustituye`, `notas`. La respuesta usa ese mismo idioma, incluido el bloque `Assumed` cuando se aplicó una plantilla y las tres partes cuando un prerrequisito todavía detiene la entrega. Las indicaciones de la referencia están en inglés: muéstralas en el idioma del pedido y conserva los nombres de los comandos.

## Cuando falta un prerrequisito

Un prerrequisito se cumple con un archivo `accepted` de esa pieza, o con el dato escrito en este turno. La referencia de la pieza nombra cada prerrequisito, la plantilla que lo llena, el estado que esa plantilla deja, el comando que lo reemplaza y el comando que regenera esta pieza.

Usa las fuentes en este orden: un archivo `accepted`, luego el dato escrito en este turno, luego la plantilla. No apliques una plantilla cuando ya existe una fuente más alta.

Cuando la referencia da una plantilla, escribe los archivos. En el mismo turno, escribe también las piezas anteriores que esa referencia dice que hay que escribir, cada una con su propio `<NNN>`, y solo esas. No escribas una pieza que este pedido no necesita.

En el Markdown, añade un encabezado `Assumed`, traducido al idioma del pedido. Una línea por plantilla: el hueco, el id de la plantilla y el valor usado. Las `notas` de `STATUS.md` de esa fila listan los ids de plantilla (`assumed: plain, linear-three`).

Después de la carpeta, los archivos, el `N` y el estado, cierra con este bloque, en el idioma del pedido. Una línea por plantilla. Omite el bloque cuando no se asumió nada.

```text
Se asumió automáticamente (no había un archivo accepted y este mensaje no lo trajo):
- <gap>: plantilla <id> (<value used>). Cámbialo con <command>. Regenera con <command>.
```

Una plantilla que la referencia marca `accepted` deja la entrega `accepted`. Una plantilla que la referencia marca `proposed` la deja `proposed`. Cada línea dice que el valor es un punto de partida, tomado automáticamente, y que no es un dato de quien pide, de una investigación ni de otro plugin.

Si la referencia no da plantilla y no se detiene, escribe el artefacto como ella dice y, al cerrar, nombra el comando que llena el hueco. Di que el blanco se dejó a propósito y que no se inventó nada para ese hueco.

Dos comprobaciones siguen deteniendo la entrega. No escribas archivos de esa pieza. Responde solo con esto, en el idioma del pedido:

1. «Falta:» y los nombres que faltan.
2. «En un mensaje:» y la indicación única de la referencia. Rellénala con lo que la persona ya dijo. Donde falte un valor, deja el hueco (`#…`, `<task>`).
3. «O, en este orden:» y los comandos anteriores que todavía faltan, en el orden de la referencia, cada uno con su indicación. Omite este bloque si no hay un comando anterior. Omite los comandos cuyo prerrequisito ya está cubierto.

Esas dos son una captura o una URL para `/uiux-implementation-review`, y un kit de interfaz del producto para `/uiux-consistency` (un kit `accepted`, o tokens en este turno). La consistencia también se detiene cuando no hay una pantalla `accepted` y este turno no describe una. No dibujes una pantalla para compararla, y no compares contra el preset `plain`.

No inventes textos, notas de accesibilidad, filas de prueba, cifras de HEART, una decisión elegida, el nombre o la biografía de una persona, ni una paleta. Esos huecos se quedan en blanco, o usan la plantilla que nombra la referencia, y la entrega se queda en el estado que nombra la referencia.

## Entrega

La carpeta es `ui-ux-design/` en la raíz del proyecto. Si `.cursor/adrenaline.json` tiene `outputDirs["plugin-ui-ux-design"]` con una ruta relativa, sin `..` y no absoluta, usa esa ruta. Si falta el archivo, la clave o una ruta válida, usa `ui-ux-design/` y, en el último caso, dilo. Crea la carpeta si no existe. No escribas fuera de ella. No elijas la carpeta de otro plugin.

`<NNN>` es el siguiente entero libre en esa carpeta, de tres dígitos, y no se reutiliza. `<type>` es `sketch`, `wireframe`, `mock`, `prototype` o `handoff`. `<topic>` y `<screen>` van en kebab-case.

Mantén `<folder>/STATUS.md` con las columnas `N`, `archivo`, `estado`, `sustituye` y `notas`. Los estados son `proposed`, `accepted`, `deprecated` y `superseded`. Al elegir qué seguir, el orden es `accepted`, luego `proposed`, luego `deprecated`, luego `superseded`.

Si el tema ya tiene un archivo:

- Quien pide cambiar esa entrega: edita los mismos archivos, conserva el `<NNN>` y déjala `accepted`.
- Quien pide un reemplazo o una decisión nueva sobre el mismo tema: toma el siguiente `<NNN>`, marca la fila anterior `superseded` (`sustituye` apunta al `N` nuevo) y deja la fila nueva `accepted`.
- En otro caso: el siguiente `<NNN>` y una fila `accepted`.

El handoff se queda `proposed` cuando faltan el texto o las notas de accesibilidad, o cuando el mock se escribió en este turno a partir de una plantilla. El mock se entrega con el preset `plain` cuando no llegan kit, tokens ni un preset nombrado. El resto queda `accepted`, salvo que la persona pida un borrador. Al cerrar, di la carpeta, los archivos, el `N` y el estado.

## Terminado

Antes de cerrar, evalúa esta lista y la lista `## Terminado` de la referencia para esta situación. Un comando fija la situación: usa la referencia que nombra ese comando. Cada ítem es verdadero, o corriges la entrega en este turno. No dejes un archivo que falle un ítem. No lo marques `accepted` mientras un ítem falle. Una plantilla que nombra la referencia se aplica y se anota bajo `Assumed`; la entrega usa el estado que nombra esa referencia. Un prerrequisito que todavía detiene la entrega no es una lista fallida: sigue «Cuando falta un prerrequisito» y no escribas archivos de esa pieza.

- La situación de este turno es la única que se escribe, salvo que el pedido pidiera dos. Cada entrega tiene su propio `<NNN>`.
- Los archivos están solo en la carpeta de salida, nombrados como dice Entrega. `<NNN>` no se reutiliza. `STATUS.md` coincide con los archivos y con el estado que esta situación permite. Un hueco que la referencia deja como `proposed` se queda `proposed`.
- El idioma del artefacto coincide con el pedido. Las columnas de `STATUS.md` siguen `N`, `archivo`, `estado`, `sustituye`, `notas`.
- Cada campo que exige la plantilla está lleno. No queda ningún marcador (`#…`, `<task>`, `TBD`, lorem ipsum). Un campo que la referencia manda dejar en blanco hasta que lleguen los datos está en blanco a propósito, y el estado es el que nombra la referencia.
- No se añadió nada que este skill prohíbe. La referencia nombra lo que queda fuera.
- La respuesta nombra la carpeta, los archivos, el `N` y el estado. Si se aplicó una plantilla, la respuesta termina con el bloque `Assumed`, una línea por plantilla, nombrando el comando que la cambia y el comando que regenera esta pieza. Un blanco dejado a propósito nombra el comando que lo llena.

## Ejemplo

Entrada: «Boceto de la pantalla de pago. La tarea es pagar con tarjeta. Plataforma web. Todavía no hay kit de interfaz.»

Salida `accepted`:

- `ui-ux-design/001-sketch-payment.md`
- `ui-ux-design/001-sketch-payment-payment.svg`
- Fila `001` en `STATUS.md` por cada archivo.

El Markdown nombra la tarea «pagar con tarjeta», lista los seis estados y dice que vacío no aplica porque el monto ya viene del pedido. El SVG tiene dos bloques en el estado ideal (monto, tarjeta) y el estado de error conserva esos datos más un bloque de mensaje. No hay medidas ni color de marca. Un pedido escrito en español usa etiquetas en español en el SVG y en el Markdown.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 360 640">
  <rect width="360" height="640" fill="#f4f4f4"/>
  <text x="16" y="32" font-family="system-ui, Segoe UI, sans-serif" font-size="14">Ideal · Compacto</text>
  <rect x="16" y="48" width="328" height="64" fill="#ffffff" stroke="#222"/>
  <text x="32" y="84" font-family="system-ui, Segoe UI, sans-serif" font-size="16">Monto del pedido</text>
  <rect x="16" y="128" width="328" height="120" fill="#ffffff" stroke="#222"/>
  <text x="32" y="164" font-family="system-ui, Segoe UI, sans-serif" font-size="16">Tarjeta</text>
  <rect x="16" y="264" width="328" height="48" fill="#ffffff" stroke="#222"/>
  <text x="32" y="294" font-family="system-ui, Segoe UI, sans-serif" font-size="16">Pagar</text>
</svg>
```
