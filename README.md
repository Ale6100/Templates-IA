# templates-ia

Templates personales para trabajar con agentes de IA.

## Templates

- **`plan-de-estudio-template.md`** — guía de estudio paso a paso para código, PDFs o apuntes. Copiar a la carpeta del tema y pedirle a la IA que arranque a partir de ese archivo.
- **`plan-de-estudio-online-template.md`** — igual que el anterior, pero en vez de estudiar desde archivos locales, la IA investiga el tema en internet (docs oficiales, tutoriales, repos, etc.). Solo decir qué se quiere aprender.
- **`apoyo-estudio-template.md`** — para consultas puntuales mientras se estudia por cuenta propia: la IA responde en base a las fuentes de la carpeta, citándolas, y avisa cuando tiene que recurrir a información externa. Copiar a la carpeta del material y hacerle preguntas a partir de ese archivo.
- **`AGENTS-template.md`** — reglas de trabajo para agentes en proyectos de código: verificar contra el código, mantener el README al día y conciso (recortando también el que ya tenga el proyecto), confirmar solo acciones con riesgo real y testear el comportamiento esperado (recortando también los tests de detalle que ya tenga), sin documentación, comentarios ni tests de relleno. Copiar a la raíz del proyecto como `AGENTS.md`; al actualizarlo desde la plantilla, conservar su sección final `## Propio de este proyecto`. Para Claude Code, agregar la línea `@AGENTS.md` al `CLAUDE.md` (o crearlo con esa línea): sin el import, lo ignora si hay un `CLAUDE.md` o `CLAUDE.local.md`.
- **`plan-de-debugging-template.md`** — bitácora para cazar un bug real con evidencia, sin inventar causas. Copiar al proyecto cuando aparezca un bug que amerite investigación, y pedirle a la IA que arranque a partir de ese archivo.
