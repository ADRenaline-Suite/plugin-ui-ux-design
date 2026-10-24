# Wireframe

Fuente: el orden de fidelidad de este plugin. Breakpoints: los del producto, o Material Design 3 si el producto no los tiene.

## Qué fija

La jerarquía y el layout de una pantalla, por breakpoint. Qué va primero, qué se apila y qué se parte en columnas.

## Qué deja abierto

El estilo visual: color de marca, tipografía final, elevación.

## Cómo hacerlo

1. Escala de grises, igual que el sketch. Esta vez los bloques tienen jerarquía: un título, el contenido, la acción primaria. El orden de lectura es de arriba a abajo y, en idiomas de izquierda a derecha, de izquierda a derecha.
2. El Markdown describe el layout de cada breakpoint. El SVG redibuja un breakpoint solo cuando el layout cambia.
3. Incluye un texto largo en al menos un bloque, para ver el quiebre de línea. Si una cadena corta puede traducirse, reserva espacio para un 200–300 % (W3C Internationalization, Text size in translation). Si el producto necesita RTL, un marco con `direction="rtl"` en el grupo SVG.
4. Lista los estados. Dibuja los que cambian el layout, en especial el error, que conserva lo escrito.
5. Sigue sin color de marca y sin medidas de construcción. Las medidas son del handoff.

## Plantilla del Markdown

```markdown
# Wireframe — <pantalla>

- Tarea o caso de uso:
- Plataforma:
- Breakpoints: <los del producto, o Material Design 3>
- Estados y cuáles cambian el layout:
- Texto largo de prueba:
- Expansión al traducir:
- RTL: sí, en el marco <nombre> | no aplica
- SVG: `<NNN>-wireframe-<tema>-<pantalla>.svg`

## Layout por breakpoint

| Breakpoint | Layout |
| --- | --- |
```

## Ejemplo

Pago, web, Material Design 3. Compact: monto, formulario y «Pagar» en una columna. Expanded: resumen a la izquierda y formulario a la derecha. El error añade el aviso encima del formulario y no borra el número de tarjeta. Large y extra-large solo ensanchan el layout expanded; el Markdown lo dice y el SVG no los repite.
