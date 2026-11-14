<p align="right">Idioma:&emsp;<a href="solution-sketch.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Facilitar un design sprint](../SKILL.es.md)

# Boceto de solución

Fuente: Jake Knapp, John Zeratsky y Braden Kowitz, *Sprint* (Simon & Schuster, 2016), martes. Un boceto de solución es una idea, con título, que se explica sola, en tres tiempos. Compite. No es el sketch de pantalla de `/uiux-sketch`, que nombra los bloques de una pantalla.

## Qué fija

Una idea que compite, contada en tres tiempos, antes de que alguien elija ganador.

## Qué deja abierto

Qué idea gana, el storyboard de la ganadora, el prototipo y la prueba.

## Cómo hacerlo

1. La idea es la que escribió quien pide en este turno: un título y qué hace la persona. Si no dio ninguna, escribe la idea como «pendiente». No inventes una idea y no marques una como `accepted`.
2. Para quién: el objetivo de un marco del sprint `accepted`, o la persona nombrada en este turno. No inventes un nombre, una edad ni una biografía.
3. Tres tiempos, en orden: apertura, acción, resultado. La apertura es el momento objetivo. La acción es lo que esta idea hace hacer a la persona. El resultado es lo que ve cuando la tarea termina.
4. Una segunda idea es otro archivo y otro `<NNN>`. No sustituyas la primera idea.
5. El archivo dice que no es la opción elegida. No escribas la decisión, el wireflow, el prototipo ni la prueba.

## Plantilla

```markdown
# <NNN> — <título>

- State: proposed | accepted
- Chosen: no
- Source: Knapp, Zeratsky, and Kowitz, Sprint (2016), Tuesday

## Idea

## Para quién

## Tres tiempos

1. Apertura —
2. Acción —
3. Resultado —

## Siguiente

El ganador se elige con `/uiux-decision`. El camino elegido es `/uiux-wireflow`. Este archivo no elige.
```

## Ejemplo

Estado: `accepted`. Chosen: no. Idea: una pantalla que propone hoy a las 8 para dos personas, con confirmar y cambiar. Para quién: quien reserva desde el teléfono. Apertura: busca la confirmación. Acción: confirma la propuesta. Resultado: ve que la mesa quedó reservada. Siguiente: `/uiux-decision`.

## Prerrequisitos

- **Idea.** Nombrada en este turno. Si falta, escribe el archivo, deja la idea como pendiente y deja el estado en `proposed`. No hay plantilla. No inventes una idea. El cierre dice que no se inventó ninguna idea. Regenera con `/uiux-solution-sketch` cuando la idea exista.
- **Tarea.** Un análisis de tareas `accepted`, o la tarea en este turno. Si no existe ninguno, escribe el análisis de tareas en este turno con la plantilla `single-task` (una tarea nombrada desde el pedido; las subtareas son introducir los datos, confirmar, ver el resultado). Ese archivo de tareas sigue a `understand-user`. El estado del boceto de solución sigue siendo el estado de la idea. Cambia la tarea con `/uiux-tasks`. Regenera este boceto con `/uiux-solution-sketch`.
- **Tres tiempos.** En este turno, o derivados cuando la idea fue dada. Si faltan los tiempos y la idea fue dada, plantilla `three-beats`: la apertura es el momento objetivo de un marco del sprint `accepted`, o el inicio de la tarea; la acción es lo que dice el título de la idea; el resultado es que ven el resultado de la tarea. Estado: `accepted` cuando la idea vino de la persona y ningún otro hueco está pendiente. Cambia los tiempos con `/uiux-solution-sketch`. Regenera con `/uiux-solution-sketch`.
- **Para quién.** Un marco del sprint `accepted`, o la persona nombrada en este turno. Si falta, plantilla `role-from-task`: «la persona que hace <task>», sin nombre, edad ni biografía. Estado: `proposed`. Cámbialo con `/uiux-solution-sketch`. Regenera con `/uiux-solution-sketch`.

Una idea pendiente deja la entrega en `proposed` aunque los otros campos estén llenos. La plantilla `role-from-task` también la deja en `proposed`. La plantilla `three-beats` la deja en `accepted` solo cuando la idea vino de la persona y quién ya se conocía.

## Indicaciones

En un mensaje:

```text
/uiux-solution-sketch de reservar mesa.
Idea: una pantalla que propone hoy a las 8 para dos personas, con confirmar y cambiar.
Tarea: reservar una mesa.
Para quién: quien reserva desde el teléfono.
```

Una segunda idea es un segundo mensaje. No hay un comando anterior dentro de esta pieza. El prompt del marco está en [sprint-frame.es.md](sprint-frame.es.md).

## Terminado

- La idea es la que dio la persona, o dice pendiente y el estado es `proposed`. No se inventó ninguna idea. El archivo dice `Chosen: no`.
- Cuando la idea fue dada, hay tres tiempos. La plantilla `three-beats` se nombra en Assumed cuando los tiempos no estaban en el mensaje.
- Quién no tiene un nombre, una edad ni una biografía inventados. La plantilla `role-from-task` deja el estado en `proposed`.
- La decisión, el wireflow, el prototipo y la prueba no se escribieron. La respuesta nombra `/uiux-decision` y no lo ejecuta.
