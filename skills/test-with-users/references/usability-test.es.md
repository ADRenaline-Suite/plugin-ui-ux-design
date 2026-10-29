<p align="right">Idioma:&emsp;<a href="usability-test.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Probar con personas](../SKILL.es.md)

# Prueba de usabilidad

Fuente: Nielsen Norman Group, Usability Testing 101. ISO 9241-11:2018 define qué se puede concluir después (eficacia, eficiencia, satisfacción); este manual solo planea la sesión.

## Qué fija

Tareas de escenario, quién participa, qué observar y cómo registrarlo.

## Qué deja abierto

Los resultados. `test-analysis` los calcula cuando existen los datos. Este plugin no recluta ni modera.

## Cómo hacerlo

1. La meta de la prueba es una tarea ya enunciada. Si no lo es, escríbela con la plantilla `single-task`.
2. Cada tarea es un escenario realista y no contiene la respuesta. No digas el nombre del botón ni el camino. «Paga tu pedido con una tarjeta» está bien. «Pulsa Pay y luego Done» no.
3. Participantes: los criterios que da la persona (quién y cuántos). Si no dan el número, aplica la plantilla `nielsen-5`: 5 personas, una sesión cualitativa, no reclutadas. Cita Nielsen, Why You Only Need to Test with 5 Users (2000). No inventes nombres. Una sesión cualitativa no es un cálculo estadístico; no la presentes como tal.
4. Qué observar: si completaron la tarea, en cuánto tiempo, qué errores, si pidieron ayuda, y citas textuales. Quien modera lo anota. El CSV de este plan puede salir vacío, con la cabecera, para esa sesión; el análisis carga los datos.
5. Si se va a pasar el SUS, dilo en el plan y reserva los diez ítems para el final. No los mezcles con la tarea.
6. El escenario de prueba de `plugin-qa-engineer` no se copia aquí.

## Plantilla

```markdown
# Usability test — <task>

- Goal of the session:
- Participants: <criteria and number the user gave>
- Who moderates: a person. This plugin does not recruit or run the session.
- Source: Nielsen Norman Group, Usability Testing 101.

## Scenario tasks

1. <scenario that does not reveal the control>

## What to write down

| Datum | How |
| --- | --- |
| Success | yes, no, or partial, per task |
| Time | seconds per task |
| Errors and assistance | what happened |
| Quotes | verbatim |

## Record

CSV `<NNN>-usability-test-<topic>.csv` with columns `participant,task,success,time_s,errors,assistance,notes`. One row per participant and task. It is filled in during the session.
```

## Ejemplo

Tarea de escenario: «Terminas el pedido de camino al trabajo y quieres pagarlo con la tarjeta que ya usas.» No dice que el control se llame «Pay». Participantes: cinco personas que ya han comprado, el número que dio la persona.

## Prerrequisitos

- **Tarea.** La tarea a probar, en este turno, o un análisis de tareas `accepted`. Si no existe ninguno, escríbela con la plantilla `single-task`. Estado: `accepted`. Cámbiala con `/uiux-tasks`. Regenera este plan con `/uiux-usability-test`.
- **Número de participantes.** Lo da quien pide el plan. Si falta, plantilla `nielsen-5`: 5 personas, cualitativo, no reclutadas. Nielsen, Why You Only Need to Test with 5 Users (2000). No inventes nombres. Estado: `accepted`. Cámbialo con `/uiux-usability-test`. Regenera con `/uiux-usability-test`.

## Indicaciones

En un mensaje:

```text
/uiux-usability-test of pay with a card.
The task is pay with a card.
Five people who have already bought in the shop take part.
```

En orden, omitiendo los que ya están cumplidos:

```text
/uiux-tasks
The goal is to pay an order with a card. Tasks: review the amount, enter the card, confirm.
```

## Terminado

- La meta es una tarea ya enunciada, o la plantilla `single-task`. Cada tarea de escenario no nombra el control ni el camino.
- Los participantes son los criterios y el número que dio la persona, o la plantilla `nielsen-5` cuando faltaba el número. Assumed dice cuál, y que no están reclutadas. No se inventaron nombres. El archivo dice que una persona modera y que este plugin no recluta ni corre la sesión.
- Qué anotar cubre el éxito, el tiempo, los errores, la ayuda y las citas. El CSV puede ser de solo cabecera. Los resultados no se calculan aquí. No es un escenario de prueba de `plugin-qa-engineer`.
