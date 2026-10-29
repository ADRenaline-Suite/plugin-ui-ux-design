<p align="right">Idioma:&emsp;<a href="tree-testing.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Probar con personas](../SKILL.es.md)

# Tree testing

Fuente: Nielsen Norman Group, Tree Testing. Evalúa una jerarquía que ya está nombrada. El éxito directo, el éxito indirecto y el primer clic son el resultado.

## Qué fija

Si la gente encuentra un destino en el sitemap, sin la apariencia visual de la pantalla.

## Cómo hacerlo

1. La jerarquía es un sitemap `accepted` o el árbol que pega la persona, con los nombres ya decididos. Si no existe ninguno, escribe un sitemap en este turno con la plantilla `one-group` y usa ese árbol. No renombres ítems durante el análisis.
2. Cada tarea pide encontrar un destino y no dice en qué rama está. «¿Dónde ves el recibo del pedido?» está bien. «Entra en Cuenta y luego en Recibos» no.
3. El plan fija a los participantes como los describe la persona. Una persona corre la sesión.
4. Con datos, el CSV es `participant,task,direct_success,indirect_success,first_click,path`. Los éxitos y el primer clic son `yes` o `no`.
   - Éxito directo: llegaron al destino sin volver atrás.
   - Éxito indirecto: llegaron al destino y sí volvieron atrás.
   - Primer clic: el primer ítem que eligieron está en un camino correcto hacia el destino.
5. Una tarea no puede ser a la vez un éxito directo y uno indirecto. Si los datos llegan así, pregunta.
6. El Markdown da, por tarea, la proporción de cada éxito y del primer clic. No conviertas el árbol en un sitemap nuevo aquí.
7. Si solo hay un plan, el CSV lleva la cabecera y la entrega es `accepted`. Si pidieron el análisis y no hay filas, se queda `proposed`.

## Plantilla

```markdown
# Tree testing — <topic>

- Tree: <sitemap or list>
- Participants:
- Source: Nielsen Norman Group, Tree Testing.

## Tasks

1. <find a destination, without naming the branch>

## Results

| Task | Direct | Indirect | Correct first click |
| --- | --- | --- | --- |

CSV: `<NNN>-tree-testing-<topic>.csv` (`participant,task,direct_success,indirect_success,first_click,path`).
```

## Ejemplo

Árbol: Tienda → Pedido → Pago. Tarea: «¿Dónde consultas el recibo?». De cinco personas, dos llegan sin volver atrás (directo 0.4), una llega después de volver atrás (indirecto 0.2), y tres eligen «Pedido» primero (primer clic 0.6).

## Prerrequisitos

- **Árbol.** Un sitemap `accepted`, o el árbol pegado en este turno. Si no existe ninguno, escribe un sitemap en este turno con la plantilla `one-group` y prueba ese árbol. Una tarea de encontrar por cada pantalla, sin nombrar la rama. Estado de un plan: `accepted`. Un análisis sin filas se queda `proposed`. Cambia el árbol con `/uiux-sitemap`. Regenera con `/uiux-tree-testing`.

## Indicaciones

En un mensaje:

```text
/uiux-tree-testing of the receipt.
Tree: Shop → Order → Payment → Receipt.
Task: where do you check the receipt?
```

En orden, omitiendo los que ya están cumplidos:

```text
/uiux-sitemap of the shop.
Groups: Shop → Order → Payment → Receipt.
Payment covers the task pay with a card.
```

## Terminado

- El árbol es un sitemap `accepted`, la lista que pegó la persona, o la plantilla `one-group` escrita en este turno. Assumed dice cuál. Los nombres de ítem que dio la persona no se renombraron.
- Cada tarea pide un destino y no nombra la rama.
- Un plan con un CSV de solo cabecera es `accepted`. Un análisis sin filas es `proposed`.
- Con datos, una tarea no es a la vez un éxito directo y uno indirecto. Se informan las proporciones. El archivo no sustituye el sitemap.
