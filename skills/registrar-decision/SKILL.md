---
name: registrar-decision
description: Registra una decisión de diseño con su contexto, las opciones, la decisión y las consecuencias. Úsala cuando haya que dejar escrito por qué la interfaz quedó de una manera y no de otra.
---

# Registrar una decisión

Deja constancia de una decisión de diseño. No diseña la pantalla: apunta a los artefactos que ya existen.

Fuente: Michael Nygard, Documenting Architecture Decisions (2011). Los estados usan los mismos nombres: `proposed`, `accepted`, `deprecated`, `superseded`. Un `accepted` es lo que se sigue. Uno más nuevo no lo desplaza por ser nuevo.

## Antes de escribir

1. Lee `references/decision.md`.
2. La decisión tiene que estar tomada por el usuario, o el usuario pide dejar una opción como propuesta. No elijas tú la opción ganadora y la marques `accepted`.
3. Si la opción cambia tokens, textos o el flujo, no los reescribas en este archivo. Esos cambios son entregas de `definir-apariencia`, `adrenaline-ux-writing` u `ordenar-pantallas`.
4. No escribas HTML ni código de interfaz.

## Entrega

La carpeta es `ui-ux-design/` en la raíz del proyecto. Si `.cursor/adrenaline.json` tiene `outputDirs["adrenaline-ui-ux-design"]` con una ruta relativa, sin `..` y no absoluta, usa esa ruta. Si falta el archivo, la clave, o la ruta no es válida, usa `ui-ux-design/` y, en el último caso, dilo. Crea la carpeta si no existe. No escribas fuera de ella.

El archivo es `<NNN>-decision-<tema>.md`. `<NNN>` es el siguiente entero libre, con tres dígitos, y no se reutiliza.

Mantén `<carpeta>/STATUS.md` con las columnas `N`, `archivo`, `estado`, `sustituye` y `notas`. El estado de la fila es el de la decisión.

Si el tema ya tiene archivo:

- El usuario pide enmendar esa misma decisión: edita el mismo archivo, conserva el `<NNN>` y mantiene `accepted` si ya lo estaba.
- El usuario cambia de opción: siguiente `<NNN>`, la fila anterior pasa a `superseded` (`sustituye` apunta al `N` nuevo) y la nueva queda en el estado que corresponda.
- Tema nuevo: siguiente `<NNN>`.

`proposed` si aún no se elige. `accepted` cuando el usuario la da por hecha. `deprecated` si sigue legible y ya no se prefiere, sin una decisión que la reemplace. `superseded` cuando otra decisión la reemplaza. Al cerrar, di la carpeta, el archivo, el `N` y el estado.

## Ejemplo

Entrada: «Dejamos el reintento en la misma pantalla de pago, no en una pantalla nueva. Anótalo.»

Salida `accepted`: `021-decision-reintento-en-el-pago.md`. Contexto: el error de red borraba la tarjeta. Opciones: pantalla nueva, o el aviso en la misma. Decisión: el aviso en la misma, y se conservan los datos. Consecuencias: el handoff del pago tiene que mostrar ese estado.
