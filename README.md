# templates-ia

Templates personales para trabajar con agentes de IA.

## Templates

- **`plan-de-estudio-template.md`** — guía de estudio paso a paso para código, PDFs o apuntes. Copiar a la carpeta del tema y pedirle a la IA que arranque a partir de ese archivo.
- **`plan-de-estudio-online-template.md`** — igual que el anterior, pero en vez de estudiar desde archivos locales, la IA investiga el tema en internet (docs oficiales, tutoriales, repos, etc.). Solo decir qué se quiere aprender.
- **`apoyo-estudio-template.md`** — para consultas puntuales mientras se estudia por cuenta propia: la IA responde en base a las fuentes de la carpeta, citándolas, y avisa cuando tiene que recurrir a información externa. Copiar a la carpeta del material y hacerle preguntas a partir de ese archivo.
- **`AGENTS-template.md`** — reglas para agentes en proyectos de código: README al día y conciso; verificar contra el código; confirmación antes de lo que puede perder trabajo, sale del entorno de desarrollo o trae código de terceros (git riesgoso, deploys, dependencias, servicios externos, archivos locales ajenos como el `.env`); commits solo si se piden; comandos de desarrollo (tests, migraciones, seeds, levantar la app) libres, salvo efectos riesgosos que el README todavía no menciona, que se consultan una sola vez y se documentan; acordar el enfoque antes de implementar pedidos ambiguos; tests proactivos según la estrategia documentada en el README del proyecto, que verifican el comportamiento esperado (no el actual) y cubren casos borde; asesorar explicando decisiones y advirtiendo riesgos; y uso de subagentes. Copiar a la raíz del proyecto como `AGENTS.md`. Para Claude Code, crear también un `CLAUDE.md` con la línea `@AGENTS.md` (o agregársela si ya existe), así lo carga en cualquier versión.
- **`plan-de-debugging-template.md`** — bitácora para cazar un bug real con evidencia, sin inventar causas. Copiar al proyecto cuando aparezca un bug que amerite investigación, y pedirle a la IA que arranque a partir de ese archivo.
