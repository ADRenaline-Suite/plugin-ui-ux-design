---
name: evaluate-ui
description: Evalúa una interfaz sin personas mediante heurísticas, un recorrido cognitivo, la consistencia con el kit de interfaz, una revisión de flujo o una revisión de implementación. Úsalo cuando se revisa un diseño o una pantalla que ya está construida.
---

<p align="right">Idioma:&emsp;<a href="SKILL.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../README.es.md)

# Evaluar la interfaz

Encuentra problemas sin invitar personas. Cada hallazgo dice dónde está, qué regla rompe, qué tan grave es y cómo corregirlo. Medir con personas es `test-with-users`.

Fuente: Nielsen Norman Group, 10 Usability Heuristics for User Interface Design, y Severity Ratings for Usability Problems (0–4). Recorrido cognitivo: Wharton, Rieman, Lewis y Polson (1994), The Cognitive Walkthrough Method: A Practitioner's Guide. La consistencia se juzga contra el kit de interfaz. La revisión de flujo no tiene otro estándar: pasos de más, callejones sin salida y estados que faltan. La revisión de implementación no tiene un estándar propio: el criterio es el handoff y el kit de interfaz. La auditoría WCAG la hace `plugin-accessibility`. Este skill la pide; no la corre.

## Antes de escribir

1. Si este turno viene de un comando, la pieza ya está fija.
2. Lee solo `references/<piece>.md` de la pieza que pidieron. No leas referencias de otro skill.
3. Evalúa una pantalla o un flujo que ya existe (un archivo `accepted`, o lo que la persona muestra en este turno). Si las heurísticas, el recorrido o la revisión de flujo no tienen nada que revisar, escribe esa pantalla o ese camino con la plantilla de la referencia y deja la revisión en `proposed`. La consistencia y la revisión de implementación siguen deteniéndose cuando la referencia lo dice.
4. No verifiques el caso de uso: eso no es esta evaluación. No marques un criterio WCAG como cumplido.
5. Al cerrar las heurísticas, el recorrido, el flujo o la revisión de implementación, pide la revisión a `plugin-accessibility`.
6. No escribas HTML ni código de interfaz. No corrijas la pantalla construida: escribe la corrección.

| Pedido | Pieza | Referencia |
| --- | --- | --- |
| Las 10 heurísticas | heurísticas | [references/heuristics.es.md](references/heuristics.es.md) |
| Las cuatro preguntas por paso | recorrido cognitivo | [references/cognitive-walkthrough.es.md](references/cognitive-walkthrough.es.md) |
| Desvío del kit | consistencia | [references/consistency.es.md](references/consistency.es.md) |
| Pasos, callejones sin salida y estados | revisión de flujo | [references/flow-review.es.md](references/flow-review.es.md) |
| Lo construido contra el handoff | revisión de implementación | [references/implementation-review.es.md](references/implementation-review.es.md) |

## Idioma

Las instrucciones se quedan en inglés. Escribe el artefacto en el idioma del pedido. Si el pedido nombra un idioma, usa ese. Si no, usa el idioma en el que está escrito el pedido. Conserva los nombres que la persona ya usó. Traduce los encabezados de la plantilla de la referencia y mantén los mismos campos. El tipo en el nombre del archivo sigue siendo el id de la pieza en inglés (`heuristics`, `cognitive-walkthrough`, `consistency`, `flow-review`, `implementation-review`). Los nombres de las heurísticas siguen siendo los de Nielsen Norman Group; puede seguir una glosa en el idioma del artefacto. Las columnas de `STATUS.md` siguen `N`, `archivo`, `estado`, `sustituye`, `notas`. La respuesta usa ese mismo idioma, incluido el bloque `Assumed` cuando se aplicó una plantilla y las tres partes cuando un prerrequisito todavía detiene la entrega. Las indicaciones de la referencia están en inglés: muéstralas en el idioma del pedido y conserva los nombres de los comandos.

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

La carpeta es `ui-ux-design/` en la raíz del proyecto. Si `.cursor/adrenaline.json` tiene `outputDirs["plugin-ui-ux-design"]` con una ruta relativa, sin `..` y no absoluta, usa esa ruta. Si falta el archivo, la clave o una ruta válida, usa `ui-ux-design/` y, en el último caso, dilo. Crea la carpeta si no existe. No escribas fuera de ella.

`<NNN>-<type>-<topic>.md`. `<type>` es `heuristics`, `cognitive-walkthrough`, `consistency`, `flow-review` o `implementation-review`. `<NNN>` es el siguiente entero libre, de tres dígitos, y no se reutiliza.

Mantén `<folder>/STATUS.md` con las columnas `N`, `archivo`, `estado`, `sustituye` y `notas`. Los estados son `proposed`, `accepted`, `deprecated` y `superseded`. Al elegir qué seguir, el orden es `accepted`, luego `proposed`, luego `deprecated`, luego `superseded`.

Si el tema ya tiene un archivo:

- Quien pide cambiar esa entrega: edita los mismos archivos, conserva el `<NNN>` y déjala `accepted`.
- Quien pide un reemplazo o una decisión nueva sobre el mismo tema: toma el siguiente `<NNN>`, marca la fila anterior `superseded` (`sustituye` apunta al `N` nuevo) y deja la fila nueva `accepted`.
- En otro caso: el siguiente `<NNN>` y una fila `accepted`.

La revisión de implementación se queda `proposed` si falta el handoff o no se pudo ver la pantalla. Las heurísticas, el recorrido y la revisión de flujo se quedan `proposed` cuando la pantalla o el camino se escribieron en este turno a partir de una plantilla. La consistencia no se escribe sin un kit del producto o sin una pantalla para comparar. El resto se queda `accepted`, salvo que la persona haya pedido un borrador. Al cerrar, di la carpeta, el archivo, el `N` y el estado.

## Terminado

Antes de cerrar, evalúa esta lista y la lista `## Terminado` de la referencia para esta situación. Un comando fija la situación: usa la referencia que nombra ese comando. Cada ítem es verdadero, o corriges la entrega en este turno. No dejes un archivo que falle un ítem. No lo marques `accepted` mientras un ítem falle. Una plantilla que nombra la referencia se aplica y se anota bajo `Assumed`; la entrega usa el estado que nombra esa referencia. Un prerrequisito que todavía detiene la entrega no es una lista fallida: sigue «Cuando falta un prerrequisito» y no escribas archivos de esa pieza.

- La situación de este turno es la única que se escribe, salvo que el pedido pidiera dos. Cada entrega tiene su propio `<NNN>`.
- Los archivos están solo en la carpeta de salida, nombrados como dice Entrega. `<NNN>` no se reutiliza. `STATUS.md` coincide con los archivos y con el estado que esta situación permite. Un hueco que la referencia deja como `proposed` se queda `proposed`.
- El idioma del artefacto coincide con el pedido. Las columnas de `STATUS.md` siguen `N`, `archivo`, `estado`, `sustituye`, `notas`.
- Cada campo que exige la plantilla está lleno. No queda ningún marcador (`#…`, `<task>`, `TBD`, lorem ipsum). Un campo que la referencia manda dejar en blanco hasta que lleguen los datos está en blanco a propósito, y el estado es el que nombra la referencia.
- No se añadió nada que este skill prohíbe. La referencia nombra lo que queda fuera.
- La respuesta nombra la carpeta, los archivos, el `N` y el estado. Si se aplicó una plantilla, la respuesta termina con el bloque `Assumed`, una línea por plantilla, nombrando el comando que la cambia y el comando que regenera esta pieza. Un blanco dejado a propósito nombra el comando que lo llena.

## Ejemplo

Entrada: «Revisa las heurísticas del pago cuando falla la red. El botón sigue diciendo Pagar y no hay mensaje.»

Salida: un archivo Markdown con un hallazgo. Pantalla: pago. Estado: error de red. Heurística: visibility of system status. Gravedad: 3 (mayor). Corrección: un mensaje de error y una acción de reintento; conservar los datos de la tarjeta. Al final, pide la revisión a `plugin-accessibility`.
