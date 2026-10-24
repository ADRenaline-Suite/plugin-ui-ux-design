# Card sorting

Fuente: Nielsen Norman Group, Card Sorting. Genera agrupaciones. No evalúa una jerarquía ya nombrada: eso es tree testing.

## Qué fija

El plan de la sesión y, cuando hay datos, cómo agruparon las tarjetas.

## Cómo hacerlo

1. El tipo lo dice el usuario. Abierto: la persona crea los grupos y les pone nombre. Cerrado: los grupos ya tienen nombre. Híbrido: hay grupos dados y puede crear otros. Si no lo dicen, pregunta.
2. Las tarjetas son los contenidos que el usuario liste. No añadas contenidos «típicos».
3. El plan dice criterios de participantes, número que haya dado el usuario, y que una persona conduce la sesión.
4. Con datos, el CSV es `participante,tarjeta,grupo,tipo`. `tipo` es `abierto`, `cerrado` o `hibrido`. El Markdown resume acuerdos (tarjetas que caen juntas) y nombres de grupo que se repiten. Un desacuerdo se cuenta, no se desempata inventando el «grupo correcto».
5. Proponer la nueva agrupación como sitemap es otra entrega (`ordenar-pantallas`) o una decisión (`registrar-decision`). Este archivo no sustituye al sitemap.
6. Si solo hay plan, el CSV lleva el encabezado y la entrega queda `accepted`. Si pidieron el análisis y no hay filas, queda `proposed`.

## Plantilla

```markdown
# Card sorting — <tema>

- Tipo: abierto | cerrado | híbrido
- Tarjetas:
- Grupos dados: <solo cerrado o híbrido>
- Participantes:
- Fuente: Nielsen Norman Group, Card Sorting.

## Acuerdos

| Tarjetas que coinciden | Grupo más frecuente | Cuántos participantes |
| --- | --- | --- |

CSV: `<NNN>-card-sorting-<tema>.csv` (`participante,tarjeta,grupo,tipo`).
```

## Ejemplo

Abierto, tarjetas «recibo», «tarjeta», «dirección». Tres personas ponen recibo y tarjeta juntas y las llaman «Pago». Eso se informa como acuerdo. El sitemap no se reescribe en este archivo.
