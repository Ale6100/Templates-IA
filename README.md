# templates-ia

Templates personales para trabajar con agentes de IA.

## Templates

- **`plan-de-estudio-template.md`** — guía de estudio paso a paso para código, PDFs o apuntes. Copiar a la carpeta del tema y pedirle a la IA que arranque a partir de ese archivo.
- **`plan-de-estudio-online-template.md`** — igual que el anterior, pero en vez de estudiar desde archivos locales, la IA investiga el tema en internet (docs oficiales, tutoriales, repos, etc.). Solo decir qué se quiere aprender.
- **`AGENTS-template.md`** — reglas para agentes en proyectos de código: README al día y conciso, verificar contra el código, git solo lectura, asesorar explicando decisiones y advirtiendo riesgos. Copiar a la raíz del proyecto como `AGENTS.md`.
- **`plan-de-debugging-template.md`** — bitácora para cazar un bug real con evidencia, sin inventar causas. Copiar al proyecto cuando aparezca un bug que amerite investigación, y pedirle a la IA que arranque a partir de ese archivo.

## Pendientes

- **`AGENTS-template.md`: revisar los cambios hechos por el programador entre sesiones.** Al empezar una tarea, la IA revisaría lo que cambió desde la última actualización del README: los cambios sin commitear (`git status`, `git diff`) y los commits posteriores al último que modificó `README.md`. Primero el resumen (`--stat`) y después solo lo relevante, para no gastar tokens de más. Con eso actualizaría el README si corresponde y le avisaría al programador si ve problemas en ese código, sin reescribirlo salvo pedido. Limitación: si se commitea mucho sin actualizar el README, el rango a revisar crece.
