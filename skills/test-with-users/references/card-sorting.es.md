<p align="right">Idioma:&emsp;<a href="card-sorting.md" style="vertical-align:middle"><img alt="English" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-en-off.svg" align="middle" style="vertical-align:middle"></a> <img alt="Español" src="https://raw.githubusercontent.com/ADRenaline-Suite/.github/main/profile/lang-es-on.svg" align="middle" style="vertical-align:middle"></p>

[🏠 UI/UX Design](../../../README.es.md) / [Probar con personas](../SKILL.es.md)

# Card sorting

Fuente: Nielsen Norman Group, Card Sorting. Genera agrupaciones. No evalúa una jerarquía que ya está nombrada: eso es tree testing.

## Qué fija

El plan de la sesión y, cuando hay datos, cómo agrupó la gente las tarjetas.

## Cómo hacerlo

1. La persona indica el tipo. Open: la persona crea los grupos y los nombra. Closed: los grupos ya tienen nombre. Hybrid: hay grupos dados y la persona puede crear otros. Si no lo dice, aplica la plantilla `open`.
2. Las tarjetas son los contenidos que lista la persona. No añadas contenidos «típicos».
3. El plan indica los criterios de los participantes, el número que dio la persona, y que una persona corre la sesión.
4. Con datos, el CSV es `participant,card,group,kind`. `kind` es `open`, `closed` o `hybrid`. El Markdown resume los acuerdos (tarjetas que caen juntas) y los nombres de grupo que se repiten. Un desacuerdo se cuenta, no se rompe inventando el «grupo correcto». La prosa sigue el idioma del artefacto.
5. Proponer la agrupación nueva como sitemap es otra entrega (`arrange-screens`) o una decisión (`record-decision`). Este archivo no sustituye el sitemap.
6. Si solo hay un plan, el CSV lleva la cabecera y la entrega es `accepted`. Si pidieron el análisis y no hay filas, se queda `proposed`.

## Plantilla

```markdown
# Card sorting — <topic>

- Kind: open | closed | hybrid
- Cards:
- Given groups: <closed or hybrid only>
- Participants:
- Source: Nielsen Norman Group, Card Sorting.

## Agreements

| Cards that match | Most frequent group | How many participants |
| --- | --- | --- |

CSV: `<NNN>-card-sorting-<topic>.csv` (`participant,card,group,kind`).
```

## Ejemplo

Tipo `open`, tarjetas «recibo», «tarjeta», «dirección». Tres personas juntan recibo y tarjeta y las llaman «Pago». Eso se informa como un acuerdo. El sitemap no se reescribe en este archivo.

## Prerrequisitos

- **Tipo.** Open, closed o hybrid, en este turno. Si falta, plantilla `open`: la persona crea los grupos y los nombra. Estado: `accepted` para un plan. Cámbialo con `/uiux-card-sorting`. Regenera con `/uiux-card-sorting`. No añadas tarjetas que la persona no listó. Si la lista de tarjetas está vacía, la entrega se queda `proposed` y Assumed dice que no se inventaron tarjetas.

## Indicaciones

En un mensaje:

```text
/uiux-card-sorting of the shop.
Kind: open.
Cards: receipt, card, address.
```

No hay un comando anterior. El único prompt es el camino.

## Terminado

- El tipo es `open`, `closed` o `hybrid`, como lo indicó la persona, o la plantilla `open` cuando no lo dijo. Las tarjetas son solo las que listó la persona. Una lista de tarjetas vacía deja la entrega `proposed`.
- Un plan con un CSV de solo cabecera es `accepted`. Un análisis sin filas es `proposed`.
- Con datos, el CSV es `participant,card,group,kind`. Los acuerdos se cuentan. No se inventó un «grupo correcto». El sitemap no se reescribió en este archivo.
