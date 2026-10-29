<p align="right">Idioma:&emsp;<a href="implementation-review.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Evaluar la interfaz](../SKILL.es.md)

# Revisión de implementación

No tiene un estándar propio. El criterio es el handoff `accepted` y el kit de interfaz `accepted`. También se mira el mock cuando el handoff apunta a él.

## Qué fija

Diferencias entre la pantalla construida y lo que se especificó: medidas, tokens, estados, tamaños de ventana y texto.

## Qué no hace

No verifica el caso de uso. No verifica WCAG: eso se le pide a `plugin-accessibility`. No corrige el código.

## Cómo hacerlo

1. La pantalla construida llega como captura o como URL. Si dan una URL, abre esa pantalla. Si no puedes abrirla, pide una captura y deja la entrega en `proposed`.
2. Compara contra el handoff. Si no hay un handoff `accepted`, compara con lo que sí existe (mock, kit) y deja la entrega en `proposed`, diciendo qué faltó.
3. Revisa medidas, tokens, estados, tamaños de ventana y texto. Un texto que difiere del handoff es un hallazgo, aunque «se pueda entender». El origen del texto es `plugin-ux-writing` o la persona; no reescribas el texto aquí.
4. Cada diferencia dice el elemento, lo que se especificó, lo que se construyó y la corrección (volver al handoff, o enmendar el handoff si lo construido fue una decisión nueva).
5. Pide a `plugin-accessibility` que audite la implementación.

## Plantilla

```markdown
# Revisión de implementación — <screen>

- Visto: captura | URL
- Handoff:
- Kit de interfaz:
- Mock:
- Estado de esta entrega: accepted | proposed (falta: )
- Fuente: el handoff y el kit de interfaz. No cubre el caso de uso ni WCAG.

| Elemento | Especificado | Construido | Corrección |
| --- | --- | --- | --- |

Accesibilidad: pide a `plugin-accessibility` la auditoría.
```

## Ejemplo

El handoff separa el monto y el formulario con `space.stack` (16 px). La captura muestra unos 8 px. Corrección: usar 16 px. Los estados de error no están en la captura: se anotan como no comprobados y se piden, sin tratarlos como correctos.

## Prerrequisitos

- **Handoff.** Un handoff `accepted`. Si solo hay un mock o un kit, la revisión se queda `proposed` y dice que faltaba el handoff. No detiene la entrega. Cámbialo con `/uiux-handoff`. Regenera esta revisión con `/uiux-implementation-review`.
- **Captura o URL.** La pantalla construida, en este turno. Esto detiene la entrega. No hay plantilla. No escribas archivos. No hay un valor por defecto para una pantalla que todavía no está construida. No hay comando anterior.

## Indicaciones

En un mensaje:

```text
/uiux-implementation-review del pago.
URL o captura: <pégala>.
Criterio: el handoff de pago accepted.
```

En orden, omitiendo los que ya se cumplieron:

```text
/uiux-handoff de la pantalla de pago.
La tarea es pagar con tarjeta.
El camino es carrito, pago, resultado. Si el cobro falla, vuelve al pago con los datos todavía rellenos.
Kit de interfaz, tema claro: acción #0066cc, fondo #ffffff, texto #1a1a1a, error #b00020, tipo Source Sans 3, espacio 16 px, radio 4 px, sombra 0 2 px 8 px.
```

## Terminado

- La pantalla construida se vio (captura o URL abierta). Si no se pudo abrir, la entrega queda en `proposed` y se pidió una captura. No se trató como correcta.
- Cada diferencia nombra el elemento, lo que se especificó, lo que se construyó y la corrección. Un texto que difiere es un hallazgo. El texto no se reescribió aquí. El código no se corrigió.
- Sin un handoff accepted, la entrega queda en `proposed` y dice qué faltó. Los estados que no estaban en la captura se marcan como no comprobados.
- El caso de uso no se verifica. El cierre pide a `plugin-accessibility` que audite la implementación.
