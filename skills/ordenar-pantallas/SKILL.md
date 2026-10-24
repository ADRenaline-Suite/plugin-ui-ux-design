---
name: ordenar-pantallas
description: Ordena las pantallas de una tarea en un user flow, un wireflow o un sitemap. Úsala cuando pidan el camino entre pantallas, el mismo camino con wireframes, o el mapa de cómo se agrupan.
---

# Ordenar pantallas

Produce el user flow, el wireflow o el sitemap. Son artefactos de UX. No son diagramas UML. Un diagrama de actividad o una máquina de estados se pide a `adrenaline-uml-diagrams`.

Fuente: la tarea que el flujo completa sigue Nielsen Norman Group, Task Analysis (objetivo, tareas, subtareas, orden). El user flow, el wireflow y el sitemap no tienen otra norma en las fuentes de este plugin: muestran ese orden como camino o como mapa.

## Antes de escribir

1. Si este turno viene de un command, la pieza ya está fijada.
2. Lee solo `references/<pieza>.md` de la pieza pedida. No leas referencias de otro skill.
3. Cada pantalla del flujo nombra la tarea o el caso de uso que cubre. Si la tarea no está dicha, pídela y detente.
4. No dibujes el aspecto visual definitivo. El wireflow usa wireframes en gris, no mocks.
5. No escribas HTML ni código de interfaz.

| Petición | Pieza | Referencia |
| --- | --- | --- |
| Camino para completar una tarea | user flow | `references/user-flow.md` |
| Ese camino con un wireframe en cada paso | wireflow | `references/wireflow.md` |
| Mapa de pantallas y grupos | sitemap | `references/sitemap.md` |

## Entrega

La carpeta es `ui-ux-design/` en la raíz del proyecto. Si `.cursor/adrenaline.json` tiene `outputDirs["adrenaline-ui-ux-design"]` con una ruta relativa, sin `..` y no absoluta, usa esa ruta. Si falta el archivo, la clave, o la ruta no es válida, usa `ui-ux-design/` y, en el último caso, dilo. Crea la carpeta si no existe. No escribas fuera de ella. No elijas la carpeta de otro plugin.

Cada archivo nuevo se llama `<NNN>-<tipo>-<tema>.<ext>`. `<NNN>` es el siguiente entero libre de esa carpeta, con tres dígitos, y no se reutiliza. `<tipo>` es `user-flow`, `wireflow` o `sitemap`. El user flow y el sitemap son un Markdown con Mermaid. El wireflow añade un SVG por pantalla: `<NNN>-wireflow-<tema>-<pantalla>.svg`, mismo `<NNN>`.

Mantén `<carpeta>/STATUS.md` con las columnas `N`, `archivo`, `estado`, `sustituye` y `notas`. Los estados son `proposed`, `accepted`, `deprecated` y `superseded`. Al elegir qué seguir, el orden es `accepted`, luego `proposed`, luego `deprecated`, luego `superseded`.

Si el tema ya tiene archivo:

- El usuario pide cambiar esa entrega: edita los mismos archivos, conserva el `<NNN>` y deja `accepted`.
- El usuario pide un reemplazo o una decisión nueva sobre el mismo tema: toma el siguiente `<NNN>`, marca la fila anterior `superseded` (en `sustituye`, el `N` nuevo) y deja la nueva en `accepted`.
- Si no: siguiente `<NNN>` y fila `accepted`.

Una entrega nueva queda `accepted`. Queda `proposed` solo si el usuario pide un borrador o si un paso no tiene destino. Al cerrar, di la carpeta, los archivos, el `N` y el estado.

## Ejemplo

Entrada: «User flow de pagar con tarjeta: el pago puede cobrarse o fallar.»

Salida: `ui-ux-design/004-user-flow-pagar.md` con un Mermaid de tres pantallas (datos, resultado, error) y la vuelta del error a los datos. No es un diagrama de actividad.
