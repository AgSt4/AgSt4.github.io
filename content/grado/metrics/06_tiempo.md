---
title: "Series de Tiempo"
date: 2026-03-15
draft: false
tags: ["econometría", "series de tiempo", "estacionariedad", "raíz unitaria", "cointegración", "ARMA", "Dickey-Fuller", "EAE2510", "EAE3102"]
description: "Tendencia e integración, procesos estacionarios y no estacionarios, tests de raíz unitaria ADF, regresión espuria, cointegración de Engle-Granger, modelo de corrección de error."
---

**Cursos:** Econometría (EAE2510) · Macroeconometría Aplicada (EAE3102)  
**Referencia principal:** Wooldridge (2008) cap. 11 · Enders (1996) · Greene (2011) cap. 20

---

## 1. Propiedades estadísticas de las series de tiempo

### 1.1 Estacionariedad

Un proceso estocástico $\{Y_t\}_{t=-\infty}^{\infty}$ es **estacionario en covarianza** (débilmente estacionario) si:

1. $E[Y_t] = \mu$ — media constante en el tiempo.
2. $\text{Var}(Y_t) = \sigma^2 < \infty$ — varianza finita y constante.
3. $\text{Cov}(Y_t, Y_{t-s}) = \gamma(s)$ — covarianza que depende solo del rezago $s$, no del tiempo $t$.

La estacionariedad es una condición de **homogeneidad temporal**: la distribución de la serie no cambia con el tiempo. Es el supuesto que justifica usar la media y varianza muestral como estimadores de los parámetros poblacionales — si la serie no es estacionaria, esos estimadores no tienen interpretación estable.

Una serie de tiempo no es estacionaria si su distribución — en particular su media, varianza o covarianza temporal — cambia con el tiempo. Las series no estacionarias no pueden usarse directamente en modelos de regresión porque pueden generar regresión espuria: una relación falsa debida, por ejemplo, a una tendencia común en variables por lo demás no relacionadas. 

### 1.2 La función de autocorrelación (FAC)

La **función de autocorrelación** (ACF) mide la correlación entre $Y_t$ e $Y_{t-s}$:

$$\rho_s = \frac{\text{Cov}(Y_t, Y_{t-s})}{\text{Var}(Y_t)} = \frac{\gamma(s)}{\gamma(0)}$$

La **función de autocorrelación parcial** (PACF) mide la correlación entre $Y_t$ e $Y_{t-s}$ eliminando el efecto de los rezagos intermedios $Y_{t-1}, \ldots, Y_{t-s+1}$. Es análoga a un coeficiente de regresión parcial.

Los correlograms (gráficos de FAC y FACP) son la herramienta de diagnóstico principal para identificar la estructura de dependencia temporal:

| Proceso | FAC | FACP |
|---|---|---|
| AR(p) | Decae gradualmente | Corte después del rezago $p$ |
| MA(q) | Corte después del rezago $q$ | Decae gradualmente |
| ARMA(p,q) | Decae gradualmente | Decae gradualmente |
| Ruido blanco | Todos los rezagos ≈ 0 | Todos los rezagos ≈ 0 |
| Caminata aleatoria | Decae muy lentamente (casi lineal) | Gran pico en rezago 1 |

---

## 2. Procesos estacionarios: ARMA

### 2.1 Procesos autorregresivos AR(p)

El proceso AR(p) expresa $Y_t$ como función lineal de sus $p$ valores pasados más un error:

$$Y_t = \phi_0 + \phi_1 Y_{t-1} + \phi_2 Y_{t-2} + \cdots + \phi_p Y_{t-p} + \varepsilon_t$$

Usando el operador de rezago $L$ ($LY_t = Y_{t-1}$):

$$\Phi(L)Y_t = \phi_0 + \varepsilon_t, \quad \Phi(L) = 1 - \phi_1 L - \phi_2 L^2 - \cdots - \phi_p L^p$$

**Condición de estacionariedad:** todas las raíces del polinomio característico $\Phi(z) = 0$ deben caer **fuera** del círculo unitario (en módulo mayor a 1). Para AR(1): $|\phi_1| < 1$.

**Propiedades del AR(1) estacionario** ($Y_t = \phi Y_{t-1} + \varepsilon_t$, $|\phi|<1$):

$$E[Y_t] = 0, \quad \text{Var}(Y_t) = \frac{\sigma^2}{1-\phi^2}, \quad \rho_s = \phi^s$$

La autocorrelación decae geométricamente — exponencialmente hacia cero. La FAC nunca cae abruptamente; la PACF tiene un único pico en el rezago 1.

### 2.2 Procesos de media móvil MA(q)

El proceso MA(q) expresa $Y_t$ como combinación lineal de los errores presentes y pasados:

$$Y_t = \mu + \varepsilon_t + \theta_1\varepsilon_{t-1} + \cdots + \theta_q\varepsilon_{t-q} = \mu + \Theta(L)\varepsilon_t$$

Los procesos MA son **siempre estacionarios** (la varianza es finita para cualquier $\theta$). La FAC del MA(q) se trunca en el rezago $q$: $\rho_s = 0$ para $s > q$.

**Invertibilidad:** para que el MA tenga una representación AR convergente, las raíces de $\Theta(z)=0$ deben estar fuera del círculo unitario.

### 2.3 Procesos ARMA(p,q)

El ARMA(p,q) combina ambas estructuras:

$$\Phi(L)Y_t = \phi_0 + \Theta(L)\varepsilon_t$$

Es más parsimonioso que AR o MA puros para series con estructura de autocorrelación compleja. La identificación de $p$ y $q$ se hace examinando FAC y FACP, y comparando criterios de información (AIC, BIC) entre especificaciones candidatas — la **metodología Box-Jenkins**.

---

## 3. Procesos no estacionarios: tendencias e integración

### 3.1 Tendencia determinística vs. estocástica

Las series macroeconómicas típicamente crecen en el tiempo. La fuente del crecimiento importa para el tratamiento estadístico:

**Proceso estacionario en tendencia (TS):**

$$Y_t = \alpha + \beta t + \varepsilon_t, \quad \varepsilon_t \sim \text{estacionario}$$

La tendencia es **determinística**: dado $t$, el proceso revierte a la tendencia. El tratamiento correcto es **demeaning**: incluir $t$ como regresor o restar la tendencia estimada.

**Proceso integrado de orden 1 — I(1) — con tendencia estocástica:**

$$Y_t = Y_{t-1} + \varepsilon_t \quad \text{(caminata aleatoria)}$$

$$Y_t = Y_0 + \sum_{s=1}^t \varepsilon_s$$

Los shocks se **acumulan permanentemente** — no hay reversión a ningún nivel fijo. La varianza crece sin límite con el tiempo: $\text{Var}(Y_t) = t\sigma^2 \to \infty$. El tratamiento correcto es **diferenciar**: $\Delta Y_t = Y_t - Y_{t-1} = \varepsilon_t$ es estacionario.

**La distinción es crucial y no es trivial identificarla visualmente** — ambos procesos pueden producir series que "parecen" con tendencia. Nelson y Plosser (1982) demostraron que la mayoría de las series macroeconómicas de EE.UU. son I(1), no TS — resultado con enormes implicancias para la interpretación de política económica.

### 3.2 La caminata aleatoria con drift

$$Y_t = \delta + Y_{t-1} + \varepsilon_t, \quad \delta \neq 0$$

Combina tendencia estocástica y drift (tendencia determinística). Es el modelo de precios de activos (hipótesis de mercados eficientes): los cambios en precios son impredecibles pero en promedio positivos.

### 3.3 Procesos I(d): orden de integración

Un proceso es **integrado de orden $d$** — denotado $Y_t \sim I(d)$ — si es necesario diferenciarlo $d$ veces para obtener un proceso estacionario. Un proceso de ruido blanco es I(0). Una caminata aleatoria es I(1). Una serie es I(1) si no es estacionaria en niveles pero sí en primeras diferencias. 

La regla práctica: la mayoría de las series macroeconómicas son I(1) — PIB, consumo, inversión, nivel de precios, tipo de cambio. Las tasas de cambio (inflación, crecimiento del PIB) son generalmente I(0).

---

## 4. Tests de raíz unitaria

### 4.1 El test de Dickey-Fuller (DF)

El test DF contrasta la hipótesis nula de raíz unitaria. Partiendo del AR(1):

$$Y_t = \rho Y_{t-1} + \varepsilon_t$$

La hipótesis de raíz unitaria es $H_0: \rho = 1$. Restando $Y_{t-1}$ de ambos lados:

$$\Delta Y_t = \delta Y_{t-1} + \varepsilon_t, \quad \delta = \rho - 1$$

$$H_0: \delta = 0 \quad (\text{raíz unitaria}), \quad H_1: \delta < 0 \quad (\text{estacionariedad})$$

El estadístico es el $t$-ratio usual de $\hat{\delta}$, pero **su distribución bajo $H_0$ no es la $t$ estándar** — es la **distribución de Dickey-Fuller**, con colas más pesadas a la izquierda. Los valores críticos son más negativos que los de la distribución $t$: aproximadamente $-2.86$ al 5% (sin constante ni tendencia), $-3.41$ (con constante), $-3.96$ (con constante y tendencia) para muestras grandes.

Si la serie es estacionaria (o trend-stationary), tiende a retornar a una media constante (o con tendencia determinística). Por tanto, valores grandes serán seguidos por valores menores (cambios negativos), y valores pequeños por mayores. El nivel de la serie será un predictor significativo del cambio del próximo período, con coeficiente negativo. Si la serie es integrada, los cambios positivos y negativos ocurren con probabilidades independientes del nivel actual. 

**Variantes del test DF:**

| Especificación | Ecuación | Cuándo usar |
|---|---|---|
| Sin constante | $\Delta Y_t = \delta Y_{t-1} + \varepsilon_t$ | Serie centrada en cero sin tendencia |
| Con constante | $\Delta Y_t = \alpha + \delta Y_{t-1} + \varepsilon_t$ | Serie con media no nula pero sin tendencia |
| Con constante y tendencia | $\Delta Y_t = \alpha + \beta t + \delta Y_{t-1} + \varepsilon_t$ | Serie con tendencia determinística posible |

La estrategia general en investigación aplicada es comenzar con la forma más general — con constante y tendencia. Si la tendencia no es estadísticamente significativa, re-estimar solo con constante. Si la constante tampoco lo es, usar el modelo sin ambos para determinar si hay raíz unitaria pura. 

### 4.2 El test ADF (Augmented Dickey-Fuller)

El test ADF es una extensión del DF que controla la autocorrelación de orden mayor en la serie de tiempo incluyendo diferencias rezagadas de la variable dependiente. 

$$\Delta Y_t = \alpha + \beta t + \delta Y_{t-1} + \sum_{j=1}^p \gamma_j \Delta Y_{t-j} + \varepsilon_t$$

Los rezagos adicionales $\Delta Y_{t-j}$ absorben la autocorrelación serial residual — el error $\varepsilon_t$ debe ser ruido blanco para que el test sea válido. La hipótesis $H_0: \delta = 0$ sigue teniendo la distribución de Dickey-Fuller.

**Selección del número de rezagos $p$:** criterios de información (AIC, BIC) o la regla de Schwert ($p_{max} = \lfloor 12(T/100)^{1/4} \rfloor$). Incluir demasiados rezagos reduce el poder; muy pocos invalida el test por autocorrelación residual.

En Stata: `dfuller y, lags(p) trend` (DF/ADF con tendencia opcional).

### 4.3 El test Phillips-Perron (PP)

El test PP es una alternativa no paramétrica al ADF que corrige la autocorrelación y heterocedasticidad de los errores sin necesidad de incluir rezagos explícitamente. Usa una corrección de Newey-West sobre el estadístico DF estándar.

Phillips y Perron (1988) desarrollaron el test PP, que provee un método no paramétrico de testeo de raíz unitaria que supera los problemas de correlación serial y heterocedasticidad sin necesidad de aumentar con términos rezagados. 

En Stata: `pperron y, trend`.

### 4.4 El test KPSS

El test KPSS invierte las hipótesis respecto al ADF: $H_0$ es **estacionariedad** (o trend-stationarity), $H_1$ es raíz unitaria. Contrastar ambos tests en conjunto provee más información:

| ADF no rechaza $H_0$ | KPSS no rechaza $H_0$ | Conclusión |
|---|---|---|
| Sí | Sí | Evidencia débil — ambiguedad |
| Sí | No | Evidencia de I(1) |
| No | Sí | Evidencia de I(0) |
| No | No | Contradicción — problema con los datos |

### 4.5 Limitaciones de los tests de raíz unitaria

Los tests de raíz unitaria tienen **bajo poder** contra alternativas estacionarias con raíz cercana a (pero distinta de) la unidad. En muestras pequeñas, distinguir $\rho = 0.95$ de $\rho = 1.0$ es estadísticamente muy difícil.

Además, los tests pueden confundir una raíz unitaria con **quiebres estructurales** — una serie estacionaria con un cambio en la media puede parecer no estacionaria si el quiebre no se controla. El test de Perron (1989) extiende el ADF para permitir quiebres estructurales conocidos; Zivot-Andrews (1992) permite quiebres desconocidos.

---

## 5. Regresión espuria

### 5.1 El problema

Las series de tiempo no estacionarias no pueden usarse en modelos de regresión porque pueden crear regresión espuria: una relación falsa debida, por ejemplo, a una tendencia común en variables por lo demás no relacionadas. 

Si $Y_t$ y $X_t$ son dos caminatas aleatorias **independientes** e $Y_t$ se regresa en $X_t$, el estimador MCO no converge a cero — converge a un valor no nulo con alta probabilidad. El $R^2$ tiende a ser alto y el estadístico $t$ rechaza $H_0: \beta = 0$ frecuentemente incluso cuando la verdadera relación es cero.

Los residuos de tal regresión espuria son autocorrelacionados. A pesar de no haber ninguna relación entre las series, hay una tendencia ascendente aparente en ambas. 

Las señales de regresión espuria: $R^2$ alto, estadístico $t$ grande, pero el estadístico de Durbin-Watson (DW) es muy bajo ($DW \approx 0$) — los residuos tienen fuerte autocorrelación positiva.

### 5.2 Soluciones a la regresión espuria

**Si las series no están cointegradas:** trabajar con primeras diferencias $\Delta Y_t$ y $\Delta X_t$. El modelo en diferencias es estacionario y la inferencia estándar es válida. El costo: se pierde la información sobre niveles y relaciones de largo plazo.

**Si las series están cointegradas:** existe una relación de largo plazo genuina — la regresión en niveles es válida y los residuos son estacionarios. Ver la sección siguiente.

---

## 6. Cointegración

### 6.1 Definición

Si el test ADF indica que tanto $x$ como $y$ son no estacionarias, modelar la cointegración entre variables no estacionarias provee un enfoque para obtener resultados de regresión útiles. A pesar de que las dos variables son individualmente no estacionarias, una combinación lineal puede ser estacionaria. En este caso se dice que existe un vínculo de cointegración y sugiere que hay una relación de largo plazo o de equilibrio entre las dos variables. 

Formalmente, dos series $I(1)$ $Y_t$ y $X_t$ son **cointegradas** si existe $\beta$ tal que:

$$z_t = Y_t - \beta X_t \sim I(0)$$

El vector $(1, -\beta)$ es el **vector de cointegración**. La existencia de cointegración implica que las dos series no pueden alejarse arbitrariamente en el largo plazo — están vinculadas por una relación de equilibrio.

Ejemplos económicos de cointegración: consumo e ingreso (hipótesis del ingreso permanente), precios en dos mercados del mismo bien (arbitraje), tipo de cambio y precios relativos (PPP de largo plazo).

### 6.2 El método de Engle-Granger (dos pasos)

Para testear cointegración, se pueden construir residuos basados en la regresión estática y testear la presencia de raíz unitaria. Si las series están cointegradas, los residuos estimados estarán cerca de ser estacionarios. 

**Paso 1 — Estimar la relación de largo plazo:**

$$Y_t = \alpha + \beta X_t + u_t$$

Obtener los residuos $\hat{u}_t = Y_t - \hat{\alpha} - \hat{\beta}X_t$.

**Paso 2 — Testear si $\hat{u}_t \sim I(0)$:**

Aplicar el test ADF a los residuos. El test de cointegración de Engle-Granger es esencialmente el test de raíz unitaria aplicado al residuo de la regresión de cointegración. Las series están cointegradas si el residuo no tiene raíz unitaria. 

**Atención:** los valores críticos del ADF aplicado a los residuos son distintos a los del ADF estándar — más negativos — porque $\hat{u}_t$ es un residuo de regresión, no una serie directamente observada. La distribución del test de Engle-Granger no sigue la distribución de Dickey-Fuller cuando $\beta$ es desconocido y estimado.  Los valores críticos apropiados son los de MacKinnon (1990).

Cuando $\{Y_t\}$ y $\{X_t\}$ están cointegradas, el estimador MCO $\hat{\beta}$ de la regresión de cointegración es **superconsistente**: converge a $\beta$ a tasa $T$ (en vez de $\sqrt{T}$), pero bajo la hipótesis nula de que $z_t$ tiene raíz unitaria, debemos correr una regresión espuria para obtener $\hat{\beta}$. 

### 6.3 El modelo de corrección de error (ECM)

El **teorema de representación de Granger** establece que si $Y_t$ y $X_t$ son cointegradas, existe una representación de **modelo de corrección de error (ECM)**:

$$\Delta Y_t = \alpha_0 + \alpha_1 \Delta X_t + \lambda(Y_{t-1} - \beta X_{t-1}) + v_t$$

donde $\lambda < 0$ es el **coeficiente de velocidad de ajuste**: mide cuán rápido el sistema corrige las desviaciones del equilibrio de largo plazo $Y_{t-1} - \beta X_{t-1}$.

El ECM tiene una interpretación económica rica:
- El término $\Delta X_t$ captura los efectos de **corto plazo**.
- El término $(Y_{t-1} - \beta X_{t-1})$ es el **error de corrección**: si $Y$ está por encima de su valor de equilibrio ($Y > \beta X$), el sistema se ajusta hacia abajo ($\lambda < 0$).
- La velocidad de ajuste $|\lambda|$ determina cuántos períodos toma el retorno al equilibrio.

La estimación del ECM sigue el método de Engle-Granger: estimar $\beta$ en la primera etapa, usar los residuos $\hat{u}_{t-1}$ como el término de corrección, y estimar la dinámica de corto plazo en la segunda etapa.

### 6.4 El enfoque de Johansen para múltiples series

Cuando hay más de dos series I(1), puede haber múltiples vectores de cointegración. El método de **Johansen (1988)** usa el sistema VAR para identificar el número de relaciones de cointegración mediante el rango de la matriz $\Pi$ en:

$$\Delta\mathbf{y}_t = \boldsymbol{\pi}_0 + \Pi\mathbf{y}_{t-1} + \sum_{i=1}^{p-1}\Phi_i\Delta\mathbf{y}_{t-i} + \boldsymbol{\varepsilon}_t$$

Si $\text{rank}(\Pi) = r$, hay $r$ relaciones de cointegración independientes. Los dos tests de Johansen son:

- **Test de traza:** $H_0: r \leq r_0$.
- **Test de máximo eigenvalor:** $H_0: r = r_0$ vs. $H_1: r = r_0 + 1$.

El enfoque de Johansen es más eficiente que Engle-Granger cuando hay múltiples vectores de cointegración — situación común en modelos macroeconómicos.

En Stata: `vecrank y1 y2 y3, trend(rconstant) lags(p)`.

---

## 7. Representaciones de tendencia y el filtro HP

### 7.1 Componentes de una serie de tiempo

Una serie de tiempo puede descomponerse en componentes con distintas características de frecuencia:

$$Y_t = T_t + C_t + S_t + I_t$$

donde $T_t$ es la tendencia, $C_t$ el ciclo, $S_t$ la estacionalidad e $I_t$ el componente irregular.

### 7.2 El filtro de Hodrick-Prescott

El **filtro de Hodrick-Prescott (HP)** es el método más usado en macroeconometría para descomponer una serie en tendencia y ciclo. Minimiza:

$$\min_{\{T_t\}} \sum_{t=1}^T (Y_t - T_t)^2 + \lambda\sum_{t=2}^{T-1}[(T_{t+1} - T_t) - (T_t - T_{t-1})]^2$$

El primer término penaliza las desviaciones de la tendencia; el segundo penaliza los cambios en la tasa de crecimiento de la tendencia. El parámetro $\lambda$ controla la suavidad: $\lambda = 1600$ para datos trimestrales (convención estándar), $\lambda = 100$ para anuales, $\lambda = 14400$ para mensuales.

La **brecha de producto** es $\tilde{Y}_t = Y_t - T_t^{HP}$ — la desviación del producto respecto a su tendencia estimada por HP.

**Crítica al filtro HP:** Cogley y Nason (1995) y Hamilton (2018) documentaron que el filtro HP puede generar ciclos espurios en series I(1) — introduce autocorrelación artificial en el componente cíclico que no estaba en los datos originales. Hamilton propone una alternativa basada en proyecciones hacia adelante que evita este problema.

---

## 8. Flujo de trabajo para series de tiempo no estacionarias

El procedimiento estándar en macroeconometría aplicada:
```
1. GRAFICAR la serie: ¿parece estacionaria? ¿Tiene tendencia clara?
2. EXAMINAR FAC y FACP: ¿decaimiento lento? → probable I(1)
3. TEST ADF/PP en niveles (con constante y tendencia):
   - No rechaza H₀ → probable I(1)
   - Rechaza H₀ → probable I(0) → usar en niveles
4. Si I(1), TEST ADF en primeras diferencias:
   - Rechaza H₀ → confirmado I(1)
   - No rechaza → probable I(2) (raro en macro)
5. Si hay múltiples series I(1):
   a. TEST DE COINTEGRACIÓN (Engle-Granger o Johansen)
   b. Si cointegradas → estimar ECM o VECM
   c. Si no cointegradas → trabajar en primeras diferencias
6. DIAGNÓSTICO de los residuos: normalidad, ausencia de autocorrelación
```

---

## 9. Síntesis: estacionariedad, integración y cointegración

| Situación | Tratamiento | Modelo resultante |
|---|---|---|
| $Y_t, X_t \sim I(0)$ | MCO en niveles | Regresión estándar |
| $Y_t \sim I(1)$, tendencia determinística | Incluir $t$ como regresor o demeaning | Modelo con tendencia |
| $Y_t \sim I(1)$, $X_t \sim I(0)$ | MCO es inválido; trabajar en diferencias | Modelo mixto |
| $Y_t, X_t \sim I(1)$, no cointegradas | Diferenciar ambas | Regresión en $\Delta$ |
| $Y_t, X_t \sim I(1)$, cointegradas | MCO superconsistente en niveles | ECM (corto + largo plazo) |
| $\mathbf{y}_t \sim I(1)$ multivariado | Johansen VECM | $r$ vectores de cointegración |

---

## Referencias

- Wooldridge, J.M. (2008). *Introductory Econometrics*. Thomson. Cap. 11.
- Enders, W. (1996). *Applied Time Series Econometrics*. Wiley.
- Engle, R.F. & Granger, C.W.J. (1987). *Co-integration and Error Correction: Representation, Estimation, and Testing*. Econometrica.
- Dickey, D.A. & Fuller, W.A. (1979). *Distribution of the Estimators for Autoregressive Time Series with a Unit Root*. JASA.
- Phillips, P.C.B. & Perron, P. (1988). *Testing for a Unit Root in Time Series Regression*. Biometrika.
- Nelson, C.R. & Plosser, C.I. (1982). *Trends and Random Walks in Macroeconomic Time Series*. JME.
- Johansen, S. (1988). *Statistical Analysis of Cointegration Vectors*. Journal of Economic Dynamics and Control.
- Hodrick, R.J. & Prescott, E.C. (1997). *Postwar U.S. Business Cycles: An Empirical Investigation*. JMCB.
- Hamilton, J.D. (2018). *Why You Should Never Use the Hodrick-Prescott Filter*. REStat.
- Greene, W.H. (2011). *Econometric Analysis*. Prentice Hall. Cap. 20.
- Stock, J.H. & Watson, M.W. (1999). *Business Cycle Fluctuations in U.S. Macroeconomic Time Series*. Handbook of Macroeconomics.