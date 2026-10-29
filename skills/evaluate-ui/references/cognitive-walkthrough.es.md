<p align="right">Idioma:&emsp;<a href="cognitive-walkthrough.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Evaluar la interfaz](../SKILL.es.md)

# Recorrido cognitivo

Fuente: Wharton, Rieman, Lewis y Polson (1994), The Cognitive Walkthrough Method: A Practitioner's Guide.

## Qué fija

Si una persona que conoce la tarea y no conoce esta interfaz puede dar cada paso explorando. No mide qué tan rápida es ya una persona experta.

## Las cuatro preguntas

En cada paso, en este orden:

1. ¿La persona intentará lograr el efecto correcto?
2. ¿Notará que la acción correcta está disponible?
3. ¿Asociará la acción correcta con el efecto que intenta lograr?
4. Si se realiza la acción correcta, ¿verá que hay avance?

Un «no» es un problema. Anota la pregunta, la evidencia en la pantalla y la corrección. Escribe las preguntas en el idioma del artefacto; conserva este orden.

## Cómo hacerlo

1. La tarea y sus pasos vienen del análisis de tareas o del flujo de usuario `accepted`. Si no están, escríbelos con las plantillas `single-task` y `linear-three` y deja esta revisión en `proposed`.
2. Recorre la historia de una persona nueva. No supongas que un icono sin etiqueta se conoce.
3. El éxito en la pregunta 4 es que la pantalla muestra el avance. Un botón que no cambia en el error falla la pregunta 4.
4. Pide la revisión a `plugin-accessibility`. No audites WCAG.

## Plantilla

```markdown
# Recorrido cognitivo — <task>

- Persona supuesta: conoce la tarea y no esta interfaz
- Origen de los pasos: <archivo>
- Fuente: Wharton, Rieman, Lewis y Polson (1994)

## Paso <n> — <acción>

| Pregunta | ¿Sí? | Evidencia |
| --- | --- | --- |
| ¿Intentarán el efecto correcto? | | |
| ¿Verán la acción? | | |
| ¿Asociarán la acción con el efecto? | | |
| ¿Verán el avance? | | |

- Problema:
- Corrección:

Accesibilidad: pide la revisión a `plugin-accessibility`.
```

## Ejemplo

Paso «confirmar el pago» en el estado de error de red. Pregunta 4: no. El botón sigue diciendo «Pagar» y el resultado no aparece. Corrección: mostrar el fallo y una acción de reintento, con los datos de la tarjeta todavía rellenos.

## Prerrequisitos

- **Tarea.** Un análisis de tareas `accepted`, o la tarea de este turno. Si no existe ninguno, escríbela con la plantilla `single-task`. Cámbiala con `/uiux-tasks`. Regenera este recorrido con `/uiux-cognitive-walkthrough`.
- **Pasos.** Un flujo de usuario `accepted`, o los pasos de este turno. Si no existe ninguno, escribe el flujo con la plantilla `linear-three`. Cámbialo con `/uiux-user-flow`. Regenera este recorrido con `/uiux-cognitive-walkthrough`. Estado de esta revisión: `accepted` cuando la tarea y los pasos ya existían; `proposed` cuando alguno se escribió en este turno a partir de una plantilla.

## Indicaciones

En un mensaje:

```text
/uiux-cognitive-walkthrough del pago.
La tarea es pagar con tarjeta.
Pasos: ver el monto, ingresar la tarjeta, confirmar. En un error de red el botón sigue diciendo Pagar.
```

En orden, omitiendo los que ya se cumplieron:

```text
/uiux-tasks
La meta es pagar un pedido con tarjeta. Tareas: revisar el monto, ingresar la tarjeta, confirmar.
```

```text
/uiux-user-flow para pagar con tarjeta.
La tarea es pagar con tarjeta.
Pantallas: carrito, pago, resultado. Si el cobro falla, vuelve al pago con los datos todavía rellenos.
```

## Terminado

- Cada paso de la tarea tiene las cuatro preguntas, en orden, cada una con sí o no y evidencia de la pantalla. Un «no» tiene un problema y una corrección. Cuando la tarea o los pasos se escribieron en este turno a partir de una plantilla, la entrega queda en `proposed` y Assumed lo dice.
- La persona supuesta conoce la tarea y no esta interfaz. Un control sin etiqueta no se trata como conocido.
- No se asigna ningún criterio WCAG. El cierre pide la revisión a `plugin-accessibility`.
