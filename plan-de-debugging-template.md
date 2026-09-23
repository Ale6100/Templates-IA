# Plan de debugging — plantilla reutilizable

## Cómo usar esta plantilla (leer una sola vez, esto no es parte del plan en sí)

1. Copiá este archivo a la raíz del proyecto cuando te encuentres con un bug que no se resuelve mirándolo dos minutos — no hace falta para cualquier error trivial. Renombralo según el bug (por ejemplo `plan-de-debugging-<bug>.md`) para no pisar una bitácora anterior.
2. Contale a la IA el síntoma real que estás viendo y señalá este archivo.
3. La IA arranca por la Fase 0 (reconocimiento) y va llenando el resto del documento a medida que investiga.

Esta sección se borra sola al final de la Fase 0.

---

## Nota para la IA que guíe esta investigación

Este documento es una **bitácora viva** de una investigación en curso, no un reporte que se escribe al final. Se actualiza a medida que se descartan o confirman hipótesis.

**Regla de oro**: nunca declares una causa como confirmada sin haber visto la evidencia real que lo prueba (un log real, un valor real inspeccionado, un test que reproduce el fallo y deja de fallar con el arreglo). "Me parece que es esto" no es una conclusión, es una hipótesis — tratala como tal hasta que haya evidencia.

**Reproducir antes que teorizar**: antes de sospechar cualquier causa, lográ reproducir el bug de forma confiable (los mismos pasos, el mismo resultado, todas las veces). Si todavía no se puede, ese es el problema a resolver primero: no tiene sentido investigar causas de algo que no se puede observar a voluntad.

**Confirmar el comportamiento esperado, no asumirlo**: antes de dar algo por bug, confirmá qué debería pasar en realidad (specs, tests existentes, tickets, README). A veces el sistema funciona como se diseñó y el desajuste está en la expectativa, no en el código. Si no lo podés determinar con lo que hay, preguntáselo al programador.

**Regla de verificación obligatoria**: no asumas qué hace una función, un config, una librería o un endpoint solo por su nombre — abrí y leé la implementación real antes de sospechar o descartar algo por esa vía, bajando al código de librerías externas si hace falta.

**Esto también aplica a las versiones de las dependencias involucradas**: antes de sospechar o descartar una causa por cómo "debería" comportarse una librería o herramienta, confirmá qué versión está realmente instalada (manifiesto de dependencias, lockfile). El comportamiento real puede diferir de lo que asumís, sobre todo si esa versión es más nueva o más vieja que la que más conocés. Si hace falta, revisá el changelog de esa versión y buscá en internet si podés, en vez de asumir por conocimiento propio (que tiene fecha de corte).

**Regla contra la invención de causas**: no completes con suposiciones lo que no está confirmado con evidencia. Lo que no se pueda determinar queda anotado como hipótesis abierta, nunca como conclusión.

**Distinguir "bug en este código" de "comportamiento esperado de algo externo"** (una librería, el runtime, el sistema operativo, una API de terceros): antes de asumir que el bug está en el código propio, confirmá que no es el funcionamiento documentado (aunque sorprendente) de algo externo.

**No arreglar sin causa raíz confirmada**: no apliques un cambio que "probablemente" arregle el síntoma sin haber confirmado la causa real — eso esconde el problema en vez de resolverlo, y puede reaparecer de otra forma.

### Cómo trabajar con el programador

**Git: solo lectura salvo pedido explícito**: podés usar libremente `status`, `diff`, `log`, `show` y `blame`. Cualquier comando que modifique el repositorio o el working tree (`commit`, `add`, `checkout`, `stash`, `bisect`, `reset`, etc.) requiere que el programador lo pida o lo apruebe explícitamente. El arreglo se deja sin commitear.

**Cambios del programador entre pedidos**: desde el segundo pedido de la sesión en adelante, antes de seguir revisá si el programador modificó código por su cuenta desde tu respuesta anterior (si el proyecto usa git, con `git status`/`git diff`, descontando tus propios cambios). Un cambio suyo puede alterar la reproducción o invalidar evidencia ya juntada: tenelo en cuenta y anotá en la bitácora lo que sea relevante.

**Preferencias del programador**: si el programador pide un cambio en cómo trabajar (qué aprobar antes de tocar código, nivel de detalle de las explicaciones, qué comandos correr o no), anotalo de inmediato en "Preferencias del programador" de "El caso" y respetalo en el resto de la investigación, incluidas las sesiones futuras.

### Cómo mantener esta bitácora

**Ninguna hipótesis descartada se borra**: se tacha (`~~hipótesis~~`) anotando por qué se descartó y con qué evidencia, para que una sesión futura no vuelva a recorrer el mismo camino muerto. Fuera de eso, mantené la bitácora concisa: evidencia y conclusiones, no narraciones largas.

**Obligación proactiva de edición de esta bitácora**: en cuanto se recolecte evidencia, se confirme o descarte una hipótesis, o se avance de fase, **actualizá este archivo directamente en esa misma iteración, sin esperar a que el programador te lo pida ni pedirle confirmación previa**. No alcanza con mencionarlo en tu respuesta: tenés que editar el archivo.

**Checklist obligatorio de cierre de turno**: antes de dar por terminada tu respuesta, preguntate: *¿Se sumó evidencia, se confirmó/descartó una hipótesis, cambió el estado, se implementó un arreglo o el programador pidió un cambio en cómo trabajar?* Si la respuesta es sí, **editá este archivo de inmediato antes de responder**.

**Este documento no es la fuente de la verdad**: si algo escrito acá (por ejemplo, una hipótesis "confirmada" en una sesión anterior) contradice lo que se ve ahora en el código o en la ejecución real, gana lo real — se corrige el documento, no se fuerza la realidad para que encaje.

---

## Estado actual

> Se actualiza en cada sesión. Estado: **arrancando — Fase 0 (reconocimiento)**.

---

## El caso

*(Se completa en la Fase 0, con evidencia real.)*

- **Síntoma real observado**:
- **Comportamiento esperado** (confirmado, no asumido):
- **Pasos para reproducirlo de forma confiable**:
- **Contexto relevante** (versión, rama, entorno, desde cuándo pasa si se sabe, si es intermitente o consistente):
- **Preferencias del programador** (cómo quiere trabajar; se suman a medida que aparecen):

---

## Bitácora de hipótesis

*(Una entrada por hipótesis, en el orden en que se investigaron. No borrar las descartadas.)*

| # | Hipótesis | Evidencia a favor / en contra | Veredicto |
|---|-----------|-------------------------------|-----------|
| 1 | | | |

---

## Fase 0 — Reconocimiento

1. **Lográ reproducir el bug de forma confiable.** Sin esto no se pasa a hipótesis.
2. **Confirmá el comportamiento esperado real** revisando tests, specs, tickets o documentación, o preguntándole al programador.
3. **Juntá evidencia real de primera mano** del fallo: el mensaje de error completo, el stack trace completo, los logs reales, el valor real de las variables relevantes en el momento del fallo — no una versión resumida o recordada de memoria.
4. Completá la sección "El caso" con todo esto.
5. **Borrá la sección "Cómo usar esta plantilla" del principio** (incluido su título).

**Checkpoint de esta fase**: bug reproducible a voluntad, comportamiento esperado confirmado y evidencia de primera mano juntada — recién ahí se pasa al ciclo de investigación.

---

## Ciclo de investigación (se repite hasta confirmar la causa raíz)

1. A partir de la evidencia juntada, planteá la hipótesis más probable — una por vez, no varias en simultáneo.
2. Diseñá una forma concreta de confirmarla o descartarla con evidencia real: agregar un log puntual y volver a reproducir, inspeccionar un valor con un debugger, aislar el problema en un caso mínimo, revisar `git blame`/`git log` del código sospechoso, comparar paso a paso el comportamiento esperado contra el real. Si se sabe que en algún momento funcionaba, `git bisect` es muy útil, pero proponéselo al programador antes de correrlo.
3. Ejecutalo y registrá el resultado en la "Bitácora de hipótesis": confirmada (con la evidencia que lo prueba) o descartada (con la evidencia y el motivo).
4. Si se descartó, volvé al paso 1 con la hipótesis siguiente, ya informada por lo aprendido. Si se confirmó, pasá a la fase final.

---

## Causa raíz y arreglo

1. Con la causa ya confirmada por evidencia (no antes), diseñá el arreglo más simple y directo que resuelva la causa real, no el síntoma. Si requiere agregar o actualizar una dependencia, proponéselo al programador en vez de instalarla por tu cuenta.
2. **Consistencia con el proyecto**: el arreglo tiene que encajar naturalmente con el código que lo rodea (nombres, patrones, manejo de errores, librerías), salvo que ese código haga algo mal: en ese caso no lo imites, hacelo bien y señalá el problema.
3. **Código autoexplicativo**: en el arreglo y en los tests de reproducción no agregues comentarios que narren el bugfix o la lógica condicional. La claridad sale de nombres descriptivos, buen tipado y estructura modular; la explicación técnica va en esta bitácora y en tu respuesta al programador. Solo si el código realmente no puede explicarse solo (por ejemplo, un workaround de un bug externo), agregá un comentario breve con el *porqué*, en el formato estándar del proyecto si existe. No borres ni alteres los comentarios preexistentes.
4. Aplicalo y **volvé a correr exactamente los pasos de reproducción** de "El caso": el bug tiene que dejar de pasar con el mismo procedimiento que antes lo reproducía.
5. Revisá si el arreglo puede afectar algo más (regresiones) — no lo des por seguro solo porque el caso puntual ya funciona. Si modificó configuración, dependencias, variables de entorno o comportamiento documentado, **actualizá el `README.md` del proyecto en esa misma iteración**.
6. Cerrá con una explicación breve de **por qué pasaba** (la causa raíz, en criollo) y, si aplica, si el mismo error podría estar repetido en otro lugar parecido del código — decilo aunque no se pida.
7. Preguntale al programador si quiere conservar esta bitácora o borrarla, para que no quede olvidada en el proyecto.

**Checkpoint final**: el bug reproducido en la Fase 0 ya no ocurre con el arreglo aplicado, la causa raíz quedó explicada con evidencia, y quedó constancia de si el mismo problema podría existir en otro lado.

---

## Cómo debería usarse este documento

Si una sesión se corta a mitad de la investigación, el documento tiene que alcanzar por sí solo para que una sesión futura retome exactamente donde quedó, sin re-investigar lo ya descartado.
