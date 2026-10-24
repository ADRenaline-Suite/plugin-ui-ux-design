# Revisión del flujo

No tiene una norma distinta de las fuentes de este plugin. El criterio es el de la tarea: pasos de más, callejones sin salida y estados que faltan.

## Qué fija

Problemas del camino, no del aspecto ni del código.

## Cómo hacerlo

1. Lee el user flow o el wireflow `accepted`. Si el usuario describe el camino en este turno, usa esa descripción.
2. Un paso de más es uno que no acerca a la tarea. Un callejón es una pantalla sin salida hacia el éxito ni hacia una recuperación. Un estado que falta es uno de la lista (ideal, vacío, carga, parcial, error, éxito y, si aplican, sin permiso y sin conexión) que el camino no contempla.
3. El error tiene que poder volver a los datos escritos.
4. Cada hallazgo nombra la pantalla y la corrección del camino. No redibujes el flujo aquí: si la corrección se acepta, se actualiza con `ordenar-pantallas`.
5. Pide la revisión a `adrenaline-accessibility`. No audites WCAG. No verifiques el caso de uso.

## Plantilla

```markdown
# Revisión del flujo — <tarea>

- Flujo revisado:
- Fuente: criterio de este plugin (pasos de más, callejones, estados que faltan).

| Tipo | Pantalla | Hallazgo | Corrección |
| --- | --- | --- | --- |

Accesibilidad: pedir revisión a `adrenaline-accessibility`.
```

## Ejemplo

Tipo: callejón. Pantalla: error de pago. Hallazgo: no hay acción para volver a los datos. Corrección: una vuelta a la pantalla de la tarjeta, que conserva lo escrito. Tipo: estado que falta. La carga del cobro no aparece en el camino.
