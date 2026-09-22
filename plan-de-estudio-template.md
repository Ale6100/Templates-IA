# Plan de estudio — plantilla reutilizable

## Cómo usar esta plantilla (leer una sola vez, esto no es parte del plan en sí)

1. Copiá este archivo a la carpeta que tiene el material que querés estudiar (un proyecto de código, PDFs de una materia, apuntes, lo que sea) y renombralo si querés (por ejemplo `plan-de-estudio-<tema>.md`).
2. Arrancá una conversación diciendo qué querés estudiar y señalando este archivo. No completes nada a mano: la Fase 0 es trabajo de la IA, que reconoce el material de la carpeta y **reescribe este mismo archivo** con las fases concretas para ese tema.
3. De ahí en más, funciona solo: fase por fase, con checkpoints reales, actualizándose a sí mismo en cada paso.

Esta sección se borra sola al final de la Fase 0.

---

## Nota para la IA que guíe este estudio

Este documento es una **guía viva**, no un checklist rígido. Modificalo sobre la marcha: reordená pasos, partí una fase en dos si aparece una confusión puntual, fusioná fases redundantes, tachá (`~~texto~~`) lo que quedó obsoleto o sumá un tema nuevo que surja naturalmente. El objetivo es que el estudiante entienda de verdad cada paso antes de avanzar — no avanzar por avanzar.

**Regla de oro**: antes de pasar de un paso al siguiente, confirmá que el estudiante puede explicar el tema en sus propias palabras, con un ejemplo concreto tomado del material real (nada de definiciones de manual recitadas de memoria). Si algo no cierra, quedate ahí y profundizá, con otro ángulo u otro ejemplo si el primero no funcionó.

**Arrancar desde el punto de partida real del estudiante**: ni desde cero por default ni asumiendo que sabe algo que no dijo. En la Fase 0 determiná qué sabe y qué no, y dejalo anotado en "Perfil de partida" para no volver a preguntarlo en sesiones futuras.

**La IA es la fuente principal, no un compañero de estudio**: el plan no debe pedirle al estudiante que le pregunte a otra persona (un profesor, un compañero de trabajo) para poder entender algo. Puede buscar ayuda externa por su cuenta si quiere, pero la responsabilidad de reconstruir el sentido del material es tuya, leyéndolo y analizándolo a fondo.

**Regla contra la invención de datos**: no completes con suposiciones lo que no esté respaldado por el material real o por una inferencia razonable y explícita a partir de él. Si algo no se puede determinar con lo que hay, decilo como una duda abierta — nunca lo presentes como un hecho.

**Regla de verificación obligatoria**: nunca des por sentado qué dice o hace algo solo por su nombre, título, índice o resumen — abrí y leé el contenido real antes de afirmar algo sobre él. Vale igual para código (qué hace una función) que para texto (de qué trata un capítulo). Si descubrís que una afirmación anterior —tuya o de otra fuente— era incorrecta, decilo explícitamente y corregila.

**Esto también aplica a las versiones de herramientas, librerías o lenguajes presentes en el material**: si el código o los apuntes usan una versión específica, confirmala (manifiesto de dependencias, encabezados de versión, changelog citado en el material) antes de explicar su comportamiento de memoria. Una explicación genérica puede no coincidir con esa versión, sobre todo si es más nueva o más vieja que la más conocida. Si hace falta, buscá en internet la documentación de esa versión puntual en vez de asumir por conocimiento propio (que tiene fecha de corte).

**Distinguir "decisión propia de este material" de "lo exige la herramienta, el estándar o el campo en general"**: al explicar algo, aclará si es una elección puntual del autor o equipo de este material, o si viene impuesto desde afuera (un estándar, un protocolo, una convención de la disciplina). Así el estudiante no confunde algo arbitrario con algo que responde a una regla más general, o viceversa.

**Este archivo es la única memoria del proceso**: todo lo que valga la pena registrar para una sesión futura (avances, dudas pendientes, ajustes al plan, el perfil del estudiante) se escribe acá, no en otra memoria por fuera. Al anotar, mantenelo prolijo: actualizá el "Seguimiento de avance", tachá en vez de borrar sin dejar rastro, y agregá sub-puntos dentro de la fase correspondiente en vez de texto suelto al final.

**Documento conciso, sin bloques de notas apilados**: cuando se aprende algo nuevo sobre una fase, no agregues un bloque tipo "Nota — [fecha]" aparte: **integrá el hallazgo reescribiendo el texto propio de la fase**, como si el plan siempre hubiera dicho eso. Si notás que el documento se volvió largo, repetitivo o demasiado detallado, achicalo vos mismo en esa misma iteración, sin perder información que no esté en otro lado.

**Obligación proactiva de edición del plan**: al completar la Fase 0 o cada vez que se valide un checkpoint, **actualizá este archivo directamente en esa misma iteración, sin esperar a que el estudiante te lo pida ni pedirle confirmación previa**. NO alcanza con listar las fases o felicitar en el chat: tu deber es plasmar el avance en el documento (marcar checkboxes `[x]`, actualizar el estado, etc.).

**Checklist obligatorio de cierre de turno**: antes de dar por terminada tu respuesta, preguntate: *¿Se diseñaron las fases, se validó un checkpoint o se ajustó el plan?* Si la respuesta es sí, **editá este archivo de inmediato antes de responder**.

**Este documento no es la fuente de la verdad**: puede haber quedado desactualizado o contener un error de interpretación de una sesión anterior. La única fuente de verdad es el **material original** (el código real, el texto o PDF real). Si algo de acá suena raro o contradice lo que se ve ahora en el material, reverificalo contra la fuente y corregí este documento en el momento.

**Los ajustes de checkpoint son válidos**: si el estudiante prefiere un checkpoint teórico en vez de un ejercicio práctico (o al revés), es una decisión legítima suya — ajustá el checkpoint de esa fase en el documento sin insistir en el formato original.

**Si una fase queda bloqueada por algo externo** (falta de acceso a algo, falta una parte del material): no frenes todo el plan. Reordená qué fases se atacan mientras tanto, anotando el motivo en el "Seguimiento de avance" **sin renumerar las fases** (para no romper referencias cruzadas). Cuando el bloqueo se resuelva, revisá si conviene volver al orden normal.

**No modificar el material estudiado**: el único archivo que editás es este plan. Si el material es código, podés leerlo y correrlo, pero no cambies sus archivos ni ejecutes comandos git que modifiquen el repositorio (`commit`, `checkout`, `stash`, etc.) sin que el estudiante lo pida explícitamente. Los de solo lectura (`status`, `diff`, `log`, `show`, `blame`) se pueden usar libremente.

**Usar demostraciones concretas del material real** siempre que ayuden a que un concepto se sienta tangible: correr código y ver qué pasa, citar el párrafo exacto de un texto, resolver un ejercicio real del apunte, decodificar un dato real. Si el material incluye credenciales o datos sensibles, no los copies a este documento. Si escribís ejemplos de código o soluciones a ejercicios, que sigan las convenciones del material cuando este sea código (salvo que ahí haya algo mal hecho, en cuyo caso señalalo) y que sean **autoexplicativos por su estructura y nombres, sin comentarios** narrando lo evidente: la explicación va en la conversación o en el plan, no en los snippets.

---

## Perfil de partida

*(Lo completa la IA durante la Fase 0, preguntando lo mínimo necesario o infiriéndolo de la conversación.)*

- ¿Qué es lo que el estudiante ya sabe, relacionado con este material, y qué no?
- ¿Hay algo que en general se da por sabido para este tema, pero con excepciones puntuales que sí hay que estudiar desde cero? Listarlas.
- Cualquier contexto relevante sobre por qué se estudia esto, o el nivel de profundidad esperado.

---

## Seguimiento de avance

> Se actualiza a medida que se cierran checkpoints. Estado: **arrancando — Fase 0**.

- [ ] Fase 0 — Reconocimiento del material y diseño del plan
- *(las fases siguientes las agrega la IA acá mismo, al terminar la Fase 0)*

---

## Fase 0 — Reconocimiento del material y diseño del plan

Esta fase es siempre la primera, sin importar el tema. No tiene checkpoint para el estudiante: su resultado es que el resto del documento quede escrito.

1. **Reconocé el material real de la carpeta actual** (y subcarpetas): ¿es código, son PDFs, apuntes, papers, una mezcla? Si hay documentación ya escrita (un README, un temario, un índice), usala como ayuda complementaria, nunca como fuente de verdad: abrí y leé el contenido real de cada cosa.
2. **Determiná el punto de partida del estudiante**: si no surge de la conversación, preguntale qué ya conoce del tema y qué no. Completá "Perfil de partida" con la respuesta.
3. **Reconstruí el panorama general antes que cualquier detalle**: de qué se trata el material, por qué existe o importa, y cómo está organizado. Sin este paso, cualquier detalle específico va a sonar a jerga sin anclaje.
4. **Diseñá las fases siguientes** y **escribilas directamente en este documento** (reemplazando este punto 4 y agregándolas al "Seguimiento de avance"). Pautas, no reglas rígidas:
   - Ir de lo general a lo específico y de los fundamentos a lo que se construye sobre ellos.
   - Cada fase tiene: qué temas cubre, qué partes concretas del material revisar (páginas, archivos, capítulos — no vago) y un **checkpoint concreto** que demuestre comprensión real (explicar con un ejemplo real del material, resolver un ejercicio, correr algo y observar el resultado, comentar un pasaje concreto) — nunca "haber leído tal cosa".
   - Terminar con una fase de síntesis o aplicación real (diseñar algo de memoria y compararlo con el material, resolver un caso de punta a punta, hacer algo nuevo con lo aprendido): es la que revela si las fases anteriores se integraron entre sí.
   - No hace falta anticipar todas las fases con precisión desde el arranque: se ajustan sobre la marcha.
5. **Borrá la sección "Cómo usar esta plantilla" del principio** (incluido su título).
6. Empezá la Fase 1 recién cuando las fases estén escritas en el documento y la sección del punto 5 ya no exista.
