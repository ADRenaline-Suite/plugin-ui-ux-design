---
name: evaluar-ui
description: Evalúa una interfaz sin usuarios mediante heurísticas, recorrido cognitivo, consistencia con el UI kit, revisión del flujo o revisión de la implementación. Úsala al revisar un diseño o una pantalla ya construida.
---

# Evaluar la interfaz

Encuentra problemas sin convocar usuarios. Cada hallazgo dice dónde está, qué regla incumple, qué tan grave es y cómo se corrige. Medir con personas es `medir-con-usuarios`.

Fuente: Nielsen Norman Group, 10 Usability Heuristics for User Interface Design, y Severity Ratings for Usability Problems (0–4). Recorrido cognitivo: Wharton, Rieman, Lewis y Polson (1994), The Cognitive Walkthrough Method: A Practitioner's Guide. La consistencia se juzga contra el UI kit. La revisión del flujo no tiene otra norma: pasos de más, callejones sin salida y estados que faltan. La revisión de la implementación no tiene norma propia: el criterio es el handoff y el UI kit. La auditoría WCAG la hace `adrenaline-accessibility`. Este skill la pide; no la ejecuta.

## Antes de escribir

1. Si este turno viene de un command, la pieza ya está fijada.
2. Lee solo `references/<pieza>.md` de la pieza pedida. No leas referencias de otro skill.
3. Evalúa una pantalla o un flujo que ya exista (archivo `accepted` o lo que el usuario muestre en este turno). Si no hay nada que revisar, pídelo y detente.
4. No verifiques el caso de uso: eso no es esta evaluación. No des por cumplido un criterio WCAG.
5. Al cerrar heurísticas, recorrido, flujo o la revisión de la implementación, pide la revisión a `adrenaline-accessibility`.
6. No escribas HTML ni código de interfaz. No corrijas la pantalla construida: anota la corrección.

| Petición | Pieza | Referencia |
| --- | --- | --- |
| Las 10 heurísticas | heurísticas | `references/heuristicas.md` |
| Las cuatro preguntas por paso | recorrido cognitivo | `references/recorrido-cognitivo.md` |
| Desviación respecto al kit | consistencia | `references/consistencia.md` |
| Pasos, callejones y estados | revisión del flujo | `references/revision-flujo.md` |
| Lo construido contra el handoff | revisión de la implementación | `references/revision-implementacion.md` |

## Entrega

La carpeta es `ui-ux-design/` en la raíz del proyecto. Si `.cursor/adrenaline.json` tiene `outputDirs["adrenaline-ui-ux-design"]` con una ruta relativa, sin `..` y no absoluta, usa esa ruta. Si falta el archivo, la clave, o la ruta no es válida, usa `ui-ux-design/` y, en el último caso, dilo. Crea la carpeta si no existe. No escribas fuera de ella.

`<NNN>-<tipo>-<tema>.md`. `<tipo>` es `heuristicas`, `recorrido-cognitivo`, `consistencia`, `revision-flujo` o `revision-implementacion`. `<NNN>` es el siguiente entero libre, con tres dígitos, y no se reutiliza.

Mantén `<carpeta>/STATUS.md` con las columnas `N`, `archivo`, `estado`, `sustituye` y `notas`. Los estados son `proposed`, `accepted`, `deprecated` y `superseded`. Al elegir qué seguir, el orden es `accepted`, luego `proposed`, luego `deprecated`, luego `superseded`.

Si el tema ya tiene archivo:

- El usuario pide cambiar esa entrega: edita los mismos archivos, conserva el `<NNN>` y deja `accepted`.
- El usuario pide un reemplazo o una decisión nueva sobre el mismo tema: toma el siguiente `<NNN>`, marca la fila anterior `superseded` (en `sustituye`, el `N` nuevo) y deja la nueva en `accepted`.
- Si no: siguiente `<NNN>` y fila `accepted`.

La revisión de la implementación queda `proposed` si falta el handoff o no se pudo ver la pantalla. El resto queda `accepted`, salvo borrador pedido por el usuario. Al cerrar, di la carpeta, el archivo, el `N` y el estado.

## Ejemplo

Entrada: «Revisa las heurísticas del pago cuando falla la red. El botón sigue diciendo Pagar y no hay mensaje.»

Salida: un Markdown con un hallazgo. Pantalla: pago. Estado: error de red. Heurística: visibilidad del estado del sistema. Gravedad: 3 (mayor). Corrección: mensaje de error y acción de reintentar; conservar los datos de la tarjeta. Al final, pedir la revisión a `adrenaline-accessibility`.
