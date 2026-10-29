---
name: test-with-users
description: Planea y analiza una prueba de usabilidad, un card sort, un tree test o métricas HEART. Úsalo cuando alguien pide medir con personas o definir métricas de un producto que ya está lanzado. No recluta ni corre las sesiones.
---

<p align="right">Idioma:&emsp;<a href="SKILL.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../README.es.md)

# Probar con personas

Planea la sesión y analiza los datos que una persona ha recogido. Reclutar participantes y correr la sesión lo hace una persona, no este skill.

Fuente: ISO 9241-11:2018 (eficacia, eficiencia y satisfacción de usuarios especificados, con metas especificadas, en un contexto de uso). Prueba: Nielsen Norman Group, Usability Testing 101. SUS: Brooke (1996). Card sorting y tree testing: Nielsen Norman Group. HEART: Rodden, Hutchinson y Fu (2010), Measuring the User Experience on a Large Scale (CHI 2010). HEART no sustituye la prueba de usabilidad.

## Antes de escribir

1. Si este turno viene de un comando, la pieza ya está fijada.
2. Lee solo `references/<piece>.md` de la pieza que pidieron. No leas referencias de otro skill.
3. No inventes nombres, citas, tiempos ni resultados. Una tarea que falta usa la plantilla `single-task`. Un número de participantes que falta usa la plantilla `nielsen-5` y el archivo dice que esas personas no están reclutadas. Un tipo de card sort que falta usa la plantilla `open`. Un árbol que falta escribe un sitemap con la plantilla `one-group` en este turno. Si el análisis no tiene filas, escribe el archivo, deja los resultados en blanco y déjalo `proposed`.
4. La prueba de usabilidad no verifica el caso de uso. El escenario de prueba de `plugin-qa-engineer` es otro artefacto.
5. No instrumentes métricas ni midas Core Web Vitals. Eso pertenece al área de frontend.
6. No escribas HTML ni código de interfaz.

| Pedido | Pieza | Referencia |
| --- | --- | --- |
| Plan de la sesión | prueba de usabilidad | [references/usability-test.es.md](references/usability-test.es.md) |
| Éxito, tiempo, problemas y SUS | análisis de la prueba | [references/test-analysis.es.md](references/test-analysis.es.md) |
| Cómo agrupa la gente el contenido | card sorting | [references/card-sorting.es.md](references/card-sorting.es.md) |
| Si la gente encuentra un ítem en el sitemap | tree testing | [references/tree-testing.es.md](references/tree-testing.es.md) |
| Metas, señales y métricas de un producto lanzado | HEART | [references/heart.es.md](references/heart.es.md) |

## Idioma

Las instrucciones siguen en inglés. Escribe el artefacto en el idioma del pedido. Si el pedido nombra un idioma, usa ese. Si no, usa el idioma en el que está escrito el pedido. Conserva los nombres que la persona ya usó. Traduce los encabezados de la plantilla de la referencia y mantén los mismos campos. El tipo en el nombre del archivo sigue el id de pieza en inglés (`usability-test`, `test-analysis`, `card-sorting`, `tree-testing`, `heart`). Los nombres de columna del CSV siguen los nombres en inglés de la referencia; la prosa de las celdas sigue el artefacto. Los ítems del SUS siguen en el inglés de Brooke. Las columnas de `STATUS.md` siguen `N`, `archivo`, `estado`, `sustituye`, `notas`. La respuesta usa ese mismo idioma, incluido el bloque Assumed cuando se aplicó una plantilla y las tres partes cuando un prerrequisito todavía detiene la entrega. Los prompts de la referencia están en inglés: muéstralos en el idioma del pedido y conserva los nombres de comando.

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

La carpeta es `ui-ux-design/` en la raíz del proyecto. Si `.cursor/adrenaline.json` tiene `outputDirs["plugin-ui-ux-design"]` con una ruta relativa, sin `..` y no absoluta, usa esa ruta. Si falta el archivo, la clave o una ruta válida, usa `ui-ux-design/` y, en el último caso, dilo. Crea la carpeta si no existe. No escribas fuera de ella.

`<NNN>` es el siguiente entero libre, de tres dígitos, y no se reutiliza. `<type>` es `usability-test`, `test-analysis`, `card-sorting`, `tree-testing` o `heart`. El plan es Markdown. Las observaciones, el SUS, el card sorting y el tree testing añaden un CSV con el mismo `<NNN>`: `<NNN>-<type>-<topic>.csv`.

Mantén `<folder>/STATUS.md` con las columnas `N`, `archivo`, `estado`, `sustituye` y `notas`. Los estados son `proposed`, `accepted`, `deprecated` y `superseded`. Al elegir qué seguir, el orden es `accepted`, luego `proposed`, luego `deprecated`, luego `superseded`.

Si el tema ya tiene un archivo:

- La persona pide cambiar esa entrega: edita los mismos archivos, conserva el `<NNN>` y déjalo `accepted`.
- La persona pide un reemplazo o una decisión nueva sobre el mismo tema: toma el siguiente `<NNN>`, marca la fila anterior `superseded` (`sustituye` apunta al `N` nuevo) y deja la fila nueva `accepted`.
- En otro caso: el siguiente `<NNN>` y una fila `accepted`.

Un análisis sin datos se queda `proposed`. Un plan completo es `accepted`. HEART de un producto que todavía no está lanzado se queda `proposed`, y la entrega dice que todavía no aplica. Al cerrar, di la carpeta, los archivos, el `N` y el estado.

## Terminado

Antes de cerrar, evalúa esta lista y la lista `## Terminado` de la referencia de esta situación. Un comando fija la situación: usa la referencia que ese comando nombra. Cada ítem es cierto, o corriges la entrega en este turno. No dejes un archivo que falle un ítem. No lo marques `accepted` mientras un ítem falle. Una plantilla que la referencia nombra se aplica y se registra bajo Assumed; la entrega usa el estado que esa referencia nombra. Un prerrequisito que todavía detiene la entrega no es una lista fallida: sigue «Cuando falta un prerrequisito» y no escribas archivos de esa pieza.

- La situación de este turno es la única que se escribe, salvo que el pedido pidiera dos. Cada entrega tiene su `<NNN>`.
- Los archivos están solo en la carpeta de salida, nombrados como dice Entrega. `<NNN>` no se reutiliza. `STATUS.md` coincide con los archivos y con el estado que esta situación permite. Un hueco que la referencia deja como `proposed` se queda `proposed`.
- El idioma del artefacto coincide con el pedido. Las columnas de `STATUS.md` siguen `N`, `archivo`, `estado`, `sustituye`, `notas`.
- Cada campo que la plantilla exige está lleno. No queda un marcador (`#…`, `<task>`, `TBD`, lorem ipsum). Un campo que la referencia manda dejar en blanco hasta que lleguen los datos está en blanco a propósito, y el estado es el que la referencia nombra.
- No se añadió nada que este skill prohíbe. La referencia nombra qué queda fuera.
- La respuesta nombra la carpeta, los archivos, el `N` y el estado. Si se aplicó una plantilla, la respuesta termina con el bloque Assumed, una línea por plantilla, nombrando el comando que lo cambia y el comando que regenera esta pieza. Un blanco dejado a propósito nombra el comando que lo llena.

## Ejemplo

Entrada: «Plan de prueba de la tarea pagar con tarjeta. Participan cinco personas que ya han comprado en la tienda. No reclutes.»

Salida: `018-usability-test-pay.md` con la tarea de escenario «Llegas al final del pedido y quieres pagarlo con la tarjeta que ya usas», sin decir qué botón pulsar, y el criterio de qué anotar. No incluye nombres de participantes.
