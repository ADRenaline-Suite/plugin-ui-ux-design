---
name: concretar-pantalla
description: Produce el sketch, el wireframe, el mock, el prototype o el handoff de una pantalla, de menor a mayor concreción. Úsala cuando pidan dibujar o especificar una pantalla para construirla.
---

# Concretar una pantalla

Produce una pantalla. El handoff es la pieza con la que se construye sin interpretar. Este skill es el que cierra esa entrega.

Fuente: ISO 9241-210:2019 (producir soluciones). Estados: Scott Hurff, The UI Stack, más éxito y, cuando aplican, sin permiso y sin conexión. Breakpoints de respaldo: Material Design 3 (compact &lt;600 dp, medium 600–839, expanded 840–1199, large 1200–1599, extra-large ≥1600), por ancho de ventana. Plataforma nativa: Apple Human Interface Guidelines, Material Design 3 o Fluent 2. Expansión del texto: W3C Internationalization, Text size in translation. Los textos los redacta `adrenaline-ux-writing`. Las anotaciones de accesibilidad las especifica `adrenaline-accessibility`.

## Antes de dibujar

1. Si este turno viene de un command, la pieza ya está fijada. Si no, elige una de la tabla.
2. Lee solo `references/<pieza>.md` de la pieza pedida. No leas referencias de otro skill.
3. Cada pantalla nombra la tarea del usuario o el caso de uso que cubre. Si la tarea no está dicha (ni en un análisis de tareas `accepted`, ni en este turno), pídela y detente. No pases de sketch sin esa tarea.
4. El orden es sketch, wireframe, mock, prototype, handoff. Si piden una pieza y la anterior no existe, se puede hacer si la tarea está dicha y, para mock o superior, el recorrido ya está decidido. No rellenes las piezas anteriores por tu cuenta.
5. No pases a mock si el recorrido no está decidido: un user flow `accepted`, o el usuario describe el camino en este turno. Si falta, detente y pide el skill `ordenar-pantallas`.
6. Plataforma y breakpoints: los del producto si existen. Si no hay breakpoints, usa los de Material Design 3. Si el producto es nativo, sigue la guía de esa plataforma. Si esa guía contradice el UI kit, dilo y sigue el UI kit.
7. Contenido real, el que ya dio el usuario o `adrenaline-ux-writing`. Sin lorem ipsum. En wireframe, mock y handoff prueba un texto largo y la expansión al traducir (una cadena de hasta 10 caracteres puede crecer al 200–300 %). Si el producto usa escritura de derecha a izquierda, incluye un marco RTL. No traduzcas: la traducción queda fuera.
8. Temas: si el producto tiene modo claro, oscuro o variantes de marca, el mock y el handoff los cubren.
9. Estados de toda pantalla: ideal, vacío, carga, parcial, error y éxito. Cuando aplican, también sin permiso y sin conexión. En el error se conserva lo que la persona escribió. Si un estado no aplica, el Markdown dice por qué.
10. Un diagrama de actividad o una máquina de estados de la pantalla se pide a `adrenaline-uml-diagrams`. No lo dibujes aquí.
11. No escribas HTML ni código de interfaz.

| Petición | Pieza | Referencia |
| --- | --- | --- |
| Idea y bloques | sketch | `references/sketch.md` |
| Jerarquía y layout | wireframe | `references/wireframe.md` |
| Aspecto visual | mock | `references/mock.md` |
| Recorrido entre pantallas | prototype | `references/prototype.md` |
| Especificación para construir | handoff | `references/handoff.md` |

| Pieza | Qué fija | Qué deja abierto |
| --- | --- | --- |
| Sketch | Idea y bloques | Medida, color, texto final |
| Wireframe | Jerarquía y layout por breakpoint | Estilo visual |
| Mock | Aspecto visual de una pantalla, por tema | Interacción entre pantallas |
| Prototype | Recorrido que se abre en el navegador | Especificación de construcción |
| Handoff | Medidas, estados, textos, comportamiento, anotaciones de accesibilidad | — |

## SVG

Uno por pantalla. SVG 1.1, con `xmlns="http://www.w3.org/2000/svg"`, `viewBox` y un rectángulo de fondo. Texto en `<text>`, `font-family="system-ui, Segoe UI, sans-serif"`. Sin imágenes externas, sin scripts y sin `foreignObject`.

Dentro de ese archivo, un marco por estado que cambie lo que se ve. Un breakpoint se vuelve a dibujar solo cuando cambia el layout (columnas, qué se muestra, qué se apila). Si solo crece, el Markdown lo dice y no se repite el marco. Los temas van como marcos del estado ideal cuando cambian color o tipo. Cada marco lleva un rótulo (`Ideal · Compact`, `Error · Oscuro`).

El Markdown es `<NNN>-<tipo>-<tema>.md`. Cada SVG es `<NNN>-<tipo>-<tema>-<pantalla>.svg`. Misma entrega, mismo `<NNN>`.

## Entrega

La carpeta es `ui-ux-design/` en la raíz del proyecto. Si `.cursor/adrenaline.json` tiene `outputDirs["adrenaline-ui-ux-design"]` con una ruta relativa, sin `..` y no absoluta, usa esa ruta. Si falta el archivo, la clave, o la ruta no es válida, usa `ui-ux-design/` y, en el último caso, dilo. Crea la carpeta si no existe. No escribas fuera de ella. No elijas la carpeta de otro plugin.

`<NNN>` es el siguiente entero libre de esa carpeta, con tres dígitos, y no se reutiliza. `<tipo>` es `sketch`, `wireframe`, `mock`, `prototype` o `handoff`. `<tema>` y `<pantalla>` van en kebab-case.

Mantén `<carpeta>/STATUS.md` con las columnas `N`, `archivo`, `estado`, `sustituye` y `notas`. Los estados son `proposed`, `accepted`, `deprecated` y `superseded`. Al elegir qué seguir, el orden es `accepted`, luego `proposed`, luego `deprecated`, luego `superseded`.

Si el tema ya tiene archivo:

- El usuario pide cambiar esa entrega: edita los mismos archivos, conserva el `<NNN>` y deja `accepted`.
- El usuario pide un reemplazo o una decisión nueva sobre el mismo tema: toma el siguiente `<NNN>`, marca la fila anterior `superseded` (en `sustituye`, el `N` nuevo) y deja la nueva en `accepted`.
- Si no: siguiente `<NNN>` y fila `accepted`.

El handoff queda `proposed` cuando faltan los textos o las anotaciones de accesibilidad. El mock queda `proposed` cuando no hay tokens del UI kit. El resto, `accepted`, salvo que el usuario pida un borrador. Al cerrar, di la carpeta, los archivos, el `N` y el estado.

## Ejemplo

Entrada: «Sketch de la pantalla de pago. La tarea es pagar con tarjeta. Plataforma web. Aún no hay UI kit.»

Salida `accepted`:

- `ui-ux-design/001-sketch-pago.md`
- `ui-ux-design/001-sketch-pago-pago.svg`
- Fila `001` en `STATUS.md` para cada archivo.

El Markdown nombra la tarea «pagar con tarjeta», lista los seis estados y dice que vacío no aplica porque el monto ya viene del pedido. El SVG tiene dos bloques en el estado ideal (monto, tarjeta) y el estado de error conserva esos datos con un bloque de mensaje. No hay medidas ni color de marca.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 360 640">
  <rect width="360" height="640" fill="#f4f4f4"/>
  <text x="16" y="32" font-family="system-ui, Segoe UI, sans-serif" font-size="14">Ideal · Compact</text>
  <rect x="16" y="48" width="328" height="64" fill="#ffffff" stroke="#222"/>
  <text x="32" y="84" font-family="system-ui, Segoe UI, sans-serif" font-size="16">Monto del pedido</text>
  <rect x="16" y="128" width="328" height="120" fill="#ffffff" stroke="#222"/>
  <text x="32" y="164" font-family="system-ui, Segoe UI, sans-serif" font-size="16">Tarjeta</text>
  <rect x="16" y="264" width="328" height="48" fill="#ffffff" stroke="#222"/>
  <text x="32" y="294" font-family="system-ui, Segoe UI, sans-serif" font-size="16">Pagar</text>
</svg>
```
