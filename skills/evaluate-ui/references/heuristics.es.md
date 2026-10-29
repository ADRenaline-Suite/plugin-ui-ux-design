<p align="right">Idioma:&emsp;<a href="heuristics.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Evaluar la interfaz](../SKILL.es.md)

# Heurísticas

Fuente: Nielsen Norman Group, 10 Usability Heuristics for User Interface Design, y Severity Ratings for Usability Problems.

## Qué fija

Cada problema de usabilidad visible en la pantalla: la heurística, el lugar, la gravedad y la corrección.

## Gravedad

| Valor | Significado |
| --- | --- |
| 0 | No es un problema de usabilidad |
| 1 | Cosmético |
| 2 | Menor |
| 3 | Mayor |
| 4 | Catástrofe: bloquea la tarea |

## Heurísticas

Usa el nombre de Nielsen Norman Group y, entre paréntesis, una glosa en el idioma del artefacto.

1. Visibility of system status
2. Match between system and the real world
3. User control and freedom
4. Consistency and standards
5. Error prevention
6. Recognition rather than recall
7. Flexibility and efficiency of use
8. Aesthetic and minimalist design
9. Help users recognize, diagnose, and recover from errors
10. Help and documentation

## Cómo hacerlo

1. Recorre los estados de la pantalla, no solo el ideal. Un error que borra lo que se escribió es un hallazgo.
2. Un hallazgo, una heurística. Si encaja en dos, elige la que explica la corrección.
3. La corrección dice qué cambia en la pantalla. No escribas el código.
4. Cierra pidiendo la revisión a `plugin-accessibility`. No asignes un criterio WCAG.

## Plantilla

```markdown
# Heurísticas — <screen>

- Qué se revisó: <archivo o descripción>
- Fuente: Nielsen Norman Group, 10 heurísticas y gravedad 0–4.

| # | Heurística | Pantalla | Estado | Gravedad | Hallazgo | Corrección |
| --- | --- | --- | --- | --- | --- | --- |

Accesibilidad: pide la revisión a `plugin-accessibility`.
```

## Ejemplo

Pantalla: pago. Estado: error de red. Heurística: Visibility of system status. Gravedad: 3. Hallazgo: el botón sigue diciendo «Pagar» y no hay mensaje. Corrección: un mensaje de error y una acción de reintento; conservar los datos de la tarjeta.

## Prerrequisitos

- **Pantalla o flujo.** Un archivo `accepted`, o lo que se describe en este turno. Si no existe ninguno, escribe un sketch en este turno con la plantilla `single-task` y la plantilla `task-blocks` (un bloque por subtarea, más la acción principal) y revisa ese sketch. Estado de esta revisión: `proposed`, porque la pantalla se asumió. Cambia la pantalla con `/uiux-sketch` o `/uiux-mock`. Regenera esta revisión con `/uiux-heuristics`.

## Indicaciones

En un mensaje:

```text
/uiux-heuristics del pago en un error de red.
La pantalla muestra el botón Pagar sin mensaje y conserva los datos de la tarjeta.
```

En orden, omitiendo los que ya se cumplieron:

```text
/uiux-mock de la pantalla de pago.
La tarea es pagar con tarjeta.
El camino es carrito, pago, resultado. Si el cobro falla, vuelve al pago con los datos todavía rellenos.
Kit de interfaz, tema claro: acción #0066cc, fondo #ffffff, texto #1a1a1a, error #b00020, tipo Source Sans 3, espacio 16 px, radio 4 px, sombra 0 2 px 8 px.
```

## Terminado

- Cada hallazgo tiene un nombre de heurística de Nielsen Norman Group, la pantalla, el estado, una gravedad de 0 a 4, el hallazgo y una corrección que dice qué cambia en la pantalla. Sin código. Cuando la pantalla se escribió en este turno a partir de una plantilla, la entrega queda en `proposed` y Assumed lo dice.
- Se recorrieron estados distintos del ideal cuando la pantalla los tiene. Un error que borra los datos escritos es un hallazgo cuando está presente.
- Ningún criterio WCAG se marca cumplido ni fallido. El cierre pide la revisión a `plugin-accessibility`.
