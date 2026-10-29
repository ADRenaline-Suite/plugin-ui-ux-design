<p align="right">Idioma:&emsp;<a href="wireflow.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Ordenar pantallas](../SKILL.es.md)

# Wireflow

Fuente: el flujo de usuario de la misma tarea, dibujado con un wireframe en cada paso. Sigue siendo UX, no UML.

## Qué fija

El mismo camino, con la jerarquía de cada paso a la vista.

## Qué deja abierto

Color, tipo y medidas para construir.

## Cómo hacerlo

1. Si hay un flujo de usuario `accepted` para esa tarea, sigue sus pantallas y sus vueltas. Si no lo hay y quien pide describe el camino en este turno, úsalo y cítalo. Si el camino no está dicho, escribe el flujo de usuario en este turno con la plantilla `linear-three`.
2. Un SVG por pantalla, en gris, con la misma regla visual que un wireframe: bloques, etiquetas, sin color de marca. `xmlns="http://www.w3.org/2000/svg"`, `viewBox`, sin scripts y sin `foreignObject`.
3. El Markdown ordena los pasos y apunta a cada SVG. Los SVG no tienen que estar enlazados: el enlace entre pantallas es el prototipo. Aquí el orden sale de la lista.
4. Incluye el paso de error cuando el flujo lo tiene. El marco de error conserva los datos que escribió la persona.
5. Cada paso nombra la tarea que cubre.

## Plantilla

```markdown
# Wireflow — <task>

- Tarea o caso de uso:
- Flujo de usuario de origen: <file> | descrito en este turno

## Pasos

| Paso | Pantalla | SVG |
| --- | --- | --- |
| 1 | Datos de pago | `<NNN>-wireflow-<topic>-details.svg` |
```

## Ejemplo

Tres SVG en gris: datos, resultado y error. El de error muestra el aviso y los campos de la tarjeta todavía rellenos. El Markdown los numera en el orden del flujo de usuario.

## Prerrequisitos

- **Tarea.** Un análisis de tareas `accepted`, o la tarea en este turno. Si no existe ninguno de los dos, escríbela con la plantilla `single-task`. Estado: `accepted`. Cámbialo con `/uiux-tasks`. Regenera este wireflow con `/uiux-wireflow`.
- **Camino.** Un flujo de usuario `accepted`, o el camino en este turno. Si no existe ninguno de los dos, escríbelo con la plantilla `linear-three`. Estado: `accepted`. Cámbialo con `/uiux-user-flow`. Regenera este wireflow con `/uiux-wireflow`.

## Indicaciones

En un mensaje:

```text
/uiux-wireflow para pagar con tarjeta.
La tarea es pagar con tarjeta.
El camino es carrito, pago, resultado. Si el cobro falla, vuelve al pago con los datos todavía rellenos.
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

- Los pasos siguen el flujo de usuario `accepted`, el camino descrito en este turno o la plantilla `linear-three` escrita en este turno, en ese orden. Cada paso nombra la tarea y apunta a un SVG en gris. `Assumed` nombra cualquier plantilla.
- Cada SVG tiene `xmlns`, un `viewBox`, bloques y etiquetas. Sin color de marca, sin scripts, sin `foreignObject` y sin enlaces entre SVG.
- El paso de error se incluye cuando el flujo lo tiene, y ese marco conserva los datos que se escribieron. No están el color, el tipo ni las medidas para construir.
