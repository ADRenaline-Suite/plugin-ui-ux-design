<p align="right">Idioma:&emsp;<a href="journey-map.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Entender a la persona](../SKILL.es.md)

# Mapa de recorrido

Fuente: Nielsen Norman Group, Journey Mapping 101.

## Qué fija

La persona que dio quien pide, el escenario y las fases con acciones, pensamientos, emociones y oportunidades.

## Qué deja abierto

La solución de interfaz. Una oportunidad no es una pantalla.

## Cómo hacerlo

1. Copia la persona como la dio quien pide: nombre o rol, y lo que ya se sabe de ella. Si no hay persona, aplica la plantilla `role-from-task`. No inventes un nombre, una edad ni una biografía.
2. El escenario es la situación concreta en la que ocurre la meta (dónde, con qué prisa, con qué información). Si quien pide no lo dio, aplica la plantilla `complete-the-task`.
3. Las fases siguen el orden de las tareas, si las tareas ya existen. Si no existen, toma las fases del relato de quien pide. Si tampoco hay relato, las fases son las tres subtareas de la plantilla `single-task` (ingresar los datos, confirmar, ver el resultado). No inventes tramos de más. El pensamiento y la emoción sin evidencia se quedan en «sin evidencia».
4. En cada fase escribe acción, pensamiento, emoción y oportunidad. El pensamiento y la emoción salen de lo que contó quien pide (una cita, una queja, una observación). Si no hay evidencia, deja el campo en «sin evidencia» y pregunta. No rellenes una curva emocional.
5. La oportunidad dice qué tendría que cambiar en esa fase. No dibujes la pantalla.

## Plantilla

```markdown
# Mapa de recorrido — <topic>

- Persona: <como la dio quien pide>
- Escenario:
- Meta:
- Fuente: Nielsen Norman Group, Journey Mapping 101.

## Fases

### <phase>
- Acción:
- Pensamiento:
- Emoción:
- Oportunidad:
```

## Ejemplo

Persona (de quien pide): «Ana paga el pedido de la tienda una vez por semana desde el teléfono, de camino al trabajo.»

Fase «Confirmar el pago». Acción: acepta el cargo. Pensamiento: «sin evidencia». Emoción: «sin evidencia». Oportunidad: saber en el acto si el cobro se hizo. Esa oportunidad queda escrita; la pantalla se pide a `specify-screen`.

## Prerrequisitos

- **Persona.** La da quien pide el mapa. Si falta, plantilla `role-from-task`: «Rol: la persona que hace <task>. Sin nombre, sin edad, sin biografía.» El pensamiento y la emoción se quedan en «sin evidencia». Estado: `proposed`. Cámbialo con `/uiux-journey-map`. Regenera con `/uiux-journey-map`.
- **Escenario.** La situación en la que ocurre el recorrido, en este turno. Si falta, plantilla `complete-the-task`: «Quieren terminar <task>. Si falla, vuelven.» Estado: `proposed`. Cámbialo con `/uiux-journey-map`. Regenera con `/uiux-journey-map`.

## Indicaciones

En un mensaje:

```text
/uiux-journey-map para confirmar el pago.
Persona: Ana paga el pedido una vez por semana desde el teléfono, de camino al trabajo.
Escenario: va de camino al trabajo y quiere saber si el cobro se hizo.
```

No hay un comando anterior. La indicación única es el camino.

## Terminado

- La persona está copiada como la dio quien pide, o es la plantilla `role-from-task` sin nombre, edad ni biografía. `Assumed` dice cuál.
- El escenario es la situación que describió quien pide, o la plantilla `complete-the-task`. Las fases siguen las tareas si existen. No se inventó ningún tramo. Cuando se usó cualquiera de las dos plantillas, la entrega es `proposed`.
- Cada fase tiene acción, pensamiento, emoción y oportunidad. El pensamiento o la emoción sin evidencia dice «sin evidencia».
- Una oportunidad no es una pantalla. No se dibuja ninguna interfaz.
