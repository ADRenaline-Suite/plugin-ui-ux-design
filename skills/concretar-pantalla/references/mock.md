# Mock

Fuente: el UI kit del producto. Los tokens, si se escriben en este turno, siguen el Design Tokens Format Module 2025.10; el archivo de tokens lo produce `definir-apariencia`, no este manual. Breakpoints: los del producto, o Material Design 3.

## Qué fija

El aspecto visual de una pantalla, con los tokens del UI kit y por tema.

## Qué deja abierto

El recorrido hacia otras pantallas y la especificación de construcción (medidas anotadas, comportamiento, accesibilidad). Eso es el prototype y el handoff.

## Cómo hacerlo

1. El recorrido tiene que estar decidido. Si no lo está, detente y pide `ordenar-pantallas`.
2. Usa los tokens del UI kit `accepted`. Color, tipo, espacio, radio y elevación salen de ahí. Si no hay kit, deja el mock en `proposed` y pide `definir-apariencia` o la ruta del kit. No inventes una paleta definitiva dentro del mock.
3. Un marco por tema en el estado ideal (claro, oscuro, variante de marca), solo los temas que el producto tiene. No añadas el modo oscuro si el producto no lo tiene.
4. Textos reales, los del usuario o los de `adrenaline-ux-writing`. Si faltan los textos finales, usa los rótulos ya acordados y dilo en el Markdown; no redactes microcopy nuevo.
5. Dibuja los estados que cambian el aspecto. El error conserva lo escrito y muestra qué falló.
6. El SVG usa los colores del kit en `fill` y `stroke`. Sigue sin redlines: las cotas son del handoff.

## Plantilla del Markdown

```markdown
# Mock — <pantalla>

- Tarea o caso de uso:
- Recorrido decidido: <archivo del user flow, o "descrito en este turno">
- UI kit: <archivo> | falta (esta entrega queda proposed)
- Temas:
- Plataforma y breakpoints:
- Estados dibujados:
- Origen de los textos: usuario | adrenaline-ux-writing | rótulos acordados, faltan los finales
- SVG: `<NNN>-mock-<tema>-<pantalla>.svg`
```

## Ejemplo

Mock del pago en tema claro, con el color de acción y el tipo del kit de la tienda. El estado de error usa el color de error del kit, el aviso «No se pudo cobrar» si `adrenaline-ux-writing` ya lo dio, y los campos de tarjeta siguen llenos. El camino hacia el resultado está en el user flow aceptado; este mock no lo enlaza.
