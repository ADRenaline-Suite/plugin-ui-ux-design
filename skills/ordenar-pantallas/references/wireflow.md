# Wireflow

Fuente: el user flow de la misma tarea, dibujado con un wireframe en cada paso. Sigue siendo UX, no UML.

## Qué fija

El mismo camino, con la jerarquía de cada paso a la vista.

## Qué deja abierto

Color, tipo y medidas de construcción.

## Cómo hacerlo

1. Si hay un user flow `accepted` de esa tarea, sigue sus pantallas y sus vueltas. Si no lo hay y el usuario describe el camino en este turno, úsalo y cítalo. Si el camino no está dicho, detente.
2. Un SVG por pantalla, en gris, con la misma regla visual que un wireframe: bloques, rótulos, sin color de marca. `xmlns="http://www.w3.org/2000/svg"`, `viewBox`, sin scripts ni `foreignObject`.
3. El Markdown ordena los pasos y apunta a cada SVG. No hace falta que los SVG estén enlazados: el enlace entre pantallas es el prototype. Aquí el orden lo da la lista.
4. Incluye el paso de error cuando el flujo lo tiene. El marco de error conserva los datos que la persona escribió.
5. Cada paso nombra la tarea que cubre.

## Plantilla

```markdown
# Wireflow — <tarea>

- Tarea o caso de uso:
- User flow de origen: <archivo> | descrito en este turno

## Pasos

| Paso | Pantalla | SVG |
| --- | --- | --- |
| 1 | Datos de pago | `<NNN>-wireflow-<tema>-datos.svg` |
```

## Ejemplo

Tres SVG grises: datos, resultado y error. El de error muestra el aviso y los campos de tarjeta todavía llenos. El Markdown los numera en el orden del user flow.
