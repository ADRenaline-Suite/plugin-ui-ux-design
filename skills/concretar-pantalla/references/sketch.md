# Sketch

Fuente: el orden de fidelidad de este plugin. El sketch fija la idea. Aún no es la especificación.

## Qué fija

La idea de la pantalla y sus bloques. Un bloque es una zona con un nombre (monto, formulario, acción).

## Qué deja abierto

Medida, color, texto final y estilo.

## Cómo hacerlo

1. Un SVG por pantalla, en escala de grises (`#f4f4f4`, `#ffffff`, trazo `#222`). Rectángulos y rótulos. Sin iconos de marca ni tipografía final.
2. Dibuja el estado ideal. Añade un marco por cada estado que cambie los bloques. El Markdown lista ideal, vacío, carga, parcial, error y éxito, y dice cuál no aplica.
3. Los rótulos son las palabras que ya usó el usuario. Si un rótulo aún no existe, usa el nombre de la subtarea, no un texto de interfaz inventado.
4. No anotes píxeles. No enlaces pantallas: eso es el prototype.

## Plantilla del Markdown

```markdown
# Sketch — <pantalla>

- Tarea o caso de uso:
- Plataforma:
- Estados: ideal, vacío, carga, parcial, error, éxito. No aplican: <cuáles y por qué>
- SVG: `<NNN>-sketch-<tema>-<pantalla>.svg`
- Deja abierto: medida, color, texto final
```

## Ejemplo

Pantalla de pago. Bloques del estado ideal: monto, datos de tarjeta, acción «Pagar». Estado de error: los mismos bloques más un aviso, y los datos de la tarjeta siguen escritos. Vacío no aplica: el monto llega del pedido.
