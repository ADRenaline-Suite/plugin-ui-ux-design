<p align="right">Idioma:&emsp;<a href="brief.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Entender a la persona](../SKILL.es.md)

# Brief de diseño

Fuente: Design Council, Framework for Innovation (doble diamante). El brief es la salida de Define. ISO 9241-210:2019: los requisitos de uso se especifican antes de producir la solución. El diamante no es lineal: lo que se aprende al evaluar puede devolver el trabajo a una fase anterior.

## Qué fija

El problema, para quién es, las restricciones y los criterios de éxito medibles.

## Qué deja abierto

La forma de la interfaz. El brief no elige sketch, wireframe ni mock.

## Cómo hacerlo

1. El problema es la dificultad de una persona concreta, no una lista de pantallas. Si no está dicho, aplica la plantilla `task-unsupported`.
2. «Para quién es» usa la persona que dio quien pide. Si todavía no hay persona, describe a quien nombró quien pide y no inventes un perfil.
3. Restricciones: plataforma (web, iOS, Android, Windows), el kit de interfaz si existe, y los plazos si los hay. Si la plataforma no está dicha, aplica la plantilla `web`.
4. Cada criterio de éxito se puede comprobar: qué se mide, en qué tarea y contra qué umbral. Si quien pide no tiene umbral, aplica la plantilla `finish-unaided`. No pongas un porcentaje tuyo.
5. Si una prueba o una revisión posterior contradice el brief, no lo reescribas en silencio: eso es otra decisión, con el siguiente `<NNN>`, o una enmienda si quien pide la pide.

## Plantilla

```markdown
# Brief — <topic>

- Problema:
- Para quién es:
- Restricciones:
  - Plataforma:
  - Kit de interfaz:
  - Plazos:
- Fuente: Design Council, Framework for Innovation. ISO 9241-210:2019.

## Criterios de éxito

| Criterio | Tarea | Cómo se mide | Umbral |
| --- | --- | --- | --- |
```

## Ejemplo

Problema: quien paga no sabe si el cobro se hizo. Para quién es: la persona que nombró quien pide. Plataforma: web. Kit de interfaz: el de la tienda, si existe. Criterio: en la tarea «confirmar el pago», la persona identifica el resultado sin preguntar; quien pide da el umbral.

## Prerrequisitos

- **Problema.** Qué le falla a la persona, en este turno. Si falta, plantilla `task-unsupported`: «La persona todavía no puede completar <task> por un camino claro.» Estado: `proposed`. Cámbialo con `/uiux-brief`. Regenera con `/uiux-brief`.
- **Plataforma.** Web o la plataforma nativa, en este turno. Si falta, plantilla `web`: web, breakpoints de Material Design 3. Estado: `accepted` cuando el problema y el criterio vinieron de quien pide. Cámbialo con `/uiux-brief`. Regenera con `/uiux-brief`.
- **Criterio de éxito.** Medible, con el umbral que da quien pide el brief. Si falta el umbral, plantilla `finish-unaided`: la persona termina la tarea sin ayuda, y la celda del umbral dice «sin umbral numérico». Estado: `proposed`. Cámbialo con `/uiux-brief`. Regenera con `/uiux-brief`. No se inventa ningún porcentaje.

## Indicaciones

En un mensaje:

```text
/uiux-brief para el pago.
Problema: quien paga no sabe si el cobro se hizo.
Para quién es: la persona que paga el pedido desde un teléfono.
Plataforma: web.
Criterio de éxito: en la tarea confirmar el pago, identifica el resultado sin preguntar. Tú das el umbral.
```

No hay un comando anterior. La indicación única es el camino.

## Terminado

- El problema es la dificultad de una persona, o la plantilla `task-unsupported`. No es una lista de pantallas.
- Para quién es usa una persona que dio quien pide, o nombra a quien nombró quien pide, sin un perfil inventado.
- La plataforma es la que se dijo, o la plantilla `web`. Cada criterio de éxito tiene una tarea y una medida. El umbral es el que dio quien pide, o «sin umbral numérico» de la plantilla `finish-unaided`. No se inventó ningún porcentaje. Cuando se usó `task-unsupported` o `finish-unaided`, la entrega es `proposed`.
- No se elige la forma de la interfaz (sketch, wireframe, mock).
