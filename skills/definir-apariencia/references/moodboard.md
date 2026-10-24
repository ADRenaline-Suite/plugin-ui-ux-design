# Moodboard

El moodboard no tiene una norma única en las fuentes de este plugin. Registra la dirección visual para repetirla en el UI kit y en los mocks.

## Qué fija

Referencias (enlaces que dio el usuario), color, tipo y tono, aplicados a pantallas de muestra.

## Qué deja abierto

Los tokens formales y los estados de cada componente. Eso es el UI kit.

## Cómo hacerlo

1. Las referencias son enlaces o piezas que el usuario aportó. No busques una galería ni inventes marcas ajenas como si fueran del producto.
2. Un SVG por pantalla de muestra. Muestras de color en rectángulos con su hex, una línea de tipo con la familia que el usuario nombró, y un bloque de pantalla en ese tono. `xmlns="http://www.w3.org/2000/svg"` y `viewBox`. Sin `foreignObject`.
3. El tono se dice con ejemplos de sí y no que el usuario haya dado. Si no los dio, describe el tono en una frase y no redactes el microcopy: eso es `adrenaline-ux-writing`.
4. Si el producto ya tiene UI kit, el moodboard no lo reemplaza. Muestra cómo se aplica.

## Plantilla

```markdown
# Moodboard — <dirección>

- Plataforma:
- Referencias:
- Color:
- Tipo:
- Tono:
- SVG: `<NNN>-moodboard-<tema>-<pantalla>.svg`
- Deja abierto: tokens y estados de componente
```

## Ejemplo

Dirección «tienda clara». Referencia: la guía que pasó el usuario. Muestra de color `#0066cc` sobre fondo `#ffffff`, una línea en la familia que nombró, y un bloque de pago con ese acento. El SVG es la muestra, no el handoff.
