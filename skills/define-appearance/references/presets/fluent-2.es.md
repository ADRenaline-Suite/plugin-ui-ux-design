<p align="right">Idioma:&emsp;<a href="fluent-2.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../../README.es.md) / [Definir la apariencia](../../SKILL.es.md) / [Presets](../presets.es.md)

# Preset fluent-2

Fluent 2, tema light de la web.

Fuente: tokens de diseño y tipografía de Fluent 2, https://fluent2.microsoft.design/design-tokens y https://fluent2.microsoft.design/typography. Los números son el tema light de la web de Fluent UI React v9. Color: `colorBrandBackground` `#0F6CBD`, `colorBrandBackgroundHover` `#115EA3`, `colorBrandBackgroundPressed` `#0C3B5E`, `colorNeutralForeground1` `#242424`, `colorNeutralForeground2` `#424242`, `colorNeutralBackground1` `#FFFFFF`, `colorNeutralBackground3` `#F5F5F5`, `colorNeutralStroke1` `#D1D1D1`, `colorNeutralForegroundOnBrand` `#FFFFFF`, `colorStatusDangerBackground3` `#C50F1F`, `colorPaletteRedForeground1` `#BC2F32`. Tipo: Segoe UI, Body 1 14/20 regular, Subtitle 1 20/26 semibold. Radio: medium 4 px, extra large 8 px. Espacio: S 8 px, M 12 px, L 16 px, XXL 24 px. `shadow4` son dos capas; el token conserva la capa de caída, 0 2 px 4 px al 14 % de negro. No añadas la segunda capa como una elevación nueva.

Los colores de disabled no están en este subconjunto. El estado disabled del botón se nombra y la entrega dice que el token no está. No inventes el gris.

- Plataforma: Windows, o web que sigue Fluent 2
- Temas: light. Fluent también tiene un tema dark de la web. No está en este preset.
- Guía nativa: Fluent 2
- Agrupación: tokens alias de Fluent. Botón, campo de texto y texto. Los demás componentes se añaden cuando una pantalla los necesita.

## Cuándo recomendarlo

El producto es Windows, o ya sigue Fluent 2. Nombrar la plataforma no es nombrar este preset.

## Componentes

### Botón

- Para qué se usa: la acción primaria.
- Estados: default, hover, focus, pressed. No aplican: selected, error, loading. Disabled aplica y su token de color no está en este subconjunto: dilo en la entrega, no inventes el gris.
- Tokens: relleno default `theme.light.color.brandBackground`, etiqueta `theme.light.color.neutralForegroundOnBrand`. Relleno hover `theme.light.color.brandBackgroundHover`. Relleno pressed `theme.light.color.brandBackgroundPressed`. Focus es un contorno de 2 px en `theme.light.color.brandBackgroundHover`. Radio `radius.medium`. Separación interior horizontal `space.m`, separación interior vertical `space.s`. Peso de la etiqueta semibold, tamaño de `type.body`. Altura mínima 32 px.

### Campo de texto

- Para qué se usa: un valor que la persona escribe.
- Estados: default, hover, focus, error. No aplican: pressed, selected, loading. Disabled aplica y su token de color no está en este subconjunto.
- Tokens: relleno `theme.light.color.neutralBackground1`, texto `theme.light.color.neutralForeground1`, borde `theme.light.color.neutralStroke1`. Borde hover `theme.light.color.neutralForeground2`. Contorno focus `theme.light.color.brandBackgroundHover`. Borde de error `theme.light.color.danger`; el aviso usa `theme.light.color.dangerForeground`; el valor escrito se conserva. Radio `radius.medium`. Estilo de texto `type.body`.

### Texto

- Para qué se usa: el cuerpo y un subtítulo.
- Estados: default. No aplican: hover, focus, pressed, disabled, selected, error, loading.
- Tokens: cuerpo `type.body` en `theme.light.color.neutralForeground1`. Subtítulo `type.subtitle` en `theme.light.color.neutralForeground1`. Texto secundario en `theme.light.color.neutralForeground2`.

## Tokens

`fluent-2.tokens.json`.
