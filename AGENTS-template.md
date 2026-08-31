# AGENTS.md

Instrucciones para agentes de IA que trabajen en este proyecto. Cumple dos funciones: mantener la documentación (`README.md`) siempre al día, y guiar el desarrollo con buenas prácticas — no solo ejecutar lo que se pide, sino asesorar como lo haría alguien senior del equipo.

---

## Documentación del proyecto (README.md y este archivo)

El **README.md es la documentación única** del proyecto: sirve tanto para humanos como para agentes de IA. Explica qué es el proyecto, cómo está armado y cómo desarrollarlo.

- Al empezar una tarea, leé el README para entender el contexto del proyecto antes de tocar código.
- El README debe estar **muy bien detallado**: cuanto más completo y preciso, mejor fuente de contexto será (aunque el código siempre manda sobre él).
- Cuando un cambio afecte cualquier cosa que documente el README (instalación, scripts, variables de entorno, arquitectura, endpoints, estructura de carpetas, decisiones de diseño, etc.), actualizá el README en la misma iteración, sin que se pida explícitamente.
- No agregues al README nada que no puedas verificar en el código.
- El README puede incluir detalles internos del desarrollo sin censurarlos. La única excepción: secretos reales (claves de API, tokens, contraseñas), que nunca se incluyen.
- Evitá afirmaciones perecederas ("en breve", "por ahora", "actualmente") tanto en este archivo como en el README: quedan viejas y dependen de que alguien se acuerde de actualizarlas. Escribí solo lo que siga siendo cierto con el tiempo.
- **Este mismo archivo (`AGENTS.md`) también se mantiene al día**, no solo el README: si durante el trabajo notás que una convención cambió de forma duradera (no una excepción puntual de una sola tarea), actualizalo vos mismo o avisá explícitamente que conviene actualizarlo. Al hacerlo, integrá la regla nueva en la sección temática que corresponda — no la cuelgues suelta al final del archivo, porque así termina siendo una lista desordenada en vez de una guía clara.

## Regla de verificación obligatoria

No des nada por hecho por cómo se ve o se llama algo (una función, una variable, un archivo, un endpoint, un flag de config). Entrá al código, leé la implementación real, y contrastá qué hace de verdad antes de confiar en ello, documentarlo, o explicárselo al usuario.

Ejemplo ilustrativo (no es necesariamente real en este repo): si existe una función `sendNotification()` o un flag `isProduction`, no asumas que la primera manda una notificación de verdad ni que el segundo refleja el ambiente real solo por el nombre — leé el cuerpo y confirmá que hacen lo que dicen (y no, por ejemplo, que solo loguean, que están sin terminar, o que el flag está hardcodeado en `true`).

La fuente de la verdad es **siempre el código**. El README (y este mismo archivo) son solo una vista de él y pueden estar desactualizados: verificá cada dato contra el código antes de confiar en él. Si el README contradice al código, manda el código y corregí el README en la misma iteración para que vuelva a reflejarlo.

## Regla contra la invención de datos

No completes con suposiciones lo que no esté respaldado por el código o por una inferencia razonable y explícita a partir de él. Si no podés determinar algo leyendo el código (por ejemplo, *por qué* se tomó una decisión de diseño puntual, o una regla de negocio que solo vive en la cabeza de alguien del equipo), decilo explícitamente como una zona gris o un supuesto a confirmar — nunca lo presentes como un hecho, ni en el README, ni explicándoselo al usuario.

## Perfil del desarrollador: asesorar, no solo ejecutar

El proyecto lo construye un equipo con experiencia variable según el dominio. Las tareas se hacen en contexto real de producción, lo que exige calidad desde el inicio. Por eso:

- Al introducir un concepto nuevo o tomar una decisión con peso de arquitectura, explicar brevemente el **porqué**: qué problema resuelve, qué patrón clásico de la industria aplica (no reinventar la rueda).
- **Distinguir explícitamente si algo es una decisión propia de este equipo/proyecto, o si viene impuesta desde afuera** (una librería, un framework, un protocolo o estándar, una convención del lenguaje). Evita que el desarrollador piense que todo lo que ve es una elección arbitraria del equipo cuando en realidad viene de afuera, o viceversa.
- Anticipar riesgos típicos de producción en lo que se implemente y avisarlos explícitamente si algo se puede hacer mal sin darse cuenta: seguridad (autenticación, autorización, validación de inputs, secrets), integridad de datos (FKs, constraints, transaccionalidad), costos (servicios con facturación por uso, ancho de banda, almacenamiento) y deuda técnica (acumulación de atajos que complican el futuro).
- Si una decisión actual va a complicar el futuro (modelado flojo, acoplamiento innecesario, dependencias pesadas, etc.), señalarlo en el momento, aunque nadie lo pregunte, y ofrecer la alternativa correcta concretamente.
- No dar nada por sabido: los conceptos del dominio pueden necesitar explicación la primera vez que aparezcan.
- Preferir siempre el camino canónico y simple por encima de soluciones exóticas o prematuramente escaladas.

## Requisitos transversales del proyecto (ejemplo — reemplazar por los reales)

Esta sección es un ejemplo de cómo documentar un requisito no funcional que atraviesa todo el proyecto y que es fácil de olvidar tarea por tarea — no una regla universal. Reemplazala por lo que corresponda al proyecto real (accesibilidad, internacionalización, límites de performance, compatibilidad de navegadores, requisitos de seguridad/compliance, soporte offline, etc.), o quitala si no aplica ninguna.

**Ejemplo — Diseño responsive**: la interfaz de usuario debe verse y funcionar bien en cualquier dispositivo. Esto no es un extra opcional, es requisito.

- Pensar siempre en múltiples tamaños de pantalla al escribir markup.
- Usar las herramientas de detección de plataforma que el proyecto provea en vez de reinventarlas.
- Seguir los patrones existentes en el proyecto para layouts adaptativos.
