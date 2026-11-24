# templates-ia

Templates personales para trabajar con agentes de IA.

## Templates

Los que empiezan con `AGENTS-` se copian como `AGENTS.md`, para que la IA los lea sola en cada sesión; abrir la sesión en esa carpeta. Claude Code lo lee nativamente salvo si existe `CLAUDE.md` o `CLAUDE.local.md` (en ese caso o en versiones viejas, agregar `@AGENTS.md` en `CLAUDE.md`); Gemini CLI requiere agregar `AGENTS.md` en `context.fileName`. Si la carpeta ya tiene su propio `AGENTS.md`, copiar los de estudio con otro nombre y señalarlos en cada sesión.

- **`AGENTS-plan-de-estudio.md`** — guía de estudio paso a paso para código, PDFs o apuntes. Copiar a la carpeta del material y decirle a la IA qué se quiere estudiar.
- **`AGENTS-plan-de-estudio-online.md`** — igual que el anterior, pero en vez de estudiar desde archivos locales, la IA investiga el tema en internet (docs oficiales, tutoriales, repos, etc.). Copiar a una carpeta nueva para el tema y decir qué se quiere aprender.
- **`AGENTS-apoyo-estudio.md`** — para consultas puntuales mientras se estudia por cuenta propia: la IA responde en base a las fuentes de la carpeta, citándolas, y avisa cuando tiene que recurrir a información externa. Copiar a la carpeta del material y hacerle preguntas.
- **`AGENTS-template.md`** — reglas de trabajo compactas y portables para agentes en proyectos de código: límites de seguridad e inyección de prompts, verificar contra el código y versiones declaradas, actualizar tests y documentación solo en lo afectado (señalando sin borrar lo que sobre fuera de alcance), confirmar solo acciones con riesgo real y reportar chequeos con honestidad. Copiar a la raíz del proyecto; al actualizarlo desde la plantilla, conservar la sección `## Propio de este proyecto`.
- **`plan-de-debugging-template.md`** — bitácora para cazar un bug real con evidencia, sin inventar causas. No va como `AGENTS.md` (el proyecto ya tiene el suyo): copiar a la raíz del proyecto cuando aparezca un bug que amerite investigación y pedirle a la IA que arranque a partir de ese archivo, volviendo a señalárselo en cada sesión.
