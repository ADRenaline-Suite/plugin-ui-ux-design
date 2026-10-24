# Test de usabilidad

Fuente: Nielsen Norman Group, Usability Testing 101. ISO 9241-11:2018 define qué se podrá concluir después (eficacia, eficiencia, satisfacción); este manual solo planea la sesión.

## Qué fija

Tareas escenario, quién participa, qué observar y cómo registrarlo.

## Qué deja abierto

Los resultados. Los calcula `analisis-test` cuando existan los datos. Este plugin no recluta ni modera.

## Cómo hacerlo

1. El objetivo del test es una tarea ya dicha. Si no está, pídela.
2. Cada tarea es un escenario realista y no contiene la respuesta. No digas el nombre del botón ni el camino. «Paga tu pedido con tarjeta» sí. «Pulsa Pagar y luego Listo» no.
3. Participantes: los criterios que dé el usuario (quién y cuántos). Si no da el número, pregunta. No inventes una muestra. Una sesión cualitativa no es un cálculo estadístico; no lo presentes como tal.
4. Qué observar: si completó la tarea, en cuánto tiempo, qué errores, si pidió ayuda, y citas textuales. La persona que modera lo anota. El CSV de este plan puede ir vacío, con el encabezado, para esa sesión; los datos los carga el análisis.
5. Si se va a pasar el SUS, dilo en el plan y reserva los diez ítems para el final. No los mezcles con la tarea.
6. El escenario de prueba de `adrenaline-qa-engineer` no se copia aquí.

## Plantilla

```markdown
# Test de usabilidad — <tarea>

- Objetivo de la sesión:
- Participantes: <criterios y número que dio el usuario>
- Quién modera: una persona. Este plugin no recluta ni conduce.
- Fuente: Nielsen Norman Group, Usability Testing 101.

## Tareas escenario

1. <escenario que no revela el control>

## Qué anotar

| Dato | Cómo |
| --- | --- |
| Éxito | sí, no o parcial, por tarea |
| Tiempo | segundos por tarea |
| Errores y asistencia | qué ocurrió |
| Citas | textuales |

## Registro

CSV `<NNN>-test-usabilidad-<tema>.csv` con columnas `participante,tarea,exito,tiempo_s,errores,asistencia,notas`. Una fila por participante y tarea. Se llena en la sesión.
```

## Ejemplo

Tarea escenario: «Terminas el pedido en el traslado al trabajo y quieres dejarlo pagado con la tarjeta que ya usas.» No dice que el control se llama «Pagar». Participantes: cinco personas que ya compraron, número dado por el usuario.
