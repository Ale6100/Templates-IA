# templates-ia

Templates personales para trabajar con agentes de IA.

## Templates

Los que empiezan con `AGENTS-` se copian como `AGENTS.md`, para que la IA los lea sola en cada sesión; abrir la sesión en esa carpeta. Para Claude Code, agregar la línea `@AGENTS.md` al `CLAUDE.md` (o crearlo con esa línea): sin el import, lo ignora si hay un `CLAUDE.md` o `CLAUDE.local.md`. Si la carpeta ya tiene su propio `AGENTS.md`, copiar los de estudio con otro nombre y señalarlos en cada sesión.

- **`AGENTS-plan-de-estudio.md`** — guía de estudio paso a paso para código, PDFs o apuntes. Copiar a la carpeta del material y decirle a la IA qué se quiere estudiar.
- **`AGENTS-plan-de-estudio-online.md`** — igual que el anterior, pero en vez de estudiar desde archivos locales, la IA investiga el tema en internet (docs oficiales, tutoriales, repos, etc.). Copiar a una carpeta nueva para el tema y decir qué se quiere aprender.
- **`AGENTS-apoyo-estudio.md`** — para consultas puntuales mientras se estudia por cuenta propia: la IA responde en base a las fuentes de la carpeta, citándolas, y avisa cuando tiene que recurrir a información externa. Copiar a la carpeta del material y hacerle preguntas.
- **`AGENTS-template.md`** — reglas de trabajo para agentes en proyectos de código: verificar contra el código, mantener el README al día y conciso (recortando también el que ya tenga el proyecto), confirmar solo acciones con riesgo real y testear el comportamiento esperado (recortando también los tests de detalle que ya tenga), sin documentación, comentarios ni tests de relleno. Copiar a la raíz del proyecto; al actualizarlo desde la plantilla, conservar su sección final `## Propio de este proyecto`.
- **`plan-de-debugging-template.md`** — bitácora para cazar un bug real con evidencia, sin inventar causas. No va como `AGENTS.md` (el proyecto ya tiene el suyo): copiar a la raíz del proyecto cuando aparezca un bug que amerite investigación y pedirle a la IA que arranque a partir de ese archivo; en las sesiones siguientes, el `AGENTS.md` de la plantilla hace que la IA la busque sola.
