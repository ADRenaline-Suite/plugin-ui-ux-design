---
name: medir-con-usuarios
description: Planea y analiza un test de usabilidad, un card sorting, un tree testing o las métricas HEART. Úsala cuando pidan medir con usuarios o definir métricas de un producto ya lanzado. No recluta ni conduce sesiones.
---

# Medir con usuarios

Planea la sesión y analiza los datos que una persona haya recogido. Reclutar participantes y conducir la sesión lo hace una persona, no este skill.

Fuente: ISO 9241-11:2018 (eficacia, eficiencia y satisfacción de usuarios concretos, con objetivos concretos, en un contexto de uso). Test: Nielsen Norman Group, Usability Testing 101. SUS: Brooke (1996). Card sorting y tree testing: Nielsen Norman Group. HEART: Rodden, Hutchinson y Fu (2010), Measuring the User Experience on a Large Scale (CHI 2010). HEART no sustituye al test de usabilidad.

## Antes de escribir

1. Si este turno viene de un command, la pieza ya está fijada.
2. Lee solo `references/<pieza>.md` de la pieza pedida. No leas referencias de otro skill.
3. No inventes participantes, citas ni tiempos. Si el análisis no tiene datos, escribe el plan y deja los resultados en blanco, o detente y pídelos.
4. El test de usabilidad no verifica el caso de uso. El escenario de prueba de `adrenaline-qa-engineer` es otro artefacto.
5. No instrumentes métricas ni midas Core Web Vitals. Eso es del área de frontend.
6. No escribas HTML ni código de interfaz.

| Petición | Pieza | Referencia |
| --- | --- | --- |
| Plan de la sesión | test de usabilidad | `references/test-usabilidad.md` |
| Éxito, tiempo, problemas y SUS | análisis del test | `references/analisis-test.md` |
| Cómo agrupan el contenido | card sorting | `references/card-sorting.md` |
| Si encuentran un ítem en el sitemap | tree testing | `references/tree-testing.md` |
| Objetivos, señales y métricas de un producto lanzado | HEART | `references/heart.md` |

## Entrega

La carpeta es `ui-ux-design/` en la raíz del proyecto. Si `.cursor/adrenaline.json` tiene `outputDirs["adrenaline-ui-ux-design"]` con una ruta relativa, sin `..` y no absoluta, usa esa ruta. Si falta el archivo, la clave, o la ruta no es válida, usa `ui-ux-design/` y, en el último caso, dilo. Crea la carpeta si no existe. No escribas fuera de ella.

`<NNN>` es el siguiente entero libre, con tres dígitos, y no se reutiliza. `<tipo>` es `test-usabilidad`, `analisis-test`, `card-sorting`, `tree-testing` o `heart`. El plan es Markdown. Las observaciones, el SUS, el card sorting y el tree testing añaden un CSV con el mismo `<NNN>`: `<NNN>-<tipo>-<tema>.csv`.

Mantén `<carpeta>/STATUS.md` con las columnas `N`, `archivo`, `estado`, `sustituye` y `notas`. Los estados son `proposed`, `accepted`, `deprecated` y `superseded`. Al elegir qué seguir, el orden es `accepted`, luego `proposed`, luego `deprecated`, luego `superseded`.

Si el tema ya tiene archivo:

- El usuario pide cambiar esa entrega: edita los mismos archivos, conserva el `<NNN>` y deja `accepted`.
- El usuario pide un reemplazo o una decisión nueva sobre el mismo tema: toma el siguiente `<NNN>`, marca la fila anterior `superseded` (en `sustituye`, el `N` nuevo) y deja la nueva en `accepted`.
- Si no: siguiente `<NNN>` y fila `accepted`.

Un análisis sin datos queda `proposed`. Un plan completo queda `accepted`. HEART de un producto que aún no está lanzado queda `proposed` y se dice que no aplica todavía. Al cerrar, di la carpeta, los archivos, el `N` y el estado.

## Ejemplo

Entrada: «Plan de test para la tarea pagar con tarjeta. Participan cinco personas que ya compraron en la tienda. No reclutes.»

Salida: `018-test-usabilidad-pagar.md` con la tarea escenario «Llegas al final del pedido y quieres dejarlo pagado con la tarjeta que ya usas», sin decir en qué botón pulsar, y el criterio de qué anotar. No incluye nombres de participantes.
