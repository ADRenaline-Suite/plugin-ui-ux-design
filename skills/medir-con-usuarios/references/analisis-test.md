# Análisis del test

Fuente: ISO 9241-11:2018. Eficacia es la tasa de éxito. Eficiencia es tiempo, errores y asistencia. Satisfacción, en este plugin, es el SUS de Brooke (1996) cuando la sesión lo aplicó. Los problemas se ordenan con la gravedad de Nielsen Norman Group (0–4), la misma escala que `evaluar-ui`.

## Qué fija

Tasa de éxito por tarea, tiempo, problemas ordenados por gravedad y, si hubo SUS, la puntuación.

## Cómo hacerlo

1. Parte de las filas que entregue el usuario. No estimes un tiempo que no esté anotado. Si no hay datos, deja la entrega `proposed`.
2. Escribe el CSV de observaciones: `participante,tarea,exito,tiempo_s,errores,asistencia,notas`. `exito` es `si`, `no` o `parcial`. Una fila por participante y tarea.
3. Eficacia: éxitos / intentos, por tarea. Cuenta `parcial` aparte; no lo sumes como éxito.
4. Eficiencia: mediana del tiempo de quienes tuvieron `exito` = `si`, y el número de errores y de asistencias. Si hay menos de dos tiempos, no calcules mediana: lista los valores.
5. Cada problema observado nombra la tarea, la gravedad (0 no es un problema, 1 cosmético, 2 menor, 3 mayor, 4 catástrofe) y la corrección de diseño. No es un hallazgo de WCAG.
6. SUS, solo si se aplicó el cuestionario de Brooke o una traducción publicada de esos diez ítems. Si usaron otro cuestionario, no lo llames SUS: repórtalo por su nombre.

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

Contribución de los ítems 1, 3, 5, 7 y 9: respuesta − 1. Contribución de los ítems 2, 4, 6, 8 y 10: 5 − respuesta. SUS = suma de las diez contribuciones × 2,5. El resultado va de 0 a 100. Brooke no define un corte de «aprobado». No añadas una letra ni un adjetivo. Entrega la puntuación de cada participante y la media.

CSV del SUS, mismo `<NNN>` si va en esta entrega, o el `<NNN>` de esta entrega si el plan era otra: `participante,item,respuesta`. Si el plan y el análisis son entregas distintas, el CSV del análisis lleva el `<NNN>` del análisis.

7. Cierra en los términos de ISO 9241-11: eficacia, eficiencia y satisfacción, para estos usuarios, esta tarea y este contexto. No generalices a «la interfaz es usable».

## Plantilla

```markdown
# Análisis del test — <tarea>

- Plan:
- Contexto de uso:
- Datos: <archivo CSV>
- Fuente: ISO 9241-11:2018. SUS: Brooke (1996), si se aplicó.

## Por tarea

| Tarea | Intentos | Éxitos | Parciales | Éxito | Tiempo (mediana, s) |
| --- | --- | --- | --- | --- | --- |

## Problemas

| Gravedad | Tarea | Problema | Corrección |
| --- | --- | --- | --- |

## SUS

| Participante | Puntuación |
| --- | --- |
| Media | |

## Lectura ISO 9241-11

- Eficacia:
- Eficiencia:
- Satisfacción:
```

## Ejemplo

Cuatro de cinco completan «pagar con tarjeta» (éxito 0,8). Una persona ve el botón «Pagar» sin cambio cuando la red falla: gravedad 3. SUS de un participante con respuestas 4,2,5,1,4,2,5,1,4,2: contribuciones 3+3+4+4+3+3+4+4+3+3 = 34; 34 × 2,5 = 85. Se informa 85, sin letra.
