Te doy una nueva tarea: revisá los cambios sin commitear de `AGENTS-template.md` con un agente independiente, sin contexto previo. Pasale el diff y la ruta del archivo: que lea el archivo entero para detectar contradicciones con el resto, pero que revise solo lo cambiado y cómo encaja. Lo que encuentre fuera de eso va en una sección aparte: no se aplica en el ciclo ni cuenta para el corte, y me lo listás al final. Aplicá lo que valga la pena, lanzá otro revisor nuevo y repetí hasta que dos rondas seguidas no traigan ningún hallazgo relevante (una sola puede tener suerte).

Relevante = un agente capaz, leyendo el archivo de buena fe, actuaría mal en un caso realista (contradicción, ambigüedad, hueco o riesgo). No cuentan los casos borde rebuscados, las preferencias de estilo ni los retoques de redacción. Esos podés aplicarlos si son baratos y no alargan el texto, pero no reinician la cuenta del corte. Tampoco cuenta lo que un agente capaz ya resolvería bien con lo que dice el archivo (la idea central de la regla u otra regla): sumarlo solo alarga el texto.

Instrucciones para los revisores (podés ajustarlas sobre la marcha):

Criterios para juzgar la plantilla:

- Alta o media solo si cumple la definición de Relevante (pasásela tal cual); lo demás va en baja. "Sin hallazgos relevantes" es un resultado válido.
- Las IAs actuales son muy capaces: ni la plantilla ni los README que le hace escribir al agente tienen que estar escritos para tontos, aunque tampoco "así nomás".
- Nada de ejemplos de acciones peligrosas (comandos o flags destructivos concretos): inducen a la IA a aplicarlas.
- Los README que la plantilla le hace escribir al agente tienen que leerse como escritos por alguien del equipo, y ser concisos.
- Nada de pedir confirmación "por las dudas": solo ante un riesgo real.
- Recorte, solo sobre el tema de los cambios y con cautela: que señalen lo que se podría quitar o fusionar sin que un agente capaz actúe distinto en un caso realista (lo redundante con otra regla, lo que se deduce solo de la idea central, casos que el propio ciclo agregó de más). Si quitarlo cambia el comportamiento en algún caso realista, o hay duda, se deja. No se recorta para compensar lo agregado ni para llegar a una cantidad de líneas.

Cómo trabajan:

- Que se apoyen en internet, no solo en su juicio, y citen las fuentes (URL).
- Que no modifiquen archivos: solo devuelven un informe priorizado (alta / media / baja), con líneas, corrección propuesta y veredicto final.

Durante el ciclo:

- Verificá cada hallazgo contra el archivo antes de aplicarlo. Lo que cambie un criterio de fondo de la plantilla (no una contradicción, ambigüedad o hueco) no lo apliques: juntalo para que lo decida yo.
- Pasales a los revisores siguientes, como decisiones tomadas que no se discuten, las sugerencias que descartes con motivo, los recortes aplicados y lo que yo decida, junto con una lista breve de lo que agregó el ciclo, para que puedan evaluar si sobra.
- Un recorte aplicado no reinicia la cuenta del corte; antes de aplicarlo, confirmá que el texto que queda sigue cubriendo los casos relevantes.
- Al terminar, resumime qué cambió (incluido lo recortado), qué descartaste y por qué, y lo que quedó fuera de alcance.
