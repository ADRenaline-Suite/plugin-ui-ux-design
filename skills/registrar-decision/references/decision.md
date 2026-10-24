# Decisión de diseño

Fuente: Michael Nygard, Documenting Architecture Decisions (2011). El título puede decir «decisión de diseño»: el formato es el de Nygard.

## Qué fija

El contexto, las opciones consideradas, la decisión y las consecuencias. El estado dice si manda.

## Cómo hacerlo

1. Contexto: qué fuerza la decisión (un hallazgo, una restricción de plataforma, un test). Cita el `<NNN>` de ese artefacto si existe.
2. Opciones: al menos dos, con su coste. Incluye la que se descartó.
3. Decisión: la que el usuario tomó, en una frase. Si todavía no elige, el estado es `proposed` y la decisión dice «pendiente».
4. Consecuencias: qué entrega hay que cambiar (handoff, kit, flujo) y qué queda fuera.
5. No copies el handoff dentro de la decisión. Enlaza por nombre de archivo.

## Plantilla

```markdown
# <NNN> — <título>

- Estado: proposed | accepted | deprecated | superseded
- Sustituye a: <N o ninguno>
- Fuente: Michael Nygard (2011)

## Contexto

## Opciones

1. <opción> — <consecuencia de elegirla>

## Decisión

## Consecuencias
```

## Ejemplo

Estado: `accepted`. Contexto: el hallazgo de heurísticas del pago en error de red (gravedad 3). Opciones: una pantalla de error vacía, o el aviso sobre el formulario. Decisión: el aviso sobre el formulario, con la tarjeta intacta. Consecuencias: enmendar el handoff del pago; el user flow no añade una pantalla.
