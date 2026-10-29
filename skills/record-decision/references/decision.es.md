<p align="right">Idioma:&emsp;<a href="decision.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Registrar una decisión](../SKILL.es.md)

# Decisión de diseño

Fuente: Michael Nygard, Documenting Architecture Decisions (2011). El título puede decir «decisión de diseño»: el formato es el de Nygard.

## Qué fija

El contexto, las opciones consideradas, la decisión y las consecuencias. El estado dice si gobierna.

## Cómo hacerlo

1. Contexto: qué fuerza la decisión (un hallazgo, una restricción de plataforma, una prueba). Cita el `<NNN>` de ese artefacto si existe.
2. Opciones: al menos dos, con su costo. Incluye la que se descartó.
3. Decisión: la que tomó quien pide, en una frase. Si todavía no eligió, el estado es `proposed` y la decisión dice «pendiente».
4. Consecuencias: qué entrega tiene que cambiar (handoff, kit, flujo) y qué queda fuera.
5. No copies el handoff dentro de la decisión. Enlázalo por el nombre del archivo.

## Plantilla

```markdown
# <NNN> — <title>

- Estado: proposed | accepted | deprecated | superseded
- Sustituye a: <N o ninguno>
- Fuente: Michael Nygard (2011)

## Contexto

## Opciones

1. <option> — <consecuencia de elegirla>

## Decisión

## Consecuencias
```

## Ejemplo

Estado: `accepted`. Contexto: el hallazgo de heurísticas del pago ante un error de red (gravedad 3). Opciones: una pantalla de error vacía, o el aviso sobre el formulario. Decisión: el aviso sobre el formulario, con la tarjeta intacta. Consecuencias: enmendar el handoff de pago; el flujo de usuario no añade una pantalla.

## Prerrequisitos

- **Decisión.** La toma quien pide el registro. Si no está tomada, escribe el archivo, deja el estado `proposed` y escribe la decisión como pendiente. No hay plantilla. No elijas una opción. El cierre dice que la decisión no se tomó y que no se eligió ninguna opción. Regenera con `/uiux-decision` cuando la decisión exista.

## Indicaciones

En un mensaje:

```text
/uiux-decision del reintento en el pago.
Decisión tomada: el aviso se queda en la misma pantalla y los datos de la tarjeta se conservan.
Opciones descartadas: una pantalla de error vacía.
```

No hay un comando anterior. La indicación única es el camino.

## Terminado

- Están el contexto, al menos dos opciones (incluida la descartada), la decisión y las consecuencias. La decisión es la que tomó quien pide. Si no ha elegido, el estado es `proposed` y la decisión dice pendiente. La opción ganadora no la eligió el skill.
- El estado del archivo y la fila de `STATUS.md` son el mismo. Un reemplazo usa el siguiente `<NNN>` y marca la fila anterior `superseded`.
- Las consecuencias nombran qué entrega cambia. El handoff, el kit y el flujo no se reescribieron en este archivo.
