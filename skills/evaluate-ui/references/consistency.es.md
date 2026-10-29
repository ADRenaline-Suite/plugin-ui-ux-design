<p align="right">Idioma:&emsp;<a href="consistency.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Evaluar la interfaz](../SKILL.es.md)

# Consistencia con el kit de interfaz

Fuente: el kit de interfaz `accepted` del producto. No hay otro estándar. Si no hay un kit `accepted` ni tokens en este turno, sigue «Cuando falta un prerrequisito» en el skill. No compares contra un kit inventado en este turno, y no llenes el hueco con el preset `plain`.

## Qué fija

Cada lugar en el que una pantalla se desvía de los componentes y los tokens del kit.

## Cómo hacerlo

1. Nombra el archivo del kit. Revisa color, tipo, espacio, radio, elevación y los estados del componente (predeterminado, hover, focus, pulsado, deshabilitado, seleccionado, error, carga).
2. Un desvío dice qué token o componente, en qué pantalla y estado, qué se ve en su lugar y cómo volver al kit.
3. Si el desvío es intencional, no lo archives como accepted. Pide una decisión a `record-decision` y deja este hallazgo en espera de esa decisión.
4. Esto no sustituye las heurísticas ni WCAG.

## Plantilla

```markdown
# Consistencia — <screen>

- Kit de interfaz:
- Pantalla revisada:

| Componente o token | Pantalla | Estado | Qué difiere | Corrección |
| --- | --- | --- | --- | --- |
```

## Ejemplo

El botón «Pagar» usa un azul que no está en `color.action`. Corrección: usar el token del kit `color.action`. Si el equipo quiere ese otro azul, se registra como decisión y el kit cambia en otra entrega.

## Prerrequisitos

- **Kit de interfaz.** Un kit `accepted`, o los tokens de este turno. Si llegan en este turno, escribe el kit con `define-appearance` antes de comparar. Si no existe ninguno, esta revisión se detiene. No escribas archivos. No compares contra el preset `plain`. Comando anterior: `/uiux-ui-kit`.
- **Pantalla.** Un archivo `accepted`, o la pantalla descrita en este turno. Si no existe ninguno, esta revisión se detiene. No dibujes una pantalla para compararla. Comando anterior: `/uiux-mock`.

## Indicaciones

En un mensaje:

```text
/uiux-consistency de la pantalla de pago.
Pantalla: el mock accepted, o descríbela aquí.
Kit de interfaz, tema claro: acción #0066cc, fondo #ffffff, texto #1a1a1a, error #b00020, tipo Source Sans 3, espacio 16 px, radio 4 px, sombra 0 2 px 8 px.
```

En orden, omitiendo los que ya se cumplieron:

```text
/uiux-ui-kit para la tienda. Plataforma web, tema claro.
Acción #0066cc, fondo #ffffff, texto #1a1a1a, error #b00020, tipo Source Sans 3, espacio 16 px, radio 4 px, sombra 0 2 px 8 px.
```

```text
/uiux-mock de la pantalla de pago.
La tarea es pagar con tarjeta.
El camino es carrito, pago, resultado. Si el cobro falla, vuelve al pago con los datos todavía rellenos.
```

## Terminado

- El kit es un archivo accepted, o tokens de este turno escritos con `define-appearance` antes de la comparación. El preset `plain` no se usó para llenar un kit que faltaba.
- Cada desvío nombra el token o el componente, la pantalla, el estado, qué se ve en su lugar y cómo volver al kit. Un desvío intencional no se archiva como accepted: espera a `record-decision`.
- Las heurísticas y WCAG no quedan sustituidas por este archivo.
