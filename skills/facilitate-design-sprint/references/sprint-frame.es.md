<p align="right">Idioma:&emsp;<a href="sprint-frame.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Facilitar un design sprint](../SKILL.es.md)

# Marco del sprint

Fuente: Jake Knapp, John Zeratsky y Braden Kowitz, *Sprint* (Simon & Schuster, 2016), lunes. La meta de largo plazo es el resultado optimista que el equipo celebraría. Las preguntas del sprint son los riesgos que podrían hundir la semana, escritos como preguntas. El objetivo es una persona y un momento del mapa, el momento que cubrirá el prototipo.

## Qué fija

La apuesta de esta semana: la meta de largo plazo, las preguntas que la semana tiene que responder y el momento objetivo. No elige una solución.

## Qué deja abierto

Las ideas que compiten, la decisión, el storyboard, el prototipo y la prueba.

## Cómo hacerlo

1. Meta de largo plazo: una frase, puesta en el futuro, sobre la persona y la dificultad. Si existe un resultado `accepted` de `plugin-product`, cita ese archivo. No escribas el resultado.
2. Preguntas del sprint: al menos una pregunta que la prueba del viernes podría responder. Una pregunta no es una función.
3. Objetivo: quién, y qué momento. Quién usa a una persona que nombró quien pide, o el «para quién» de un brief `accepted`. No inventes un nombre, una edad ni una biografía.
4. Mapa: cita un mapa de recorrido `accepted` por nombre de archivo cuando exista. Si el mensaje describe la situación, cita esa frase. Si no existe ninguno, nombra `/uiux-journey-map` y no inventes las fases.
5. No dibujes una pantalla y no registres una idea.

## Plantilla

```markdown
# <NNN> — <título>

- State: proposed | accepted
- Source: Knapp, Zeratsky, and Kowitz, Sprint (2016), Monday

## Meta de largo plazo

## Preguntas del sprint

1. <pregunta>

## Objetivo

- Quién:
- Momento:

## Mapa

## Siguiente

`/uiux-solution-sketch` escribe una idea que compite. Este archivo no la dibuja.
```

## Ejemplo

Estado: `accepted`. Meta de largo plazo: en dos años, quien reserva desde el teléfono sabe que la mesa quedó apartada. Pregunta del sprint: ¿puede ver que la mesa quedó apartada en el primer intento? Objetivo: quien reserva desde el teléfono, en el momento en que busca la confirmación. Mapa: cita el mapa de recorrido cuando ese archivo existe. Siguiente: `/uiux-solution-sketch`.

## Prerrequisitos

- **Meta de largo plazo.** En este turno, o citada desde un resultado de producto `accepted`. Si falta, plantilla `two-year-outcome`: «En dos años, la persona que hace <task> ya no se topa con esta dificultad: <problem>.» Usa la tarea y el problema de un brief `accepted` o de este turno. Si alguno se desconoce, usa «la tarea» y «todavía no puede completarla por un camino claro». Estado: `proposed`. Cámbialo con `/uiux-sprint-frame`. Regenera con `/uiux-sprint-frame`.
- **Pregunta del sprint.** Al menos una, en este turno. Si falta, plantilla `one-question`: «¿Puede la persona terminar <task> en el primer intento, sin pedir ayuda?» Usa la tarea de un análisis de tareas `accepted`, del brief o de este turno. Si la tarea se desconoce, usa «la tarea». Estado: `proposed`. Cámbialo con `/uiux-sprint-frame`. Regenera con `/uiux-sprint-frame`.
- **Objetivo.** Quién y qué momento, en este turno o en un brief `accepted`. Si falta el momento, plantilla `target-result`: el momento en que ve el resultado de la tarea. Si falta quién, usa «la persona que hace <task>» y no inventes un nombre. Estado: `proposed`. Cámbialo con `/uiux-sprint-frame`. Regenera con `/uiux-sprint-frame`.

La entrega queda `accepted` solo cuando la meta, al menos una pregunta y el objetivo vinieron de la persona o de un archivo `accepted`, y no se aplicó ninguna plantilla. Cualquier plantilla deja la entrega en `proposed`.

## Indicaciones

En un mensaje:

```text
/uiux-sprint-frame de reservar mesa.
Meta de largo plazo: en dos años, quien reserva desde el teléfono sabe que la mesa quedó apartada.
Pregunta del sprint: ¿puede ver que la mesa quedó apartada en el primer intento?
Objetivo: quien reserva desde el teléfono, en el momento en que busca la confirmación.
```

No hay un comando anterior dentro de este skill. El brief, las tareas y el mapa de recorrido van antes en la semana. Sus prompts están en [La semana](../SKILL.es.md#la-semana).

## Terminado

- La meta de largo plazo, al menos una pregunta del sprint y un objetivo con quién y un momento están presentes, de la persona, de un archivo `accepted` o de la plantilla nombrada.
- Quién no tiene un nombre, una edad ni una biografía inventados.
- El archivo cita un mapa de recorrido o nombra `/uiux-journey-map`. No inventa las fases. No escribe una solución, una pantalla, un prototipo ni una prueba.
- Cualquier plantilla deja el estado en `proposed`. La respuesta nombra `/uiux-solution-sketch` y no escribe ese archivo.
