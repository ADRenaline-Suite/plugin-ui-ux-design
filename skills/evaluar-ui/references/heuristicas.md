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
| 4 | Catástrofe: impide completar la tarea |

## Heurísticas

Usa el nombre de Nielsen Norman Group y, entre paréntesis, la glosa.

1. Visibility of system status (visibilidad del estado del sistema)
2. Match between system and the real world (correspondencia con el mundo real)
3. User control and freedom (control y libertad del usuario)
4. Consistency and standards (consistencia y estándares)
5. Error prevention (prevención de errores)
6. Recognition rather than recall (reconocer antes que recordar)
7. Flexibility and efficiency of use (flexibilidad y eficiencia de uso)
8. Aesthetic and minimalist design (estética y diseño minimalista)
9. Help users recognize, diagnose, and recover from errors (ayudar a reconocer, diagnosticar y recuperarse de errores)
10. Help and documentation (ayuda y documentación)

## Cómo hacerlo

1. Recorre los estados de la pantalla, no solo el ideal. El error que borra lo escrito es un hallazgo.
2. Un hallazgo, una heurística. Si encaja en dos, elige la que explica la corrección.
3. La corrección dice qué cambia en la pantalla. No escribas el código.
4. Cierra pidiendo la revisión a `adrenaline-accessibility`. No asignes un criterio WCAG.

## Plantilla

```markdown
# Heurísticas — <pantalla>

- Qué se revisó: <archivo o descripción>
- Fuente: Nielsen Norman Group, 10 heurísticas y gravedad 0–4.

| # | Heurística | Pantalla | Estado | Gravedad | Hallazgo | Corrección |
| --- | --- | --- | --- | --- | --- | --- |

Accesibilidad: pedir revisión a `adrenaline-accessibility`.
```

## Ejemplo

Pantalla: pago. Estado: error de red. Heurística: Visibility of system status (visibilidad del estado del sistema). Gravedad: 3. Hallazgo: el botón sigue en «Pagar» y no hay mensaje. Corrección: mensaje de error y acción de reintentar; conservar los datos de la tarjeta.
