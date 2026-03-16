---
title: "Inferencia Causal"
date: 2026-03-15
draft: false
tags: ["econometría", "causalidad", "variables instrumentales", "MC2E", "instrumentos débiles", "endogeneidad", "experimentos", "EAE2510"]
description: "Efectos de tratamiento, identificación causal, variables instrumentales, estimador MC2E, validez de instrumentos, instrumentos débiles, test de endogeneidad y evaluación experimental."
---

**Cursos:** Econometría (EAE2510) · Microeconometría Aplicada (EAE3101)  
**Referencia principal:** Wooldridge (2008) caps. 15–16 · Angrist & Pischke (2009) caps. 3–5 · Stock & Watson (2006) cap. 12

---

## 1. El problema de la endogeneidad

### 1.1 Fuentes de endogeneidad

La condición de exogeneidad GM4 ($E[\varepsilon_i|\mathbf{X}_i] = 0$) falla cuando el regresor de interés está correlacionado con el error. Las tres fuentes principales son:

**Sesgo por omisión de variables:** el más común. Si el verdadero modelo incluye una variable no observada $A_i$ correlacionada con $X_i$, el error del modelo estimado captura $A_i$ y viola GM4. Ejemplo: regresión de salarios en educación cuando la habilidad no observada determina ambas.

**Causalidad simultánea (simultaneidad):** $Y$ causa $X$ y $X$ causa $Y$ simultáneamente. Ejemplo: cantidad y precio en el mercado se determinan simultáneamente por oferta y demanda — regresar precio en cantidad da un estimador que refleja tanto la demanda como la oferta, no solo una de ellas.

**Errores de medición en $X$:** produce sesgo de atenuación hacia cero — discutido en el capítulo anterior.

### 1.2 La consecuencia: inconsistencia

Cuando $\text{Cov}(X_i, \varepsilon_i) \neq 0$, el estimador MCO es **inconsistente**:

$$\text{plim}(\hat{\beta}_{MCO}) = \beta + \frac{\text{Cov}(X_i, \varepsilon_i)}{\text{Var}(X_i)} \neq \beta$$

Más observaciones no resuelven el problema — el estimador converge al valor sesgado. Este es cualitativamente distinto del problema de varianza: con endogeneidad, la inferencia es fundamentalmente inválida sin importar el tamaño muestral.

---

## 2. El marco de efectos de tratamiento

### 2.1 Notación de resultados potenciales

Siguiendo el marco de Rubin-Neyman (introducido en el capítulo de método científico), definimos para cada unidad $i$:

- $Y_i(1)$: resultado potencial bajo tratamiento.
- $Y_i(0)$: resultado potencial bajo control.
- $D_i \in \{0,1\}$: indicador de tratamiento recibido.

El resultado observado: $Y_i = D_i Y_i(1) + (1-D_i)Y_i(0)$.

### 2.2 Los parámetros de interés

**ATE (Average Treatment Effect):** $E[Y_i(1) - Y_i(0)]$ — efecto promedio para la población.

**ATT (Average Treatment Effect on the Treated):** $E[Y_i(1) - Y_i(0) | D_i = 1]$ — efecto promedio para quienes reciben el tratamiento.

**LATE (Local Average Treatment Effect):** efecto para el subgrupo de "compliers" — quienes cambian su tratamiento en respuesta al instrumento. Es el parámetro identificado por variables instrumentales. Formalmente: $LATE = E[Y_i(1) - Y_i(0) | \text{complier}]$.

La distinción entre estos parámetros importa para la política: el LATE puede diferir sustancialmente del ATE si los compliers son una subpoblación atípica. Un instrumento que solo mueve a personas con alta elasticidad al tratamiento identifica el LATE para ese grupo, que puede no generalizarse.

---

## 3. Variables instrumentales

### 3.1 La intuición

La idea de las variables instrumentales (VI) es explotar variación **exógena** en el regresor endógeno $X$ — variación que no está contaminada por la correlación con el error. Si existe una variable $Z$ que:

1. **Relevancia:** afecta a $X$ ($\text{Cov}(Z_i, X_i) \neq 0$).
2. **Exclusión (exogeneidad):** no afecta a $Y$ directamente ($\text{Cov}(Z_i, \varepsilon_i) = 0$).

entonces podemos usar la variación en $X$ inducida por $Z$ para identificar el efecto causal de $X$ sobre $Y$.

El segundo supuesto no es testeable directamente en el caso exactamente identificado — es una restricción de exclusión que debe justificarse con argumentos de diseño de investigación y conocimiento sustantivo.

### 3.2 El estimador IV en el caso simple

Con un regresor endógeno $X$, un instrumento $Z$ y sin controles:

$$\hat{\beta}_{IV} = \frac{\sum_i (Z_i - \bar{Z})(Y_i - \bar{Y})}{\sum_i (Z_i - \bar{Z})(X_i - \bar{X})} = \frac{\widehat{\text{Cov}}(Z, Y)}{\widehat{\text{Cov}}(Z, X)}$$

Alternativamente, usando la forma de Wald:

$$\hat{\beta}_{IV} = \frac{E[Y|Z=1] - E[Y|Z=0]}{E[X|Z=1] - E[X|Z=0]}$$

cuando $Z$ es binario. El numerador es el efecto reducido de $Z$ sobre $Y$; el denominador es el efecto de primera etapa de $Z$ sobre $X$. El estimador IV escala el efecto de $Z$ sobre $Y$ por el efecto de $Z$ sobre $X$ — extrayendo solo el componente de la variación de $X$ explicado por $Z$.

**Consistencia del estimador IV:**

$$\text{plim}(\hat{\beta}_{IV}) = \frac{\text{Cov}(Z_i, Y_i)}{\text{Cov}(Z_i, X_i)} = \frac{\text{Cov}(Z_i, \beta X_i + \varepsilon_i)}{\text{Cov}(Z_i, X_i)} = \beta + \frac{\text{Cov}(Z_i, \varepsilon_i)}{\text{Cov}(Z_i, X_i)}$$

Si la restricción de exclusión se cumple ($\text{Cov}(Z_i, \varepsilon_i) = 0$), el segundo término desaparece y el estimador es consistente.

### 3.3 Interpretación como LATE

Bajo los supuestos de independencia, exclusión, primera etapa positiva y monotonicidad, el estimador IV identifica el LATE — el efecto causal promedio para el subgrupo de compliers, es decir, aquellas unidades cuyo tratamiento cambia en respuesta al instrumento. 

La **monotonicidad** es el supuesto adicional: el instrumento mueve a todas las unidades en la misma dirección (no hay "defiers" — unidades que hacen exactamente lo opuesto al instrumento). Bajo monotonicidad:

$$\hat{\beta}_{IV} \xrightarrow{p} LATE = E[Y_i(1) - Y_i(0) | \text{complier}]$$

Los **compliers** son quienes toman el tratamiento solo cuando $Z=1$ y no cuando $Z=0$. Los **always-takers** siempre toman el tratamiento; los **never-takers** nunca. El IV no identifica el efecto para estos últimos grupos.

---

## 4. Mínimos cuadrados en dos etapas (MC2E / 2SLS)

### 4.1 El procedimiento

Con múltiples regresores, controles exógenos $\mathbf{W}$ y variables instrumentales $\mathbf{Z}$, el estimador **MC2E (2SLS)** se implementa en dos etapas:

**Primera etapa:** regresar el regresor endógeno $X$ en los instrumentos $\mathbf{Z}$ y los controles $\mathbf{W}$ por MCO:

$$X_i = \pi_0 + \pi_1 Z_i + \mathbf{W}_i'\boldsymbol{\gamma} + v_i$$

Guardar los valores ajustados $\hat{X}_i = \hat{\pi}_0 + \hat{\pi}_1 Z_i + \mathbf{W}_i'\hat{\boldsymbol{\gamma}}$.

**Segunda etapa:** regresar $Y$ en $\hat{X}$ y los controles $\mathbf{W}$ por MCO:

$$Y_i = \beta_0 + \beta_1 \hat{X}_i + \mathbf{W}_i'\boldsymbol{\delta} + \varepsilon_i$$

El coeficiente $\hat{\beta}_1$ es el estimador MC2E.

**Advertencia crucial:** los errores estándar de la segunda etapa calculados manualmente son incorrectos — subestiman la varianza real porque no propagan la incertidumbre de la primera etapa. Siempre usar el comando dedicado en Stata (`ivregress 2sls`) que calcula los SE correctos automáticamente.

### 4.2 La fórmula matricial

El estimador IV (2SLS) con múltiples instrumentos es: $\hat{\boldsymbol{\beta}}_{2SLS} = (\hat{\mathbf{X}}'\hat{\mathbf{X}})^{-1}\hat{\mathbf{X}}'\mathbf{y}$, donde $\hat{\mathbf{X}} = \mathbf{P}_Z \mathbf{X}$ son los valores ajustados de la primera etapa y $\mathbf{P}_Z = \mathbf{Z}(\mathbf{Z}'\mathbf{Z})^{-1}\mathbf{Z}'$ es la matriz de proyección sobre el espacio de los instrumentos. 

Equivalentemente: $\hat{\boldsymbol{\beta}}_{2SLS} = (\mathbf{X}'\mathbf{P}_Z\mathbf{X})^{-1}\mathbf{X}'\mathbf{P}_Z\mathbf{y}$.

La varianza asintótica bajo homocedasticidad: $\text{Var}(\hat{\boldsymbol{\beta}}_{2SLS}) = \sigma^2(\mathbf{X}'\mathbf{P}_Z\mathbf{X})^{-1}$.

### 4.3 Propiedades del estimador MC2E

- **Consistencia:** bajo relevancia y exclusión del instrumento.
- **Sesgo de muestras finitas:** el MC2E es sesgado en muestras finitas. El sesgo es proporcional a $1/F$ donde $F$ es el estadístico de la primera etapa — a mayor $F$ (instrumento más fuerte), menor el sesgo.
- **Mayor varianza que MCO:** siempre. El costo de corregir la endogeneidad es pérdida de precisión.
- **Normalidad asintótica:** bajo condiciones de regularidad, $\sqrt{n}(\hat{\boldsymbol{\beta}}_{2SLS} - \boldsymbol{\beta}) \xrightarrow{d} \mathcal{N}(\mathbf{0}, \mathbf{V})$.

---

## 5. Validez de los instrumentos

### 5.1 La relevancia: primer estadístico $F$ de la primera etapa

La **debilidad** de los instrumentos es el problema más práctico en la aplicación de VI. Un instrumento débil genera:

- Sesgo de muestras finitas severo hacia el estimador MCO.
- Distribuciones asintóticas incorrectas — los errores estándar estándar no son válidos.
- Poder muy bajo para detectar efectos cuando el verdadero efecto existe.

La regla práctica estándar de Stock & Yogo (2005): el estadístico $F$ de la primera etapa debe superar 10 para que el sesgo del MC2E no supere el 10% del sesgo MCO. Si el estadístico F supera 10, se rechaza la hipótesis nula de que todos los instrumentos son débiles. 

Sin embargo, para los rangos del F de primera etapa típicamente aceptados de 10–20, la probabilidad de que 2SLS genere una estimación más cercana a la verdad que MCO es notablemente pequeña, a menos que la endogeneidad sea muy severa. Se argumenta que deberían adoptarse umbrales de F más rigurosos en el trabajo aplicado. 

El umbral más exigente recomendado actualmente en la literatura es $F > 104.7$ para el caso exactamente identificado (Lee et al., 2022), basado en la condición de que el intervalo de confianza tenga cobertura de 95%.

En Stata: después de `ivregress 2sls`, ejecutar `estat firststage` para obtener el estadístico $F$ de la primera etapa y el $F$ parcial de cada instrumento excluido.

### 5.2 La exclusión: validez de los instrumentos

La restricción de exclusión ($\text{Cov}(Z_i, \varepsilon_i) = 0$) no es directamente testeable en el caso exactamente identificado. Su justificación es inherentemente argumentativa — depende de teoría económica, conocimiento institucional y diseño de investigación.

Algunas estrategias para fortalecer la credibilidad de la exclusión:

- **Aleatorización:** si $Z$ se asigna aleatoriamente, la exclusión se cumple por diseño.
- **Experimentos naturales:** cambios legislativos exógenos, discontinuidades geográficas, variación climática. La credibilidad depende de que el evento exógeno no afecte $Y$ por otros canales.
- **Pruebas de falsificación:** si el instrumento tiene efecto sobre outcomes que no deberían verse afectados por $X$, sugiere que la exclusión viola.
- **Pruebas de balance:** verificar que $Z$ no está correlacionado con características pre-tratamiento observadas que podrían estar correlacionadas con $\varepsilon$.

### 5.3 Test de sobreidentificación: Sargan-Hansen

Cuando hay más instrumentos que variables endógenas (caso sobreidentificado), es posible contrastar si los instrumentos adicionales son exógenos — **condicionalmente a que al menos un instrumento sea válido**. Este es el único test directo de la restricción de exclusión, y solo aplica para los instrumentos "en exceso".

El **test de Sargan-Hansen (test J):**

1. Estimar el modelo MC2E y obtener residuos $\hat{\varepsilon}_{2SLS}$.
2. Regresar $\hat{\varepsilon}_{2SLS}$ en todos los instrumentos y controles exógenos.
3. El estadístico $nR^2 \sim \chi^2(q)$ bajo $H_0$, donde $q$ es el número de restricciones de sobreidentificación (número de instrumentos menos número de variables endógenas).

Bajo la hipótesis nula de que todos los instrumentos son exógenos, el estadístico $nR^2$ sigue una distribución $\chi^2$ con grados de libertad iguales al número de restricciones de sobreidentificación. 

Un estadístico de prueba grande y $p$-valor pequeño en el test de Sargan sugiere que el modelo está mal especificado — al menos un instrumento puede estar correlacionado con el error. 

**Limitación crítica:** el test de Sargan-Hansen solo puede rechazar la validez del conjunto de instrumentos; no puede identificar cuál instrumento específico es inválido. Y si todos los instrumentos son igualmente inválidos, el test no tiene poder para detectarlo. El no-rechazo es evidencia débil de validez — no ausencia de violación.

En Stata: `estat overid` después de `ivregress 2sls`.

---

## 6. Test de endogeneidad: Hausman-Wu

### 6.1 La lógica del test

Si el regresor $X$ es **exógeno**, tanto MCO como MC2E son consistentes, y MCO es más eficiente (menor varianza). Si $X$ es **endógeno**, MCO es inconsistente pero MC2E sigue siendo consistente. La diferencia $\hat{\beta}_{2SLS} - \hat{\beta}_{MCO}$ converge en probabilidad a cero bajo exogeneidad y a un valor no nulo bajo endogeneidad.

El test de Wu-Hausman aplicado a la regresión 2SLS es un test de endogeneidad. Si todos los regresores son exógenos, tanto MCO como 2SLS son consistentes, y MCO es más eficiente. Si hay endogeneidad, MCO es inconsistente. Un estadístico grande y $p$-valor pequeño sugiere que el estimador MCO es inconsistente y el 2SLS es preferible. 

### 6.2 Implementación práctica

La implementación más directa del test Hausman-Wu para endogeneidad:

1. En la **primera etapa**, regresar $X$ en $Z$ y los controles $\mathbf{W}$. Guardar los residuos $\hat{v}$.
2. En el **modelo aumentado**, incluir $\hat{v}$ como regresor adicional junto a $X$ y $\mathbf{W}$:

$$Y_i = \beta_0 + \beta_1 X_i + \mathbf{W}_i'\boldsymbol{\delta} + \rho \hat{v}_i + \varepsilon_i$$

3. Contrastar $H_0: \rho = 0$ con un test $t$ estándar.

Si $\rho \neq 0$ estadísticamente, hay evidencia de endogeneidad — $X$ está correlacionado con el error del modelo estructural. El coeficiente $\rho$ captura exactamente la parte endógena de $X$.

Este test puede realizarse fácilmente: imagina que se estima la ecuación aumentada con los residuos de la primera etapa como regresor adicional. Un test $t$ sobre el coeficiente de estos residuos es equivalente al test de Hausman. La presencia de múltiples variables endógenas extiende el test a un F conjunto. 

En Stata: `estat endog` después de `ivregress 2sls`.

**Sobre el resultado del test:** no rechazar $H_0$ no prueba exogeneidad — solo dice que no hay evidencia estadística suficiente de endogeneidad dado el tamaño muestral e instrumento disponible. En presencia de instrumentos débiles, el test tiene poco poder.

---

## 7. Instrumentos débiles: diagnóstico avanzado

### 7.1 El problema en detalle

Cuando los instrumentos son débiles (modelados como locales a cero), las distribuciones asintóticas estándar del estimador 2SLS no proveen buenas aproximaciones a las distribuciones muestrales. Esto afecta tanto las estimaciones puntuales como los intervalos de confianza. 

Con instrumento débil: el numerador del estimador IV ($\widehat{\text{Cov}}(Z,Y)$) converge a cero junto con el denominador ($\widehat{\text{Cov}}(Z,X)$). La distribución del cociente es una distribución de Cauchy-like con colas muy pesadas — los errores estándar estándar son severamente incorrectos.

### 7.2 Estadísticos robustos a instrumentos débiles

Ante instrumentos débiles, los estadísticos $t$ y $F$ estándar del MC2E tienen tasas de rechazo incorrectas bajo $H_0$. Las alternativas robustas incluyen:

**Estadístico Anderson-Rubin (AR):** invierte un test de la forma reducida para construir regiones de confianza. Es válido incluso con instrumentos débiles porque no requiere invertir la primera etapa. El precio es menor poder cuando los instrumentos son fuertes.

**Conditional Likelihood Ratio (CLR):** óptimo entre los tests robustos a debilidad. En Stata: `weakivtest` (de Pflueger & Wang).

**Regiones de confianza robustas:** en vez de reportar el estimador puntual ± 2×SE (que es inválido con instrumentos débiles), reportar la región de valores de $\beta$ que el test AR no rechaza. Puede ser un intervalo muy amplio o incluso no acotado — lo que revela honestamente la poca información que el instrumento débil provee.

---

## 8. Introducción a la evaluación experimental

### 8.1 El experimento aleatorio como gold standard

En un **experimento controlado aleatorio (RCT)**, la asignación al tratamiento $D_i$ es independiente de $(Y_i(0), Y_i(1))$ por diseño. La diferencia simple en medias estima el ATE sin sesgo:

$$\hat{\tau}_{ATE} = \bar{Y}_{D=1} - \bar{Y}_{D=0} \xrightarrow{p} E[Y(1)] - E[Y(0)] = ATE$$

No se necesita ni VI ni controles para identificar el efecto causal — la aleatorización los hace innecesarios para consistencia. Los controles pueden agregarse para mejorar la precisión (reducir varianza) pero no para corregir sesgo.

### 8.2 La estimación por regresión en experimentos

En la práctica, los efectos de tratamiento de RCTs se estiman por regresión:

$$Y_i = \alpha + \tau D_i + \mathbf{X}_i'\boldsymbol{\gamma} + \varepsilon_i$$

donde $\mathbf{X}_i$ son características de control pre-tratamiento. Bajo aleatorización, $D_i$ es ortogonal a $\varepsilon_i$ con o sin controles, por lo que $\hat{\tau}_{MCO}$ es insesgado. La inclusión de $\mathbf{X}_i$ reduce la varianza residual y mejora la precisión de $\hat{\tau}$ sin afectar su consistencia.

### 8.3 Amenazas a la validez interna del experimento

**Incumplimiento (non-compliance):** los asignados al tratamiento no lo reciben o los del control lo reciben de todas formas. La solución es la **intención de tratar (ITT)**: regresar $Y$ en la asignación aleatoria $Z_i$ (no en el tratamiento efectivo $D_i$). El ITT es el efecto de la política de asignación, que puede ser el parámetro relevante para el diseñador de políticas. Si se quiere el efecto del tratamiento efectivo, usar $Z$ como instrumento para $D$ — el estimador IV identifica el LATE para los compliers.

**Desgaste (attrition):** si algunos individuos salen del experimento de forma diferencial según el grupo, los resultados pueden sesgarse. Prueba: verificar que el desgaste no está correlacionado con el tratamiento.

**Efectos de equilibrio general:** en experimentos pequeños, los efectos identificados son locales y pueden no generalizarse si el programa se escala — la escala puede cambiar los precios de equilibrio o la composición de los grupos.

### 8.4 Experimentos naturales y cuasi-experimentos

Cuando los RCTs son éticamente inviables o demasiado costosos, los cuasi-experimentos explotan variación cuasi-aleatoria en la asignación al tratamiento. Los principales diseños son:

**Diferencias en diferencias (DiD):** compara el cambio en $Y$ antes y después del tratamiento entre el grupo tratado y un grupo de control no tratado. Bajo el supuesto de **tendencias paralelas** (en ausencia del tratamiento, ambos grupos habrían seguido la misma tendencia), DiD identifica el ATT. Requiere datos de panel o dos cortes transversales del mismo grupo.

**Regresión discontinua (RDD):** explota un umbral en la regla de asignación. Unidades justo por encima y debajo del umbral son comparables — el tratamiento es "como si" aleatorio en un vecindario del corte. Identifica el LATE en el umbral, que puede no generalizarse lejos de él.

**Variables instrumentales con experimento natural:** un cambio de política, una variación legislativa o un evento climático actúa como instrumento que afecta el tratamiento de forma exógena. La credibilidad depende de la plausibilidad de la restricción de exclusión.

---

## 9. Implementación en Stata

Los comandos esenciales para VI/2SLS en Stata:
```stata
* Estimación 2SLS básica
ivregress 2sls y w1 w2 (x = z1 z2), robust

* Primera etapa
estat firststage          // F de primera etapa y F parciales
estat firststage, all     // incluye tests de Cragg-Donald y Kleibergen-Paap

* Test de endogeneidad (Hausman-Wu)
estat endog               // test de Durbin-Wu-Hausman

* Test de sobreidentificación (Sargan-Hansen)
estat overid              // solo con más instrumentos que endógenas

* Errores robustos a heterocedasticidad (siempre recomendable)
ivregress 2sls y w1 w2 (x = z1 z2), vce(robust)

* Errores clusterizados (si hay correlación intra-cluster)
ivregress 2sls y w1 w2 (x = z1 z2), vce(cluster id)

* Tests robustos a instrumentos débiles (requiere ivreg2)
ivreg2 y w1 w2 (x = z1 z2), robust ffirst
```

---

## 10. Ejemplos clásicos de instrumentos en economía

| Pregunta | Endógena | Instrumento | Restricción de exclusión |
|---|---|---|---|
| Retorno a la educación (Angrist-Krueger 1991) | Años de educación | Trimestre de nacimiento | Nacimiento en Q1 → menos educación por leyes de asistencia escolar, sin efecto directo en salarios |
| Efecto del tamaño familiar (Angrist-Evans 1998) | Número de hijos | Gemelos o composición de sexos | Gemelos/composición de sexos afecta el tamaño de la familia pero no el empleo directamente |
| Efecto del servicio militar (Angrist 1990) | Servicio militar Vietnam | Número de lotería del draft | El número asignado aleatoriamente determina el servicio pero no afecta directamente los salarios futuros |
| Efecto del comercio en salarios (Card 2009) | Inmigración local | Distribución histórica de inmigrantes | Redes históricas determinan flujos actuales pero no afectan directamente el mercado laboral local excepto a través de la inmigración |

---

## 11. Síntesis: cuándo usar MCO vs. VI

| Situación | Estimador recomendado | Razón |
|---|---|---|
| Exogeneidad plausible | MCO | Consistente, más eficiente, errores estándar menores |
| Endogeneidad sospechada, instrumento fuerte y válido | MC2E / 2SLS | Consistente bajo endogeneidad |
| Endogeneidad sospechada, instrumento débil | MC2E con SE robustos a debilidad, LIML | 2SLS estándar tiene distribución incorrecta |
| Endogeneidad sospechada, sin instrumento | MCO con caveat, o diseño alternativo | Reportar sesgo esperado, buscar otros diseños |
| RCT con cumplimiento completo | MCO de $Y$ en $D$ | Equivale al estimador de diferencia de medias |
| RCT con incumplimiento | ITT o IV usando $Z$ como instrumento de $D$ | Identifica LATE de compliers |

---

## Referencias

- Angrist, J. & Pischke, J.S. (2009). *Mostly Harmless Econometrics*. Princeton. Caps. 3–5.
- Imbens, G. & Angrist, J. (1994). *Identification and Estimation of Local Average Treatment Effects*. Econometrica.
- Staiger, D. & Stock, J.H. (1997). *Instrumental Variables Regression with Weak Instruments*. Econometrica.
- Stock, J.H. & Yogo, M. (2005). *Testing for Weak Instruments in Linear IV Regression*. En Andrews & Stock (eds.).
- Hausman, J.A. (1978). *Specification Tests in Econometrics*. Econometrica.
- Angrist, J. & Krueger, A. (1991). *Does Compulsory School Attendance Affect Schooling and Earnings?* QJE.
- Lee, D.S., McCrary, J., Moreira, M.J. & Porter, J. (2022). *Valid t-ratio Inference for IV*. AER.
- Wooldridge, J.M. (2008). *Introductory Econometrics*. Thomson. Caps. 15–16.
- Stock, J.H. & Watson, M.W. (2006). *Introduction to Econometrics*. Pearson. Cap. 12.