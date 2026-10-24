# Revisión de la implementación

No tiene norma propia. El criterio es el handoff `accepted` y el UI kit `accepted`. También se mira el mock cuando el handoff remite a él.

## Qué fija

Diferencias entre la pantalla construida y lo especificado: medidas, tokens, estados, breakpoints y textos.

## Qué no hace

No verifica el caso de uso. No verifica WCAG: eso se pide a `adrenaline-accessibility`. No corrige el código.

## Cómo hacerlo

1. La pantalla construida llega como captura o como URL. Si dan una URL, abre esa pantalla. Si no puedes abrirla, pide una captura y deja la entrega `proposed`.
2. Compara contra el handoff. Si no hay handoff `accepted`, compara con lo que sí haya (mock, kit) y deja la entrega `proposed`, diciendo qué faltó.
3. Revisa medidas, tokens, estados, breakpoints y textos. Un texto distinto del handoff es un hallazgo, aunque «se entienda». El origen de los textos es `adrenaline-ux-writing` o el usuario; no reescribas el texto aquí.
4. Cada diferencia dice el elemento, lo especificado, lo construido y la corrección (volver al handoff, o enmendar el handoff si lo construido fue una decisión nueva).
5. Pide la auditoría de la implementación a `adrenaline-accessibility`.

## Plantilla

```markdown
# Revisión de la implementación — <pantalla>

- Visto: captura | URL
- Handoff:
- UI kit:
- Mock:
- Estado de esta entrega: accepted | proposed (falta: )
- Fuente: el handoff y el UI kit. No cubre el caso de uso ni WCAG.

| Elemento | Especificado | Construido | Corrección |
| --- | --- | --- | --- |

Accesibilidad: pedir auditoría a `adrenaline-accessibility`.
```

## Ejemplo

El handoff separa el monto y el formulario con `space.stack` (16 px). En la captura se ven unos 8 px. Corrección: usar 16 px. Los estados de error no están en la captura: se anotan como no comprobados y se piden, no se dan por buenos.
