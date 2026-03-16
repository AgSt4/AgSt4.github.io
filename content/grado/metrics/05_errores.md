---
title: "Heterocedasticidad y Dependencia de los Errores"
date: 2026-03-15
draft: false
tags: ["econometría", "heterocedasticidad", "autocorrelación", "GLS", "FGLS", "errores robustos", "Newey-West", "EAE2510"]
description: "Causas y consecuencias de la heterocedasticidad y autocorrelación, tests de diagnóstico, mínimos cuadrados generalizados, errores estándar robustos HAC e inferencia robusta."
---

**Cursos:** Econometría (EAE2510) · Macroeconometría Aplicada (EAE3102)  
**Referencia principal:** Wooldridge (2008) caps. 8, 12 · Greene (2011) caps. 9–10 · Johnston & DiNardo (2001)

---

## 1. El supuesto de errores esféricos y sus violaciones

El teorema de Gauss-Markov requiere que $\text{Var}(\boldsymbol{\varepsilon}|\mathbf{X}) = \sigma^2\mathbf{I}_n$ — la **condición de esfericidad**. Este supuesto tiene dos componentes:

- **Homocedasticidad:** $\text{Var}(\varepsilon_i|\mathbf{X}) = \sigma^2$ para todo $i$ — varianza constante.
- **No autocorrelación:** $\text{Cov}(\varepsilon_i, \varepsilon_j|\mathbf{X}) = 0$ para $i \neq j$ — no correlación entre errores.

Cuando se viola, la estructura de la matriz de varianza-covarianza es:

$$\text{Var}(\boldsymbol{\varepsilon}|\mathbf{X}) = \sigma^2\boldsymbol{\Omega} \neq \sigma^2\mathbf{I}_n$$

donde $\boldsymbol{\Omega}$ es una matriz positiva definida no necesariamente diagonal o escalar. Las dos violaciones tienen nombres distintos:

- **Heterocedasticidad:** $\boldsymbol{\Omega} = \text{diag}(\omega_1, \ldots, \omega_n)$ con $\omega_i$ no constante — diagonal pero heterogénea.
- **Autocorrelación:** elementos fuera de la diagonal de $\boldsymbol{\Omega}$ son no nulos — correlación entre observaciones.

---

## 2. Heterocedasticidad

### 2.1 Definición y causas

La **heterocedasticidad** ocurre cuando la varianza del error depende de los regresores o de otras variables:

$$\text{Var}(\varepsilon_i | \mathbf{X}_i) = \sigma_i^2 \neq \sigma^2$$

Las causas son variadas y frecuentemente identificables:

- **Escala de las unidades:** empresas grandes tienen mayor variabilidad en ventas que pequeñas. Datos de hogares ricos tienen mayor varianza en consumo.
- **Aprendizaje y mejora:** la variabilidad de errores disminuye conforme las unidades acumulan experiencia (modelos de producción).
- **Variables omitidas heterogéneas:** si las variables omitidas afectan más a algunas observaciones que a otras.
- **Datos combinados de subpoblaciones:** si se juntan grupos con distintas varianzas intrínsecas.
- **Transformación de modelos multiplicativos:** si el verdadero modelo es $Y = e^{\beta_0 + \beta_1 X + \varepsilon}$ y se estima la versión lineal.

### 2.2 Consecuencias sobre MCO

La heterocedasticidad viola la suposición de varianza constante, lo que hace que el estimador MCO pierda eficiencia — deja de ser el estimador lineal insesgado de mínima varianza (BLUE). Esto lleva a errores estándar sesgados y complicaciones en el contraste de hipótesis. 

Precisamente:

**MCO sigue siendo insesgado y consistente** bajo heterocedasticidad si GM4 ($E[\varepsilon|\mathbf{X}]=0$) se mantiene — la heterocedasticidad no afecta la insesgadez ni la consistencia del estimador.

**MCO deja de ser BLUE** — ya no tiene la menor varianza entre estimadores lineales e insesgados.

**Los errores estándar usuales son incorrectos:** la fórmula $s^2(\mathbf{X}'\mathbf{X})^{-1}$ asume homocedasticidad. Bajo heterocedasticidad, la verdadera varianza del estimador es:

$$\text{Var}(\hat{\boldsymbol{\beta}}_{MCO}|\mathbf{X}) = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\boldsymbol{\Sigma}\mathbf{X}(\mathbf{X}'\mathbf{X})^{-1}$$

donde $\boldsymbol{\Sigma} = \text{diag}(\sigma_1^2, \ldots, \sigma_n^2)$. Los errores estándar usuales pueden subestimar o sobreestimar esta varianza, haciendo los estadísticos $t$ y $F$ inválidos.

### 2.3 Detección: tests de heterocedasticidad

#### Test de Breusch-Pagan (1979)

El test de Breusch-Pagan examina si la varianza de los residuos depende de las variables independientes. La hipótesis nula es homocedasticidad; la alternativa es que la varianza depende linealmente de los regresores. 

**Procedimiento:**

1. Estimar el modelo por MCO y obtener los residuos $\hat{\varepsilon}_i$.
2. Regresar $\hat{\varepsilon}_i^2$ en los regresores (o en un subconjunto de ellos):
$$\hat{\varepsilon}_i^2 = \alpha_0 + \alpha_1 X_{1i} + \cdots + \alpha_K X_{Ki} + u_i$$
3. El estadístico $LM = nR^2_{\text{aux}} \sim \chi^2(K)$ bajo $H_0$.

Rechazar $H_0$ implica heterocedasticidad del tipo modelado en la regresión auxiliar.

#### Test de White (1980)

El test de White es más general — no asume una forma funcional específica de la heterocedasticidad. La regresión auxiliar incluye cuadrados e interacciones de todos los regresores:

$$\hat{\varepsilon}_i^2 = \alpha_0 + \sum_j \alpha_j X_{ji} + \sum_j \alpha_{jj} X_{ji}^2 + \sum_{j<k} \alpha_{jk} X_{ji}X_{ki} + u_i$$

El estadístico $nR^2_{\text{aux}} \sim \chi^2(p)$ donde $p$ es el número de regresores en la regresión auxiliar. El test de White es más potente que Breusch-Pagan contra formas generales de heterocedasticidad pero consume más grados de libertad.

**Versión simplificada:** regresar $\hat{\varepsilon}_i^2$ en $\hat{Y}_i$ y $\hat{Y}_i^2$ — captura la mayoría de las formas comunes de heterocedasticidad con solo 2 grados de libertad.

En Stata: `estat hettest` (Breusch-Pagan), `estat imtest, white` (White).

### 2.4 Solución 1: errores estándar robustos de White (HC)

La solución más simple y robusta es mantener el estimador MCO pero corregir los errores estándar para que sean válidos bajo heterocedasticidad de forma desconocida.

Bajo heterocedasticidad, se puede seguir usando el estimador MCO ineficiente pero corregir los errores estándar usando errores estándar heteroscedasticidad-consistentes (HC), también llamados errores robustos o errores estándar de White. Estos son los más comunes y fáciles de implementar. 

El estimador de varianza robusto de White:

$$\widehat{\text{Var}}_{HC}(\hat{\boldsymbol{\beta}}_{MCO}) = (\mathbf{X}'\mathbf{X})^{-1}\left(\sum_i \hat{\varepsilon}_i^2 \mathbf{X}_i\mathbf{X}_i'\right)(\mathbf{X}'\mathbf{X})^{-1}$$

Este estimador es **consistente** bajo heterocedasticidad de cualquier forma desconocida. Las variantes HC0 (original de White), HC1, HC2, HC3 difieren en correcciones de muestras finitas — HC3 tiene mejores propiedades en muestras pequeñas.

En Stata: `regress y x1 x2, robust` o `vce(robust)`.

**La práctica moderna** es usar errores robustos por defecto en datos de corte transversal, como medida de precaución, independiente de si se rechaza o no la homocedasticidad. El costo es pequeño (SE ligeramente más grandes cuando los errores son homocedásticos); el beneficio es protección contra inferencia inválida cuando no lo son.

### 2.5 Solución 2: Mínimos Cuadrados Generalizados (MCG/GLS)

Si se conoce la forma de la heterocedasticidad ($\boldsymbol{\Omega}$ conocida), el MCG produce el estimador eficiente:

$$\hat{\boldsymbol{\beta}}_{MCG} = (\mathbf{X}'\boldsymbol{\Omega}^{-1}\mathbf{X})^{-1}\mathbf{X}'\boldsymbol{\Omega}^{-1}\mathbf{y}$$

El GLS hace OLS con las variables transformadas $\mathbf{y}^* = \mathbf{P}\mathbf{y}$ y $\mathbf{X}^* = \mathbf{P}\mathbf{X}$, donde $\mathbf{P} = \boldsymbol{\Omega}^{-1/2}$. Bajo las condiciones del modelo transformado, GLS es BLUE por el teorema de Gauss-Markov. 

**Mínimos Cuadrados Ponderados (WLS):** caso especial de MCG con heterocedasticidad multiplicativa $\sigma_i^2 = \sigma^2 h_i$. La transformación divide cada observación por $\sqrt{h_i}$ — observaciones con mayor varianza reciben menor peso. Si $h_i = X_i^2$, las observaciones con $X$ grande se ponderan menos.

El estimador WLS minimiza:

$$\sum_i \frac{(Y_i - \mathbf{X}_i'\boldsymbol{\beta})^2}{h_i}$$

### 2.6 Solución 3: MCG Factible (MCGF/FGLS)

En la práctica, $\boldsymbol{\Omega}$ es desconocida y debe estimarse. El **MCGF** sigue el procedimiento:

Si no conocemos el valor de $\sigma^2\boldsymbol{\Omega}$, podemos estimarlo. El FGLS usa MCO para obtener residuos, estima la estructura de la heterocedasticidad a partir de ellos, y luego aplica GLS con los pesos estimados. 

1. Estimar el modelo por MCO y obtener $\hat{\varepsilon}_i$.
2. Modelar la heterocedasticidad: regresionar $\ln(\hat{\varepsilon}_i^2)$ en los regresores → obtener $\hat{h}_i = \exp(\hat{g}_i)$.
3. Usar WLS con pesos $1/\hat{h}_i$.

El MCGF es consistente y asintóticamente más eficiente que MCO, pero tiene sesgo en muestras finitas por el error de estimación de $\boldsymbol{\Omega}$.

---

## 3. Autocorrelación

### 3.1 Definición y contexto

La **autocorrelación** (o correlación serial) ocurre cuando los errores de distintas observaciones están correlacionados:

$$\text{Cov}(\varepsilon_t, \varepsilon_{t-s}|\mathbf{X}) \neq 0 \quad \text{para } s \neq 0$$

Es especialmente relevante en **datos de series de tiempo** (donde la dependencia temporal es natural) y en **datos de panel** (donde las observaciones del mismo individuo en distintos períodos pueden estar correlacionadas). En datos de corte transversal puro es menos frecuente salvo con dependencia espacial.

### 3.2 El proceso AR(1): el caso estándar

El modelo de autocorrelación más frecuente es el proceso autorregresivo de orden 1:

$$\varepsilon_t = \rho \varepsilon_{t-1} + u_t, \quad ||\rho|| < 1, \quad u_t \sim \text{i.i.d.}(0, \sigma_u^2)$$

Las propiedades del proceso AR(1) estacionario:

$$E[\varepsilon_t] = 0, \quad \text{Var}(\varepsilon_t) = \frac{\sigma_u^2}{1-\rho^2}, \quad \text{Cov}(\varepsilon_t, \varepsilon_{t-s}) = \rho^s \frac{\sigma_u^2}{1-\rho^2}$$

La correlación decae geométricamente con el rezago $s$. Para $\rho > 0$ (autocorrelación positiva), los errores consecutivos tienen el mismo signo — típico en series macroeconómicas (inercia). Para $\rho < 0$ (autocorrelación negativa), los errores alternan signo — menos común.

### 3.3 Consecuencias sobre MCO

Las consecuencias son análogas a la heterocedasticidad:

- MCO sigue siendo **insesgado y consistente** (si GM4 se mantiene — exogeneidad estricta de los regresores).
- MCO **deja de ser BLUE** — no es eficiente.
- Los **errores estándar usuales son incorrectos** — típicamente los subestiman bajo autocorrelación positiva, generando estadísticos $t$ inflados y tasas de rechazo de $H_0$ mayores a las nominales.

La intuición: con autocorrelación positiva, observaciones consecutivas aportan información redundante — efectivamente hay menos observaciones "independientes" que $n$. Los errores estándar usuales asumen $n$ observaciones independientes y subestiman la varianza real.

### 3.4 Detección: tests de autocorrelación

#### Estadístico de Durbin-Watson

El estadístico de Durbin-Watson (DW) contrasta específicamente la autocorrelación de orden 1:

$$DW = \frac{\sum_{t=2}^n (\hat{\varepsilon}_t - \hat{\varepsilon}_{t-1})^2}{\sum_{t=1}^n \hat{\varepsilon}_t^2} \approx 2(1-\hat{\rho})$$

- $DW \approx 2$: sin autocorrelación ($\hat{\rho} \approx 0$).
- $DW < 2$: autocorrelación positiva ($\hat{\rho} > 0$).
- $DW > 2$: autocorrelación negativa ($\hat{\rho} < 0$).

Las tablas de Durbin-Watson proveen valores críticos $d_L$ y $d_U$: rechazar $H_0$ si $DW < d_L$ (positiva) o $DW > 4-d_L$ (negativa); zona de indeterminación si $d_L < DW < d_U$.

**Limitación:** el test DW no es válido cuando hay variables dependientes rezagadas como regresores — un caso muy frecuente en macroeconometría.

#### Test de Breusch-Godfrey (LM)

El test de Breusch-Godfrey (BG) es más general — contrasta autocorrelación de orden $p$ y es válido con rezagos de la variable dependiente como regresores:

1. Estimar por MCO y obtener $\hat{\varepsilon}_t$.
2. Regresar $\hat{\varepsilon}_t$ en $\mathbf{X}_t$, $\hat{\varepsilon}_{t-1}, \ldots, \hat{\varepsilon}_{t-p}$.
3. El estadístico $(n-p)R^2_{\text{aux}} \sim \chi^2(p)$ bajo $H_0: \rho_1 = \cdots = \rho_p = 0$.

En Stata: `estat bgodfrey, lags(p)` después de la regresión.

### 3.5 Solución 1: errores estándar HAC (Newey-West)

La solución práctica más extendida es usar errores estándar **heteroscedasticidad y autocorrelación consistentes (HAC)**, también llamados errores de Newey-West.

Los errores estándar de Newey-West modifican el estimador de varianza para incluir el enfoque robusto de White a la heterocedasticidad y además la estructura de correlación serial. Para un número de rezagos $m$, el estimador HAC incluye tanto la heterocedasticidad como una estimación de la autocorrelación con estructura de $m$ rezagos. 

El estimador de varianza de Newey-West con $m$ rezagos:

$$\hat{\mathbf{V}}_{HAC} = (\mathbf{X}'\mathbf{X})^{-1}\hat{\mathbf{S}}(\mathbf{X}'\mathbf{X})^{-1}$$

donde:

$$\hat{\mathbf{S}} = \hat{\boldsymbol{\Gamma}}_0 + \sum_{j=1}^m \left(1 - \frac{j}{m+1}\right)\left(\hat{\boldsymbol{\Gamma}}_j + \hat{\boldsymbol{\Gamma}}_j'\right)$$

y $\hat{\boldsymbol{\Gamma}}_j = \frac{1}{n}\sum_{t=j+1}^n \hat{\varepsilon}_t\hat{\varepsilon}_{t-j}\mathbf{X}_t\mathbf{X}_{t-j}'$.

El estimador de Newey-West colapsa al estimador de White (1980) si la correlación serial está ausente, pero incorpora apropiadamente la correlación serial en el cálculo de los errores estándar robustos cuando hay autocorrelación. 

La **elección del ancho de banda** $m$: la regla empírica de Newey-West es $m = \lfloor 4(n/100)^{2/9} \rfloor$. Más rezagos captura más autocorrelación pero reduce la precisión del estimador. La elección es más arte que ciencia — es buena práctica reportar sensibilidad a distintos $m$.

En Stata: `newey y x1 x2, lag(m)` o `regress y x1 x2, vce(hac nw m)`.

### 3.6 Solución 2: MCG con AR(1) conocido

Si la estructura de autocorrelación es AR(1) y $\rho$ es conocido, la transformación de Cochrane-Orcutt elimina la autocorrelación:

$$Y_t^* = Y_t - \rho Y_{t-1}, \quad X_t^* = X_t - \rho X_{t-1}, \quad \varepsilon_t^* = \varepsilon_t - \rho\varepsilon_{t-1}$$

El modelo transformado tiene errores no autocorrelacionados:

$$Y_t^* = \beta_0(1-\rho) + \beta_1 X_t^* + \varepsilon_t^*$$

Las nuevas variables son $y_t - \phi y_{t-1}$ y $x_t - \phi x_{t-1}$. Crucialmente, el nuevo error es ruido blanco sin correlación. El estimador GLS es simplemente MCO aplicado al modelo transformado. Como la regresión transformada satisface las condiciones del teorema de Gauss-Markov, GLS es BLUE, más eficiente que MCO. 

### 3.7 Solución 3: MCGF con Prais-Winsten o Cochrane-Orcutt iterado

En la práctica $\rho$ es desconocido. El procedimiento iterado de Cochrane-Orcutt:

1. Estimar el modelo por MCO y obtener $\hat{\varepsilon}_t$.
2. Estimar $\rho$: regresionar $\hat{\varepsilon}_t$ en $\hat{\varepsilon}_{t-1}$ → obtener $\hat{\rho}$.
3. Transformar las variables: $Y_t^* = Y_t - \hat{\rho}Y_{t-1}$, $X_t^* = X_t - \hat{\rho}X_{t-1}$.
4. Estimar el modelo transformado por MCO → nuevos residuos → nueva estimación de $\rho$.
5. Repetir hasta convergencia.

En la práctica $\phi$ es desconocido. Sin embargo, el procedimiento factible de tres pasos es: primero, ajustar MCO y guardar el residuo $\hat{u}_t$; segundo, reemplazar $u_t$ con $\hat{u}_t$ y obtener $\hat{\phi}$ por regresión; finalmente, regresionar $y_t - \hat{\phi}y_{t-1}$ en $x_t - \hat{\phi}x_{t-1}$. 

La variante de **Prais-Winsten** retiene la primera observación (que Cochrane-Orcutt descarta), mejorando la eficiencia en muestras pequeñas.

En Stata: `prais y x1 x2` (Prais-Winsten/Cochrane-Orcutt iterado).

---

## 4. Errores clusterizados

En datos de panel o cuando las observaciones se agrupan en clusters (escuelas, empresas, regiones), los errores pueden estar correlacionados **dentro** de cada cluster pero ser independientes entre clusters. Este es un caso especial de dependencia que requiere una corrección específica.

Los **errores estándar clusterizados** extienden los errores de White al contexto de dependencia intra-cluster:

$$\widehat{\text{Var}}_{CL}(\hat{\boldsymbol{\beta}}) = (\mathbf{X}'\mathbf{X})^{-1}\left(\sum_{c=1}^C \mathbf{X}_c'\hat{\boldsymbol{\varepsilon}}_c\hat{\boldsymbol{\varepsilon}}_c'\mathbf{X}_c\right)(\mathbf{X}'\mathbf{X})^{-1}$$

donde $c$ indexa clusters y $\mathbf{X}_c$, $\hat{\boldsymbol{\varepsilon}}_c$ son los regresores y residuos del cluster $c$.

Los errores clusterizados son **robustos a heterocedasticidad y a autocorrelación dentro del cluster de forma arbitraria**, sin necesidad de especificar la estructura de correlación intra-cluster. Requieren suficiente número de clusters ($C \geq 50$ es una regla práctica para la validez asintótica) y que los clusters sean la unidad de asignación del tratamiento.

En Stata: `regress y x1 x2, vce(cluster id)`.

---

## 5. Inferencia robusta: resumen práctico

El flujo de trabajo estándar en econometría aplicada:

**Paso 1 — Estimar por MCO.** Los coeficientes son consistentes bajo exogeneidad.

**Paso 2 — Elegir el estimador de varianza apropiado:**

| Contexto | Estimador de varianza | Stata |
|---|---|---|
| Corte transversal, sin heterocedasticidad aparente | Clásico $s^2(\mathbf{X}'\mathbf{X})^{-1}$ | `regress y x` |
| Corte transversal, posible heterocedasticidad | HC (errores robustos de White) | `, robust` |
| Series de tiempo, posible autocorrelación + heterocedasticidad | HAC (Newey-West) | `newey y x, lag(m)` |
| Panel, dependencia intra-cluster | Errores clusterizados | `, vce(cluster id)` |
| Panel, heterocedasticidad conocida | WLS/FGLS | `wls` o `xtgls` |

**Paso 3 — Contrastar hipótesis con los errores estándar corregidos.**

**Una advertencia:** los errores robustos corrigen la inferencia pero no la eficiencia del estimador — si la heterocedasticidad o autocorrelación es severa y se conoce su estructura, MCGF produce estimadores más precisos. En la práctica, la robustez de los SE es la solución más común porque la estructura de $\boldsymbol{\Omega}$ rara vez se conoce con certeza.

---

## 6. MCG vs. errores robustos: el debate

En lugar de aceptar el estimador MCO ineficiente y corregir los errores estándar, se puede corregir la heterocedasticidad o autocorrelación usando un estimador completamente eficiente a través del GLS. Bajo heterocedasticidad o autocorrelación, aunque MCO y GLS son ambos insesgados, GLS tiene menor varianza. 

El debate en la práctica econométrica moderna:

**A favor de errores robustos:**
- No requieren especificar la forma de $\boldsymbol{\Omega}$.
- Son robustos a errores de especificación de la estructura de la varianza.
- En muestras grandes, la pérdida de eficiencia de MCO sobre MCG es pequeña.
- Son la práctica estándar en microeconometría de corte transversal.

**A favor de MCG/MCGF:**
- Son más eficientes cuando la estructura de $\boldsymbol{\Omega}$ está bien especificada.
- En series de tiempo con autocorrelación persistente, los errores HAC tienen propiedades de tamaño y potencia pobres en muestras finitas.
- El MCGF bien especificado domina a MCO+HAC en eficiencia y en control del tamaño del test.

La tendencia reciente en macroeconometría es usar MCGF o modelos que modelan explícitamente la dinámica (VAR, modelos de corrección de error) en lugar de MCO+HAC. En microeconometría de corte transversal, los errores robustos (o clusterizados) son el estándar sin excepción.

---

## 7. Síntesis

| Problema | Supuesto violado | Consecuencia | Diagnóstico | Solución |
|---|---|---|---|---|
| **Heterocedasticidad** | GM5a ($\sigma_i^2$ no constante) | MCO ineficiente; SE incorrectos | BP, White | Errores robustos HC; WLS; MCGF |
| **Autocorrelación** | GM5b ($\text{Cov}(\varepsilon_i,\varepsilon_j)\neq 0$) | MCO ineficiente; SE incorrectos | DW; BG | Errores HAC (NW); Cochrane-Orcutt; Prais-Winsten |
| **Ambas** | GM5a y GM5b | Ídem | Ambos tests | Errores HAC; MCGF |
| **Dependencia intra-cluster** | GM5b dentro de clusters | SE incorrectos | Inspección del diseño | Errores clusterizados |

---

## Referencias

- Wooldridge, J.M. (2008). *Introductory Econometrics*. Thomson. Caps. 8, 12.
- Greene, W.H. (2011). *Econometric Analysis*. Prentice Hall. Caps. 9–10.
- White, H. (1980). *A Heteroskedasticity-Consistent Covariance Matrix Estimator and a Direct Test for Heteroskedasticity*. Econometrica.
- Newey, W.K. & West, K.D. (1987). *A Simple, Positive Semidefinite, Heteroskedasticity and Autocorrelation Consistent Covariance Matrix*. Econometrica.
- Breusch, T.S. & Pagan, A.R. (1979). *A Simple Test for Heteroscedasticity and Random Coefficient Variation*. Econometrica.
- Cochrane, D. & Orcutt, G.H. (1949). *Application of Least Squares Regression to Relationships Containing Auto-Correlated Error Terms*. JASA.
- Prais, S.J. & Winsten, C.B. (1954). *Trend Estimators and Serial Correlation*. Cowles Commission Discussion Paper.
- Stock, J.H. & Watson, M.W. (2006). *Introduction to Econometrics*. Pearson. Cap. 15.
- Cameron, A.C. & Miller, D.L. (2015). *A Practitioner's Guide to Cluster-Robust Inference*. Journal of Human Resources.