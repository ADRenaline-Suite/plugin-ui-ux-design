<p align="right">Idioma:&emsp;<a href="tasks.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Entender a la persona](../SKILL.es.md)

# Tareas de la persona

Fuente: Nielsen Norman Group, Task Analysis. La meta, si viene de un caso de uso, es la de `plugin-project-manager`.

## Qué fija

La meta de la persona, las tareas, las subtareas y el orden en que ocurren. Cada tarea es algo que la persona termina. Una subtarea es un paso de esa tarea.

## Qué deja abierto

Pantallas, apariencia visual, texto final y métricas.

## Cómo hacerlo

1. Escribe la meta con las palabras de quien pide o con las del caso de uso. Si la meta no cabe en una frase, pide que la acoten. Si no se dice ninguna meta, aplica la plantilla `single-task`.
2. Lista las tareas en el orden en que las hace la persona. Numéralas.
3. Bajo cada tarea, lista las subtareas. No añadas una tarea que quien pide no describió y que la meta no exige. La plantilla `single-task` es la excepción: añade las tres subtareas de abajo.
4. Marca qué tarea depende de otra.
5. Cada tarea que después tendrá una pantalla debe poder citarse por su nombre. Usa esos nombres, tal como están, en las entregas posteriores.

## Plantilla

```markdown
# Tareas — <topic>

- Meta:
- Origen: caso de uso <name> | meta dicha en la conversación
- Fuente: Nielsen Norman Group, Task Analysis. ISO 9241-210:2019, contexto de uso.

## Tareas

1. <task>
   - Subtareas:
   - Depende de:
```

## Ejemplo

Meta: pagar un pedido con tarjeta.

1. Revisar el monto — subtareas: ver el total, ver el desglose. Depende de: ninguna.
2. Ingresar la tarjeta — subtareas: número, caducidad, código. Depende de: 1.
3. Confirmar el pago — subtareas: aceptar el cargo, ver el resultado. Depende de: 2.

## Prerrequisitos

- **Meta.** La dice quien pide el análisis, en este turno. Si falta, plantilla `single-task`: una tarea nombrada a partir del sustantivo o del verbo del pedido; las subtareas son ingresar los datos, confirmar y ver el resultado; cada una depende de la anterior, y la primera no depende de ninguna. Origen: `template single-task`. Estado: `accepted`. Cámbialo con `/uiux-tasks`. Regenera con `/uiux-tasks`.

## Indicaciones

En un mensaje:

```text
/uiux-tasks
La meta es pagar un pedido con tarjeta. Tareas: revisar el monto, ingresar la tarjeta, confirmar.
```

No hay un comando anterior. La indicación única es el camino.

## Terminado

- La meta es una frase. El origen es el caso de uso, la conversación o la plantilla `single-task`. Cuando se usó la plantilla, `Assumed` lo dice.
- Las tareas están numeradas y en orden. Cada una tiene subtareas y Depende de. No se añadió ninguna tarea que quien pide no describió y que la meta no exige, salvo las tres subtareas de la plantilla `single-task`.
- No hay pantallas, apariencia visual, texto final, métricas ni una persona.
- La línea de fuente cita Nielsen Norman Group, Task Analysis.
