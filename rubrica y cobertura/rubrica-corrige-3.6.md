# CORRIGE — Rúbrica de evaluación (versión 3.6)

Se aplica si agregás «y evaluá con la rúbrica». Reemplaza la versión 3.5. Los casos entre paréntesis y en cursiva vienen de la auditoría de *El dispositivo caldereño* y explican cada cambio: los de la 3.5 salían de nueve rondas; los de la 3.6, de treinta y cuatro.

## Qué se evalúa

Se dan **dos notas**:

- **Nota inicial:** el libro tal como llegó, con todos los hallazgos de la auditoría a la vista.
- **Nota final:** el libro después de la fase 6, con las correcciones aplicadas. Se puntúan igual que en la nota inicial:
  - las verificaciones en fuente que sigan abiertas al cerrar la fase 6;
  - los hallazgos confirmados que no se aplicaron.

La diferencia entre las dos mide cuánto mejoró el libro con la auditoría. Si no hubo fase 6, se da sólo la inicial.

**Las dos notas se informan dos veces: antes del tope y después del tope.** La nota topeada es la que vale; la nota sin topear es la que permite ver si el libro se mueve mientras el tope no se levanta.

La rúbrica evalúa **el libro**, no la auditoría. La calidad de la auditoría se informa aparte, en **cinco** datos:

1. **cobertura** —qué proporción de las líneas se leyó en esta ronda, y el registro que lo prueba—;
2. **[v3.6] cobertura acumulada** —la suma de las rondas anteriores, con su registro—;
3. **falsos positivos** descartados;
4. **recortes** —lo que la auditoría no pudo hacer y por qué—;
5. **errores introducidos por la propia auditoría**: cuántos de los hallazgos de esta ronda están en material que la auditoría misma incorporó, en qué ronda lo incorporó, y **[v3.6] cuántos fueron atrapados por un control automático antes de llegar al libro**.

La única excepción a «la rúbrica evalúa el libro» es el tope de cobertura, que no mide el libro sino cuánto se puede confiar en la nota.

---

## **[v3.6] Tipo de ronda**

Una ronda es de uno de estos tres tipos, y **se declara al abrir la salida**:

| Tipo | Qué hace | Cómo se puntúa |
|---|---|---|
| **Auditoría** | Lee el manuscrito buscando defectos | Nota completa, inicial y final |
| **Incorporación** | Integra material nuevo al libro | **Sólo nota final**, y sin tope de cobertura |
| **Mixta** | Incorpora y además audita | Nota completa; la cobertura cuenta sólo lo auditado |

*(Caso: de treinta y cuatro rondas, veintiuna fueron de incorporación pura. Puntuarlas con la escala de auditoría mide otra cosa —el libro crece y la nota no se mueve— y por eso la serie de notas tiene huecos y mesetas que no significan nada.)*

**En una ronda de incorporación, el aspecto 7 no se calcula** —no hay páginas auditadas— y los hallazgos que la propia incorporación genera y corrige dentro de la misma ronda no restan (ver §«Hallazgos atrapados»).

---

## Escala común

Cada aspecto se puntúa de 0 a 100 con estas anclas.

| Nota | Significado general |
|---|---|
| 100 | Sin observaciones después de una auditoría completa. |
| 90 | Observaciones menores y aisladas, sin efecto en lo que el libro afirma. |
| 70 | Observaciones repetidas o una que afecta una sección. |
| 50 | Problemas que afectan un capítulo o una afirmación central. |
| 30 | Problemas generalizados; el aspecto no es confiable. |
| 0 | El aspecto no se cumple. |

**Relación entre la escala y los criterios.** Cada aspecto agrega, cuando hace falta, un criterio medible. El criterio puntúa lo que cubre; la escala general puntúa lo que el criterio no cubre. **La nota del aspecto es la más baja de las dos.**

**Cómo se aplican los criterios medibles:**
- **Criterios con anclas:** entre dos anclas, se interpola. Los umbrales con «≤» o «o menos» son escalones: no se interpola.
- **Criterios que restan:** se parte de 100 y la nota no baja de 0.
- **Aspectos con los dos tipos de criterio:** vale la nota más baja.
- **Criterios por muestra** (aspectos 1 y 9, y el 4 cuando el cotejo es parcial) **y criterios de juicio** (aspectos 10 y 11): llegan como máximo a 90.
- **Cuánto de la distancia a 100 es estructural.** Los aspectos con tope de muestra o de juicio suman 31 puntos de peso y no pueden pasar de 90 mientras la auditoría no sea completa. La salida informa, en una línea, cuántos puntos están retenidos por ese techo y cuántos por hallazgos corregibles.

**Alcance de un hallazgo.** Un dato sostiene una frase, una sección, un capítulo o una tesis cuando, sin él, esa unidad no se mantiene. Se toma el alcance mayor. Los aspectos 2, 5 y 7 y los topes usan estos mismos cuatro niveles.

**Un hallazgo, un aspecto.** Cada hallazgo resta en un solo aspecto, el más específico. Dos excepciones: los topes, que se aplican además, y el aspecto 14, que mide el efecto del hallazgo sobre las propuestas.

**Redondeo y orden de cálculo.** Las notas por aspecto se dan en enteros; la nota global se pondera y se informa con un decimal. Los topes se aplican después de ponderar, y por separado a la nota inicial y a la final.

---

## **[v3.6] Hallazgos atrapados antes de llegar al libro**

**Un desfase que un control automático detecta y que se corrige antes de compilar no es un defecto del libro y no resta.** Se cuenta e informa en la calidad de la auditoría, en su propia línea, y ahí es una buena noticia y no una mala.

**Qué cuenta como atrapado**, y las tres condiciones son necesarias:
1. Lo detectó un **control que corre solo** —un script, un hook—, no la lectura.
2. Se corrigió **en la misma ronda**, antes de la compilación que se entrega.
3. La versión entregada del libro **no lo contiene**.

*(Caso: el recuento de pedidos del capítulo prospectivo y la partición del apéndice de dominio se desfasaban en cada incorporación. Desde que `control_recuentos.py` corre como último paso, nueve de esos desfases se corrigieron antes de compilar. Contarlos como defectos castiga justamente el procedimiento que funciona.)*

---

## Aspectos

| # | Aspecto | Peso | Qué se mide | Criterio medible |
|---|---|---|---|---|
| 1 | **Rigor documental** | 11 | Cada afirmación tiene una fuente identificable: número, fecha, boletín o expediente, y página. | Proporción de afirmaciones de hecho con fuente localizable, en una muestra de 50 al azar: 100 % → 90; 95 % → 70; 85 % → 50; 75 % o menos → 30. |
| 2 | **Vigencia normativa** | 8 | Toda norma citada en presente está vigente a la fecha del libro. Las derogadas van en pasado, con la norma que las reemplazó. | Una norma derogada citada en presente, en una frase → 85; sosteniendo una sección → 70; un capítulo o una tesis → 50. Desde la sección rige, además, el tope que corresponda. La nota es la del caso más grave; cada caso adicional resta 5. |
| 3 | **Versión, fecha y origen del dato** | 6 | Se distinguen sanción, promulgación y publicación, y texto original de consolidado. Toda cifra, intervalo o recuento que provenga de un informe de barrido se rehace sobre el documento antes de publicarlo. | Cada fecha, cifra o intervalo tomado de segunda mano sin declararlo resta 5. Cada fecha de sanción o promulgación dada como fecha de publicación, o texto consolidado citado como original, resta 5. Cada intervalo o resta importado de un informe y no recalculado resta 5, aunque resulte correcto. |
| 4 | **Fidelidad de transcripción** | 7 | Las citas coinciden con el facsímil; las erratas del original se transcriben tal cual. | Cotejo de al menos 10 citas contra la imagen. Cada corrección silenciosa resta 3; cada cita que cambia el sentido, 15. Con cotejo parcial el aspecto llega como máximo a 90. |
| 5 | **Honestidad epistémica y cobertura** | 12 | Se separan dato, inferencia y conjetura. Cada ausencia declarada cae dentro de un período o repositorio leído completo y se vuelve a buscar antes de cerrar. Y cada afirmación de máximo, de unicidad o de primacía declara sobre qué universo se hace. | Ver la ampliación de abajo. |
| 6 | **Tipo y jerarquía de fuente** | 5 | Se distingue documento primario, documento que cita a otro, expediente judicial, expediente administrativo y prensa. Un hecho que sólo consta en la prensa se marca así. Si dos fuentes discrepan, se dice. | Cada hecho sostenido sólo por la prensa sin marcarlo resta 5; cada discrepancia entre fuentes no señalada, 5. |
| 7 | **Consistencia interna** | 9 | Contradicciones entre pasajes, cifras que no cierran, recuentos del contenido que no coinciden. Los recuentos del aparato van al aspecto 8. | Hallazgos de tipo «Error» de consistencia por cada 100 páginas **efectivamente auditadas en esa ronda**, en escalones: 0 → 100; ≤ 0,5 → 90; ≤ 1 → 80; ≤ 2 → 70; ≤ 4 → 50; ≤ 8 → 40; > 8 → 30. Una contradicción que sostiene un capítulo o una tesis limita el aspecto a 50. Una contradicción con material que el propio libro expone a menos de diez páginas de distancia resta un escalón adicional. **No se calcula en rondas de incorporación.** |
| 8 | **Integridad del aparato** | 8 | Cada `\pendiente{}` tiene su pedido; los recuentos del aparato coinciden en todas sus menciones; no hay pedidos duplicados ante un mismo destinatario; los apéndices tienen `\label`. **[v3.6]** Y ningún pedido satisfecho sigue en la lista. | Todo verificable por script. Cada falta resta 5. Los recuentos se comprueban sobre la estructura que los produce —filas de la tabla, `\item` del apéndice, entradas del `.lof`— y no sobre lo que el texto dice de ellos. **[v3.6]** Cada pedido cuyo objeto el libro ya incorporó resta 5. |
| 9 | **Trazabilidad** | 6 | Cada dato tomado de la web o de un documento aportado tiene URL o repositorio, fecha de consulta y página. | Muestra de 20 datos: 20 trazables → 90; 18 → 70; 15 → 50; 10 o menos → 30. |
| 10 | **Argumentación** | 9 | Cuánto sostiene la evidencia a las tesis, y si las tesis sobreviven a los documentos nuevos. | Para cada tesis que el libro declara: ¿tiene evidencia primaria?, ¿declara qué la refutaría?, ¿sobrevivió a las verificaciones? Tres sí → 90; dos → 70; uno → 50; ninguno → 30. Se promedia entre tesis. |
| 11 | **Aporte y originalidad** | 5 | Lo que el libro establece y no existía antes. | Series, cruces o bases inéditas y reproducibles → 90; inéditas pero sin datos o método que permitan reproducirlas → 70; síntesis de lo publicado → 50; sin aporte propio → 30. |
| 12 | **Estructura y prosa** | 2 | Orden de lectura, densidad y cautelas proporcionadas. | Cada remisión a un capítulo posterior sin marcar resta 5. |
| 13 | **Cartografía y figuras** | 3 | Legibilidad y coherencia de estilo. Cada figura propia lleva fuente; cada mapa propio, además, escala y norte. Cada captura web lleva fecha de consulta. Cada facsímil lleva procedencia. | Ver la ampliación de abajo. |
| 14 | **Utilidad pública** | 4 | Propuestas concretas y priorizadas, con responsable y con base en la ley vigente. | Cada propuesta que invoca una norma derogada resta 10. |
| 15 | **Riesgo legal, ético y de privacidad** | 5 | Personas privadas nombradas, imputaciones, datos personales tomados de las fuentes, inferencias sobre atributos sensibles. | Ver la gradación de abajo. |

Los pesos suman 100 y no cambian respecto de la versión 3.

---

### Aspecto 5 · ampliación

Cada ausencia falsa en una frase resta 5; sosteniendo una sección, 10; un capítulo o una tesis, 20. Desde la sección rige, además, el tope que corresponda. Cada texto desactualizado (algo obtenido que se sigue dando por faltante) resta 3.

**Cada superlativo afirmado sobre un universo que el libro no midió entero resta 5, o 10 si el propio libro contiene el dato que lo desmiente.**

#### **[v3.6] Los superlativos se repasan cada vez que se cierra una ventana temporal**

Un superlativo correcto al escribirse se vuelve falso cuando el corpus crece. **No es un descuido: es el efecto previsible de incorporar material, y por eso se controla por procedimiento y no por sospecha.**

**Regla.** Al cerrar una ventana temporal —el último año de un tramo, el último expediente de una serie— se repasan **todas** las afirmaciones de unicidad, primacía, máximo y ausencia del libro que se refieran a esa ventana, y se comprueba que sigan siendo ciertas sobre el corpus ampliado. El repaso es barato y se hace por script: las formas a buscar son *el único*, *la única*, *el primero*, *la primera*, *el más antiguo*, *nunca*, *jamás*, *ninguno del departamento*.

**Cómo se puntúa.** Un superlativo que el material incorporado en esa misma ronda desmiente y que se corrige antes de entregar **no resta** (ver «Hallazgos atrapados»). Un superlativo que sobrevive al cierre de la ventana y se encuentra en una ronda posterior resta como cualquier ausencia falsa, por su alcance.

*(Casos: «la única vez, en dieciséis años de archivo leído, en que el departamento aparece por un acto propio» era cierto en 1924 y dejó de serlo cuando entraron 1927, 1942, 1943, 1945 y 1946. «De los más de treinta relevos que este capítulo registra» quedó corto cuando la serie llegó a setenta y cuatro. Los dos se detectaron en la ronda 34, sobre material incorporado en las rondas 21 a 33.)*

**Y la corrección de un superlativo es una oportunidad, no sólo una reparación.** En el primer caso, cambiar «la única vez» por «la primera vez» permitió decir algo que el libro no tenía: que lo excepcional en 1924 era rutina en los años cuarenta, y que esa transición es ella misma un dato.

---

### Aspecto 13 · ampliación

Se audita en la fase 2 (punto 15). **El inventario incluye las imágenes que no aparecen en el índice de láminas: portada, cubierta, portadillas y cualquier figura sin `\caption`.**

Cada figura sin procedencia o sin fuente resta 10; cada mapa propio sin escala, 5; cada mapa propio sin norte, 5; cada captura web sin fecha de consulta, 5.

#### **[v3.6] Tres estados para el script de una figura propia, no dos**

| Estado | Qué significa | Resta |
|---|---|---|
| **Con script publicado** | El epígrafe nombra el script y el script está en el repositorio público | 0 |
| **Con script no publicado** | La figura es reproducible por quien la hizo, pero el script no está publicado, **y el libro lo declara** | 2 |
| **Sin script** | La figura no indica con qué se produjo, o indica uno que no existe | 5 |

*(Caso: cinco láminas propias llevaron doce rondas restando 5 cada una, cuando su situación real era la del estado intermedio: los datos están declarados y son verificables, y lo que falta es subir el script. Y el caso inverso también apareció: el apéndice afirmaba que dos láminas se dibujaban con un script que no existía, que es el estado «sin script» disfrazado del primero.)*

**Lo que no vale en ninguno de los tres es callarlo.** Una figura cuyo estado el libro no declara se puntúa como «sin script».

---

### Gradación del aspecto 15

**Atributos sensibles:** salud, condición migratoria, etnia u orientación.

**Contexto sensible:** cualquiera de los atributos sensibles, más situación socioeconómica o imputación de conducta.

**Identificable.** Se distinguen dos grados:

- **Identificación directa:** el libro nombra a la persona, o da un dato que lleva a una persona determinada sin salir del libro: número de partida, matrícula o expediente, domicilio, parentesco con alguien nombrado.
- **Identificación indirecta:** llegar a la persona exige leer la fuente que el libro cita, porque el libro describe una clase de la que ella es el único caso.

**No** hay identificación de ningún grado por el solo hecho de figurar en una fuente pública citada.

**Pasaje.** La unidad que el lector lee de corrido: una sección o subsección, o un cuadro o ficha con sus comentarios.

**Excepción: descripción del origen de apellidos en registros históricos.** No resta ni activa tope describir el origen lingüístico o geográfico de un conjunto de apellidos que figura en un registro histórico, siempre que se cumplan las tres condiciones:

1. **Todas las personas nombradas en el pasaje se presumen fallecidas** según la regla de los 100 años.
2. **La descripción recae sobre los apellidos, no sobre las personas.**
3. **Ninguna persona que pueda estar viva es identificable de manera directa en el mismo pasaje.**

#### **[v3.6] Hechos de violencia tomados de un acto administrativo**

Cuando un acto publicado consigna un hecho de violencia atribuido a una persona nombrada —un expediente de pensión que dice cómo murió el causante y quién disparó—, el libro puede transcribirlo **si y sólo si** cumple las cuatro condiciones:

1. La persona a quien el acto atribuye la conducta **se presume fallecida** por la regla de los 100 años.
2. El libro **atribuye la afirmación al acto** y no la hace propia.
3. El libro **declara que no consta el resultado judicial**, si no consta.
4. El libro **no infiere nada** del apellido ni lo conecta con otras apariciones de ese apellido como si fuera la misma persona.

Si falta cualquiera de las cuatro, resta 20 como imputación de conducta a particular sin cautela.

*(Caso: el expediente de pensión de 1941 consigna que un agente de policía murió «de resultas de un tiro de revólver que le descerrajara» una persona nombrada. Es la primera muerte violenta del archivo temprano y llega por vía administrativa; el libro la transcribe cumpliendo las cuatro y pidiendo la causa penal, que es lo único que permitiría decir más.)*

| Situación | Efecto |
|---|---|
| Dato o inferencia de un **atributo sensible** sobre **personas que pueden estar vivas e identificables**, en cualquiera de los dos grados | Tope 60; el aspecto queda en 30 o menos. |
| **Menores de edad** (a la fecha del registro) **que pueden estar vivos**, identificables **de manera directa**, en un **contexto sensible** | Tope 60; el aspecto queda en 30 o menos. |
| Los mismos menores, identificables **de manera indirecta**, en un contexto **sólo socioeconómico** | Sin tope; resta 20, o 10 si el libro declara el criterio por el cual no los nombra. |
| Inferencia de atributos sensibles, aunque sea agregada, sobre **adultos que se presumen fallecidos**, **salvo la excepción de los registros históricos** | Sin tope; el aspecto queda en 70 o menos. |
| Datos que permiten identificar a personas que pueden estar vivas en un contexto socioeconómico | Resta 10 si la identificación exige cruzar la fuente citada u otra; 20 si el libro las nombra. |
| Imputación de conducta a particulares sin cautela ni derecho a réplica | Resta 20 por caso. |

**Quién puede estar vivo.** Toda persona nombrada o identificable se presume viva mientras no conste su muerte o no hayan pasado 100 años desde su nacimiento. La cuenta es por años calendario. Si no se conoce la edad, se toma la menor compatible con el registro: un menor sin edad declarada, como nacido el año del registro; un adulto, como nacido 18 años antes. En 2026 esto deja como presumiblemente fallecidos a los adultos de registros de 1944 o anteriores, y a los menores de registros de 1926 o anteriores.

---

## Topes de la nota global

Se aplica sólo el más restrictivo; no se acumulan.

| Tope | Condición |
|---|---|
| 60 | Dato o inferencia de un atributo sensible sobre personas que pueden estar vivas e identificables; o menores que pueden estar vivos, identificables de manera directa, en un contexto sensible. |
| 70 | Una ausencia falsa o un error de vigencia sostiene una tesis. |
| 75 | Una ausencia falsa o un error de vigencia sostiene un capítulo. |
| 80 | **[v3.6]** La cobertura acumulada demostrada es **el 25 % o menos** de las líneas. |
| 85 | Una ausencia falsa o un error de vigencia sostiene una sección; **[v3.6]** o la cobertura acumulada demostrada está **entre el 25 % y el 60 %**. |
| 90 | **[v3.6]** La cobertura acumulada demostrada está **entre el 60 % y el 99 %**. |

### **[v3.6] Cobertura acumulada**

El tope de cobertura pasa a mirar **la suma de las rondas**, no la ronda sola.

**Qué se acumula.** Las líneas del manuscrito leídas en cualquier ronda anterior, **con su registro por archivo y por tramo**. Una línea leída dos veces se cuenta una vez.

**Qué la invalida.** Una línea cuyo archivo cambió sustancialmente después de leerse vuelve a contar como no leída. En la práctica: **al reescribir un capítulo, su cobertura anterior caduca**.

**Qué exige.** El registro acumulado se mantiene en un archivo, no en la memoria de la conversación, y se informa entero en la salida —archivo por archivo, con el tramo de líneas y la ronda—. **Sin ese archivo, la cobertura acumulada es cero** por más que se haya leído.

*(Caso: el tope quedó clavado en 80 durante treinta y cuatro rondas. La cobertura de cada ronda por separado nunca pasó del 17 %, pero entre todas se leyó cerca de un tercio del manuscrito. Tal como estaba escrito, el tope **no se podía levantar nunca**: pedía en una sola ronda algo que sólo se consigue en varias. Y el escalón de 90 se agrega porque entre el 60 % y el 100 % hay mucho trabajo y ninguna recompensa.)*

### **[v3.6] Todo control muestral declara su denominador**

Cuando un aspecto se verifica sobre una muestra y no sobre el universo, **el resultado y el denominador van en la misma frase**. No se escribe «el control cierra»: se escribe «cierra en las 24 hojas en que la capa resuelve la cabecera, sobre 746».

Vale para: cobertura, citas cotejadas contra facsímil, muestras de los aspectos 1 y 9, recuentos verificados por script sobre parte del corpus, y cualquier comprobación que no alcance al total.

**Un control sin denominador se puntúa como no realizado.**

---

## Control de figuras en la fase 2

**15. Figuras.** Por cada lámina y figura, **incluidas las que no aparecen en el índice de láminas —portada, cubierta, portadillas y cualquier figura sin `\caption`—**, anotar:
- si tiene procedencia o fuente;
- si tiene fecha (del documento o de la consulta);
- si los mapas propios tienen escala y norte;
- **[v3.6]** en cuál de los tres estados está su script, y si el libro lo declara.

---

## Salida

1. **[v3.6] El tipo de ronda**, en la primera línea: auditoría, incorporación o mixta.
2. Una tabla con la nota por aspecto, **inicial y final**, con una o dos líneas de justificación. En una ronda de incorporación, sólo la final.
3. Las dos notas globales ponderadas, **cada una informada antes y después del tope**, con el tope aplicado y dicho, y una línea que separe cuántos puntos de la distancia a 100 son estructurales y cuántos son corregibles.
4. Las cinco acciones que más subirían la nota final, con la ganancia estimada de cada una en puntos de la nota global, contando el efecto de los topes.
5. El avance, con método:
   - **Avance del libro:** la proporción de hallazgos resueltos y el estado de compilación, por separado.
   - **Avance de la investigación:** las tesis, hipótesis y preguntas que el libro declara, cada una con 1 si quedó resuelta con documento, 0,5 si parcial y 0 si abierta. Se informa la lista, no sólo el porcentaje, y **cuántas cambiaron de estado en esta ronda y cuántas ganaron evidencia sin cambiarlo**.
6. **La calidad de la auditoría**, en los cinco datos del encabezado, con la cobertura acumulada y su registro.

---

## Cambios respecto de la versión 3.5

Todos salen de las treinta y cuatro rondas de auditoría e incorporación de *El dispositivo caldereño*.

**Lo que hacía imposible mejorar la nota:**

- **El tope de cobertura miraba la ronda y no la serie.** Treinta y cuatro rondas con la nota clavada en 80,0. Pasa a mirar la **cobertura acumulada**, con registro en archivo, y se agrega un escalón de 90 entre el 60 % y el 100 %.

**Lo que medía mal:**

- **Las rondas de incorporación se puntuaban como auditorías.** Veintiuna de treinta y cuatro no buscaban defectos: integraban material. Ahora se declara el tipo de ronda y se puntúan distinto.
- **Un desfase atrapado por un control automático contaba como defecto del libro.** Pasó nueve veces desde que el control corre solo. Ahora se cuenta aparte, y es una buena noticia.
- **El aspecto 13 tenía dos estados donde hay tres.** «Sin script» y «con script no publicado y declarado» no son lo mismo.

**Lo que faltaba controlar:**

- **Los superlativos, al cerrar una ventana temporal.** Es la falla más frecuente de todas y es previsible: el corpus crece y la afirmación de unicidad envejece. Ahora se repasan por procedimiento.
- **Los pedidos satisfechos que siguen en la lista.** Un pedido cumplido que no se retira es ruido, y el apéndice es lo que el libro le pide al Estado.
- **Los hechos de violencia tomados de un acto administrativo**, que la 3.5 no preveía y que aparecen en cuanto el archivo se lee entero.
- **El denominador de todo control muestral.**

**No cambian:** los pesos, la estructura de los aspectos, la regla de los 100 años, la excepción de los apellidos históricos, ni los topes 60, 70 y 75.

---

## Cambios de la versión 3.5 respecto de la 3.4

- Se controlan los **superlativos** además de las ausencias, con agravante cuando el libro se desmiente a sí mismo.
- El aspecto 3 se extiende a las **cifras de segunda mano**, no sólo a las fechas.
- El inventario de figuras incluye por definición **las que están fuera del `.lof`**.
- El denominador del aspecto 7 pasa a ser **páginas efectivamente auditadas en esa ronda**.
- El tope de cobertura se escalona en 80 y 85.
- Se informan **la nota antes del tope**, **cuánto de la distancia a 100 es estructural**, **cuántas preguntas cambiaron de estado** y **cuántos hallazgos los introdujo la propia auditoría**.
- Aspecto 7: contradicción con material propio a menos de diez páginas resta un escalón más.
- Aspecto 8: los recuentos se comprueban sobre la estructura que los produce.
- Aspecto 13: las figuras derivadas de un procesamiento propio indican dónde está su script.
