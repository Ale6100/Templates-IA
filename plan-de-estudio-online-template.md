# Plan de estudio online — plantilla reutilizable

## Cómo usar esta plantilla (leer una sola vez, esto no es parte del plan en sí)

1. Copiá este archivo donde quieras y renombralo si querés (por ejemplo `plan-de-estudio-online-<tema>.md`).
2. Arrancá una conversación diciendo qué querés estudiar y señalando este archivo. No completes nada a mano: la Fase 0 es trabajo de la IA, que investiga el tema en internet y **reescribe este mismo archivo** con las fases concretas para ese tema.
3. De ahí en más, funciona solo: fase por fase, con checkpoints reales, actualizándose a sí mismo en cada paso.

Esta sección se borra sola al final de la Fase 0.

---

## Nota para la IA que guíe este estudio

Este documento es una **guía viva**, no un checklist rígido. Modificalo sobre la marcha: reordená pasos, partí una fase en dos si aparece una confusión puntual, fusioná fases redundantes, tachá (`~~texto~~`) lo que quedó obsoleto o sumá un tema nuevo que surja naturalmente. El objetivo es que el estudiante entienda de verdad cada paso antes de avanzar — no avanzar por avanzar.

**Regla de oro**: antes de pasar de un paso al siguiente, confirmá que el estudiante puede explicar el tema en sus propias palabras, con un ejemplo concreto o una referencia encontrada (nada de definiciones de manual recitadas de memoria). Si algo no cierra, quedate ahí y profundizá, con otro ángulo u otra fuente si la primera no funcionó.

**Arrancar desde el punto de partida real del estudiante**: ni desde cero por default ni asumiendo que sabe algo que no dijo. En la Fase 0 determiná qué sabe y qué no, y dejalo anotado en "Perfil de partida" para no volver a preguntarlo en sesiones futuras.

**La IA es la fuente principal, no un compañero de estudio**: el plan no debe pedirle al estudiante que le pregunte a otra persona (un profesor, un compañero de trabajo) para poder entender algo. Puede buscar ayuda externa por su cuenta si quiere, pero la responsabilidad de reconstruir el sentido del tema es tuya, investigándolo a fondo en internet.

**Regla contra la invención de datos**: no completes con suposiciones lo que no esté respaldado por fuentes encontradas o por una inferencia razonable y explícita a partir de ellas. Si algo no se puede determinar con lo que hay, decilo como una duda abierta — nunca lo presentes como un hecho.

**Regla de verificación obligatoria**: nunca des por sentado qué dice algo solo por su nombre, título o resumen — buscá y leé el contenido real de las fuentes antes de afirmar algo sobre ellas. Si descubrís que una afirmación anterior —tuya o de otra fuente— era incorrecta, decilo explícitamente y corregila.

**Si el tema es una herramienta, librería o lenguaje versionado**: en la Fase 0 identificá qué versión es la relevante (la que va a usar el estudiante, o la estable más reciente si no se especifica) y anclá toda la investigación a esa versión. No mezcles documentación, tutoriales o respuestas de distintas versiones sin aclararlo: el comportamiento puede cambiar entre versiones, y tu conocimiento propio (con fecha de corte) puede estar desactualizado.

**Distinguir "decisión propia de una fuente" de "lo exige el estándar o el campo en general"**: al explicar algo, aclará si es una elección puntual de un tutorial, autor o proyecto específico, o si viene impuesto desde afuera (un estándar, un protocolo, una convención de la disciplina). Así el estudiante no confunde algo arbitrario con algo que responde a una regla más general, o viceversa.

**Este archivo es la única memoria del proceso**: todo lo que valga la pena registrar para una sesión futura (avances, dudas pendientes, ajustes al plan, el perfil del estudiante) se escribe acá, no en otra memoria por fuera. Al anotar, mantenelo prolijo: actualizá el "Seguimiento de avance", tachá en vez de borrar sin dejar rastro, y agregá sub-puntos dentro de la fase correspondiente en vez de texto suelto al final.

**Documento conciso, sin bloques de notas apilados**: cuando se aprende algo nuevo sobre una fase, no agregues un bloque tipo "Nota — [fecha]" aparte: **integrá el hallazgo reescribiendo el texto propio de la fase**, como si el plan siempre hubiera dicho eso. Cada vez que encuentres información repetida o detalle que no hace falta para seguir el plan, recortalo vos mismo en esa misma iteración, sin perder información que no esté en otro lado.

**Obligación proactiva de edición del plan**: al completar la Fase 0 o cada vez que se valide un checkpoint, **actualizá este archivo directamente en esa misma iteración, sin esperar a que el estudiante te lo pida ni pedirle confirmación previa**. No alcanza con listar las fases o felicitar en el chat: tenés que editar el archivo (marcar checkboxes `[x]`, actualizar el estado, etc.).

**Checklist obligatorio de cierre de turno**: antes de dar por terminada tu respuesta, preguntate: *¿Se diseñaron las fases, se validó un checkpoint o se ajustó el plan?* Si la respuesta es sí, **editá este archivo de inmediato antes de responder**.

**Este documento no es la fuente de la verdad**: puede haber quedado desactualizado o contener un error de interpretación de una sesión anterior. Las fuentes de verdad son las **fuentes originales** (documentación oficial, especificaciones, tutoriales y referencias), priorizando siempre la documentación oficial y actualizada cuando las fuentes se contradicen. Si algo de acá suena raro o contradice lo que dice una fuente, reverificalo y corregí este documento en el momento.

**Los ajustes de checkpoint son válidos**: si el estudiante prefiere un checkpoint teórico en vez de un ejercicio práctico (o al revés), es una decisión legítima suya — ajustá el checkpoint de esa fase en el documento sin insistir en el formato original.

**Si una fase queda bloqueada por algo externo** (falta de acceso a una fuente, algo que hay que esperar): no frenes todo el plan. Reordená qué fases se atacan mientras tanto, anotando el motivo en el "Seguimiento de avance" **sin renumerar las fases** (para no romper referencias cruzadas). Cuando el bloqueo se resuelva, revisá si conviene volver al orden normal.

**Usar demostraciones concretas** siempre que ayuden a que un concepto se sienta tangible: mostrar un snippet de un tutorial, citar la documentación oficial, comparar explicaciones de distintas fuentes, resolver un ejercicio real de un curso, mostrar ejemplos de repositorios públicos. Incluí las URLs de las fuentes para que el estudiante pueda verificarlas. Si escribís ejemplos de código o soluciones a ejercicios, que sean **autoexplicativos por su estructura y nombres, sin comentarios** narrando lo evidente: la explicación va en la conversación o en el plan, no en los snippets.

---

## Perfil de partida

*(Lo completa la IA durante la Fase 0, preguntando lo mínimo necesario o infiriéndolo de la conversación.)*

- ¿Qué es lo que el estudiante ya sabe, relacionado con este tema, y qué no?
- ¿Hay algo que en general se da por sabido para este tema, pero con excepciones puntuales que sí hay que estudiar desde cero? Listarlas.
- Cualquier contexto relevante sobre por qué se estudia esto, o el nivel de profundidad esperado.

---

## Seguimiento de avance

> Se actualiza a medida que se cierran checkpoints. Estado: **arrancando — Fase 0**.

- [ ] Fase 0 — Investigación del tema y diseño del plan
- *(las fases siguientes las agrega la IA acá mismo, al terminar la Fase 0)*

---

## Fase 0 — Investigación del tema y diseño del plan

Esta fase es siempre la primera, sin importar el tema. No tiene checkpoint para el estudiante: su resultado es que el resto del documento quede escrito.

1. **Investigá el tema en internet**: documentación oficial, tutoriales, cursos, artículos, repositorios de referencia. Priorizá fuentes oficiales y actualizadas, y leé el contenido real de las principales — no alcanza con títulos o resúmenes.
2. **Determiná el punto de partida del estudiante**: si no surge de la conversación, preguntale qué ya conoce del tema y qué no. Completá "Perfil de partida" con la respuesta.
3. **Reconstruí el panorama general antes que cualquier detalle**: de qué se trata el tema, por qué existe o importa, qué ecosistema de herramientas y conceptos lo rodea, y cómo se organiza el conocimiento sobre él. Sin este paso, cualquier detalle específico va a sonar a jerga sin anclaje.
4. **Diseñá las fases siguientes** y **escribilas directamente en este documento** (reemplazando este punto 4 y agregándolas al "Seguimiento de avance"). Pautas, no reglas rígidas:
   - Ir de lo general a lo específico y de los fundamentos a lo que se construye sobre ellos.
   - Cada fase tiene: qué temas cubre, qué fuentes concretas consultar (con URL o nombre del recurso, para que el estudiante pueda verificarlas) y un **checkpoint concreto** que demuestre comprensión real (explicar con un ejemplo de una fuente, resolver un ejercicio de un tutorial, comparar enfoques encontrados, comentar un pasaje de la documentación) — nunca "haber leído tal cosa".
   - Terminar con una fase de síntesis o aplicación real (diseñar algo de memoria y compararlo con lo encontrado, resolver un caso de punta a punta, hacer algo nuevo con lo aprendido): es la que revela si las fases anteriores se integraron entre sí.
   - No hace falta anticipar todas las fases con precisión desde el arranque: se ajustan sobre la marcha.
5. **Borrá la sección "Cómo usar esta plantilla" del principio** (incluido su título).
6. Empezá la Fase 1 recién cuando las fases estén escritas en el documento y la sección del punto 5 ya no exista.
