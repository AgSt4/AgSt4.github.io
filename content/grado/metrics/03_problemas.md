---
title: "Especificación y Problemas en el MRL"
date: 2026-03-15
draft: false
tags: ["econometría", "especificación", "sesgo de omisión", "multicolinealidad", "heterocedasticidad", "errores de medición", "cambio estructural", "EAE2510"]
description: "Transformaciones de variables, variables ficticias, sesgo por omisión, inclusión de irrelevantes, multicolinealidad, errores de medición, cambio estructural y selección de modelos."
---

**Cursos:** Econometría (EAE2510) · Inferencia Estadística (EAA1520)  
**Referencia principal:** Wooldridge (2008) caps. 6–9 · Johnston & DiNardo (2001) · Greene (2011) caps. 5–8

---

## 1. Transformaciones de variables y relaciones no lineales

### 1.1 El MRL es lineal en parámetros, no en variables

La denominación "lineal" en el MRL se refiere a la linealidad en los **parámetros**, no en las variables. Cualquier transformación de los datos puede incluirse como regresor sin abandonar el marco lineal. Las transformaciones más usadas son:

**Transformación logarítmica:** estabiliza varianza, comprime distribuciones asimétricas y da interpretación de elasticidad a los coeficientes.

| Modelo | Interpretación de $\beta_1$ |
|---|---|
| $Y = \beta_0 + \beta_1 X$ | $\Delta Y = \beta_1 \Delta X$ (efecto lineal) |
| $\ln Y = \beta_0 + \beta_1 X$ | $\% \Delta Y \approx 100\beta_1 \Delta X$ (semielasticidad) |
| $Y = \beta_0 + \beta_1 \ln X$ | $\Delta Y \approx \beta_1 \% \Delta X / 100$ |
| $\ln Y = \beta_0 + \beta_1 \ln X$ | $\% \Delta Y \approx \beta_1 \% \Delta X$ (elasticidad) |

**Términos cuadráticos y polinomiales:** permiten efectos marginales variables. Con $Y = \beta_0 + \beta_1 X + \beta_2 X^2 + \varepsilon$:

$$\frac{\partial E[Y|X]}{\partial X} = \beta_1 + 2\beta_2 X$$

El efecto marginal depende del nivel de $X$. El punto de inflexión (máximo o mínimo) está en $X^* = -\beta_1/(2\beta_2)$. La hipótesis de que la relación es lineal equivale a $H_0: \beta_2 = 0$.

**Términos de interacción:** permiten que el efecto de $X_1$ dependa del valor de $X_2$:

$$Y = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + \beta_3 X_1 X_2 + \varepsilon$$

$$\frac{\partial E[Y|X_1, X_2]}{\partial X_1} = \beta_1 + \beta_3 X_2$$

El coeficiente $\beta_3$ captura si el efecto marginal de $X_1$ sobre $Y$ es diferente a distintos niveles de $X_2$. La prueba $H_0: \beta_3 = 0$ contrasta si la interacción es estadísticamente significativa.

### 1.2 Variables ficticias (dummies)

Una **variable ficticia** $D_i \in \{0, 1\}$ representa una característica binaria (género, región, período de tiempo, tratamiento). En el modelo:

$$Y_i = \beta_0 + \beta_1 D_i + \beta_2 X_i + \varepsilon_i$$

$\beta_1$ es el diferencial en el intercepto entre $D=1$ y $D=0$, manteniendo $X$ constante. Equivale a correr dos regresiones con la misma pendiente pero distintos interceptos.

**La trampa de la dummy (dummy variable trap):** con $K$ categorías mutuamente excluyentes y exhaustivas, se deben incluir exactamente $K-1$ dummies. Incluir las $K$ dummies más el intercepto genera multicolinealidad perfecta (las $K$ dummies suman 1, que es idéntico al intercepto). La categoría omitida es la **categoría base o de referencia** — los coeficientes de las otras dummies se interpretan relativos a ella.

**Interacción de dummy con variable continua:**

$$Y_i = \beta_0 + \beta_1 D_i + \beta_2 X_i + \beta_3 D_i X_i + \varepsilon_i$$

Permite que la **pendiente** también difiera entre grupos. El efecto marginal de $X$ es $\beta_2$ para $D=0$ y $\beta_2 + \beta_3$ para $D=1$.

---

## 2. Omisión de variables relevantes: el sesgo de omisión

### 2.1 La fórmula del sesgo

El sesgo de omisión (OVB) es la violación más crítica del MRL porque destruye la insesgadez e **inconsistencia** del estimador MCO.

**Configuración:** el verdadero modelo es $Y = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + \varepsilon$, con $\beta_2 \neq 0$ y $\text{Cov}(X_1, X_2) \neq 0$. Se estima el modelo corto omitiendo $X_2$: $Y = \tilde{\beta}_0 + \tilde{\beta}_1 X_1 + u$.

El estimador MCO del modelo corto satisface:

$$\text{plim}(\tilde{\beta}_1) = \beta_1 + \beta_2 \cdot \frac{\text{Cov}(X_1, X_2)}{\text{Var}(X_1)} = \beta_1 + \beta_2 \delta_{21}$$

donde $\delta_{21} = \text{Cov}(X_1, X_2)/\text{Var}(X_1)$ es el coeficiente de la regresión de $X_2$ sobre $X_1$. El sesgo es $\beta_2 \delta_{21}$.

El sesgo resulta en que el modelo atribuye el efecto de las variables omitidas a las que fueron incluidas. La dirección del sesgo depende de los estimadores y la covarianza entre los regresores y las variables omitidas. 

### 2.2 Las dos condiciones para el sesgo

El sesgo de omisión requiere que **ambas** condiciones se cumplan simultáneamente:

1. La variable omitida $X_2$ afecta a $Y$: $\beta_2 \neq 0$.
2. La variable omitida $X_2$ está correlacionada con $X_1$: $\text{Cov}(X_1, X_2) \neq 0$.

Si cualquiera de las dos no se cumple, no hay sesgo. Si la variable omitida no es determinante de $Y$ (aunque esté correlacionada con $X$), omitirla no causa sesgo. Si es determinante de $Y$ pero no está correlacionada con $X$, tampoco causa sesgo — solo aumenta la varianza del error. 

### 2.3 Signo y magnitud del sesgo

La tabla de signos del sesgo es:

| $\text{Corr}(X_1, X_2)$ | $\beta_2 > 0$ | $\beta_2 < 0$ |
|---|---|---|
| **Positiva** | Sesgo positivo (sobreestimación) | Sesgo negativo (subestimación) |
| **Negativa** | Sesgo negativo | Sesgo positivo |

**Ejemplo canónico — retorno a la educación:** la ecuación de Mincer estima el efecto de años de educación ($X_1 = educ$) sobre el ingreso ($Y = \ln w$). La habilidad innata ($X_2 = abil$) determina el ingreso ($\beta_2 > 0$) y está positivamente correlacionada con la educación ($\delta_{21} > 0$). El sesgo es positivo — MCO sobreestima el retorno a la educación al atribuirle parte del efecto de la habilidad no observada.

### 2.4 Soluciones al sesgo de omisión

- **Incluir la variable omitida** si es observable.
- **Usar una variable proxy** correlacionada con la omitida (por ejemplo, puntaje en prueba estandarizada como proxy de habilidad).
- **Variables instrumentales (VI):** si existe una variable que afecta $X_1$ pero no $Y$ directamente (excepto a través de $X_1$) — ver capítulo de inferencia causal.
- **Efectos fijos** en datos de panel: controla por todas las variables omitidas invariantes en el tiempo a nivel de unidad.

---

## 3. Inclusión de variables irrelevantes

Si se incluye $X_2$ en el modelo cuando su verdadero coeficiente es $\beta_2 = 0$:

- MCO de $\beta_1$ sigue siendo **insesgado y consistente** — no hay sesgo por incluir irrelevantes.
- Los errores estándar de todos los coeficientes se **inflan** — pérdida de eficiencia.
- El $R^2$ sube o se mantiene pero el $\bar{R}^2$ puede caer.

Las variables irrelevantes aumentan los errores estándar de los coeficientes estimados y reducen la precisión de las estimaciones, debilitando el poder estadístico de los tests de hipótesis. 

El **trade-off sesgo-varianza** en la selección de modelos: modelos grandes (muchas variables) tienden a ser insesgados pero imprecisos; modelos pequeños tienden a ser más precisos pero potencialmente sesgados. No hay una solución dominante universal — depende del uso del modelo.

---

## 4. Multicolinealidad

### 4.1 Definición y tipos

La **multicolinealidad** es la correlación (alta, aunque no perfecta) entre los regresores. La multicolinealidad **perfecta** (GM3 violado) hace que $(\mathbf{X}'\mathbf{X})$ sea singular y el estimador MCO no exista. La multicolinealidad **imperfecta** no viola ningún supuesto del MRL — pero tiene consecuencias prácticas importantes.

### 4.2 Consecuencias

La multicolinealidad no sesga las estimaciones — MCO sigue siendo insesgado y consistente. Lo que hace es inflar los errores estándar, haciendo las estimaciones menos precisas. 

Formalmente, la varianza del estimador MCO de $\beta_j$ en el modelo con múltiples regresores es:

$$\text{Var}(\hat{\beta}_j) = \frac{\sigma^2}{SCT_j \cdot (1 - R_j^2)}$$

donde $SCT_j = \sum_i (X_{ji} - \bar{X}_j)^2$ es la variación total de $X_j$ y $R_j^2$ es el $R^2$ de la regresión de $X_j$ sobre todos los demás regresores. Cuando $R_j^2 \to 1$ (alta multicolinealidad), $\text{Var}(\hat{\beta}_j) \to \infty$.

Mientras el sesgo de omisión afecta la consistencia de los estimadores, la multicolinealidad afecta la eficiencia. La multicolinealidad puede hacer difícil distinguir los efectos individuales de las variables correlacionadas. 

Las consecuencias prácticas son: estadísticos $t$ pequeños (difícil rechazar $H_0: \beta_j = 0$ individualmente), coeficientes sensibles a pequeños cambios en la muestra o especificación, y $R^2$ alto pero pocas variables individuales significativas.

### 4.3 Detección

El **factor de inflación de la varianza (VIF)** para el regresor $j$:

$$VIF_j = \frac{1}{1 - R_j^2}$$

Si $VIF_j = 1$ no hay correlación entre $X_j$ y los demás regresores. $VIF_j > 5$ amerita investigación adicional; $VIF_j > 10$ indica multicolinealidad severa que requiere corrección. 

Otras señales: altos $R^2$ entre pares de regresores (correlaciones cruzadas), coeficientes que cambian drásticamente al agregar o quitar variables.

### 4.4 Soluciones

Eliminar una de las variables altamente correlacionadas puede aliviar la multicolinealidad, pero puede introducir sesgo de omisión. Combinar las variables correlacionadas en un índice compuesto puede ser una solución. La regresión ridge y la regresión de componentes principales son técnicas de regularización que pueden manejar la multicolinealidad. 

La solución más apropiada depende del objetivo: si el interés es predicción, la regularización (ridge) es válida; si el interés es interpretación causal de coeficientes individuales, el problema es fundamentalmente de información insuficiente en los datos — ninguna técnica estadística puede resolverlo si los regresores son genuinamente indistinguibles en la muestra.

---

## 5. Errores de medición

### 5.1 Error en la variable dependiente

Si $Y^* = \beta_0 + \beta_1 X + \varepsilon$ es el verdadero modelo pero observamos $Y = Y^* + v$ con $v$ ruido clásico ($E[v]=0$, $\text{Cov}(v, X) = 0$, $\text{Cov}(v, \varepsilon) = 0$):

$$Y = \beta_0 + \beta_1 X + (\varepsilon + v)$$

El error compuesto $\varepsilon + v$ sigue siendo exógeno — MCO es insesgado y consistente. El único efecto es que la varianza del error sube, reduciendo la precisión de las estimaciones.

### 5.2 Error en un regresor: atenuación

El caso más problemático es cuando el regresor tiene error de medición. Observamos $X = X^* + w$ (el verdadero $X^*$ más error de medición $w$ con $E[w]=0$, $\text{Cov}(w, X^*)=0$, $\text{Cov}(w, \varepsilon)=0$).

El verdadero modelo es $Y = \beta_0 + \beta_1 X^* + \varepsilon$, pero estimamos con $X$ en vez de $X^*$:

$$Y = \beta_0 + \beta_1(X - w) + \varepsilon = \beta_0 + \beta_1 X + (\varepsilon - \beta_1 w)$$

El error compuesto $\varepsilon - \beta_1 w$ está **correlacionado con $X$** porque $X = X^* + w$ y $w$ aparece en el error. La covarianza es:

$$\text{Cov}(X, \varepsilon - \beta_1 w) = -\beta_1 \text{Var}(w) < 0 \quad (\text{si } \beta_1 > 0)$$

Esto viola GM4. El estimador MCO tiene un **sesgo de atenuación**:

$$\text{plim}(\hat{\beta}_1) = \beta_1 \cdot \frac{\text{Var}(X^*)}{\text{Var}(X^*) + \text{Var}(w)} = \beta_1 \cdot \lambda \in (0, 1)$$

donde $\lambda = \text{Var}(X^*)/(\text{Var}(X^*) + \text{Var}(w)) \leq 1$ es la **ratio señal-ruido**. El estimador MCO sesga el coeficiente **hacia cero** — subestima el efecto en valor absoluto. Este sesgo no desaparece con muestras grandes — es un problema de consistencia, no de precisión.

El sesgo de atenuación es particularmente relevante en economía cuando las variables no se miden perfectamente (ingresos reportados, horas trabajadas, precios declarados). Las variables instrumentales pueden corregirlo si existe un instrumento para $X^*$ no correlacionado con $w$.

---

## 6. Cambio estructural: el test de Chow

### 6.1 La hipótesis de estabilidad de parámetros

Un supuesto implícito del MRL es que los parámetros $\boldsymbol{\beta}$ son constantes para todas las observaciones. Si hay razones para creer que los parámetros difieren entre subgrupos (por período, región, género), la restricción de estabilidad puede testearse formalmente.

### 6.2 El test de Chow (1960)

Con dos subgrupos ($G=1$ y $G=2$), el **test de Chow** contrasta:

$$H_0: \boldsymbol{\beta}^{(1)} = \boldsymbol{\beta}^{(2)} \quad \text{(parámetros iguales en ambos grupos)}$$

**Procedimiento:**

1. Estimar el modelo **restringido** (mismos parámetros para todos): $SCR_R$ con $n-K-1$ gl.
2. Estimar los modelos **irrestrictos** para cada subgrupo: $SCR_1 + SCR_2$ con $n-2(K+1)$ gl.
3. El estadístico $F$:

$$F = \frac{(SCR_R - SCR_1 - SCR_2)/(K+1)}{(SCR_1 + SCR_2)/(n - 2(K+1))} \sim F_{K+1,\, n-2(K+1)} \quad \text{bajo } H_0$$

Un $F$ grande rechaza la estabilidad de parámetros. En series de tiempo, el test requiere conocer el punto de quiebre $\tau$ a priori — si $\tau$ es desconocido, se usa el test de Bai-Perron para quiebres estructurales desconocidos.

**Implementación con dummies:** equivalentemente, se puede incluir una dummy $D_i$ para el segundo grupo e interacciones $D_i X_{ji}$ para todos los regresores, y testar conjuntamente que todos los coeficientes de las interacciones son cero — la $F$ resultante es idéntica al test de Chow.

---

## 7. Selección de modelos

### 7.1 El trade-off sesgo-varianza

La selección de modelos enfrenta un trade-off fundamental: modelos más ricos (más variables) reducen el sesgo de omisión pero aumentan la varianza; modelos más parsimoniosos reducen la varianza pero pueden ser sesgados.

No existe un criterio óptimo universal — depende del objetivo del análisis:

- **Inferencia causal sobre $\beta_j$:** el criterio principal es la validez de la identificación, no la bondad de ajuste. Incluir controles que cortan el sesgo de omisión es prioritario, incluso si reducen la precisión.
- **Predicción:** el $\bar{R}^2$ o criterios de información son relevantes.

### 7.2 Criterios de información

Los **criterios de información** penalizan la bondad de ajuste por el número de parámetros, permitiendo comparar modelos no anidados:

$$AIC = \ln\left(\frac{SCR}{n}\right) + \frac{2K}{n}$$

$$BIC = \ln\left(\frac{SCR}{n}\right) + \frac{K \ln n}{n}$$

Un valor menor indica mejor modelo. El BIC penaliza más fuerte que el AIC — tiende a preferir modelos más parsimoniosos, especialmente en muestras grandes. Para predicción fuera de muestra, el AIC a veces domina; para identificar el verdadero modelo generador de datos, el BIC es asintóticamente consistente.

### 7.3 El test RESET de Ramsey

El **test RESET** (Regression Equation Specification Error Test) contrasta si potencias de los valores ajustados $\hat{Y}^2, \hat{Y}^3$ tienen poder explicativo adicional sobre el modelo especificado:

$$Y = \beta_0 + \beta_1 X_1 + \cdots + \beta_K X_K + \gamma_1 \hat{Y}^2 + \gamma_2 \hat{Y}^3 + u$$

$$H_0: \gamma_1 = \gamma_2 = 0 \quad \text{(el modelo está bien especificado)}$$

Rechazar $H_0$ sugiere que la forma funcional especificada es incorrecta — posiblemente hay variables omitidas o términos no lineales necesarios. El test RESET es general pero no diagnóstica exactamente el problema.

### 7.4 El problema de la pesca de especificación (data mining)

Un peligro importante en la selección de modelos es el **p-hacking** o data mining: si se prueban suficientes especificaciones, eventualmente se encontrará una con $p < 0.05$ por pura aleatoriedad. Con nivel de significancia del 5%, se esperan rechazos espurios en 1 de cada 20 tests bajo $H_0$.

Las prácticas que mitigan este problema incluyen: pre-registrar la especificación del modelo antes de ver los datos, usar correcciones para tests múltiples (Bonferroni, Benjamini-Hochberg), reportar todos los tests realizados, y distinguir entre análisis confirmatorio (hipótesis establecidas a priori) y exploratorio.

---

## 8. El teorema de Frisch-Waugh-Lovell

El **teorema de Frisch-Waugh-Lovell (FWL)** es uno de los resultados más útiles del álgebra de la regresión. Establece que el estimador MCO de $\boldsymbol{\beta}_1$ en el modelo:

$$\mathbf{y} = \mathbf{X}_1\boldsymbol{\beta}_1 + \mathbf{X}_2\boldsymbol{\beta}_2 + \boldsymbol{\varepsilon}$$

es numéricamente idéntico al estimador MCO de $\boldsymbol{\beta}_1$ en la regresión de los residuos de $\mathbf{y}$ sobre $\mathbf{X}_2$ en los residuos de $\mathbf{X}_1$ sobre $\mathbf{X}_2$:

$$\mathbf{M}_2\mathbf{y} = \mathbf{M}_2\mathbf{X}_1\boldsymbol{\beta}_1 + \text{error}$$

donde $\mathbf{M}_2 = \mathbf{I} - \mathbf{X}_2(\mathbf{X}_2'\mathbf{X}_2)^{-1}\mathbf{X}_2'$ es la matriz de proyección ortogonal sobre el complemento del espacio de $\mathbf{X}_2$.

El FWL tiene tres implicancias importantes:

1. **Los controles "limpian" los regresores de interés:** incluir $\mathbf{X}_2$ como control equivale a remover la variación de $\mathbf{X}_1$ explicada por $\mathbf{X}_2$. Los coeficientes de MCO miden el efecto de la variación en $\mathbf{X}_1$ que es ortogonal a $\mathbf{X}_2$.

2. **El estimador de efectos fijos es MCO en desviaciones:** en datos de panel con efecto fijo de unidad $\alpha_i$, el estimador de efectos fijos equivale a MCO en la regresión "demeaned" — donde $\mathbf{X}_2$ es la matriz de dummies de unidad. El FWL garantiza que esto produce el mismo resultado que la regresión directa con las dummies.

3. **Interpretación de la multicolinealidad:** el FWL muestra que $\hat{\beta}_{1j}$ se identifica por la variación en $X_{1j}$ no explicada por los demás regresores — si $R_j^2 \to 1$, esa variación desaparece y la varianza de $\hat{\beta}_{1j}$ diverge.

---

## 9. Síntesis: taxonomía de problemas de especificación

| Problema | Supuesto violado | Consecuencia para MCO | Solución |
|---|---|---|---|
| **Omisión de variable relevante** | GM4 ($E[\varepsilon|X]\neq 0$) | Sesgo e inconsistencia | Incluir variable, proxy, IV, EF |
| **Inclusión de irrelevante** | Ninguno formalmente | Pérdida de eficiencia (SE más grandes) | Parsimonia, criterios de información |
| **Multicolinealidad** | Ninguno (aproximación de GM3) | SE inflados, t-stats pequeños | Más datos, combinar variables, regularización |
| **Error de medición en $Y$** | Ninguno | Solo mayor varianza del error | Mejor medición |
| **Error de medición en $X$** | GM4 (atenuación) | Sesgo hacia cero, inconsistencia | Variables instrumentales |
| **Cambio estructural** | Constancia de $\boldsymbol{\beta}$ | Estimadores "promedio" inválidos | Test de Chow, modelos separados, dummies |
| **Forma funcional incorrecta** | GM1 | Sesgo en todo el rango | Transformaciones, test RESET |

---

## Referencias

- Wooldridge, J.M. (2008). *Introductory Econometrics*. Thomson. Caps. 6–9.
- Greene, W.H. (2011). *Econometric Analysis*. Prentice Hall. Caps. 5–8.
- Johnston, J. & DiNardo, J. (2001). *Métodos de Econometría*. Vicens Vives.
- Chow, G. (1960). *Tests of Equality between Sets of Coefficients in Two Linear Regressions*. Econometrica.
- Ramsey, J.B. (1969). *Tests for Specification Errors in Classical Linear Least-Squares Regression Analysis*. Journal of the Royal Statistical Society B.
- Frisch, R. & Waugh, F. (1933). *Partial Time Regressions as Compared with Individual Trends*. Econometrica.
- Lovell, M. (1963). *Seasonal Adjustment of Economic Time Series*. JASA.
- Stock, J.H. & Watson, M.W. (2006). *Introduction to Econometrics*. Pearson. Caps. 6–8.