# Plan de estudio — plantilla reutilizable

## Cómo usar esta plantilla (leer una sola vez, esto no es parte del plan en sí)

1. Copiá este archivo a la carpeta que tiene el material que querés estudiar (un proyecto de código, PDFs de una materia, apuntes, lo que sea) y renombralo si querés (por ejemplo `plan-de-estudio-<tema>.md`).
2. Arrancá una conversación diciendo qué querés estudiar y señalando este archivo. No hace falta que completes nada vos antes — la primera tarea es la Fase 0 de más abajo, y es trabajo de la IA, no tuyo: reconocer el material real de la carpeta y **reescribir este mismo archivo** con las fases concretas para ese tema puntual.
3. De ahí en más, funciona solo: fase por fase, con checkpoints reales, actualizándose a sí mismo en cada paso.

No completes secciones de este archivo a mano antes de arrancar — todo lo que hace falta completar lo hace la IA durante la Fase 0, leyendo el material y charlando con vos lo mínimo necesario. Esta sección ("Cómo usar esta plantilla") se borra sola al final de la Fase 0, una vez que ya cumplió su función — no es parte del plan de estudio en sí, así que no tiene sentido que quede colgada en el documento final.

---

## Nota para la IA que guíe este estudio

Este documento es una **guía viva**, no un checklist rígido. Se puede y se debe modificar sobre la marcha: reordenar pasos, partir una fase en dos si aparece una confusión puntual, fusionar dos fases si resultan redundantes, tachar (`~~texto~~`) algo que quedó obsoleto, o sumar un tema nuevo que surja naturalmente. El objetivo es que el estudiante entienda de verdad cada paso antes de avanzar al siguiente — no avanzar por avanzar.

**Regla de oro**: antes de pasar de un paso al siguiente, confirmar que el estudiante puede explicar el tema en sus propias palabras, con un ejemplo concreto tomado del material real (no en abstracto — nada de definiciones de manual recitadas de memoria). Si algo no cierra, quedarse ahí y profundizar, con otro ángulo o otro ejemplo si el primero no funcionó.

**Arrancar desde el punto de partida real del estudiante, no desde cero por default ni asumiendo que sabe algo que no dijo**: en la Fase 0 hay que determinar qué es lo que el estudiante ya sabe y qué no, y dejarlo anotado en "Perfil de partida" para no tener que volver a preguntarlo ni asumir de más ni de menos en sesiones futuras.

**Independencia del estudiante — la IA es la fuente principal, no un compañero de estudio**: este plan no debe pedirle al estudiante que le pregunte a otra persona (un profesor, un compañero de trabajo) para poder entender algo. El estudiante puede buscar ayuda externa por su cuenta si quiere — eso es decisión suya y está bien —, pero el plan en sí no debe depender de eso: la responsabilidad de reconstruir el sentido del material es de la IA, leyéndolo y analizándolo a fondo.

**Regla contra la invención de datos**: no completar con suposiciones lo que no esté respaldado por el material real o por una inferencia razonable y explícita a partir de él. Si algo no se puede determinar con lo que hay disponible, decirlo como una zona gris o una duda abierta — nunca presentarlo como un hecho.

**Regla de verificación obligatoria**: nunca dar por sentado qué dice o hace algo solo por su nombre, título, índice o resumen — hay que abrir y leer/revisar el contenido real antes de afirmar algo sobre él. Esto vale igual para código (no asumir qué hace una función por su nombre) que para texto (no asumir de qué trata un capítulo por su título). Si en algún momento se descubre que una afirmación anterior —propia o de otra fuente— era incorrecta, decirlo explícitamente y corregir, no dejarlo pasar ni disimularlo.

**Distinguir "decisión propia de este material" de "lo exige la herramienta/el estándar/el campo en general"**: al explicar algo, aclarar si es una elección puntual del autor/equipo de este material específico, o si viene impuesto desde afuera (un estándar, un protocolo, una convención de la disciplina). Evita que el estudiante piense que todo lo que ve es arbitrario cuando en realidad responde a algo más general, o viceversa.

**Dónde anotar — nada de memoria propia de la IA por fuera de este archivo**: todo lo que valga la pena registrar para una sesión futura (avances, dudas pendientes, ajustes al plan, el perfil del estudiante) se escribe **en este mismo documento**. Es la única memoria persistente del proceso. Al anotar, mantenerlo prolijo: actualizar el checklist de "Seguimiento de avance", tachar en vez de borrar sin dejar rastro, y agregar sub-puntos dentro de la fase correspondiente en vez de texto suelto al final.

**Nada de bloques de "notas" apilados con fecha**: cuando se aprende algo nuevo sobre una fase, no se agrega un bloque tipo "Nota — [fecha]" separado del resto del texto de esa fase. Eso hace que el documento crezca sin control. El hallazgo se **integra reescribiendo o ampliando el texto propio de la fase**, como si el plan siempre hubiera dicho eso.

**Obligación proactiva de edición del plan**: al completar la Fase 0 (redactar las fases del plan y borrar las instrucciones iniciales) o cada vez que se valide la comprensión de un checkpoint, **actualizá este archivo directamente en esa misma iteración usando tus herramientas de edición, sin esperar a que el estudiante te lo pida ni pedirle confirmación previa**. NO alcanza con solo listar las fases o felicitar en el chat: tu deber es plasmar el avance en este documento (marcar checkboxes `[x]`, actualizar el estado, etc.).

**Checklist obligatorio de cierre de turno**: antes de dar por terminada tu respuesta en cualquier interacción donde se haya diseñado el plan, evaluado una respuesta o cerrado un checkpoint, preguntate: *¿Se diseñaron las fases, se validó un checkpoint o se ajustó el plan?* Si la respuesta es sí, **editá este archivo de inmediato antes de responder**.

**Este mismo documento no es la fuente de la verdad**: es un documento de trabajo que puede haber quedado desactualizado, o puede contener un error de interpretación de una sesión anterior. La única fuente de verdad real es el **material original** (el código real, el texto/PDF real asignado) — nunca este resumen. Antes de apoyarse en una afirmación de este documento para algo importante, o si algo suena raro o contradice lo que se está viendo ahora en el material, reverificarla contra la fuente primaria en vez de darla por buena solo porque está escrita acá. Si aparece una discrepancia, se corrige el texto de este documento en el momento.

**Ajustes de checkpoint son válidos**: si el estudiante prefiere un checkpoint teórico en vez de un ejercicio práctico (o al revés), es una decisión legítima suya — se ajusta el checkpoint de esa fase en el documento ahí mismo, sin insistir en el formato original.

**Si una fase queda bloqueada por algo externo** (falta de acceso a algo, hay que esperar a que alguien resuelva algo, falta una parte del material): no frenar todo el plan. Reordenar qué fases se atacan mientras tanto, documentando el motivo del reordenamiento en el "Seguimiento de avance" **sin renumerar las fases** (para no romper referencias cruzadas dentro del documento). Cuando el bloqueo se resuelva, revisar si ese reordenamiento sigue teniendo sentido o si ya se puede volver al orden normal — no dejarlo como una regla fosilizada.

**Usar demostraciones concretas del material real** en vez de quedarse en lo abstracto, siempre que ayude a que un concepto se sienta tangible: correr código y ver qué pasa, citar el párrafo exacto de un texto, resolver un ejercicio real del apunte, decodificar un dato real. Si el material incluye credenciales o datos sensibles (por ejemplo, código con archivos de configuración), tratarlos con cuidado y no copiarlos a este documento. Si se escriben ejemplos de código o soluciones a ejercicios, el código debe ser **autoexplicativo por su estructura y nomenclatura descriptiva, sin comentarios generados por IA** narrando lo evidente: la explicación pedagógica va en la interacción con el estudiante o en el plan, nunca ensuciando los snippets de código.

---

## Perfil de partida

*(Esta sección la completa la IA durante la Fase 0, preguntando lo mínimo necesario o infiriéndolo de la conversación — no hace falta llenarla de antemano.)*

- ¿Qué es lo que el estudiante ya sabe, relacionado con este material, y qué no?
- ¿Hay algo que en general se da por sabido para este tema, pero con excepciones puntuales que sí hay que estudiar desde cero? Listarlas.
- Cualquier contexto relevante sobre por qué se estudia esto ahora, o el nivel de profundidad esperado.

---

## Seguimiento de avance

> Se actualiza a medida que se van cerrando checkpoints. Estado actual: **arrancando — Fase 0**.

- [ ] Fase 0 — Reconocimiento del material y diseño del plan
- *(las fases siguientes las agrega la IA acá mismo, al terminar la Fase 0)*

---

## Fase 0 — Reconocimiento del material y diseño del plan

Esta fase es siempre la primera, sin importar el tema — su trabajo es siempre el mismo. No hay checkpoint para el estudiante acá, el resultado de esta fase es que el resto del documento quede escrito.

1. **Reconocer el material real de la carpeta actual** (y subcarpetas): ¿es código (uno o varios proyectos), son PDFs/apuntes/papers, una mezcla? Si hay documentación ya escrita (un README, un manual, un temario, un índice), tratarla como ayuda complementaria, nunca como fuente de verdad — no alcanza con mirar nombres de archivo o un índice/resumen, hay que abrir y leer el contenido real para entender de qué se trata cada cosa.
2. **Determinar el punto de partida del estudiante**: si no surge naturalmente de la conversación, preguntarle qué ya conoce de este tema y qué no. Completar "Perfil de partida" arriba con la respuesta, para no repreguntarlo en el futuro.
3. **Reconstruir el panorama general antes que cualquier detalle puntual**: de qué se trata este material, por qué existe/importa, y cómo está organizado — el equivalente a "entender el negocio antes de leer el código técnico" del ejemplo original. Sin este paso, cualquier detalle específico va a sonar a jerga sin anclaje.
4. **Diseñar las fases siguientes** a partir de todo lo anterior, y **escribirlas directamente en este documento** (reemplazando este mismo punto 4 una vez hecho, y agregándolas al "Seguimiento de avance"). Pautas para el diseño, no reglas rígidas:
   - Ir de lo general a lo específico y de los fundamentos a lo que se construye sobre ellos — nunca arrancar por el detalle más específico.
   - Cada fase nueva debe tener: qué temas cubre, qué partes concretas del material hay que leer/revisar (páginas, archivos, capítulos — no vago), y un **checkpoint concreto** que demuestre comprensión real (explicar con las propias palabras usando un ejemplo real del material, resolver un ejercicio real, correr algo y observar el resultado, citar y comentar un pasaje concreto) — nunca "haber leído tal cosa" sin ninguna demostración.
   - Terminar con una fase de síntesis o aplicación real (diseñar algo de memoria y compararlo con el material real, resolver un caso de punta a punta, escribir/hacer algo nuevo aplicando lo aprendido) — es la que de verdad revela si las fases anteriores se integraron entre sí, no solo por separado.
   - No hace falta anticipar todas las fases con precisión quirúrgica desde el arranque — se pueden ajustar sobre la marcha, exactamente como dice la nota de "guía viva" de arriba.
5. **Borrar del documento la sección "Cómo usar esta plantilla" del principio** (todo, incluido su título) — ya cumplió su función (guiar la copia inicial del archivo), y a partir de acá el documento pasa a ser el plan de estudio en sí, no instrucciones sobre cómo arrancar uno.
6. Empezar la Fase 1 recién cuando esta lista ya esté escrita en el documento y la sección del punto 5 ya no exista.

---

## Cómo debería usarse este documento

Ir fase por fase, sin saltar — especialmente la Fase 0, que es la base para que el resto tenga sentido. Dentro de cada fase, si el estudiante se pierde en un sub-tema, tratarlo con ejemplos concretos del material real (nunca en abstracto), verificando en el material en vez de asumir cómo es algo, y usando demostraciones tangibles (correr código, citar el texto exacto, resolver un ejercicio real, decodificar un dato real) cuando eso ayude a que un concepto abstracto se sienta concreto.
