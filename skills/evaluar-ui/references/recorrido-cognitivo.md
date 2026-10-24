# Recorrido cognitivo

Fuente: Wharton, Rieman, Lewis y Polson (1994), The Cognitive Walkthrough Method: A Practitioner's Guide.

## Qué fija

Si una persona que conoce la tarea y no conoce esta interfaz puede dar cada paso explorando. No mide la rapidez de quien ya es experto.

## Las cuatro preguntas

En cada paso, en este orden:

1. ¿Intentará el efecto correcto?
2. ¿Verá la acción?
3. ¿Asociará la acción con el efecto?
4. ¿Verá el progreso?

Una respuesta «no» es un problema. Anota la pregunta, la evidencia en la pantalla y la corrección.

## Cómo hacerlo

1. La tarea y sus pasos salen del análisis de tareas o del user flow `accepted`. Si no están, pídelos.
2. Recorre la historia de una persona nueva. No des por sabido un icono sin rótulo.
3. El éxito del paso 4 es que la pantalla muestre el avance. Un botón que no cambia en el error falla la pregunta 4.
4. Pide la revisión a `adrenaline-accessibility`. No audites WCAG.

## Plantilla

```markdown
# Recorrido cognitivo — <tarea>

- Persona supuesta: conoce la tarea y no esta interfaz
- Pasos de origen: <archivo>
- Fuente: Wharton, Rieman, Lewis y Polson (1994)

## Paso <n> — <acción>

| Pregunta | ¿Sí? | Evidencia |
| --- | --- | --- |
| ¿Intentará el efecto correcto? | | |
| ¿Verá la acción? | | |
| ¿Asociará la acción con el efecto? | | |
| ¿Verá el progreso? | | |

- Problema:
- Corrección:

Accesibilidad: pedir revisión a `adrenaline-accessibility`.
```

## Ejemplo

Paso «confirmar el pago» en el estado de error de red. Pregunta 4: no. El botón sigue diciendo «Pagar» y no aparece el resultado. Corrección: mostrar el fallo y una acción de reintentar, con los datos de la tarjeta todavía escritos.
