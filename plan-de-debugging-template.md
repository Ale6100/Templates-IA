# Plan de debugging — plantilla reutilizable

## Cómo usar esta plantilla (leer una sola vez, esto no es parte del plan en sí)

1. Copiá este archivo a la raíz del proyecto (o a la carpeta del repo) cuando te encuentres con un bug que no se resuelve mirándolo dos minutos — no hace falta para cualquier error trivial.
2. Contale a la IA el síntoma real que estás viendo y señalá este archivo.
3. La IA arranca por la Fase 0 (reconocimiento) y va llenando el resto del documento a medida que investiga, contrastando cada hipótesis con evidencia real antes de darla por buena.

Esta sección se borra sola al final de la Fase 0, una vez que ya cumplió su función.

---

## Nota para la IA que guíe esta investigación

Este documento es una **bitácora viva** de una investigación en curso, no un reporte que se escribe al final. Se actualiza a medida que se descartan o confirman hipótesis, no de una sola vez al terminar.

**Regla de oro**: nunca declarar una causa como confirmada sin haber visto la evidencia real que lo prueba (un log real, un valor real inspeccionado, un test que reproduce el fallo y deja de fallar con el arreglo). "Me parece que es esto" no es una conclusión, es una hipótesis — se trata como tal hasta que haya evidencia.

**Reproducir antes que teorizar**: el primer objetivo, antes de sospechar cualquier causa, es lograr reproducir el bug de forma confiable (los mismos pasos, el mismo resultado, todas las veces). Si no se puede reproducir todavía, ese es el problema a resolver primero — no tiene sentido investigar causas de algo que no se puede observar de nuevo a voluntad.

**Confirmar el comportamiento esperado, no asumirlo**: antes de asumir que algo es un bug, confirmar qué debería pasar en realidad (revisando specs, tests existentes, tickets, el comportamiento documentado) — a veces lo que parece un bug es el sistema funcionando como se diseñó, y el desajuste real está en la expectativa, no en el código.

**Regla de verificación obligatoria**: no asumir qué hace una función, un config, una librería o un endpoint solo por su nombre — abrir y leer la implementación real antes de sospechar o descartar algo por esa vía. Esto vale también para el código de librerías externas si hace falta bajar hasta ahí.

**Regla contra la invención de causas**: no completar con suposiciones lo que no está confirmado con evidencia. Si algo no se puede determinar con la evidencia disponible, decirlo explícitamente como hipótesis abierta — nunca como una conclusión.

**Distinguir "bug en este código" de "comportamiento esperado de algo externo"** (una librería, el runtime, el sistema operativo, una API de terceros): antes de asumir que el bug está en el código propio, confirmar que no es, en realidad, el funcionamiento documentado (aunque sorprendente) de algo externo.

**Ninguna hipótesis descartada se borra**: se tacha (`~~hipótesis~~`) dejando anotado por qué se descartó y con qué evidencia — así no se vuelve a investigar por error el mismo camino muerto en una sesión futura, ni se repite un razonamiento ya refutado.

**Obligación proactiva de edición de esta bitácora**: en cuanto se recolecte evidencia, se confirme o descarte una hipótesis, o se avance de fase, **actualizá este archivo directamente en esa misma iteración usando tus herramientas de edición, sin esperar a que el usuario te lo pida ni pedirle confirmación previa**. NO alcanza con solo avisarlo o comentarlo en tu respuesta: tu deber es plasmar el cambio en el documento.

**Checklist obligatorio de cierre de turno**: antes de dar por terminada tu respuesta en cualquier interacción de debugging, preguntate: *¿Se sumó evidencia, se confirmó/descartó una hipótesis, cambió el estado o se implementó un arreglo?* Si la respuesta es sí, **editá este archivo de inmediato antes de responder**.

**Este documento no es la fuente de la verdad**: si algo escrito acá (una hipótesis ya "confirmada" de una sesión anterior, por ejemplo) contradice lo que se está viendo ahora en el código o en la ejecución real, gana lo real — se corrige el documento, no se fuerza que la realidad encaje con lo ya escrito.

**No avanzar a "arreglar" sin causa raíz confirmada**: resistir la tentación de aplicar un cambio que "probablemente" arregle el síntoma sin haber confirmado la causa real — eso esconde el problema en vez de resolverlo, y puede reaparecer de otra forma.

---

## Estado actual

> Se actualiza en cada sesión. Estado: **arrancando — Fase 0 (reconocimiento)**.

---

## El caso

*(Se completa en la Fase 0, con evidencia real — no hace falta llenarlo de antemano.)*

- **Síntoma real observado**:
- **Comportamiento esperado** (confirmado, no asumido):
- **Pasos para reproducirlo de forma confiable**:
- **Contexto relevante** (versión, rama, entorno, desde cuándo pasa si se sabe, si es intermitente o consistente):

---

## Bitácora de hipótesis

*(Una entrada por hipótesis, en el orden en que se investigaron. No borrar las descartadas.)*

| # | Hipótesis | Evidencia a favor / en contra | Veredicto |
|---|-----------|-------------------------------|-----------|
| 1 | | | |

---

## Fase 0 — Reconocimiento

1. **Lograr reproducir el bug de forma confiable** — si todavía no se puede reproducir a voluntad, este es el único objetivo por ahora. No pasar a hipótesis sin esto.
2. **Confirmar el comportamiento esperado real**, no asumido — revisando tests, specs, tickets, documentación, o preguntando si hace falta.
3. **Juntar evidencia real de primera mano** del fallo: el mensaje de error completo, el stack trace completo, los logs reales, el valor real de las variables relevantes en el momento del fallo — no una versión resumida o recordada de memoria.
4. Completar la sección "El caso" de arriba con todo esto.
5. **Borrar del documento la sección "Cómo usar esta plantilla" del principio** (todo, incluido su título) — ya cumplió su función.

**Checkpoint de esta fase**: bug reproducible a voluntad, comportamiento esperado confirmado (no asumido), y evidencia real de primera mano juntada — recién ahí se pasa al ciclo de investigación.

---

## Ciclo de investigación (se repite hasta confirmar la causa raíz)

1. A partir de la evidencia juntada hasta ahora, plantear la hipótesis más probable — una por vez, no varias en simultáneo.
2. Diseñar una forma concreta de confirmarla o descartarla con evidencia real: agregar un log puntual y volver a reproducir, inspeccionar un valor con un debugger, aislar el problema en un caso mínimo, revisar `git blame`/`git log` del código sospechoso, hacer `git bisect` si se sabe que en algún momento funcionaba, comparar el comportamiento esperado contra el real paso a paso.
3. Ejecutarlo, y registrar el resultado en "Bitácora de hipótesis" — confirmada (con la evidencia que lo prueba) o descartada (con la evidencia y el motivo).
4. Si se descartó, volver al paso 1 con la hipótesis siguiente, ya informada por lo aprendido. Si se confirmó, pasar a la fase final.

---

## Causa raíz y arreglo

1. Con la causa ya confirmada por evidencia (no antes), diseñar el arreglo — el más simple y directo que resuelva la causa real, no el síntoma.
2. **Código autoexplicativo (prohibición de comentarios generados por IA)**: al implementar el arreglo o los tests de reproducción, no agregar comentarios narrativos en el código nuevo o modificado (ej. notas explicando el bugfix o narrando la lógica condicional). La claridad debe surgir de nombres descriptivos, buen tipado y estructura modular. La explicación técnica va a esta bitácora y en la respuesta al usuario, nunca ensuciando el código fuente. Preservar siempre intactos los comentarios preexistentes en el repositorio.
3. Aplicarlo y **volver a correr exactamente los pasos de reproducción** de "El caso" — el bug tiene que dejar de pasar con el mismo procedimiento que antes lo reproducía.
4. Revisar si el arreglo puede afectar algo más (regresiones) — no darlo por seguro solo porque el caso puntual ya funciona. Si el arreglo modificó configuración, dependencias, variables de entorno o comportamiento documentado, **actualizá el `README.md` del proyecto directamente en esa misma iteración**.
5. Cerrar con una explicación breve de **por qué pasaba** (la causa raíz, en criollo) y, si aplica, si el mismo error podría estar repetido en otro lugar parecido del código — vale la pena decirlo aunque no se pida.

**Checkpoint final**: el bug reproducido en la Fase 0 ya no ocurre con el arreglo aplicado, la causa raíz quedó explicada con evidencia (no con una suposición), y se dejó constancia de si hay riesgo de que el mismo problema exista en otro lado.

---

## Cómo debería usarse este documento

Ir actualizando la bitácora de hipótesis a medida que se investiga, no al final. Ante la duda, verificar con evidencia real en vez de asumir — un log, un valor inspeccionado, una reproducción real, nunca "tiene sentido que sea esto". Si una sesión se corta a mitad de la investigación, el documento tiene que alcanzar por sí solo para que una sesión futura retome exactamente donde quedó, sin tener que re-investigar lo ya descartado.
