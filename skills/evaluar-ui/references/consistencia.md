# Consistencia con el UI kit

Fuente: el UI kit `accepted` del producto. No hay otra norma. Si no hay kit, detente y pídelo. No compares contra un kit inventado en este turno.

## Qué fija

Cada desviación de una pantalla respecto a componentes y tokens del kit.

## Cómo hacerlo

1. Nombra el archivo del kit. Revisa color, tipo, espacio, radio, elevación y los estados del componente (por defecto, hover, foco, presionado, deshabilitado, seleccionado, error, carga).
2. Una desviación dice qué token o componente, en qué pantalla y estado, qué se ve en su lugar y cómo volver al kit.
3. Si la desviación es intencional, no la archives como aceptada. Pide una decisión a `registrar-decision` y deja este hallazgo a la espera de esa decisión.
4. Esto no sustituye a las heurísticas ni a WCAG.

## Plantilla

```markdown
# Consistencia — <pantalla>

- UI kit:
- Pantalla revisada:

| Componente o token | Pantalla | Estado | Qué difiere | Corrección |
| --- | --- | --- | --- | --- |
```

## Ejemplo

El botón «Pagar» usa un azul que no está en `color.action`. Corrección: usar el token `color.action` del kit. Si el equipo quiere ese otro azul, se registra como decisión y el kit cambia en otra entrega.
