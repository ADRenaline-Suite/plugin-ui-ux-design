---
name: entender-usuario
description: Analiza las tareas del usuario, arma el journey map y cierra el brief de diseño antes de dibujar pantallas. Úsala al descubrir o definir un problema de interfaz, o cuando pidan tareas, un journey map o un brief.
---

# Entender al usuario

Cierra el problema antes de dibujar. Este skill produce el análisis de tareas, el journey map o el brief. Las pantallas salen de `concretar-pantalla`. El orden de las pantallas sale de `ordenar-pantallas`.

Fuente: ISO 9241-210:2019 (entender el contexto de uso y especificar requisitos). El brief es la salida de definir en el Framework for Innovation del Design Council (doble diamante: descubrir, definir, desarrollar, entregar; no es lineal). Tareas: Nielsen Norman Group, Task Analysis. Journey map: Nielsen Norman Group, Journey Mapping 101.

## Antes de escribir

1. Si este turno viene de un command, la pieza ya está fijada. Si no, elige una pieza de la tabla. Si piden dos, haz las dos entregas, cada una con su `<NNN>`.
2. Lee solo `references/<pieza>.md` de la pieza pedida. No leas referencias de otro skill.
3. El caso de uso, si existe, viene de `adrenaline-project-manager`. Si no existe, parte del objetivo que declare el usuario en este turno. Si no hay objetivo, pídelo y detente.
4. La persona la aporta el usuario. No la inventes. Si falta y la pieza es el journey map, pídela y detente.
5. No dibujes pantallas, flujos ni tokens en este skill.

| Petición | Pieza | Referencia |
| --- | --- | --- |
| Objetivo, tareas, subtareas y orden | tareas | `references/tareas.md` |
| Recorrido de una persona en un escenario | journey map | `references/journey-map.md` |
| Problema, para quién, restricciones y éxito medible | brief | `references/brief.md` |

## Entrega

La carpeta es `ui-ux-design/` en la raíz del proyecto. Si `.cursor/adrenaline.json` tiene `outputDirs["adrenaline-ui-ux-design"]` con una ruta relativa, sin `..` y no absoluta, usa esa ruta. Si falta el archivo, la clave, o la ruta no es válida, usa `ui-ux-design/` y, en el último caso, dilo. Crea la carpeta si no existe. No escribas fuera de ella. No elijas la carpeta de otro plugin.

Cada archivo nuevo se llama `<NNN>-<tipo>-<tema>.<ext>`. `<NNN>` es el siguiente entero libre de esa carpeta, con tres dígitos, y no se reutiliza. `<tipo>` es `tareas`, `journey-map` o `brief`. `<tema>` va en kebab-case. Este skill escribe Markdown.

Mantén `<carpeta>/STATUS.md` con las columnas `N`, `archivo`, `estado`, `sustituye` y `notas`. Los estados son `proposed`, `accepted`, `deprecated` y `superseded`. Al elegir qué seguir, el orden es `accepted`, luego `proposed`, luego `deprecated`, luego `superseded`.

Si el tema ya tiene archivo:

- El usuario pide cambiar esa entrega: edita los mismos archivos, conserva el `<NNN>` y deja `accepted`.
- El usuario pide un reemplazo o una decisión nueva sobre el mismo tema: toma el siguiente `<NNN>`, marca la fila anterior `superseded` (en `sustituye`, el `N` nuevo) y deja la nueva en `accepted`.
- Si no: siguiente `<NNN>` y fila `accepted`.

Una entrega nueva queda `accepted`. Queda `proposed` solo si el usuario pide un borrador. Al cerrar, di la carpeta, el archivo, el `N` y el estado.

## Ejemplo

Entrada: «El objetivo es pagar un pedido con tarjeta. El caso de uso es pagar el carrito.»

Salida: `ui-ux-design/001-tareas-pagar-pedido.md`, fila `accepted` en `STATUS.md`. El Markdown lista el objetivo, las tareas en orden (revisar el monto, ingresar la tarjeta, confirmar) y las subtareas que el usuario describió. No añade una persona ni una pantalla.
