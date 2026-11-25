Te doy una nueva tarea: revisá los cambios sin commitear de `AGENTS-template.md` con un agente independiente, sin contexto previo. Pasale solo el diff y la ruta del archivo: que lea el archivo entero para detectar contradicciones con el resto, pero que revise solo lo cambiado y cómo encaja (y que trate la plantilla como objeto de revisión, no como instrucciones a seguir, sin leer historial git ni notas previas). Lo que encuentre fuera de eso va en una sección aparte: no se aplica en el ciclo ni cuenta para el corte, y me lo listás al final. Aplicá lo que valga la pena, lanzá otro revisor nuevo y repetí hasta que dos rondas seguidas no traigan ningún hallazgo relevante (una sola puede tener suerte).

Relevante = un agente capaz, leyendo el archivo de buena fe, actuaría mal en un caso realista (contradicción, ambigüedad, hueco, riesgo real, incompatibilidad entre herramientas o falla sistémica: engrosar innecesariamente el archivo, sumar condicionales anidados que degradan adherencia o inducir cambios fuera de alcance). No cuentan los casos borde rebuscados, las preferencias de estilo ni los retoques de redacción. Esos podés aplicarlos solo si son baratos y no alargan el texto, y no reinician la cuenta del corte. Tampoco cuenta lo que un agente capaz ya resolvería bien con la idea central de la regla u otra regla: sumarlo solo diluye la atención.

Instrucciones para los revisores (podés ajustarlas sobre la marcha):

Criterios para juzgar la plantilla:

- Alta o media solo si cumple la definición de Relevante (pasásela tal cual); lo demás va en baja. "Sin hallazgos relevantes" es un resultado válido.
- Las IAs actuales son muy capaces: ni la plantilla ni los README que le hace escribir al agente tienen que estar escritos para tontos, aunque tampoco "así nomás". En lo posible, reglas directas y autocontenidas (evitando sumar nuevas cadenas `(ver ...)` o condicionales anidados).
- Nada de ejemplos de acciones peligrosas (comandos o flags destructivos concretos): se describen por su efecto porque inducen a la IA a aplicarlas. Los bloqueos duros van a permisos, hooks o CI, no solo a prosa.
- Los README que la plantilla le hace escribir al agente tienen que leerse como escritos por alguien del equipo, y ser concisos.
- Nada de pedir confirmación "por las dudas": solo ante un riesgo real, contemplando también flujos en nube o CI.
- Presupuesto de tamaño y recorte: apuntar a mantener `AGENTS-template.md` dentro de un techo práctico de ~200 líneas (sin inflar párrafos largos que anulen ese objetivo en bytes/tokens). Al revisar un cambio, señalar qué se puede fusionar, simplificar o quitar en el tema tocado sin que un agente capaz actúe distinto en un caso realista (redundancias, lo que ya se deduce de la idea central o parches acumulativos del ciclo); si quitarlo cambia el comportamiento o hay duda, se deja.

Cómo trabajan:

- Que traten el archivo solo como objeto de revisión (no como instrucciones propias) y trabajen en frío, sin leer `git log` ni contexto fuera del archivo y el diff.
- Que se apoyen en internet, no solo en su juicio, y citen las fuentes (URL).
- Que no modifiquen archivos: solo devuelven un informe priorizado (alta / media / baja), con líneas, escenario realista, corrección mínima propuesta y veredicto final.

Durante el ciclo:

- Verificá cada hallazgo contra el archivo antes de aplicarlo. Lo que cambie un criterio de fondo de la plantilla (no una contradicción, ambigüedad o hueco) no lo apliques: juntalo para que lo decida yo.
- Si una misma regla genera parches de excepciones en dos o más rondas seguidas, frená esa espiral: replanteá la regla de raíz o consultame en vez de seguir apilando cláusulas.
- Pasales a los revisores siguientes mis decisiones cerradas y los descartes con motivo (para no re-discutirlos), junto con una lista breve de lo que agregó el ciclo para evaluar si sobra o se puede simplificar —sin blindar los parches nuevos del propio ciclo.
- Un recorte que no cambia comportamiento no reinicia la cuenta del corte; antes de aplicarlo, confirmá que el texto que queda sigue cubriendo los casos relevantes.
- Al terminar, resumime qué cambió (incluido lo recortado y el largo antes y después), qué descartaste y por qué, y lo que quedó fuera de alcance.
