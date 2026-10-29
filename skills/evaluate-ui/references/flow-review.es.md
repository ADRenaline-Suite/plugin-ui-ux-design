<p align="right">Idioma:&emsp;<a href="flow-review.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Evaluar la interfaz](../SKILL.es.md)

# Revisión de flujo

No tiene otro estándar que las fuentes de este plugin. El criterio es la tarea: pasos de más, callejones sin salida y estados que faltan.

## Qué fija

Problemas del camino, no de la apariencia ni del código.

## Cómo hacerlo

1. Lee el flujo de usuario `accepted` o el wireflow `accepted`. Si la persona describe el camino en este turno, usa esa descripción. Si no hay camino, escribe un flujo de usuario con la plantilla `linear-three` y deja esta revisión en `proposed`.
2. Un paso de más es uno que no hace avanzar la tarea. Un callejón sin salida es una pantalla sin salida hacia el éxito o hacia la recuperación. Un estado que falta es uno de la lista (ideal, vacío, carga, parcial, error, éxito y, cuando aplican, sin permiso y sin conexión) que el camino no cubre.
3. El error tiene que poder volver a los datos que se escribieron.
4. Cada hallazgo nombra la pantalla y la corrección del camino. No vuelvas a dibujar el flujo aquí: si la corrección se acepta, se actualiza con `arrange-screens`.
5. Pide la revisión a `plugin-accessibility`. No audites WCAG. No verifiques el caso de uso.

## Plantilla

```markdown
# Revisión de flujo — <task>

- Flujo revisado:
- Fuente: el criterio de este plugin (pasos de más, callejones sin salida, estados que faltan).

| Tipo | Pantalla | Hallazgo | Corrección |
| --- | --- | --- | --- |

Accesibilidad: pide la revisión a `plugin-accessibility`.
```

## Ejemplo

Tipo: callejón sin salida. Pantalla: error de pago. Hallazgo: no hay una acción para volver a los datos. Corrección: un regreso a la pantalla de la tarjeta, que conserva lo que se escribió. Tipo: estado que falta. El estado de carga del cobro no aparece en el camino.

## Prerrequisitos

- **Camino.** Un flujo de usuario `accepted`, o el camino de este turno. Si no existe ninguno, escríbelo con la plantilla `linear-three`. Estado de esta revisión: `proposed` cuando ese flujo se escribió en este turno; `accepted` cuando el camino ya existía. Cambia el camino con `/uiux-user-flow`. Regenera esta revisión con `/uiux-flow-review`.

## Indicaciones

En un mensaje:

```text
/uiux-flow-review de pagar con tarjeta.
La tarea es pagar con tarjeta.
El camino es carrito, pago, resultado. Si el cobro falla, vuelve al pago con los datos todavía rellenos.
```

En orden, omitiendo los que ya se cumplieron:

```text
/uiux-user-flow para pagar con tarjeta.
La tarea es pagar con tarjeta.
Pantallas: carrito, pago, resultado. Si el cobro falla, vuelve al pago con los datos todavía rellenos.
```

## Terminado

- Los hallazgos son solo pasos de más, callejones sin salida o estados que faltan. Cada uno nombra la pantalla y una corrección del camino. El flujo no se volvió a dibujar aquí. Cuando el camino se escribió en este turno a partir de la plantilla `linear-three`, la entrega queda en `proposed` y Assumed lo dice.
- El error puede volver a los datos que se escribieron, o ese hueco es un hallazgo.
- El caso de uso no se verifica. No se asigna ningún criterio WCAG. El cierre pide la revisión a `plugin-accessibility`.
