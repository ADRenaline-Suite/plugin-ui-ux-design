# UI kit

Fuente de los tokens: Design Tokens Format Module 2025.10 (https://www.w3.org/community/reports/design-tokens/CG-FINAL-format-20251028/) y Design Tokens Color Module 2025.10 (https://www.designtokens.org/TR/2025.10/color/). No son un estándar W3C. El archivo termina en `.tokens.json`.

## Qué fija

Componentes, tokens y reglas para repetir el diseño. Tokens de color, tipografía, espacio, radio y elevación, por tema.

## Qué deja abierto

La pantalla concreta. El mock y el handoff consumen este kit.

## Tokens

Cada token tiene `$value` y, salvo que lo herede del grupo, `$type`. Un token sin tipo es inválido: no lo infieras del valor.

| Uso | `$type` | `$value` |
| --- | --- | --- |
| Color | `color` | Objeto con `colorSpace`, `components` (0–1 en `srgb`), `hex` opcional de 6 dígitos y `alpha` opcional entre 0 y 1 (si falta, es 1) |
| Espacio y radio | `dimension` | `{ "value": <número>, "unit": "px" }` o `"rem"` |
| Familia | `fontFamily` | Nombre o lista de nombres |
| Peso | `fontWeight` | Número 1–1000, o un alias del módulo (`regular`, `bold`, …) |
| Interlineado | `number` | Multiplicador del tamaño |
| Estilo de texto | `typography` | `fontFamily`, `fontSize`, `fontWeight`, `letterSpacing`, `lineHeight` |
| Elevación | `shadow` | `color`, `offsetX`, `offsetY`, `blur`, `spread`; `inset` si aplica |

Un alias es `"{grupo.token}"`. Los temas del producto son grupos (`theme.light`, `theme.dark`), solo los que existan. `$description` dice para qué sirve el token, en el idioma del producto.

Si el producto ya tiene kit, copia sus valores. No los «mejores». Un cambio de valor es otra entrega o una enmienda, según pida el usuario.

## Componentes

Agrupa como el kit del producto. Si no hay kit, puedes agrupar al modo de Atomic Design (Brad Frost) y dilo en el Markdown. Cada componente lista los estados que le aplican, de esta lista: por defecto, hover, foco, presionado, deshabilitado, seleccionado, error y carga. El que no aplica se dice en una línea.

Las reglas del Markdown dicen cuándo se usa el componente y qué token usa. No escribas el componente en HTML.

## Plantilla del Markdown

```markdown
# UI kit — <producto>

- Plataforma:
- Temas:
- Guía nativa: <ninguna | HIG | Material Design 3 | Fluent 2>. Si contradice al kit: manda el kit.
- Agrupación: la del producto | Atomic Design, porque aún no hay kit
- Tokens: `<NNN>-ui-kit-<tema>.tokens.json`
- Fuente: Design Tokens Format Module 2025.10

## Componentes

### <componente>
- Se usa para:
- Estados: por defecto, hover, foco, presionado, deshabilitado. No aplican: seleccionado, error, carga.
- Tokens:
```

## Ejemplo de tokens

```json
{
  "color": {
    "action": {
      "$type": "color",
      "$description": "Acción primaria sobre fondo claro",
      "$value": { "colorSpace": "srgb", "components": [0, 0.4, 0.8], "hex": "#0066cc" }
    }
  },
  "space": {
    "stack": {
      "$type": "dimension",
      "$value": { "value": 16, "unit": "px" }
    }
  },
  "radius": {
    "control": {
      "$type": "dimension",
      "$value": { "value": 4, "unit": "px" }
    }
  },
  "font": {
    "family": {
      "$type": "fontFamily",
      "$value": "Source Sans 3"
    },
    "weight": {
      "$type": "fontWeight",
      "$value": "regular"
    }
  },
  "type": {
    "body": {
      "$type": "typography",
      "$value": {
        "fontFamily": "{font.family}",
        "fontSize": { "value": 16, "unit": "px" },
        "fontWeight": "{font.weight}",
        "letterSpacing": { "value": 0, "unit": "px" },
        "lineHeight": 1.5
      }
    }
  },
  "elevation": {
    "panel": {
      "$type": "shadow",
      "$value": {
        "color": { "colorSpace": "srgb", "components": [0, 0, 0], "alpha": 0.12, "hex": "#000000" },
        "offsetX": { "value": 0, "unit": "px" },
        "offsetY": { "value": 2, "unit": "px" },
        "blur": { "value": 8, "unit": "px" },
        "spread": { "value": 0, "unit": "px" }
      }
    }
  }
}
```

El color de la sombra sigue el Color Module 2025.10: `alpha` entre 0 y 1, y `hex` de 6 dígitos sin el canal alfa. No uses un borrador posterior del formato.
