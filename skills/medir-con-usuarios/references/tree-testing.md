# Tree testing

Fuente: Nielsen Norman Group, Tree Testing. Evalúa una jerarquía ya nombrada. El éxito directo, el éxito indirecto y el primer clic son el resultado.

## Qué fija

Si las personas encuentran un destino en el sitemap, sin el aspecto visual de la pantalla.

## Cómo hacerlo

1. La jerarquía es un sitemap `accepted` o el árbol que el usuario pegue, con los nombres ya decididos. No renombres ítems durante el análisis.
2. Cada tarea pide encontrar un destino y no dice en qué rama está. «¿Dónde ves el recibo del pedido?» sí. «Entra en Cuenta y luego Recibos» no.
3. El plan fija participantes como los describa el usuario. Una persona conduce la sesión.
4. Con datos, el CSV es `participante,tarea,exito_directo,exito_indirecto,primer_clic,ruta`. Los éxitos y el primer clic son `si` o `no`.
   - Éxito directo: llegó al destino sin retroceder.
   - Éxito indirecto: llegó al destino y sí retrocedió.
   - Primer clic: el primer ítem elegido está en un camino correcto hacia el destino.
5. Una tarea no puede tener éxito directo e indirecto a la vez. Si los datos vienen así, pregunta.
6. El Markdown da, por tarea, la proporción de cada éxito y del primer clic. No conviertas el árbol en un sitemap nuevo aquí.
7. Si solo hay plan, el CSV lleva el encabezado y la entrega queda `accepted`. Si pidieron el análisis y no hay filas, queda `proposed`.

## Plantilla

```markdown
# Tree testing — <tema>

- Árbol: <sitemap o lista>
- Participantes:
- Fuente: Nielsen Norman Group, Tree Testing.

## Tareas

1. <encontrar un destino, sin nombrar la rama>

## Resultados

| Tarea | Directo | Indirecto | Primer clic correcto |
| --- | --- | --- | --- |

CSV: `<NNN>-tree-testing-<tema>.csv` (`participante,tarea,exito_directo,exito_indirecto,primer_clic,ruta`).
```

## Ejemplo

Árbol: Tienda → Pedido → Pago. Tarea: «¿Dónde consultas el recibo?». De cinco personas, dos llegan sin retroceder (directo 0,4), una llega tras volver atrás (indirecto 0,2) y tres eligen primero «Pedido» (primer clic 0,6).
