<p align="right">Idioma:&emsp;<a href="test-analysis.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Probar con personas](../SKILL.es.md)

# Análisis de la prueba

Fuente: ISO 9241-11:2018. La eficacia es la tasa de éxito. La eficiencia es el tiempo, los errores y la asistencia. La satisfacción, en este plugin, es el SUS de Brooke (1996) cuando la sesión lo usó. Los problemas se ordenan con la gravedad de Nielsen Norman Group (0–4), la misma escala que `evaluate-ui`.

## Qué fija

La tasa de éxito por tarea, el tiempo, los problemas ordenados por gravedad y, si hubo un SUS, la puntuación.

## Cómo hacerlo

1. Parte de las filas que entrega la persona. No estimes un tiempo que no se anotó. Si no hay datos, deja la entrega `proposed`.
2. Escribe el CSV de observaciones: `participant,task,success,time_s,errors,assistance,notes`. `success` es `yes`, `no` o `partial`. Una fila por participante y tarea. La prosa de `notes` sigue el idioma del artefacto.
3. Eficacia: éxitos / intentos, por tarea. Cuenta `partial` aparte; no lo sumes como éxito.
4. Eficiencia: la mediana del tiempo de quienes tienen `success` = `yes`, y el número de errores y de ayudas. Si hay menos de dos tiempos, no calcules una mediana: lista los valores.
5. Cada problema observado nombra la tarea, la gravedad (0 no es un problema, 1 cosmético, 2 menor, 3 mayor, 4 catástrofe) y la corrección de diseño. No es un hallazgo de WCAG.
6. SUS, solo si se usó el cuestionario de Brooke, o una traducción publicada de esos diez ítems. Si usaron otro cuestionario, no lo llames SUS: infórmalo con su propio nombre.

### Puntuación SUS

Ítems de Brooke (1996), en su inglés. La respuesta es 1–5.

1. I think that I would like to use this system frequently.
2. I found the system unnecessarily complex.
3. I thought the system was easy to use.
4. I think that I would need the support of a technical person to be able to use this system.
5. I found the various functions in this system were well integrated.
6. I thought there was too much inconsistency in this system.
7. I would imagine that most people would learn to use this system very quickly.
8. I found the system very cumbersome to use.
9. I felt very confident using the system.
10. I needed to learn a lot of things before I could get going with this system.

Aportación de los ítems 1, 3, 5, 7 y 9: respuesta − 1. Aportación de los ítems 2, 4, 6, 8 y 10: 5 − respuesta. SUS = suma de las diez aportaciones × 2.5. El resultado va de 0 a 100. Brooke no define un corte de «aprobado». No añadas una letra ni un adjetivo. Entrega la puntuación de cada participante y la media.

CSV del SUS, el mismo `<NNN>` si pertenece a esta entrega, o el `<NNN>` de esta entrega si el plan fue otra entrega: `participant,item,answer`. Si el plan y el análisis son entregas distintas, el CSV del análisis lleva el `<NNN>` del análisis.

7. Cierra en los términos de ISO 9241-11: eficacia, eficiencia y satisfacción, para estas personas, esta tarea y este contexto. No generalices a «la interfaz es usable».

## Plantilla

```markdown
# Test analysis — <task>

- Plan:
- Context of use:
- Data: <CSV file>
- Source: ISO 9241-11:2018. SUS: Brooke (1996), if it was used.

## Per task

| Task | Attempts | Successes | Partials | Success | Time (median, s) |
| --- | --- | --- | --- | --- | --- |

## Problems

| Severity | Task | Problem | Correction |
| --- | --- | --- | --- |

## SUS

| Participant | Score |
| --- | --- |
| Mean | |

## ISO 9241-11 reading

- Effectiveness:
- Efficiency:
- Satisfaction:
```

## Ejemplo

Cuatro de cinco completan «pagar con tarjeta» (éxito 0.8). Una persona ve el botón «Pay» sin cambios cuando falla la red: gravedad 3. SUS de un participante con respuestas 4,2,5,1,4,2,5,1,4,2: aportaciones 3+3+4+4+3+3+4+4+3+3 = 34; 34 × 2.5 = 85. Informa 85, sin letra.

## Prerrequisitos

- **Datos.** Las filas de la prueba, en este turno. Sin filas, escribe el archivo, deja los resultados en blanco y deja la entrega `proposed`. No se inventan resultados. El cierre dice que las filas se dejaron en blanco. Comando anterior: `/uiux-usability-test`. Regenera con `/uiux-test-analysis` cuando existan las filas.

## Indicaciones

En un mensaje:

```text
/uiux-test-analysis of pay with a card.
Data: participant, task, success, time, problem.
Paste the rows here. SUS, if there was one: the ten answers.
```

En orden, omitiendo los que ya están cumplidos:

```text
/uiux-usability-test of pay with a card.
The task is pay with a card.
Five people who have already bought in the shop take part.
```

## Terminado

- Las filas son las que entregó la persona. No se estimó ningún tiempo. Sin filas, la entrega es `proposed`.
- Las columnas del CSV son `participant,task,success,time_s,errors,assistance,notes`. `success` es `yes`, `no` o `partial`. `partial` no se cuenta como éxito. La eficacia y la eficiencia siguen la referencia. Con menos de dos tiempos con éxito, se listan los valores y no se calcula una mediana.
- Cada problema tiene una tarea, una gravedad 0–4 y una corrección de diseño. No es un hallazgo de WCAG.
- El SUS se puntúa solo para los diez ítems de Brooke, sin corte de aprobado, letra ni adjetivo. Otro cuestionario conserva su propio nombre. El cierre es eficacia, eficiencia y satisfacción para estas personas, esta tarea y este contexto, y no dice que la interfaz es usable.
