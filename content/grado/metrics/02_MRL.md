---
title: "El Modelo de Regresión Lineal (MRL) como Modelo Probabilístico"
date: 2026-03-15
draft: false
tags: ["econometría", "MCO", "Gauss-Markov", "BLUE", "inferencia", "predicción", "EAE2510"]
description: "Supuestos del MRL, derivación y propiedades del estimador MCO, teorema de Gauss-Markov, inferencia estadística, bondad de ajuste y predicción."
---

**Cursos:** Econometría (EAE2510) · Inferencia Estadística (EAA1520)  
**Referencia principal:** Wooldridge (2008) caps. 2–4 · Johnston & DiNardo (2001) · Greene (2011) caps. 2–4

---

## 1. El modelo de regresión lineal múltiple

### 1.1 La ecuación del modelo

El **modelo de regresión lineal múltiple (MRL)** especifica una relación lineal entre una variable dependiente $Y$ y $K$ variables independientes $X_1, \ldots, X_K$:

$$Y_i = \beta_0 + \beta_1 X_{1i} + \beta_2 X_{2i} + \cdots + \beta_K X_{Ki} + \varepsilon_i, \quad i = 1, \ldots, n$$

En notación matricial, con $\mathbf{y} = (Y_1, \ldots, Y_n)'$, $\mathbf{X}$ la matriz $n \times (K+1)$ de regresores (incluyendo una columna de unos para el intercepto), $\boldsymbol{\beta} = (\beta_0, \ldots, \beta_K)'$ el vector de parámetros y $\boldsymbol{\varepsilon} = (\varepsilon_1, \ldots, \varepsilon_n)'$ el vector de errores:

$$\mathbf{y} = \mathbf{X}\boldsymbol{\beta} + \boldsymbol{\varepsilon}$$

El término de error $\varepsilon_i$ captura todos los determinantes de $Y_i$ que no están incluidos en el modelo: factores omitidos, no observables, errores de medición y aleatoriedad inherente. Es el componente que hace al modelo **probabilístico** — sin él, la regresión sería una identidad algebraica exacta.

### 1.2 Interpretación de los coeficientes

El coeficiente $\beta_j$ tiene la interpretación de **efecto ceteris paribus**: el cambio en $E[Y]$ asociado a un incremento unitario en $X_j$, manteniendo constantes todas las demás variables del modelo:

$$\beta_j = \frac{\partial E[Y | \mathbf{X}]}{\partial X_j}$$

Esta interpretación es válida bajo los supuestos del modelo. El intercepto $\beta_0$ es el valor esperado de $Y$ cuando todos los regresores son cero — frecuentemente no tiene interpretación sustantiva directa.

La **linealidad en parámetros** no requiere que la relación entre $Y$ y los $X$ sea lineal en las variables. Transformaciones como $\ln Y$, $X^2$, $X_1 \cdot X_2$ son perfectamente admisibles:

| Especificación | Interpretación de $\beta_1$ |
|---|---|
| $Y = \beta_0 + \beta_1 X + \varepsilon$ | Cambio absoluto en $Y$ por unidad de $X$ |
| $\ln Y = \beta_0 + \beta_1 X + \varepsilon$ | Cambio porcentual en $Y$ por unidad de $X$ (semielasticidad) |
| $\ln Y = \beta_0 + \beta_1 \ln X + \varepsilon$ | Elasticidad: cambio % en $Y$ por 1% de cambio en $X$ |
| $Y = \beta_0 + \beta_1 X + \beta_2 X^2 + \varepsilon$ | Efecto marginal variable: $\partial Y/\partial X = \beta_1 + 2\beta_2 X$ |

---

## 2. Los supuestos del modelo clásico

Los supuestos de Gauss-Markov (GM) son las condiciones bajo las cuales el estimador MCO tiene propiedades óptimas. Se enuncian en dos versiones según el tratamiento de los regresores.

### 2.1 Los supuestos (formulación condicional en $\mathbf{X}$)

**GM1 — Linealidad en parámetros:** $\mathbf{y} = \mathbf{X}\boldsymbol{\beta} + \boldsymbol{\varepsilon}$ con el verdadero proceso generador de datos siendo lineal en $\boldsymbol{\beta}$.

**GM2 — Muestreo aleatorio:** las observaciones $(Y_i, \mathbf{X}_i)$ son una muestra aleatoria de la población de interés. En datos de corte transversal, garantiza que los errores son independientes entre observaciones.

**GM3 — Rango completo (no multicolinealidad perfecta):** $\text{rank}(\mathbf{X}) = K+1$ — ninguna columna de $\mathbf{X}$ es combinación lineal exacta de las demás. Garantiza que $(\mathbf{X}'\mathbf{X})^{-1}$ existe y el estimador MCO está bien definido.

**GM4 — Media condicional cero (exogeneidad):** 

$$E[\varepsilon_i | \mathbf{X}] = 0 \quad \forall i$$

Este es el supuesto más importante para la **insesgadez**. Implica que los regresores no están correlacionados con el error: $\text{Cov}(X_{ji}, \varepsilon_i) = 0$ para todo $j$. Cuando se viola — por variables omitidas, simultaneidad o errores de medición en los regresores — el estimador MCO es **sesgado e inconsistente**.

**GM5 — Errores esféricos (homocedasticidad y no autocorrelación):**

$$\text{Var}(\boldsymbol{\varepsilon} | \mathbf{X}) = \sigma^2 \mathbf{I}_n$$

Descompuesto: (a) $\text{Var}(\varepsilon_i | \mathbf{X}) = \sigma^2$ para todo $i$ (homocedasticidad); (b) $\text{Cov}(\varepsilon_i, \varepsilon_j | \mathbf{X}) = 0$ para $i \neq j$ (no autocorrelación). Cuando se viola, MCO sigue siendo insesgado pero ineficiente, y los errores estándar usuales son incorrectos.

**GM6 — Normalidad (opcional para inferencia en muestras pequeñas):**

$$\boldsymbol{\varepsilon} | \mathbf{X} \sim \mathcal{N}(\mathbf{0}, \sigma^2 \mathbf{I}_n)$$

Permite derivar distribuciones exactas de los estadísticos de prueba en muestras finitas. No es necesaria para las propiedades asintóticas del estimador.

---

## 3. El estimador de mínimos cuadrados ordinarios (MCO)

### 3.1 El principio de mínimos cuadrados

El estimador MCO minimiza la **suma de cuadrados de los residuos (SCR)**:

$$\hat{\boldsymbol{\beta}}_{MCO} = \arg\min_{\boldsymbol{b}} \sum_{i=1}^n (Y_i - \mathbf{X}_i'\boldsymbol{b})^2 = \arg\min_{\boldsymbol{b}} (\mathbf{y} - \mathbf{X}\boldsymbol{b})'(\mathbf{y} - \mathbf{X}\boldsymbol{b})$$

El residuo $\hat{\varepsilon}_i = Y_i - \hat{Y}_i = Y_i - \mathbf{X}_i'\hat{\boldsymbol{\beta}}$ es la diferencia entre el valor observado y el valor ajustado. MCO minimiza la suma de cuadrados de estos residuos.

### 3.2 Derivación matricial

Las condiciones de primer orden (ecuaciones normales):

$$\frac{\partial SCR}{\partial \boldsymbol{b}} = -2\mathbf{X}'(\mathbf{y} - \mathbf{X}\boldsymbol{b}) = \mathbf{0}$$

$$\mathbf{X}'\mathbf{X}\hat{\boldsymbol{\beta}} = \mathbf{X}'\mathbf{y}$$

Bajo GM3 ($\mathbf{X}'\mathbf{X}$ invertible):

$$\boxed{\hat{\boldsymbol{\beta}}_{MCO} = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{y}}$$

Esta es la fórmula matricial del estimador MCO. Para el caso simple con dos variables, se reduce a:

$$\hat{\beta}_1 = \frac{\sum_i (X_i - \bar{X})(Y_i - \bar{Y})}{\sum_i (X_i - \bar{X})^2} = \frac{\widehat{\text{Cov}}(X, Y)}{\widehat{\text{Var}}(X)}$$

El estimador MCO es la covarianza muestral entre $X$ e $Y$ dividida por la varianza muestral de $X$ — la pendiente de la línea que mejor ajusta los datos en el sentido de mínima suma de cuadrados.

### 3.3 Propiedades algebraicas de los residuos MCO

Las ecuaciones normales implican propiedades algebraicas exactas de los residuos $\hat{\boldsymbol{\varepsilon}} = \mathbf{y} - \mathbf{X}\hat{\boldsymbol{\beta}}$:

$$\mathbf{X}'\hat{\boldsymbol{\varepsilon}} = \mathbf{0}$$

En particular: (a) la suma de residuos es cero: $\sum_i \hat{\varepsilon}_i = 0$ (si hay intercepto); (b) la correlación muestral entre cada regresor y los residuos es cero: $\sum_i X_{ji}\hat{\varepsilon}_i = 0$ para todo $j$.

Estas son **condiciones de momento muestrales** — el análogo muestral del supuesto $E[\varepsilon_i | \mathbf{X}] = 0$. Se satisfacen por construcción en cualquier regresión MCO, independiente de si los supuestos del modelo son válidos.

---

## 4. Propiedades del estimador MCO

### 4.1 Propiedades de muestras finitas

**Insesgadez (GM1–GM4):**

$$E[\hat{\boldsymbol{\beta}}_{MCO} | \mathbf{X}] = \boldsymbol{\beta}$$

Prueba: $\hat{\boldsymbol{\beta}} = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{y} = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'(\mathbf{X}\boldsymbol{\beta} + \boldsymbol{\varepsilon}) = \boldsymbol{\beta} + (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\boldsymbol{\varepsilon}$.

Tomando esperanza condicional en $\mathbf{X}$ y usando GM4: $E[(\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\boldsymbol{\varepsilon} | \mathbf{X}] = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}' E[\boldsymbol{\varepsilon}|\mathbf{X}] = \mathbf{0}$. $\blacksquare$

La insesgadez depende fundamentalmente de GM4 — si $E[\varepsilon_i|\mathbf{X}] \neq 0$, el estimador MCO es sesgado. Ninguna cantidad de datos puede corregir el sesgo si el supuesto de exogeneidad falla.

**Matriz de varianza-covarianza (GM1–GM5):**

$$\text{Var}(\hat{\boldsymbol{\beta}}_{MCO} | \mathbf{X}) = \sigma^2(\mathbf{X}'\mathbf{X})^{-1}$$

Prueba: $\text{Var}(\hat{\boldsymbol{\beta}}|\mathbf{X}) = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}' \text{Var}(\boldsymbol{\varepsilon}|\mathbf{X}) \mathbf{X}(\mathbf{X}'\mathbf{X})^{-1} = \sigma^2(\mathbf{X}'\mathbf{X})^{-1}$ usando GM5.

La varianza del estimador depende de: (a) $\sigma^2$ — la varianza del error de la población; (b) $(\mathbf{X}'\mathbf{X})^{-1}$ — la variación en los regresores. Más variación en $X$ → menor varianza del estimador → estimaciones más precisas.

**Estimación de $\sigma^2$:**

$$s^2 = \frac{\hat{\boldsymbol{\varepsilon}}'\hat{\boldsymbol{\varepsilon}}}{n - K - 1} = \frac{SCR}{n-K-1}$$

El divisor $n-K-1$ (grados de libertad) corrige el sesgo que resultaría de usar $n$ — los residuos MCO son construidos para minimizar $SCR$, lo que tiende a subestimar $\sigma^2$ si se divide por $n$.

### 4.2 El Teorema de Gauss-Markov: BLUE

El teorema de Gauss-Markov establece que el estimador MCO tiene la menor varianza muestral dentro de la clase de estimadores lineales e insesgados, si los errores son no correlacionados, tienen igual varianza y esperanza cero. 

**Teorema (Gauss-Markov):** Bajo GM1–GM5, el estimador MCO $\hat{\boldsymbol{\beta}}_{MCO}$ es el **estimador lineal insesgado de mínima varianza (BLUE)** de $\boldsymbol{\beta}$.

El teorema de Gauss-Markov establece que si el modelo de regresión lineal satisface los primeros seis supuestos clásicos, entonces la regresión MCO produce estimaciones insesgadas que tienen la menor varianza de todos los posibles estimadores lineales. 

El acrónimo BLUE descompone el resultado:
- **B (Best):** mínima varianza entre todos los estimadores lineales e insesgados.
- **L (Linear):** el estimador es lineal en $\mathbf{y}$: $\hat{\boldsymbol{\beta}} = \mathbf{C}\mathbf{y}$ para alguna matriz $\mathbf{C}$.
- **U (Unbiased):** $E[\hat{\boldsymbol{\beta}}] = \boldsymbol{\beta}$.
- **E (Estimator):** es un estimador del parámetro poblacional $\boldsymbol{\beta}$.

OLS es BLUE si y solo si cualquier combinación lineal de los coeficientes de regresión es estimada más precisamente por OLS que por cualquier otro estimador lineal insesgado. 

**Prueba sketch:** Sea $\tilde{\boldsymbol{\beta}} = \mathbf{C}\mathbf{y}$ cualquier otro estimador lineal e insesgado. Definir $\mathbf{D} = \mathbf{C} - (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'$. La insesgadez requiere $\mathbf{D}\mathbf{X} = \mathbf{0}$. La varianza de $\tilde{\boldsymbol{\beta}}$ es:

$$\text{Var}(\tilde{\boldsymbol{\beta}}|\mathbf{X}) = \sigma^2\mathbf{C}\mathbf{C}' = \sigma^2[(\mathbf{X}'\mathbf{X})^{-1} + \mathbf{D}\mathbf{D}']$$

Como $\mathbf{D}\mathbf{D}'$ es positiva semidefinida, $\text{Var}(\tilde{\boldsymbol{\beta}}|\mathbf{X}) \geq \text{Var}(\hat{\boldsymbol{\beta}}_{MCO}|\mathbf{X})$ en sentido matricial. $\blacksquare$

**Alcance y limitaciones del teorema:**

El teorema de Gauss-Markov establece optimalidad solo dentro de la clase de estimadores lineales e insesgados, que es bastante restrictiva. Dependiendo de la distribución de los errores, otros estimadores no lineales pueden dar mejores resultados que OLS. 

Si también se invoca el supuesto de normalidad, entonces los estimadores OLS se convierten en "mejores" entre todos los estimadores insesgados (tanto lineales como no lineales). 

Esto conecta con el resultado de que bajo normalidad, MCO = MLE, y el estimador MCO alcanza la cota de Cramér-Rao — es eficiente en la clase de todos los estimadores insesgados.

### 4.3 Propiedades asintóticas (sin normalidad)

En muestras grandes, pueden establecerse propiedades bajo supuestos más débiles:

**Consistencia:** bajo GM1–GM4 y condiciones de regularidad:

$$\hat{\boldsymbol{\beta}}_{MCO} \xrightarrow{p} \boldsymbol{\beta}$$

La convergencia en probabilidad requiere que $\frac{1}{n}\mathbf{X}'\mathbf{X} \xrightarrow{p} \mathbf{Q}_{XX}$ (matriz definida positiva) y $\frac{1}{n}\mathbf{X}'\boldsymbol{\varepsilon} \xrightarrow{p} \mathbf{0}$. La segunda condición se satisface bajo exogeneidad y condiciones de momentos finitos.

**Normalidad asintótica:** por el Teorema Central del Límite:

$$\sqrt{n}(\hat{\boldsymbol{\beta}}_{MCO} - \boldsymbol{\beta}) \xrightarrow{d} \mathcal{N}(\mathbf{0}, \mathbf{Q}_{XX}^{-1}\boldsymbol{\Omega}\mathbf{Q}_{XX}^{-1})$$

donde $\boldsymbol{\Omega} = E[\varepsilon_i^2 \mathbf{X}_i\mathbf{X}_i']$. Bajo homocedasticidad, $\boldsymbol{\Omega} = \sigma^2 \mathbf{Q}_{XX}$ y la varianza asintótica simplifica a $\sigma^2\mathbf{Q}_{XX}^{-1}$ — consistente con la fórmula de muestras finitas.

La normalidad asintótica justifica el uso de los estadísticos $t$ y $F$ en muestras grandes incluso sin suponer normalidad de los errores.

---

## 5. Inferencia estadística

### 5.1 Distribución del estimador bajo normalidad

Bajo GM1–GM6 ($\boldsymbol{\varepsilon}|\mathbf{X} \sim \mathcal{N}(\mathbf{0}, \sigma^2\mathbf{I})$):

$$\hat{\boldsymbol{\beta}}_{MCO} | \mathbf{X} \sim \mathcal{N}(\boldsymbol{\beta}, \sigma^2(\mathbf{X}'\mathbf{X})^{-1})$$

Para el coeficiente $j$-ésimo:

$$\hat{\beta}_j | \mathbf{X} \sim \mathcal{N}(\beta_j, \sigma^2 [(\mathbf{X}'\mathbf{X})^{-1}]_{jj})$$

El **error estándar** de $\hat{\beta}_j$ es $se(\hat{\beta}_j) = s\sqrt{[(\mathbf{X}'\mathbf{X})^{-1}]_{jj}}$, donde $s = \sqrt{SCR/(n-K-1)}$.

### 5.2 El estadístico $t$

Para probar $H_0: \beta_j = \beta_j^0$ (típicamente $\beta_j^0 = 0$):

$$t_j = \frac{\hat{\beta}_j - \beta_j^0}{se(\hat{\beta}_j)} \sim t_{n-K-1} \quad \text{bajo } H_0$$

La distribución $t$ con $n-K-1$ grados de libertad emerge porque $s^2$ es aleatorio (no conocemos $\sigma^2$). Para $n$ grande, $t_{n-K-1} \approx \mathcal{N}(0,1)$.

**Regla de decisión:** rechazar $H_0$ si $|t_j| > t_{\alpha/2, n-K-1}$ (prueba bilateral) o $t_j > t_{\alpha, n-K-1}$ (prueba unilateral), donde $\alpha$ es el nivel de significancia.

**El $p$-valor:** la probabilidad de observar un estadístico tan extremo o más extremo que el observado, bajo $H_0$. Un $p$-valor pequeño (< $\alpha$) es evidencia en contra de $H_0$. El $p$-valor no mide la magnitud del efecto ni su relevancia económica.

### 5.3 El estadístico $F$: restricciones lineales múltiples

Para probar $q$ restricciones lineales simultáneamente: $H_0: \mathbf{R}\boldsymbol{\beta} = \mathbf{r}$ (donde $\mathbf{R}$ es $q \times (K+1)$ y $\mathbf{r}$ es $q \times 1$):

$$F = \frac{(SCR_R - SCR_U)/q}{SCR_U/(n-K-1)} \sim F_{q, n-K-1} \quad \text{bajo } H_0$$

donde $SCR_R$ es la SCR del modelo restringido y $SCR_U$ la del irrestricto. El estadístico $F$ mide cuánto empeora el ajuste al imponer las restricciones, ponderado por los grados de libertad.

El **F global** (donde $H_0: \beta_1 = \cdots = \beta_K = 0$) contrasta si el modelo explica alguna variación en $Y$ más allá del promedio:

$$F = \frac{SCE/K}{SCR/(n-K-1)} = \frac{R^2/K}{(1-R^2)/(n-K-1)}$$

### 5.4 Intervalos de confianza

Un intervalo de confianza al $(1-\alpha)\times 100\%$ para $\beta_j$:

$$\hat{\beta}_j \pm t_{\alpha/2, n-K-1} \cdot se(\hat{\beta}_j)$$

El intervalo de confianza contiene al verdadero $\beta_j$ en el $(1-\alpha)\times 100\%$ de las muestras hipotéticas posibles — es una propiedad del procedimiento, no una afirmación sobre la probabilidad de que $\beta_j$ esté en el intervalo calculado para una muestra específica.

---

## 6. Bondad de ajuste

### 6.1 La descomposición de la varianza total

La identidad de descomposición:

$$\underbrace{\sum_i (Y_i - \bar{Y})^2}_{SCT} = \underbrace{\sum_i (\hat{Y}_i - \bar{Y})^2}_{SCE} + \underbrace{\sum_i \hat{\varepsilon}_i^2}_{SCR}$$

La suma de cuadrados total (SCT) se descompone como la suma cuadrada explicada (SCE) más la suma cuadrada de residuos (SCR). 

Esta descomposición es exacta y se sostiene por construcción en cualquier regresión MCO con intercepto (porque $\sum_i \hat{\varepsilon}_i(\hat{Y}_i - \bar{Y}) = 0$ por las ecuaciones normales).

### 6.2 El coeficiente de determinación $R^2$

$$R^2 = \frac{SCE}{SCT} = 1 - \frac{SCR}{SCT} \in [0, 1]$$

El $R^2$ mide la fracción de la variación total de $Y$ explicada por el modelo. Equivale al cuadrado de la correlación entre $Y$ y $\hat{Y}$.

**Limitaciones del $R^2$:**
- Siempre aumenta (o se mantiene) al agregar regresores, aunque sean irrelevantes — no es válido para comparar modelos con distinto número de regresores.
- Un $R^2$ alto no garantiza causalidad ni ausencia de sesgo.
- El $R^2$ no mide si los coeficientes son estimados con precisión ni si los supuestos se cumplen.

### 6.3 El $R^2$ ajustado

El **$R^2$ ajustado** penaliza por el número de regresores:

$$\bar{R}^2 = 1 - \frac{SCR/(n-K-1)}{SCT/(n-1)} = 1 - (1-R^2)\frac{n-1}{n-K-1}$$

Puede disminuir al agregar un regresor si la reducción en $SCR$ no compensa el costo de un grado de libertad adicional. Es la métrica estándar para comparar modelos anidados.

---

## 7. Predicción

### 7.1 Predicción puntual

Dado un nuevo vector de regresores $\mathbf{X}_0$, la predicción puntual es:

$$\hat{Y}_0 = \mathbf{X}_0'\hat{\boldsymbol{\beta}}$$

Es un estimador insesgado de $E[Y_0|\mathbf{X}_0] = \mathbf{X}_0'\boldsymbol{\beta}$ bajo los supuestos del modelo.

### 7.2 El error de predicción y sus componentes

El error de predicción $\hat{Y}_0 - Y_0$ tiene dos fuentes:

$$\hat{Y}_0 - Y_0 = \mathbf{X}_0'(\hat{\boldsymbol{\beta}} - \boldsymbol{\beta}) - \varepsilon_0$$

1. **Error de estimación:** $\mathbf{X}_0'(\hat{\boldsymbol{\beta}} - \boldsymbol{\beta})$ — incertidumbre sobre $\boldsymbol{\beta}$.
2. **Error estocástico:** $\varepsilon_0$ — aleatoriedad del proceso generador de datos.

La varianza del error de predicción es:

$$\text{Var}(\hat{Y}_0 - Y_0 | \mathbf{X}) = \sigma^2[1 + \mathbf{X}_0'(\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}_0]$$

El factor $\mathbf{X}_0'(\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}_0$ es la contribución del error de estimación — es mayor cuando $\mathbf{X}_0$ está lejos del centro de la nube de datos (extrapolación).

### 7.3 Intervalo de predicción vs. intervalo de confianza para la media

El **intervalo de predicción** al $(1-\alpha)\%$ para un valor individual $Y_0$:

$$\hat{Y}_0 \pm t_{\alpha/2, n-K-1} \cdot s\sqrt{1 + \mathbf{X}_0'(\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}_0}$$

El **intervalo de confianza para la media condicional** $E[Y_0|\mathbf{X}_0]$:

$$\hat{Y}_0 \pm t_{\alpha/2, n-K-1} \cdot s\sqrt{\mathbf{X}_0'(\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}_0}$$

El intervalo de predicción es siempre más ancho que el de confianza porque incorpora adicionalmente la varianza del error idiosincrático $\varepsilon_0$ — predecir un valor individual es más incierto que estimar la media condicional.

---

## 8. MCO como estimador GMM

El estimador MCO puede interpretarse como un caso especial del método generalizado de momentos (GMM). Las condiciones de momento que MCO satisface son:

$$E[\mathbf{X}_i \varepsilon_i] = E[\mathbf{X}_i(Y_i - \mathbf{X}_i'\boldsymbol{\beta})] = \mathbf{0}$$

Estas $K+1$ condiciones de momento (una por regresor) son exactamente identificadas — hay el mismo número de condiciones que de parámetros. El estimador MCO es el estimador GMM con estas condiciones de momento.

Esta perspectiva es útil porque generaliza directamente a estimadores con más condiciones de momento que parámetros (GMM sobreidentificado, usado en variables instrumentales) y hace explícito que MCO es consistente si y solo si $E[\mathbf{X}_i \varepsilon_i] = \mathbf{0}$ — la condición de exogeneidad.

---

## 9. Síntesis: propiedades bajo distintos supuestos

| Propiedad | Supuestos requeridos | Falla si... |
|---|---|---|
| **Insesgadez** | GM1–GM4 | $E[\varepsilon|\mathbf{X}] \neq 0$ (endogeneidad, omisión) |
| **Varianza $\sigma^2(\mathbf{X}'\mathbf{X})^{-1}$** | GM1–GM5 | Heterocedasticidad o autocorrelación |
| **BLUE (Gauss-Markov)** | GM1–GM5 | Cualquier violación de GM5 |
| **Distribución exacta $t$, $F$** | GM1–GM6 | No normalidad (corregible asintóticamente) |
| **Consistencia** | GM1–GM4 + regularidad | $\text{plim}(\frac{1}{n}\mathbf{X}'\boldsymbol{\varepsilon}) \neq \mathbf{0}$ |
| **Normalidad asintótica** | GM1–GM4 + regularidad | Distribuciones de colas muy pesadas |

---

## Referencias

- Wooldridge, J.M. (2008). *Introductory Econometrics*. Thomson. Caps. 2–4.
- Greene, W.H. (2011). *Econometric Analysis*. 7ma ed. Prentice Hall. Caps. 2–4.
- Johnston, J. & DiNardo, J. (2001). *Métodos de Econometría*. Vicens Vives. Caps. 1–3.
- Stock, J.H. & Watson, M.W. (2006). *Introduction to Econometrics*. Pearson. Caps. 4–7.
- Gauss, C.F. (1823). *Theoria Combinationis Observationum Erroribus Minimis Obnoxiae*. Göttingen.
- Markov, A.A. (1900). *Wahrscheinlichkeitsrechnung*. Leipzig.
- Hansen, B. (2022). *Econometrics*. Princeton University Press. Caps. 3–5.