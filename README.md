# UI/UX Design (`adrenaline-ui-ux-design`)

Diseña la experiencia y la interfaz de las pantallas de un producto digital: cómo se recorren, cómo se ven y cómo se construyen. No escribe el código de la interfaz.

Cada pieza está en `skills/<skill>/references/`. El resultado es Markdown y, cuando la pieza es visual, un SVG por pantalla. Los tokens van en `.tokens.json`. Las observaciones de pruebas van en CSV.

## Para quién

Quien diseña pantallas dentro de una conversación con el agente. Pide los diagramas UML a `adrenaline-uml-diagrams`, la accesibilidad a `adrenaline-accessibility` y los textos a `adrenaline-ux-writing`. No copia sus skills.

## Qué incluye

Portable, para cualquier agente que siga [Agent Skills](https://agentskills.io/specification):

- Siete skills. Cada uno lleva la carpeta de salida y las restricciones de fidelidad, para un agente que no carga rules.

Cursor y Claude Code:

- 25 commands: `/uiux-help` (catálogo de una línea) y uno por pieza. En Cursor, `/uiux-help` o `/uiux-wireframe`. En Claude Code, `/adrenaline-ui-ux-design:uiux-help`.

Solo Cursor:

- Rule `output-folder`, que guarda todo en la carpeta de salida.
- Rule `fidelidad-ui`, que impide saltar de fidelidad, dejar una pantalla sin estados o hacer aquí el oficio de otro plugin.

## Instalación

En Cursor, instala el plugin desde este repositorio en Customize.

En Claude Code, este repositorio también es un marketplace:

```text
claude plugin marketplace add d-mente/adrenaline-ui-ux-design
claude plugin install adrenaline-ui-ux-design@adrenaline-ui-ux-design
```

Para probar una copia local sin instalarla, arranca Claude Code con `claude --plugin-dir <ruta de este repositorio>`.

En otro agente, instala el skill con el mecanismo de ese agente. Por ejemplo:

```text
gh skill install d-mente/adrenaline-ui-ux-design
```

## Configuración

No usa variables ni servicios.

Cada entrega se guarda en `ui-ux-design/` en la raíz del proyecto, con un `<NNN>` monótono que no se reutiliza. La misma entrega comparte ese número: el Markdown y sus SVG, CSV o `.tokens.json`. La carpeta mantiene `STATUS.md` (`proposed` | `accepted` | `deprecated` | `superseded`). Al elegir qué seguir, manda `accepted`.

Para usar otra carpeta, añade `.cursor/adrenaline.json` al proyecto:

```json
{
  "outputDirs": {
    "adrenaline-ui-ux-design": "docs/ui"
  }
}
```

La ruta es relativa a la raíz del proyecto y no puede contener `..`. Claude Code y otros agentes leen el mismo archivo.

## Cómo pedirlo

En Cursor, `/uiux-sketch` o el nombre de otro command. En Claude Code, el mismo nombre con el prefijo del plugin: `/adrenaline-ui-ux-design:uiux-sketch`. Pedirlo en lenguaje natural basta: el skill elige la referencia.

El orden es entender la tarea, y después sketch, wireframe, mock, prototype y handoff. Sin la tarea no se pasa de sketch. Sin el recorrido decidido no se pasa a mock. La persona del journey map la aporta quien pide el mapa. Los textos finales los aporta `adrenaline-ux-writing` o quien los pegue en el turno. Las anotaciones de accesibilidad las aporta `adrenaline-accessibility`.

Un handoff sin textos o sin anotaciones queda `proposed`. No se entrega HTML.

## Catálogo

| Pieza | Acción | Documentación |
| --- | --- | --- |
| Tareas | `/uiux-tareas` | [referencia](skills/entender-usuario/references/tareas.md) |
| Journey map | `/uiux-journey-map` | [referencia](skills/entender-usuario/references/journey-map.md) |
| Brief | `/uiux-brief` | [referencia](skills/entender-usuario/references/brief.md) |
| Sketch | `/uiux-sketch` | [referencia](skills/concretar-pantalla/references/sketch.md) |
| Wireframe | `/uiux-wireframe` | [referencia](skills/concretar-pantalla/references/wireframe.md) |
| Mock | `/uiux-mock` | [referencia](skills/concretar-pantalla/references/mock.md) |
| Prototype | `/uiux-prototype` | [referencia](skills/concretar-pantalla/references/prototype.md) |
| Handoff | `/uiux-handoff` | [referencia](skills/concretar-pantalla/references/handoff.md) |
| User flow | `/uiux-user-flow` | [referencia](skills/ordenar-pantallas/references/user-flow.md) |
| Wireflow | `/uiux-wireflow` | [referencia](skills/ordenar-pantallas/references/wireflow.md) |
| Sitemap | `/uiux-sitemap` | [referencia](skills/ordenar-pantallas/references/sitemap.md) |
| Moodboard | `/uiux-moodboard` | [referencia](skills/definir-apariencia/references/moodboard.md) |
| UI kit | `/uiux-ui-kit` | [referencia](skills/definir-apariencia/references/ui-kit.md) |
| Heurísticas | `/uiux-heuristicas` | [referencia](skills/evaluar-ui/references/heuristicas.md) |
| Recorrido cognitivo | `/uiux-recorrido-cognitivo` | [referencia](skills/evaluar-ui/references/recorrido-cognitivo.md) |
| Consistencia | `/uiux-consistencia` | [referencia](skills/evaluar-ui/references/consistencia.md) |
| Revisión del flujo | `/uiux-revision-flujo` | [referencia](skills/evaluar-ui/references/revision-flujo.md) |
| Revisión de la implementación | `/uiux-revision-implementacion` | [referencia](skills/evaluar-ui/references/revision-implementacion.md) |
| Test de usabilidad | `/uiux-test-usabilidad` | [referencia](skills/medir-con-usuarios/references/test-usabilidad.md) |
| Análisis del test | `/uiux-analisis-test` | [referencia](skills/medir-con-usuarios/references/analisis-test.md) |
| Card sorting | `/uiux-card-sorting` | [referencia](skills/medir-con-usuarios/references/card-sorting.md) |
| Tree testing | `/uiux-tree-testing` | [referencia](skills/medir-con-usuarios/references/tree-testing.md) |
| HEART | `/uiux-heart` | [referencia](skills/medir-con-usuarios/references/heart.md) |
| Decisión de diseño | `/uiux-decision` | [referencia](skills/registrar-decision/references/decision.md) |

## Licencia

MIT. Ver [LICENSE](LICENSE).
