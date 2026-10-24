---
name: definir-apariencia
description: Fija la dirección visual de la interfaz en un moodboard y el UI kit con sus tokens. Úsala cuando pidan cómo se ve la interfaz, los componentes o los design tokens.
---

# Definir la apariencia

Produce el moodboard o el UI kit. El kit manda sobre el mock y el handoff. Si el producto ya tiene kit, se parte de ese y no se inventa otro.

Fuente de los tokens: Design Tokens Format Module 2025.10 y Color Module 2025.10 (W3C Design Tokens Community Group, Final Community Group Report, 28 de octubre de 2025). Son estables y no son un estándar W3C. No cites un borrador posterior. Los componentes siguen el UI kit del producto. Atomic Design (Brad Frost) es solo un modelo posible de agrupación cuando el producto aún no tiene el suyo. El moodboard no tiene una norma única en las fuentes: registra referencias, color, tipo y tono aplicados a pantallas.

## Antes de escribir

1. Si este turno viene de un command, la pieza ya está fijada.
2. Lee solo `references/<pieza>.md` de la pieza pedida. No leas referencias de otro skill.
3. Plataforma: web, o la guía nativa (Apple Human Interface Guidelines, Material Design 3, Fluent 2). Si la guía contradice el kit, dilo y sigue el kit.
4. Temas: solo los que el producto tiene (claro, oscuro, variantes de marca). No añadas un tema.
5. No dibujes el flujo ni audites WCAG. No escribas HTML ni código de interfaz.

| Petición | Pieza | Referencia |
| --- | --- | --- |
| Dirección visual | moodboard | `references/moodboard.md` |
| Componentes, tokens y reglas | UI kit | `references/ui-kit.md` |

## Entrega

La carpeta es `ui-ux-design/` en la raíz del proyecto. Si `.cursor/adrenaline.json` tiene `outputDirs["adrenaline-ui-ux-design"]` con una ruta relativa, sin `..` y no absoluta, usa esa ruta. Si falta el archivo, la clave, o la ruta no es válida, usa `ui-ux-design/` y, en el último caso, dilo. Crea la carpeta si no existe. No escribas fuera de ella. No elijas la carpeta de otro plugin.

`<NNN>` es el siguiente entero libre, con tres dígitos, y no se reutiliza. El moodboard es `<NNN>-moodboard-<tema>.md` más un SVG por pantalla de muestra, `<NNN>-moodboard-<tema>-<pantalla>.svg`. El UI kit es `<NNN>-ui-kit-<tema>.md` y `<NNN>-ui-kit-<tema>.tokens.json`. Misma entrega, mismo `<NNN>`.

Mantén `<carpeta>/STATUS.md` con las columnas `N`, `archivo`, `estado`, `sustituye` y `notas`. Los estados son `proposed`, `accepted`, `deprecated` y `superseded`. Al elegir qué seguir, el orden es `accepted`, luego `proposed`, luego `deprecated`, luego `superseded`.

Si el tema ya tiene archivo:

- El usuario pide cambiar esa entrega: edita los mismos archivos, conserva el `<NNN>` y deja `accepted`.
- El usuario pide un reemplazo o una decisión nueva sobre el mismo tema: toma el siguiente `<NNN>`, marca la fila anterior `superseded` (en `sustituye`, el `N` nuevo) y deja la nueva en `accepted`.
- Si no: siguiente `<NNN>` y fila `accepted`.

Una entrega nueva queda `accepted`. Queda `proposed` si el usuario pide un borrador o si el kit no cubre los temas que el producto ya tiene. Al cerrar, di la carpeta, los archivos, el `N` y el estado.

## Ejemplo

Entrada: «UI kit mínimo de la tienda, tema claro. Acción azul #0066cc, fondo blanco, texto casi negro, espacio 16 px.»

Salida: `012-ui-kit-tienda.md` y `012-ui-kit-tienda.tokens.json`, con color, tipo, espacio, radio y elevación en DTCG 2025.10, y el botón con sus estados.
