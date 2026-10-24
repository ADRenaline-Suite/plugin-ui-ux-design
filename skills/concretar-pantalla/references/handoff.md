# Handoff

Fuente: la práctica de este plugin. No hay una norma única del handoff. Alcanza para construir la pantalla sin interpretar: medidas, estados, textos, comportamiento por breakpoint y anotaciones de accesibilidad. La revisión de la implementación usa esta entrega como criterio, junto con el UI kit.

## Qué fija

Todo lo que quien construye la pantalla tendría que adivinar.

## Qué deja abierto

Nada de la pantalla. El código queda fuera de este plugin.

## Cómo hacerlo

1. Parte del mock `accepted`. El SVG del handoff es ese mock con redlines: líneas de cota (trazo discontinuo) y el valor medido. La unidad es la del UI kit (`px` o `rem` en los tokens). No inventes una medida que el kit no tiene: si falta, anótala como hueco y deja la entrega `proposed`.
2. El Markdown describe el comportamiento por breakpoint: qué se muestra, qué se apila, qué cambia de sitio. Repite un marco en el SVG solo cuando el layout cambia.
3. Textos: pídelos a `adrenaline-ux-writing` (microcopy, errores, vacío, carga, éxito, confirmaciones). Si el usuario ya los pegó, úsalos y cita el origen. No los redactes aquí. Si faltan, la entrega queda `proposed` y lista los huecos.
4. Anotaciones de accesibilidad: pídelas a `adrenaline-accessibility` (orden de foco, encabezados, regiones, nombres accesibles, textos alternativos). Inclúyelas tal cual, cada una con el criterio WCAG que ese plugin haya nombrado. No hagas la auditoría. Si faltan, la entrega queda `proposed`.
5. Estados: ideal, vacío, carga, parcial, error y éxito; sin permiso y sin conexión cuando aplican. En el error se conserva lo escrito. Cada estado dice qué se ve y qué hace la acción primaria.
6. Prueba de contenido: un texto largo y la expansión al traducir. RTL si el producto lo necesita. La traducción en sí queda fuera.
7. Temas del producto, con los tokens de cada uno.

## Plantilla del Markdown

```markdown
# Handoff — <pantalla>

- Tarea o caso de uso:
- UI kit:
- Mock de origen:
- Plataforma y breakpoints:
- Temas:
- SVG con redlines: `<NNN>-handoff-<tema>-<pantalla>.svg`
- Origen de los textos:
- Origen de las anotaciones de accesibilidad:
- Estado de esta entrega: accepted | proposed (faltan: )

## Comportamiento por breakpoint

| Breakpoint | Qué cambia |
| --- | --- |

## Estados

| Estado | Qué se ve | Acción primaria | Conserva lo escrito |
| --- | --- | --- | --- |

## Textos

| Elemento | Texto | Origen |
| --- | --- | --- |

## Accesibilidad

| Anotación | Elemento | Criterio |
| --- | --- | --- |

## Medidas

| Elemento | Medida | Token |
| --- | --- | --- |
```

## Ejemplo

Handoff del pago. La cota entre el monto y el formulario es el token `space.stack`. El error muestra el texto que dio `adrenaline-ux-writing` y no vacía la tarjeta. El orden de foco es el que anotó `adrenaline-accessibility`. Si ese plugin no está en la sesión, se pide la anotación al usuario y, hasta recibirla, la fila de `STATUS.md` queda `proposed`.
