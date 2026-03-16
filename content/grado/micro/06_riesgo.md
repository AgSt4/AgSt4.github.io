---
title: "Elección bajo Incertidumbre"
date: 2026-03-15
draft: false
tags: ["microeconomía", "incertidumbre", "utilidad esperada", "von Neumann-Morgenstern", "aversión al riesgo", "Arrow-Pratt", "seguros", "CAPM", "EAE2120"]
description: "Teoría de utilidad esperada, axiomas vNM, aversión al riesgo, medidas Arrow-Pratt, equivalente de certeza, prima de riesgo, mercado de seguros, diversificación y precios de activos."
---

**Curso:** Microeconomía II (EAE2120)  
**Referencia principal:** Vial & Zurita — *Microeconomía* · Mas-Colell, Whinston & Green (1995) caps. 6, 11 · Pratt (1964) · Arrow (1965)

---

## 1. El problema de la decisión bajo incertidumbre

### 1.1 Motivación: el problema de San Petersburgo

La teoría de decisión bajo incertidumbre parte de una paradoja planteada por Nicolás Bernoulli (1713): una lotería que paga $2^n$ con probabilidad $2^{-n}$ tiene valor esperado infinito:

$$E[X] = \sum_{n=1}^\infty 2^n \cdot \frac{1}{2^n} = \sum_{n=1}^\infty 1 = \infty$$

Sin embargo, nadie pagaría una suma infinita (ni siquiera muy grande) por participar. La paradoja muestra que maximizar el **valor esperado monetario** no describe adecuadamente las decisiones bajo riesgo. La solución de Bernoulli: los agentes maximizan la **utilidad esperada** del resultado, donde la utilidad crece con el dinero pero a tasa decreciente (utilidad logarítmica en su formulación).

### 1.2 Loterías como objetos de elección

Von Neumann y Morgenstern no se referían exactamente a Powerball cuando hablaban de loterías. En su definición, una lotería o apuesta es simplemente una distribución de probabilidad sobre un conjunto conocido y finito de resultados. Los resultados pueden ser cualquier cosa: sumas de dinero, bienes, o incluso eventos. 

Formalmente, una **lotería simple** $L$ es una distribución de probabilidad sobre el conjunto de resultados $Z = \{z_1, \ldots, z_N\}$:

$$L = (p_1, \ldots, p_N) \quad \text{con} \quad p_n \geq 0, \quad \sum_n p_n = 1$$

Una **lotería compuesta** es una distribución de probabilidad sobre loterías simples — puede reducirse a una lotería simple calculando las probabilidades compuestas. El espacio de todas las loterías simples es el simplex $\Delta(Z)$.

---

## 2. Los axiomas de von Neumann-Morgenstern

### 2.1 Las preferencias sobre loterías

En su influyente libro de 1944 *Theory of Games and Economic Behavior*, von Neumann y Morgenstern se propusieron responder una pregunta engañosamente simple: ¿cuándo podemos decir que alguien que toma decisiones bajo incertidumbre se comporta racionalmente? 

La respuesta son cuatro axiomas sobre preferencias $\succeq$ sobre $\Delta(Z)$:

**A1 — Completitud y transitividad:** $\succeq$ es un orden completo y transitivo — idéntico al caso sin incertidumbre. La novedad es que el dominio son loterías, no canastas de bienes.

**A2 — Continuidad:** si $L \succ L' \succ L''$, existe $\alpha \in (0,1)$ tal que $L' \sim \alpha L + (1-\alpha)L''$. Pequeños cambios en probabilidades no generan saltos en las preferencias. Este axioma excluye lexicografías y otros ordenamientos discontinuos.

**A3 — Independencia (el axioma crucial):** para todo $L, L', L''$ y $\alpha \in (0,1)$:

$$L \succeq L' \iff \alpha L + (1-\alpha)L'' \succeq \alpha L' + (1-\alpha)L''$$

Mezclar cualquier lotería $L''$ con igual probabilidad en ambos lados no cambia el orden de preferencia. Este axioma tiene una justificación de "consequentialism": lo que importa es el resultado final, no el camino para llegar a él. Es también el axioma más controversial empíricamente.

**A4 — Monotonicidad:** si $L \succ L'$, entonces para $\alpha > \beta$: $\alpha L + (1-\alpha)L' \succ \beta L + (1-\beta)L'$. Más probabilidad en la lotería preferida es mejor.

### 2.2 El teorema de representación

**Teorema (von Neumann-Morgenstern, 1944):** Si $\succeq$ sobre $\Delta(Z)$ satisface A1–A4, entonces existe una función $u: Z \to \mathbb{R}$ tal que para cualquier par de loterías:

$$L \succeq L' \iff \sum_n p_n u(z_n) \geq \sum_n p'_n u(z_n) \equiv E_L[u] \geq E_{L'}[u]$$

Las preferencias se representan por la **utilidad esperada** de los resultados. $u$ se llama función de utilidad de Bernoulli o función de utilidad de von Neumann-Morgenstern (vNM).

**Unicidad:** $u$ es única salvo transformaciones afines positivas: si $u$ representa las preferencias, también lo hace $a + bu$ con $b > 0$. A diferencia de la utilidad ordinal (única salvo transformaciones monótonas), la utilidad vNM es **cardinal** en un sentido específico: las diferencias de utilidad tienen significado, pero no los niveles absolutos.

La formulación de von Neumann-Morgenstern es importante porque revivió la idea de utilidad cardinal después de la "revolución ordinal" de los 1930s de Hicks-Allen. Sin embargo, aunque la función de utilidad es cardinal en el sentido de que el comportamiento cambiaría con una transformación no lineal de $u$, la función de utilidad esperada es ordinal porque cualquier transformación monótona creciente de la utilidad esperada genera el mismo comportamiento. 

### 2.3 El axioma de independencia y sus violaciones

El axioma de independencia implica que las curvas de indiferencia en el simplex son **paralelas y lineales**. Esta es la propiedad más fuertemente rechazada en los experimentos.

La **paradoja de Allais (1953)** es el contraejemplo clásico. Considerando cuatro loterías con pagos en millones de francos:

- $L_1$: $1$ con certeza.
- $L_2$: $(0.89, 0.10, 0.01)$ para pagos $(1, 5, 0)$.
- $L_3$: $(0.11, 0, 0.89)$ para pagos $(1, 0, 0)$.
- $L_4$: $(0, 0.10, 0.90)$ para pagos $(0, 5, 0)$.

La mayoría prefiere $L_1 \succ L_2$ y $L_4 \succ L_3$. Pero esta combinación viola la independencia: $L_1 \succ L_2$ implica $u(1) > 0.10u(5) + 0.89u(1) + 0.01u(0)$, que a su vez implica $0.11u(1) > 0.10u(5) + 0.01u(0)$, es decir $L_3 \succ L_4$. Contradicción.

La paradoja de Allais revela que los individuos otorgan peso especial a los resultados seguros — el **efecto de certeza** — que el modelo vNM no captura.

---

## 3. Aversión al riesgo

### 3.1 Definición

Un individuo es averso al riesgo si y solo si para todo $p \in \mathcal{P}$, $E_p\{u\} \leq u(E_p\{x\})$. Es amante del riesgo si $E_p\{u\} \geq u(E_p\{x\})$. El agente es neutral al riesgo si $E_p\{u\} = u(E_p\{x\})$. 

**Teorema:** Un agente con función de utilidad vNM $u$ es:
- **Averso al riesgo** $\iff$ $u$ es cóncava ($u'' < 0$).
- **Neutral al riesgo** $\iff$ $u$ es lineal ($u'' = 0$).
- **Amante del riesgo** $\iff$ $u$ es convexa ($u'' > 0$).

**Prueba para aversión:** Por la desigualdad de Jensen, para $u$ cóncava: $u(E[X]) \geq E[u(X)]$. El agente prefiere el valor esperado con certeza a la lotería — define precisamente la aversión al riesgo.

### 3.2 El equivalente de certeza y la prima de riesgo

El **equivalente de certeza (CE)** de una lotería es un monto de dinero que provee igual utilidad al pago aleatorio de la lotería. El equivalente de certeza es menor que el resultado esperado si la persona es aversa al riesgo. 

Formalmente, $CE$ satisface:

$$u(CE) = E[u(X)]$$

Para un agente averso al riesgo, $CE < E[X]$.

La **prima de riesgo** $\pi$ es la diferencia entre el pago esperado y el equivalente de certeza: $\pi = E[X] - CE$. La prima de riesgo cae al aumentar la riqueza para cualquier lotería si y solo si la medida Arrow-Pratt de aversión absoluta al riesgo es decreciente. 

### 3.3 Las medidas Arrow-Pratt

Dado que las actitudes al riesgo no cambian bajo transformaciones afinas de $u$, la segunda derivada $u''$ no es una medida adecuada de aversión al riesgo por sí sola — necesita normalizarse. Esto lleva a la definición de la medida Arrow-Pratt de aversión absoluta al riesgo. 

La **aversión absoluta al riesgo (ARA)** de Arrow-Pratt:

$$A(w) = -\frac{u''(w)}{u'(w)}$$

La prima de riesgo es aproximadamente igual a la medida Arrow-Pratt multiplicada por la mitad de la varianza cuando la varianza es pequeña: 

$$\pi \approx \frac{1}{2}A(w)\sigma^2$$

Esta aproximación es la base de la demanda de seguros: la máxima prima que un agente está dispuesto a pagar por eliminar un riesgo de varianza $\sigma^2$ es proporcional a su ARA y a la varianza del riesgo.

La **aversión relativa al riesgo (ARR)**:

$$R(w) = -\frac{wu''(w)}{u'(w)} = wA(w)$$

Mide la aversión al riesgo ante apuestas proporcionales a la riqueza (como retornos porcentuales de activos). Es la medida relevante en finanzas.

### 3.4 Funciones de utilidad estándar

Las clases especiales de funciones de utilidad son las CRRA (aversión relativa al riesgo constante), donde $R(w)$ es constante, y las CARA (aversión absoluta al riesgo constante), donde $A(w)$ es constante. Estas funciones se usan frecuentemente en economía para simplificar. 

**CARA (Constant Absolute Risk Aversion):**

$$u(w) = -e^{-\alpha w}, \quad \alpha > 0$$

$A(w) = \alpha$ constante — la aversión al riesgo no depende de la riqueza. La demanda de activos riesgosos (en unidades monetarias) es independiente de la riqueza. Tractable con retornos normales.

La utilidad CARA exhibe aversión absoluta al riesgo constante y por esta razón es frecuentemente evitada — aunque tiene la ventaja de ofrecer tractabilidad matemática sustancial cuando los retornos de activos son normalmente distribuidos. 

**CRRA (Constant Relative Risk Aversion):**

$$u(w) = \frac{w^{1-\gamma}}{1-\gamma}, \quad \gamma > 0, \quad \gamma \neq 1$$

Con $\gamma = 1$: $u(w) = \ln(w)$ (Bernoulli). $R(w) = \gamma$ constante — la aversión relativa es independiente de la riqueza; la proporción óptima de riqueza invertida en activos riesgosos no varía con la riqueza. Es la especificación dominante en macroeconomía y finanzas.

**Utilidad cuadrática:** $u(w) = w - \frac{b}{2}w^2$, $b > 0$

Implica preferencias media-varianza: $E[u] = E[w] - \frac{b}{2}(E[w]^2 + \text{Var}(w))$. La utilidad cuadrática presenta utilidad marginal negativa para niveles de riqueza mayores al "punto de saciedad", y tiene la característica poco atractiva de aversión absoluta al riesgo creciente  — a mayor riqueza, más averso al riesgo. Por estas razones se usa solo como aproximación.

---

## 4. El mercado de seguros

### 4.1 Demanda óptima de seguro

Un agente con riqueza inicial $w$ enfrenta la posibilidad de una pérdida $L$ con probabilidad $p$. Puede comprar cobertura $d \in [0,1]$ (proporción de la pérdida cubierta) a prima actuarialmente justa $qd \cdot L$ donde $q = p$ (precio justo).

El problema de optimización es:

$$\max_d \; (1-p)u(w - qd \cdot L) + p \cdot u(w - L + dL - qdL)$$

$$= \max_d \; (1-p)u(w - qdL) + p \cdot u(w - (1-d)(1-q)L - qL)$$

Cuando $q = p$ (prima justa), el seguro completo $d = 1$ es óptimo. La utilidad marginal del gasto en seguro iguala la utilidad marginal de la riqueza en el estado sin pérdida. 

La condición de primer orden, evaluada en $d = 1$:

$$\frac{d E[u]}{dd}\bigg|_{d=1} = (1-p)(-pL)u'(w - pL) + p(1-p)Lu'(w - pL) = 0$$

Con prima actuarialmente justa, el **seguro completo es óptimo** para cualquier agente averso al riesgo: las utilidades marginales de la riqueza en el estado bueno y en el malo se igualan, que es la condición de asignación eficiente del riesgo.

Un agente averso al riesgo está dispuesto a pagar una prima por encima del valor esperado para evitar incertidumbre. Esto explica por qué las personas compran seguros incluso cuando el pago esperado es menor que la prima — la ganancia de utilidad al eliminar el riesgo supera el costo monetario. 

### 4.2 Prima cargada: seguro incompleto

Cuando $q > p$ (la compañía de seguros carga una prima sobre el costo actuarial justo para cubrir gastos operativos y generar beneficios), la condición de optimalidad da $d^* < 1$: el agente toma **seguro incompleto**. La cobertura óptima satisface:

$$\frac{1-p}{p} \cdot \frac{u'(w - q d^* L)}{u'(w - L(1-d^*(1-q)))} = \frac{1-q}{q}$$

La razón de utilidades marginales iguala la razón de las probabilidades ajustadas por el precio del seguro. Con CARA, la demanda de seguro es:

$$d^* = 1 - \frac{1}{\alpha L}\ln\left(\frac{q(1-p)}{p(1-q)}\right)$$

La cobertura óptima cae cuando la prima cargada $q$ sube, cuando la aversión al riesgo $\alpha$ baja, o cuando la pérdida $L$ cae.

---

## 5. Diversificación de riesgos y precios de activos

### 5.1 El principio de diversificación

Con múltiples riesgos independientes, la diversificación reduce la varianza sin reducir el retorno esperado. Formalmente, si $X_1, \ldots, X_N$ son iid con media $\mu$ y varianza $\sigma^2$, la cartera igualmente ponderada $\bar{X} = \frac{1}{N}\sum_i X_i$ tiene:

$$E[\bar{X}] = \mu, \qquad \text{Var}(\bar{X}) = \frac{\sigma^2}{N} \to 0$$

Para un agente CARA con $u(w) = -e^{-\alpha w}$ y retornos normales, la inversión óptima en el activo riesgoso $\alpha^*$ es independiente de la riqueza — consistente con CARA. El beneficio marginal de diversificar es la reducción en la prima de riesgo $\approx \frac{1}{2}\alpha \cdot \text{Var}$.

Un inversor con función de utilidad de Bernoulli cóncava prefiere distribuir su riqueza entre múltiples activos antes que concentrarla en uno solo, incluso si los retornos esperados son idénticos. La reducción en varianza aumenta la utilidad más que cualquier ganancia potencial de la concentración. 

### 5.2 El modelo media-varianza y la frontera eficiente

Con utilidad cuadrática o retornos normales, las preferencias sobre carteras se resumen en el par $(\mu, \sigma)$:

$$E[u(\tilde{w})] = V(\mu_p, \sigma_p^2), \quad V_\mu > 0, \quad V_{\sigma^2} < 0$$

La **frontera eficiente** de Markowitz es el conjunto de carteras que minimizan $\sigma_p^2$ para cada nivel de $\mu_p$. El inversor es generalmente averso al riesgo y por tanto prefiere carteras con mayor retorno medio $\mu$ y menor riesgo (desviación estándar) $\sigma$. El conjunto de oportunidades se reduce a las carteras en la frontera eficiente — el arco que domina a todas las demás por tener mayor $\mu$ y menor $\sigma$. 

### 5.3 El CAPM como resultado de equilibrio

En el modelo de una economía con $I$ inversores con preferencias media-varianza, un activo libre de riesgo con retorno $r_f$ y $N$ activos riesgosos, el equilibrio competitivo genera el **Capital Asset Pricing Model**:

$$E[\tilde{r}_i] - r_f = \beta_i(E[\tilde{r}_M] - r_f)$$

donde $\beta_i = \text{Cov}(\tilde{r}_i, \tilde{r}_M) / \text{Var}(\tilde{r}_M)$ y $\tilde{r}_M$ es el retorno de la cartera de mercado.

El CAPM dice que el exceso de retorno esperado de un activo es proporcional a su **riesgo sistemático** $\beta_i$ — la covarianza con el mercado, no la varianza total. El riesgo idiosincrático (diversificable) no es compensado porque puede eliminarse gratis con diversificación. Solo el riesgo no diversificable exige prima.

La aversión absoluta al riesgo constante provee una base para las preferencias media-varianza, que es el fundamento de la teoría financiera moderna. El CAPM surgió como corolario del marco media-varianza introducido por Markowitz en los 1950s. 

La conexión entre utilidad esperada y media-varianza es exacta con retornos normales o utilidad cuadrática; es una aproximación de segundo orden en el caso general.

---

## 6. Modelación alternativa de preferencias al riesgo

### 6.1 Dominancia estocástica

La dominancia estocástica establece órdenes sobre distribuciones sin especificar la forma funcional de $u$.

**Dominancia de primer orden (FSD):** $F$ domina $G$ en primer orden si $F(x) \leq G(x)$ para todo $x$. Equivale a que $E_F[u] \geq E_G[u]$ para toda $u$ creciente. Una distribución FSD-domina a otra si, para cualquier nivel $x$, la probabilidad acumulada de resultados menores a $x$ es menor — toda la distribución está "corrida a la derecha".

**Dominancia de segundo orden (SSD):** $F$ domina $G$ en segundo orden si $\int_{-\infty}^x [F(t) - G(t)]dt \leq 0$ para todo $x$. Equivale a que $E_F[u] \geq E_G[u]$ para toda $u$ creciente y cóncava (agentes aversos al riesgo). Si $F$ y $G$ tienen la misma media, $F$ domina en SSD si tiene menor dispersión.

La dominancia estocástica permite comparaciones sin imponer forma funcional específica — útil para derivar resultados aplicables a toda una clase de agentes (por ejemplo, todos los aversos al riesgo).

### 6.2 La teoría prospectiva de Kahneman-Tversky

La teoría de la utilidad esperada falla empíricamente en múltiples dimensiones documentadas sistemáticamente por Kahneman y Tversky (1979). Los hechos estilizados son:

- **Aversión a la pérdida:** las pérdidas pesan aproximadamente el doble que las ganancias equivalentes — la función de valor es más inclinada en el dominio de pérdidas.
- **Efecto de certeza:** se sobrepondera los resultados ciertos relativo a los probables (paradoja de Allais).
- **Dependencia del punto de referencia:** los resultados se evalúan relativo a un punto de referencia (status quo), no en niveles absolutos de riqueza.
- **Distorsión de probabilidades:** probabilidades pequeñas son sobreestimadas; probabilidades altas son subestimadas.

El efecto de dotación, que contribuye a explicar la aversión al riesgo, surge porque la desutilidad de arriesgar la pérdida de $1 es mayor que la utilidad de ganar $1. 

La **función de valor** de la teoría prospectiva es cóncava en ganancias, convexa en pérdidas, con un punto de quiebre en el punto de referencia — los agentes son aversos al riesgo en el dominio de ganancias y amantes del riesgo en el dominio de pérdidas. Esto explica comportamientos como el **efecto de disposición** en finanzas: los inversores mantienen activos perdedores demasiado tiempo (aversión a realizar la pérdida) y venden los ganadores demasiado pronto.

---

## 7. Síntesis

| Concepto | Condición | Implicancia |
|---|---|---|
| Utilidad esperada | Axiomas A1–A4 (independencia) | Representación $E[u(X)]$ |
| Aversión al riesgo | $u'' < 0$ (concavidad) | $CE < E[X]$, prima de riesgo positiva |
| CARA | $A(w) = \alpha$ constante | Demanda monetaria de activos riesgosos independiente de $w$ |
| CRRA | $R(w) = \gamma$ constante | Proporción de riqueza en activos riesgosos independiente de $w$ |
| Seguro óptimo (prima justa) | $q = p$ | Cobertura completa es óptima |
| Diversificación | Activos no perfectamente correlacionados | Reduce varianza sin reducir retorno esperado |
| CAPM | Equilibrio con media-varianza | Solo el riesgo sistemático $\beta$ es compensado |

---

## Referencias

- von Neumann, J. & Morgenstern, O. (1944). *Theory of Games and Economic Behavior*. Princeton University Press.
- Arrow, K.J. (1965). *Aspects of the Theory of Risk-Bearing*. Yrjö Jahnsson Lectures.
- Pratt, J.W. (1964). *Risk Aversion in the Small and in the Large*. Econometrica.
- Allais, M. (1953). *Le Comportement de l'Homme Rationnel devant le Risque*. Econometrica.
- Markowitz, H. (1952). *Portfolio Selection*. Journal of Finance.
- Sharpe, W. (1964). *Capital Asset Prices: A Theory of Market Equilibrium*. Journal of Finance.
- Kahneman, D. & Tversky, A. (1979). *Prospect Theory: An Analysis of Decision under Risk*. Econometrica.
- Mas-Colell, A., Whinston, M. & Green, J. (1995). *Microeconomic Theory*. Oxford. Caps. 6, 11.
- Vial, B. & Zurita, F. *Microeconomía*. Ediciones UC.