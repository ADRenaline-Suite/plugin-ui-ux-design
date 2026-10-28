# plugin-ui-ux-design

Designs the experience and the interface of the screens of a digital product. The procedure is in `skills/`. Each piece has its manual in `skills/<skill>/references/`.

Files are saved in `ui-ux-design/` at the project root, or in the path `.cursor/adrenaline.json` sets in `outputDirs["plugin-ui-ux-design"]`. The name is `<NNN>-<type>-<topic>.<ext>`, with a monotonic `<NNN>`, and the folder keeps `STATUS.md`.

The artifact is written in the language of the request. The type in the file name stays the English piece id. `STATUS.md` columns stay `N`, `archivo`, `estado`, `sustituye`, `notas`.

A missing design input is filled with the named template in the piece reference. The file records it under `Assumed`, and the reply says it was taken automatically, which command changes it, and which command regenerates the piece. Consistency without a product UI kit, and an implementation review without a screenshot or a URL, write no files.

UML diagrams are asked of `plugin-uml-diagrams`. Accessibility, of `plugin-accessibility`. Interface copy, of `plugin-ux-writing`. This plugin does not write HTML or interface code.
