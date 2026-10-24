# Brief de diseño

Fuente: Design Council, Framework for Innovation (doble diamante). El brief es la salida de definir. ISO 9241-210:2019: los requisitos de uso se especifican antes de producir la solución. El diamante no es lineal: lo que se aprenda al evaluar puede devolver a una fase anterior.

## Qué fija

El problema, para quién es, las restricciones y los criterios de éxito medibles.

## Qué deja abierto

La forma de la interfaz. El brief no elige sketch, wireframe ni mock.

## Cómo hacerlo

1. El problema es la dificultad de una persona concreta, no una lista de pantallas.
2. «Para quién» usa la persona que aportó el usuario. Si aún no hay persona, describe a quién nombró el usuario y no inventes una ficha.
3. Restricciones: plataforma (web, iOS, Android, Windows), UI kit si existe, y plazos si los hay. Si la plataforma no está dicha, pídela.
4. Cada criterio de éxito se puede comprobar: qué se mide, en qué tarea y con qué umbral. Si el usuario no tiene umbral, pregunta. No pongas un porcentaje de tu cuenta.
5. Si más adelante un test o una revisión contradice el brief, no lo reescribas en silencio: es otra decisión, con el siguiente `<NNN>`, o una enmienda si el usuario lo pide.

## Plantilla

```markdown
# Brief — <tema>

- Problema:
- Para quién:
- Restricciones:
  - Plataforma:
  - UI kit:
  - Plazos:
- Fuente: Design Council, Framework for Innovation. ISO 9241-210:2019.

## Criterios de éxito

| Criterio | Tarea | Cómo se mide | Umbral |
| --- | --- | --- | --- |
```

## Ejemplo

Problema: quien paga no sabe si el cargo se hizo. Para quién: la persona que el usuario nombró. Plataforma: web. UI kit: el de la tienda, si existe. Criterio: en la tarea «confirmar el pago», la persona identifica el resultado sin preguntar; el umbral lo da el usuario.
