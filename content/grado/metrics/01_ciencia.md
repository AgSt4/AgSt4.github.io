---
title: "Método Científico en Economía"
date: 2026-03-15
draft: false
tags: ["econometría", "causalidad", "resultados potenciales", "sesgo de selección", "ceteris paribus", "EAE2510"]
description: "Estructura del dato en economía, causalidad vs. correlación, el modelo de resultados potenciales de Rubin-Neyman, sesgo de selección y el problema fundamental de la inferencia causal."
---

**Cursos:** Econometría (EAE2510) · Microeconometría Aplicada (EAE3101)  
**Referencia principal:** Wooldridge (2008) cap. 1 · Angrist & Pischke (2009) caps. 1–2 · Heckman (2008)

---

## 1. ¿Qué hace a la economía una ciencia empírica?

La economía aspira a responder preguntas causales sobre el mundo: ¿cuánto aumenta el ingreso con un año adicional de educación? ¿Reduce el salario mínimo el empleo? ¿Tiene la política monetaria efectos reales? La dificultad es que estas preguntas no pueden responderse con observación directa — requieren inferir relaciones causales a partir de datos que no provienen de experimentos controlados.

La econometría es la disciplina que desarrolla los métodos para hacer esa inferencia de forma rigurosa. Pero antes de aplicar cualquier técnica estadística, es necesario entender qué estamos preguntando cuando preguntamos por un efecto causal, qué datos necesitamos para responderla, y qué puede salir mal.

---

## 2. Estructura de los datos en economía

Los datos económicos se presentan en cuatro estructuras principales, cada una con sus particularidades para el análisis:

**Corte transversal (cross-section):** observaciones de múltiples unidades (individuos, firmas, países) en un único punto del tiempo. Ejemplo: encuesta de hogares de un año. No permite controlar por características no observadas que no varían en el tiempo.

**Serie de tiempo (time-series):** observaciones de una única unidad a lo largo del tiempo. Ejemplo: PIB trimestral de Chile. Permite estudiar dinámica y dependencia temporal, pero la identificación causal es difícil porque las variables económicas co-evolucionan.

**Datos de panel (panel data):** múltiples unidades observadas en múltiples períodos. Combina variación cross-section e intertemporal. Es la estructura más rica para identificación causal porque permite controlar por características no observadas que son constantes en el tiempo (efectos fijos).

**Datos de panel no balanceado:** no todas las unidades están presentes en todos los períodos — la situación más común en la práctica.

La estructura del dato no es neutral: las preguntas causales identificables dependen de qué variación existe en los datos. Un estimador de efectos fijos necesita variación intra-unidad en el tiempo; sin variación longitudinal, el parámetro de interés no está identificado con esa estrategia.

---

## 3. Correlación, causalidad y ceteris paribus

### 3.1 La distinción fundamental

La confusión más frecuente en el análisis empírico es tratar la correlación como evidencia de causalidad. La correlación entre $X$ e $Y$ puede surgir de tres fuentes completamente distintas:

1. $X$ causa $Y$ (la relación causal de interés).
2. $Y$ causa $X$ (causalidad inversa o endogeneidad).
3. Una tercera variable $Z$ causa tanto $X$ como $Y$ (variable omitida o confounding).

La frase "correlación no es causalidad" aplica aquí con toda su fuerza. El efecto de tratamiento mide el efecto de un cambio ceteris paribus en el status de tratamiento, mientras que las comparaciones intuitivas capturan tanto el efecto de ese cambio como el de otros cambios correlacionados que contaminan espuriamente la comparación. 

### 3.2 El concepto de ceteris paribus

El **ceteris paribus** ("todo lo demás igual") es la condición bajo la cual queremos medir el efecto causal de $X$ sobre $Y$: cuánto cambia $Y$ cuando variamos solo $X$, manteniendo todo lo demás constante. Produce un efecto causal ceteris paribus del argumento sobre el resultado. Cambiar una coordenada mientras se fijan las otras produce un efecto causal marshalliano ceteris paribus de un cambio en esa coordenada sobre las variables de resultado. 

El problema fundamental es que en los datos observacionales, cuando $X$ varía, generalmente también varían otras cosas correlacionadas con $X$. El reto metodológico de la econometría es construir comparaciones que se aproximen al ceteris paribus.

---

## 4. El modelo de resultados potenciales (Neyman-Rubin)

### 4.1 El marco conceptual

El modelo causal de Rubin está basado en la idea de resultados potenciales. Por ejemplo, una persona tendría un ingreso particular a los 40 años si hubiera asistido a la universidad, mientras que tendría un ingreso diferente si no hubiera asistido. Para medir el efecto causal de ir a la universidad para esta persona, necesitamos comparar el resultado para el mismo individuo en ambos futuros alternativos. 

Formalmente, para cada unidad $i$ y un tratamiento binario $D_i \in \{0, 1\}$:

- $Y_i(1)$: el resultado potencial de la unidad $i$ **si recibe tratamiento**.
- $Y_i(0)$: el resultado potencial de la unidad $i$ **si no recibe tratamiento**.

El **efecto causal individual** de $D$ sobre $Y$ para la unidad $i$ es:

$$\tau_i = Y_i(1) - Y_i(0)$$

La **ecuación de observación** (switching equation) relaciona los resultados observados con los potenciales:

$$Y_i = D_i Y_i(1) + (1-D_i)Y_i(0)$$

Solo observamos $Y_i(1)$ si $D_i = 1$, y solo $Y_i(0)$ si $D_i = 0$. El resultado que no se observa es el **contrafactual**.

### 4.2 El problema fundamental de la inferencia causal

Medir el efecto causal de ir a la universidad para esta persona requiere comparar el resultado para el mismo individuo en ambos futuros alternativos alternativos. Como es imposible ver ambos resultados potenciales al mismo tiempo, uno de los resultados potenciales siempre está faltando. Este dilema es el "problema fundamental de la inferencia causal". 

Nunca podemos observar $\tau_i = Y_i(1) - Y_i(0)$ directamente para ningún individuo — siempre falta uno de los dos resultados potenciales. Este no es un problema de tamaño muestral o poder estadístico: es un problema estructural de la causalidad.

La inferencia causal se hace posible no porque podamos observar efectos individuales, sino porque bajo ciertas condiciones podemos estimar **efectos promedio** que son parámetros de población bien definidos.

### 4.3 Los parámetros de interés

Los estimandos causales estándar son:

**Efecto promedio del tratamiento (ATE):**
$$ATE = E[\tau_i] = E[Y_i(1) - Y_i(0)]$$

El efecto promedio para un individuo elegido al azar de la población.

**Efecto promedio del tratamiento sobre los tratados (ATT):**
$$ATT = E[\tau_i | D_i = 1] = E[Y_i(1) - Y_i(0) | D_i = 1]$$

El efecto promedio para quienes efectivamente reciben el tratamiento. Es el parámetro relevante para evaluar un programa existente.

**Efecto promedio local del tratamiento (LATE):**
$$LATE = E[\tau_i | \text{complier}]$$

El efecto para el subgrupo de "compliers" — quienes cambian su tratamiento en respuesta a una variación exógena (instrumento). Es el parámetro identificado por variables instrumentales. El LATE, introducido por Imbens y Angrist (1994), es el efecto promedio para la subpoblación de compliers, es decir, aquellos que se verían afectados en su toma del tratamiento por el instrumento. 

La elección del estimando no es neutral: ATE, ATT y LATE responden preguntas distintas sobre poblaciones distintas. Un policy maker que quiere evaluar si escalar un programa debería interesarse en el ATE; uno que quiere evaluar el programa existente, en el ATT.

---

## 5. El sesgo de selección

### 5.1 La descomposición del sesgo

La diferencia simple en medias de resultados entre tratados y no tratados es:

$$E[Y_i | D_i = 1] - E[Y_i | D_i = 0]$$

¿Cuándo estima esto el ATT? Expandiendo usando la switching equation:

$$E[Y_i | D_i = 1] - E[Y_i | D_i = 0] = \underbrace{E[Y_i(1) - Y_i(0) | D_i = 1]}_{ATT} + \underbrace{E[Y_i(0) | D_i = 1] - E[Y_i(0) | D_i = 0]}_{\text{sesgo de selección}}$$

El sesgo de selección es la diferencia inherente entre los dos grupos si ambos hubieran recibido el tratamiento de control. Usualmente es una descripción de las diferencias entre los grupos si nunca hubiera habido tratamiento. El parámetro de interés ha sido enmascarado por el sesgo de selección y el sesgo de efectos de tratamiento heterogéneos. 

El **sesgo de selección** es $E[Y_i(0) | D_i = 1] - E[Y_i(0) | D_i = 0]$: la diferencia en resultados potenciales bajo control entre quienes se auto-seleccionan al tratamiento y quienes no. Si los que reciben educación universitaria habrían tenido ingresos mayores incluso sin ir a la universidad (por habilidad, familia, motivación), el sesgo de selección es positivo y la diferencia simple sobreestima el efecto causal de la educación.

### 5.2 Cuando la diferencia simple es válida: independencia

La diferencia simple en medias estima el ATT (y el ATE si los efectos son homogéneos) si y solo si:

$$Y_i(0), Y_i(1) \perp D_i$$

Es decir, la asignación al tratamiento es **independiente** de los resultados potenciales — quienes reciben tratamiento y quienes no son comparables en todas las dimensiones relevantes, observadas y no observadas. Esta condición se satisface **por diseño** en experimentos aleatorios: la aleatorización garantiza que $D_i$ es independiente de $(Y_i(0), Y_i(1))$.

En datos observacionales, la independencia no se puede asumir libremente — requiere justificación sustantiva y estrategia de identificación.

### 5.3 El supuesto de independencia condicional (CIA)

Una versión más débil frecuentemente invocada es la **independencia condicional** o **ignorabilidad**:

$$Y_i(0), Y_i(1) \perp D_i | X_i$$

Dado el vector de controles observados $X_i$, la asignación al tratamiento es independiente de los resultados potenciales. Este es el supuesto que justifica la estimación por regresión múltiple, propensity score matching y métodos relacionados. Su plausibilidad depende de que $X_i$ capture todos los factores de confusión relevantes — un supuesto no testeable directamente.

---

## 6. SUTVA: el supuesto de no-interferencia

El marco de resultados potenciales coloca límites sobre el cálculo de efectos de tratamiento. El SUTVA (Stable Unit Treatment Value Assumption) establece que cada unidad recibe la misma dosis del tratamiento, no hay spillovers a los resultados potenciales de otras unidades cuando una unidad está expuesta al tratamiento, y no hay efectos de equilibrio general. 

El SUTVA tiene dos componentes:

**No interferencia (SUTVA-1):** el resultado potencial de la unidad $i$ bajo tratamiento $d$ no depende del tratamiento recibido por otras unidades. Formalmente: $Y_i(D_1, \ldots, D_N) = Y_i(D_i)$ — la notación de resultados potenciales solo necesita el tratamiento propio.

Violaciones comunes: vacunación (la inmunidad de rebaño hace que el resultado de $i$ dependa de cuántos otros se vacunan), programas de empleo (un programa que capacita a muchos trabajadores puede afectar los salarios de quienes no participan).

**Versión única del tratamiento (SUTVA-2):** no hay variación en la intensidad o calidad del tratamiento — todos los tratados reciben la misma "dosis". Si algunos médicos son mejores operadores que otros, el "tratamiento" (cirugía) no es homogéneo y el resultado potencial $Y_i(1)$ no está bien definido sin especificar qué médico opera.

---

## 7. Estructura causal y modelos estructurales

### 7.1 Ecuaciones estructurales vs. reducidas

La tradición econométrica estructural (Haavelmo, 1943) modela el proceso generador de datos mediante sistemas de ecuaciones que representan mecanismos económicos:

$$Y = f(D, X, \varepsilon)$$

donde $\varepsilon$ captura los determinantes no observados de $Y$. El **parámetro estructural** tiene interpretación causal directa: mide el efecto de cambiar $D$ manteniendo $X$ y $\varepsilon$ fijos — el ceteris paribus formal.

La **forma reducida** expresa la variable de resultado como función de variables exógenas solamente:

$$Y = g(Z, \eta)$$

La forma reducida es más fácil de estimar pero los parámetros no tienen necesariamente interpretación estructural directa. La relación entre ambas determina si los parámetros de la forma reducida identifican los estructurales.

### 7.2 La crítica de Lucas

Lucas (1976) argumentó que los parámetros de los modelos econométricos de forma reducida no son invariantes a cambios de política — cuando cambia la política, los agentes ajustan sus expectativas y comportamiento, alterando las relaciones empíricas observadas. Esto implica que los modelos de forma reducida no pueden usarse para evaluar el efecto de políticas nunca implementadas.

La resolución es estimar parámetros estructurales — preferencias, tecnologías — que sí son invariantes a cambios de política porque representan características profundas del comportamiento de los agentes. Esta crítica es el fundamento intelectual de la macroeconomía moderna basada en modelos DSGE y de la microeconometría estructural.

---

## 8. La jerarquía de diseños de investigación

No todos los estudios empíricos tienen igual credibilidad para establecer relaciones causales. La **jerarquía de diseños** organiza las estrategias de identificación según la plausibilidad de sus supuestos:

**1. Experimento aleatorio controlado (RCT):** la aleatorización garantiza independencia entre tratamiento y resultados potenciales por diseño. El "gold standard" de la inferencia causal. Limitado por factibilidad ética, costo y validez externa.

**2. Experimentos naturales:** variaciones exógenas en $D$ generadas por el mundo (cambios legislativos, discontinuidades geográficas, loterías naturales) que aproximan la aleatorización sin intervención del investigador. La validez depende de la plausibilidad de la exogeneidad.

**3. Variables instrumentales:** cuando existe una variable $Z$ que afecta $D$ pero no afecta $Y$ directamente (solo a través de $D$), puede usarse para identificar el efecto causal de $D$ sobre $Y$. Identifica el LATE para los compliers.

**4. Diferencias en diferencias:** compara el cambio en $Y$ antes y después del tratamiento entre el grupo tratado y un grupo de control. Requiere el supuesto de tendencias paralelas: en ausencia del tratamiento, tratados y controles habrían tenido la misma evolución temporal.

**5. Regresión discontinua (RDD):** explota discontinuidades en la regla de asignación al tratamiento (un umbral de puntaje, una fecha de corte). Las unidades justo por encima y por debajo del umbral son comparables — el tratamiento es "como si" aleatorio en un vecindario del umbral.

**6. Efectos fijos y controles:** en ausencia de variación exógena, controlar por variables observadas (CIA) o efectos fijos que capturan heterogeneidad no observada constante en el tiempo.

El enfoque econométrico modela la dependencia entre el resultado observado $Y = DY_1 + (1-D)Y_0$ y $D$ para sugerir estimadores alternativos que identifiquen parámetros causales. 

---

## 9. Validez interna y validez externa

Todo estudio empírico enfrenta un trade-off entre dos dimensiones de validez:

**Validez interna:** ¿el estudio mide correctamente el efecto causal en la muestra/contexto analizado? Un RCT bien implementado tiene alta validez interna; un estudio observacional con fuerte sesgo de selección tiene baja validez interna.

**Validez externa:** ¿los resultados del estudio se generalizan a otros contextos, poblaciones o períodos? El LATE de un RCT identifica el efecto para los compliers en el contexto específico del experimento — puede no generalizarse a la población general o a otros contextos.

El dilema es frecuentemente agudo: los diseños con mayor validez interna (experimentos muy controlados, RDDs con ventanas angostas) tienden a tener menor validez externa por su especificidad. Los estudios más generalizables (grandes muestras observacionales) tienen mayor dificultad para establecer causalidad.

La evaluación de la evidencia empírica requiere juzgar ambas dimensiones simultáneamente — no basta con que un estudio sea "estadísticamente significativo" si el diseño no permite inferencia causal, ni basta con un diseño impecable si el contexto es tan específico que los resultados no son informativos para otras políticas.

---

## 10. La revolución de la credibilidad

La investigación económica empírica se ha transformado con el desarrollo de métodos de inferencia causal. La aleatorización de experimentos, cuando es factible, garantiza que los resultados potenciales son independientes de la asignación — haciendo la inferencia causal directa. En estudios observacionales, los investigadores buscan aproximar estas condiciones a través de diseños que explotan variación exógena. 

Angrist y Pischke (2010) documentaron lo que llamaron la "revolución de la credibilidad" en econometría: el giro de la profesión desde modelos estructurales complejos identificados por supuestos cuestionables hacia estrategias de identificación más transparentes basadas en variación cuasi-experimental. El estándar de prueba se volvió más exigente: no basta con estimar un modelo — hay que justificar por qué los parámetros estimados tienen interpretación causal.

Esta revolución produjo los métodos que ocupan el núcleo de la econometría moderna: variables instrumentales con supuestos explícitos, diferencias en diferencias con pruebas de tendencias paralelas, regresión discontinua con pruebas de manipulación del running variable, y experimentos aleatorios en el campo. Es el lenguaje en que se escribe la investigación empírica de frontera en economía hoy.

---

## Referencias

- Angrist, J. & Pischke, J.S. (2009). *Mostly Harmless Econometrics*. Princeton University Press. Caps. 1–2.
- Heckman, J. (2008). *Econometric Causality*. International Statistical Review.
- Holland, P.W. (1986). *Statistics and Causal Inference*. JASA.
- Imbens, G. & Angrist, J. (1994). *Identification and Estimation of Local Average Treatment Effects*. Econometrica.
- Lucas, R.E. (1976). *Econometric Policy Evaluation: A Critique*. Carnegie-Rochester Conference.
- Rubin, D.B. (1974). *Estimating Causal Effects of Treatments in Randomized and Nonrandomized Studies*. Journal of Educational Psychology.
- Wooldridge, J.M. (2008). *Introductory Econometrics*. Thomson. Cap. 1.
- Splawa-Neyman, J. (1923/1990). *On the Application of Probability Theory to Agricultural Experiments*. Statistical Science (traducción).
- Haavelmo, T. (1944). *The Probability Approach in Econometrics*. Econometrica (suplemento).