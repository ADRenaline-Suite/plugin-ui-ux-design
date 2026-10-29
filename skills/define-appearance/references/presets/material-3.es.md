<p align="right">Idioma:&emsp;<a href="material-3.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../../README.es.md) / [Definir la apariencia](../../SKILL.es.md) / [Presets](../presets.es.md)

# Preset material-3

Baseline estático de Material Design 3, tema light. Los valores de abajo son ese baseline. No les cambies el color.

Fuente: Material Design 3. Roles de color y el baseline estático, https://m3.material.io/styles/color/roles y https://m3.material.io/styles/color/static/baseline. Los roles light del baseline que se usan aquí son primary `#6750A4`, onPrimary `#FFFFFF`, surface `#FEF7FF`, onSurface `#1D1B20`, error `#B3261E`, outline `#79747E`. Escala de tipo: body large 16/24, title large 22/28 medium, label large 14/20 medium, Roboto, como se publican para Material 3. Escala de esquinas: extra small 4 dp, medium 12 dp, large increased 20 dp, https://m3.material.io/styles/shape/corner-radius-scale. Niveles de elevación, no una sombra proyectada: un botón relleno descansa en el nivel 0 y una tarjeta elevada en el nivel 1 (1 dp), https://m3.material.io/styles/elevation/tokens. Capas de estado en un botón relleno: hover 8 %, focus 12 %, pressed 12 % de onPrimary. El contenedor disabled es onSurface al 12 % y la etiqueta es onSurface al 38 %.

El token de sombra es una capa para el nivel 1 cuando hay que dibujar una sombra (desplazamiento 0 1 px, desenfoque 3 px, 12 % de negro). La regla propia de Material 3 es el nivel, no esta sombra. El archivo lo dice. No añadas una segunda sombra al entregar.

- Plataforma: Android, o web que sigue Material Design 3
- Temas: light. El baseline también tiene un esquema dark. No está en este preset. Añádelo solo cuando el producto tiene dark, como otra entrega.
- Guía nativa: Material Design 3
- Agrupación: roles de color de Material. Botón, campo de texto y texto. Los demás componentes se añaden cuando una pantalla los necesita.

## Cuándo recomendarlo

El producto es Android, o ya sigue Material Design 3. Nombrar la plataforma no es nombrar este preset.

## Componentes

### Botón

- Para qué se usa: la acción primaria rellena.
- Estados: default, hover, focus, pressed, disabled. No aplican: selected, error, loading.
- Tokens: relleno default `theme.light.color.primary`, etiqueta `theme.light.color.onPrimary`, elevación `elevation.level0`. Hover, focus y pressed conservan ese relleno y añaden la capa de estado descrita en la fuente (8 %, 12 %, 12 %). Disabled usa `theme.light.color.onSurface` al 12 % para el relleno y al 38 % para la etiqueta. Radio `radius.button` (20 dp, el paso large-increased). Un estadio («full») es la mitad del lado más corto cuando se conoce la altura; no inventes otro radio. La separación interior sigue `space.16` en horizontal y `space.8` en vertical. Estilo de la etiqueta `type.label`.

### Campo de texto

- Para qué se usa: un campo outlined.
- Estados: default, hover, focus, disabled, error. No aplican: pressed, selected, loading.
- Tokens: texto `theme.light.color.onSurface`, contenedor `theme.light.color.surface`. Contorno default `theme.light.color.outline`. Contorno hover `theme.light.color.onSurface`. Contorno focus `theme.light.color.primary`. Contorno de error `theme.light.color.error`; el valor escrito se conserva. El contorno disabled es `theme.light.color.onSurface` al 12 %. Radio `radius.extraSmall`. Estilo de texto `type.body`.

### Texto

- Para qué se usa: el cuerpo y el título de la pantalla.
- Estados: default. No aplican: hover, focus, pressed, disabled, selected, error, loading.
- Tokens: cuerpo `type.body` en `theme.light.color.onSurface`. Título `type.title` en `theme.light.color.onSurface`. Texto secundario `type.body` en `theme.light.color.onSurfaceVariant`.

## Tokens

`material-3.tokens.json`. El espacio es el incremento de 4 dp (4, 8, 16, 24).
