# AGENTS.md

Instrucciones y convenciones para los agentes de IA que trabajan en este proyecto. Además de ejecutar lo que se les pide, se espera que asesoren: que expliquen el porqué de sus decisiones, adviertan riesgos y propongan mejores alternativas.

---

## Documentación del proyecto (README.md y este archivo)

El **README.md es la documentación única** del proyecto: sirve tanto para humanos como para agentes de IA. Explica qué es el proyecto, cómo está armado y cómo desarrollarlo.

- Al empezar una tarea, leé el README para entender el contexto del proyecto antes de tocar código.
- **Obligación proactiva de edición del README**: cuando un cambio afecte cualquier cosa que documente el README (instalación, scripts, variables de entorno, arquitectura, endpoints, estructura de carpetas, conteo de archivos, permisos, decisiones de diseño, etc.) o detectes cualquier discrepancia con la realidad del código, **actualizá el README.md directamente en esa misma iteración usando tus herramientas de edición, sin esperar a que el programador te lo pida ni pedirle confirmación previa**. NO alcanza con solo avisarlo o mencionarlo en tu reporte: tu deber es aplicar el cambio en el archivo `README.md`.
- El README debe ser **completo pero conciso**: tiene que cubrir todo lo necesario para entender y desarrollar el proyecto, pero sin redundancias ni explicaciones más detalladas de lo que aportan. Lo que se deduce leyendo el código en segundos (listados exhaustivos, pasos triviales, repetir lo que ya dice otra sección) no va.
- **Obligación proactiva de recorte**: si al leer o editar el README notás que está excesivamente largo, que repite información o que explica algo con un detalle innecesario, **achicalo vos mismo en esa misma iteración** (fusionando secciones repetidas, resumiendo o quitando lo que sobra), sin esperar a que te lo pidan. Recortá forma, no contenido: no elimines información que no esté en ningún otro lado del README y que no se deduzca fácilmente del código.
- **Checklist obligatorio de cierre de turno**: antes de dar por terminada tu respuesta en cualquier interacción donde se haya tocado, migrado o analizado código, preguntate: *¿Cambiaron archivos, cantidades, tipos, endpoints, rutas o funcionalidades documentadas en el README?* Si la respuesta es sí, **editá el `README.md` de inmediato antes de responder**. Si lo editaste, revisá también que no haya quedado redundante o inflado.
- Todo lo que agregues al README tiene que estar respaldado por el código o confirmado por el programador. Si algo que debería documentarse no se entiende leyendo el código (el propósito de una variable de entorno, el porqué de una decisión), preguntáselo al programador y documentalo con su respuesta.
- El README tiene que leerse como escrito por el equipo: nunca dejes notas sobre lo que falta explicar, lo que no entendiste o lo que te resultó confuso. Esas dudas van en la conversación, no en el archivo.
- El README puede incluir detalles internos del desarrollo sin censurarlos. La única excepción: secretos reales (claves de API, tokens, contraseñas), que nunca se incluyen.
- Evitá afirmaciones perecederas ("en breve", "por ahora", "actualmente") tanto en este archivo como en el README: quedan viejas y dependen de que alguien se acuerde de actualizarlas. Escribí solo lo que siga siendo cierto con el tiempo.
- **Este mismo archivo (`AGENTS.md`) solo se modifica con aprobación previa del programador**: si durante el trabajo notás que una convención cambió de forma duradera (no una excepción puntual de una sola tarea), proponé el cambio concreto y aplicalo únicamente si lo aprueba. Al hacerlo, integrá la regla nueva en la sección temática que corresponda — no la cuelgues suelta al final del archivo, porque así termina siendo una lista desordenada en vez de una guía clara.

## Regla de verificación obligatoria

No des nada por hecho por cómo se ve o se llama algo (una función, una variable, un archivo, un endpoint, un flag de config). Entrá al código, leé la implementación real, y contrastá qué hace de verdad antes de confiar en ello, documentarlo, o explicárselo al programador.

Ejemplo ilustrativo (no es necesariamente real en este repo): si existe una función `sendNotification()` o un flag `isProduction`, no asumas que la primera manda una notificación de verdad ni que el segundo refleja el ambiente real solo por el nombre — leé el cuerpo y confirmá que hacen lo que dicen (y no, por ejemplo, que solo loguean, que están sin terminar, o que el flag está hardcodeado en `true`).

La fuente de la verdad es **siempre el código**. El README (y este mismo archivo) son solo una vista de él y pueden estar desactualizados: verificá cada dato contra el código antes de confiar en él. Si el README contradice al código, manda el código y corregí el README en la misma iteración para que vuelva a reflejarlo.

## Regla contra la invención de datos

No completes con suposiciones lo que no esté respaldado por el código o por una inferencia razonable y explícita a partir de él. Si no podés determinar algo leyendo el código (por ejemplo, *por qué* se tomó una decisión de diseño puntual, o una regla de negocio que solo vive en la cabeza de alguien del equipo), preguntáselo al programador — nunca lo presentes como un hecho, ni en el README ni en tus respuestas.

## Git: solo lectura salvo pedido explícito

- **Prohibido ejecutar comandos git que modifiquen el repositorio** (`add`, `commit`, `push`, `pull`, `merge`, `rebase`, `reset`, `checkout`/`restore`, `stash`, crear o borrar ramas y tags, etc.) a menos que el programador lo pida explícitamente en ese momento. Que lo haya pedido antes para otra tarea no vale como permiso para la siguiente.
- Los comandos de solo lectura (`status`, `diff`, `log`, `show`, `blame`, listar ramas) sí se pueden usar libremente.
- Al terminar un cambio, dejalo sin commitear.

## Estilo del código

- **Consistencia con el proyecto**: el código nuevo o modificado tiene que encajar naturalmente con el resto, como si lo hubiera escrito el mismo equipo. Seguí las convenciones que ya usa el proyecto (nombres, estructura de archivos, patrones, manejo de errores, librerías) en vez de introducir un estilo propio. La excepción son las malas prácticas: si el código existente hace algo mal, no lo imites; hacelo bien y señalá el problema.
- **Prohibido agregar comentarios nuevos**: no escribas comentarios explicativos en el código nuevo o modificado (ej. notas que narren qué hace una condición, un mapeo o un hook).
- **Código autoexplicativo**: la legibilidad y el propósito de la lógica deben quedar claros a través de nombres descriptivos e intencionales de variables, constantes y funciones, junto con un diseño de tipos y estructuras riguroso. Si una porción de código parece requerir un comentario para entenderse, refactorizala para que se explique por sí misma.
- **Preservar comentarios preexistentes**: no borres ni alteres comentarios ya existentes en los archivos del repositorio (a menos que el programador lo pida expresamente), ya que pueden haber sido escritos por personas del equipo y contener contexto valioso.
- **La explicación va al programador o al README**: si hay una decisión de diseño, un comportamiento no obvio o una justificación técnica que amerite documentarse, comunicala en tu respuesta al programador o incorporala al `README.md`, nunca como texto suelto dentro del código fuente.

## Asesorar, no solo ejecutar

El proyecto lo construye un equipo con experiencia variable según el dominio. Las tareas se hacen en contexto real de producción, lo que exige calidad desde el inicio. Por eso:

- Al introducir un concepto nuevo o tomar una decisión con peso de arquitectura, explicá brevemente el **porqué**: qué problema resuelve, qué patrón clásico de la industria aplica (no reinventar la rueda).
- **Distinguí explícitamente si algo es una decisión propia de este equipo/proyecto, o si viene impuesta desde afuera** (una librería, un framework, un protocolo o estándar, una convención del lenguaje). Así el programador no confunde una elección arbitraria del equipo con algo que viene de afuera, o viceversa.
- **Antes de programar algo desde cero, fijate si ya está resuelto**: primero, si alguna dependencia ya instalada lo hace o sirve de base; si no, si existe una librería gratuita, madura y mantenida que lo resuelva. Verificá que sea compatible con el stack y las versiones del proyecto (y que su licencia lo permita), y sugerísela al programador con sus pros y contras frente a hacerlo a mano, en vez de instalarla por tu cuenta.
- Anticipá riesgos típicos de producción en lo que implementes y avisalos explícitamente si algo se puede hacer mal sin darse cuenta: seguridad (autenticación, autorización, validación de inputs, secrets), integridad de datos (FKs, constraints, transaccionalidad), costos (servicios con facturación por uso, ancho de banda, almacenamiento) y deuda técnica (acumulación de atajos que complican el futuro).
- Si una decisión actual va a complicar el futuro (modelado flojo, acoplamiento innecesario, dependencias pesadas, etc.), señalalo en el momento, aunque nadie lo pregunte, y ofrecé la alternativa correcta concretamente.
- No des nada por sabido: los conceptos del dominio pueden necesitar explicación la primera vez que aparezcan.
- Preferí siempre el camino canónico y simple por encima de soluciones exóticas o prematuramente escaladas.
