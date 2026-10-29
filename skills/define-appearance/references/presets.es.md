<p align="right">Idioma:&emsp;<a href="presets.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Definir la apariencia](../SKILL.es.md)

# Presets

Cinco puntos de partida para el kit de interfaz. Son lo que hay que recomendar. El archivo que se guarda sigue siendo un kit de interfaz normal en la carpeta del proyecto.

`plain` y `dense` son puntos de partida de este plugin. No tienen un estándar externo. `material-3`, `hig` y `fluent-2` copian la guía publicada que nombra su archivo. Donde esa guía no publica un valor que el formato de tokens necesita, el archivo del preset lo dice. No llenes ese hueco con un valor nuevo al entregar.

## Cuál

| Id | Cuándo recomendarlo |
| --- | --- |
| `plain` | Web, sin marca, lectura cómoda. Este es el de partida. |
| `material-3` | Android, o un producto que ya sigue Material Design 3. |
| `hig` | iOS, iPadOS o macOS. |
| `fluent-2` | Windows. |
| `dense` | Una herramienta web con tablas o un backoffice. El mismo color que `plain`, con tipo y espacio más apretados. |

## Regla

1. Un kit `accepted` del producto gana. No lo sustituyas por un preset salvo que la persona pida sustituir ese kit.
2. El color, el tipo, el espacio, el radio y la elevación escritos en este turno ganan a un preset. Escribe esos valores. No los corrijas hacia un preset.
3. Un preset nombrado son los valores. Lee `presets/<id>.md` y `presets/<id>.tokens.json`. Copia los valores de los tokens en la entrega. No cambies un número, un nombre ni un hex. Traduce la prosa y cada `$description` al idioma del pedido. El id del preset sigue en inglés.
4. Si no hay un kit `accepted`, ni valores en este turno, ni un preset nombrado, usa `plain`. Regístralo bajo Assumed: plantilla `plain`, porque no se seleccionó ninguno, y nombra los otros cuatro en el orden de la tabla, cada uno con su línea de «cuándo recomendarlo». Cámbialo con `/uiux-ui-kit`. Regenera el kit con `/uiux-ui-kit`, y regenera el mock o el handoff con ese comando si ya se dibujó uno.
5. Un nombre desconocido no es una selección. No escribas el kit. Nombra los cinco y di que `plain` es el que se usa cuando no eligen.
6. No inventes un sexto preset. Estos cinco son solo light. No añadas un tema dark.
7. El mock y el handoff siguen esta misma regla cuando necesitan un kit y no lo tienen: escribe primero el kit, luego la pieza. La consistencia no. Una revisión compara contra el kit que la pantalla ya tiene. Un kit que falta detiene esa revisión. No juzgues una pantalla contra `plain` solo porque no se seleccionó un kit.

Nombrar la plataforma no es nombrar un preset. «La app está en iOS» recomienda `hig` en la respuesta y aun así escribe `plain` hasta que nombren `hig`.

## Alias

| Dicen | Preset |
| --- | --- |
| default, none | `plain` |
| material, material 3, m3 | `material-3` |
| apple, human interface, ios, macos | `hig` |
| fluent, fluent 2 | `fluent-2` |

## Archivos

| Preset | Manual | Tokens |
| --- | --- | --- |
| `plain` | [presets/plain.es.md](presets/plain.es.md) | `presets/plain.tokens.json` |
| `material-3` | [presets/material-3.es.md](presets/material-3.es.md) | `presets/material-3.tokens.json` |
| `hig` | [presets/hig.es.md](presets/hig.es.md) | `presets/hig.tokens.json` |
| `fluent-2` | [presets/fluent-2.es.md](presets/fluent-2.es.md) | `presets/fluent-2.tokens.json` |
| `dense` | [presets/dense.es.md](presets/dense.es.md) | `presets/dense.tokens.json` |

## Terminado

Este archivo no es una situación. La entrega es el kit de interfaz. Evalúa `## Terminado` en `ui-kit.es.md`. El preset copiado ahí es el que este archivo selecciona, con sus valores sin cambios.
