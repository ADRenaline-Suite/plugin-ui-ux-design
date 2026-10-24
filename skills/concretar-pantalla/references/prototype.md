# Prototype

Fuente: el orden de fidelidad de este plugin. El prototype es el recorrido, no la especificación de construcción.

## Qué fija

El camino de una tarea entre pantallas. Se abre en el navegador.

## Qué deja abierto

Medidas, tokens anotados y requisitos de accesibilidad. Eso queda en el handoff.

## Cómo hacerlo

1. Parte de las pantallas ya dibujadas: el mock si está `accepted`; si no, el wireframe. Vuelve a dibujar cada pantalla en su SVG de prototype y añade los enlaces. No reescribas el archivo del mock.
2. Un SVG por pantalla. Enlaza con `<a href="<archivo.svg>">` alrededor de la zona que se acciona. La ruta es relativa, al SVG hermano de la misma entrega. Sin JavaScript.
3. El primer SVG es el inicio del recorrido. El Markdown dice cuál abrir.
4. Cada destino existe. Si una acción no tiene pantalla, no inventes el destino: pregunta o deja esa zona sin enlace y marca la entrega `proposed`.
5. Incluye el estado de error cuando la tarea puede fallar, como SVG propio si es otra vista, o como marco enlazado dentro de la misma pantalla si el error no cambia de archivo. El enlace de «reintentar» vuelve a la pantalla donde están los datos.
6. El recorrido no es un diagrama UML. Si hace falta una máquina de estados, pídela a `adrenaline-uml-diagrams`.

## Plantilla del Markdown

```markdown
# Prototype — <recorrido>

- Tarea o caso de uso:
- Abrir primero: `<NNN>-prototype-<tema>-<pantalla>.svg`
- Origen visual: mock <N> | wireframe <N>

## Enlaces

| Pantalla | Acción | Destino |
| --- | --- | --- |
```

## Ejemplo

`001-prototype-pagar-pago.svg` enlaza «Pagar» con `001-prototype-pagar-resultado.svg`. «Reintentar» en el resultado de error vuelve a `001-prototype-pagar-pago.svg`. Se abre el SVG de pago en el navegador.
