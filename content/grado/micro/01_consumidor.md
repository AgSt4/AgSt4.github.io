---
title: "Elección del Consumidor y Demanda"
date: 2026-03-15
draft: false
tags: ["microeconomía", "teoría del consumidor", "demanda", "Slutsky", "dualidad", "EAE2110"]
description: "Preferencias, UMP, EMP, dualidad, demanda marshalliana e hicksiana, ecuación de Slutsky, efectos ingreso y sustitución, elasticidades y medidas de bienestar."
---

**Curso:** Microeconomía I (EAE2110) · **Profesora:** María Luisa Vergara  
**Referencia principal:** Vial & Zurita — *Microeconomía* · Nicholson (2008) · Mas-Colell, Whinston & Green (1995) caps. 2–3

---

## 1. Preferencias y representación por utilidad

### 1.1 Relaciones de preferencia

El consumidor se modela como un agente que tiene preferencias sobre el conjunto de consumo $X \subseteq \mathbb{R}^L_+$. La relación de preferencia $\succeq$ (débilmente preferido) debe satisfacer dos axiomas fundamentales:

- **Completitud:** para todo $x, y \in X$: $x \succeq y$ o $y \succeq x$ (o ambas).
- **Transitividad:** si $x \succeq y$ e $y \succeq z$, entonces $x \succeq z$.

Con estos dos axiomas, $\succeq$ es una **relación de orden**. La preferencia estricta $\succ$ y la indiferencia $\sim$ se derivan: $x \succ y \iff x \succeq y$ pero no $y \succeq x$; $x \sim y \iff x \succeq y$ e $y \succeq x$.

Axiomas adicionales con implicancias económicas:

- **No saciedad local:** para todo $x$ y $\varepsilon > 0$, existe $y$ con $\|y - x\| < \varepsilon$ tal que $y \succ x$. Implica que la restricción presupuestaria es activa en el óptimo (se gasta todo el ingreso).
- **Continuidad:** los conjuntos $\{y : y \succeq x\}$ y $\{y : x \succeq y\}$ son cerrados para todo $x$. Garantiza que pequeños cambios en los bienes no producen saltos en la preferencia.
- **Convexidad:** si $x \sim y$, entonces $\alpha x + (1-\alpha)y \succeq x$ para $\alpha \in [0,1]$. Refleja preferencia por variedades — las curvas de indiferencia son convexas al origen.
- **Convexidad estricta:** $\alpha x + (1-\alpha)y \succ x$ para $\alpha \in (0,1)$ cuando $x \neq y$. Garantiza demandas únicas (no correspondencias).

### 1.2 Representación por función de utilidad

**Teorema (Debreu, 1954):** Si $\succeq$ es completa, transitiva y continua, entonces existe una función de utilidad continua $u: X \to \mathbb{R}$ que la representa: $u(x) \geq u(y) \iff x \succeq y$.

Puntos clave:

- La representación **no es única**: cualquier transformación monótona creciente $f(u)$ representa las mismas preferencias. La utilidad es ordinal, no cardinal.
- La convexidad de preferencias equivale a quasiconcavidad de $u$: $u(\alpha x + (1-\alpha)y) \geq \min\{u(x), u(y)\}$.
- La convexidad estricta equivale a quasiconcavidad estricta.

**Ejemplos canónicos:**

| Función | Forma | Elasticidad sustitución | Propiedad |
|---|---|---|---|
| Cobb-Douglas | $u = x_1^\alpha x_2^\beta$ | 1 | Homotética |
| CES | $u = [\alpha x_1^\rho + (1-\alpha)x_2^\rho]^{1/\rho}$ | $1/(1-\rho)$ | Homotética |
| Cuasilineal | $u = v(x_1) + x_2$ | Variable | No homotética |
| Perfectamente complementarios | $u = \min\{x_1/a, x_2/b\}$ | 0 | Demanda proporcional fija |
| Sustitutos perfectos | $u = ax_1 + bx_2$ | $\infty$ | Solución esquina |

---

## 2. El problema de maximización de utilidad (UMP)

### 2.1 Formulación

Dado precios $\mathbf{p} \gg 0$ e ingreso $w > 0$, el consumidor resuelve:

$$\max_{\mathbf{x} \geq 0} u(\mathbf{x}) \quad \text{s.a.} \quad \mathbf{p} \cdot \mathbf{x} \leq w$$

El conjunto de consumo factible es el **conjunto presupuestario** $B(\mathbf{p}, w) = \{\mathbf{x} \in \mathbb{R}^L_+ : \mathbf{p} \cdot \mathbf{x} \leq w\}$, que es convexo y compacto (cerrado y acotado para $\mathbf{p} \gg 0$, $w > 0$). Por el teorema del máximo, si $u$ es continua, el UMP tiene solución.

### 2.2 Condiciones de primer orden (solución interior)

El Lagrangiano es:

$$\mathcal{L} = u(\mathbf{x}) + \lambda(w - \mathbf{p} \cdot \mathbf{x})$$

Las CPO son:

$$\frac{\partial u}{\partial x_i} = \lambda p_i \quad \forall i, \qquad \mathbf{p} \cdot \mathbf{x} = w$$

Para dos bienes, dividiendo las CPO:

$$\frac{\partial u / \partial x_1}{\partial u / \partial x_2} = \frac{p_1}{p_2} \implies \text{TMS}_{12} = \frac{p_1}{p_2}$$

La **tasa marginal de sustitución** (TMS) debe igualar el precio relativo: la tasa subjetiva de intercambio entre bienes iguala la tasa objetiva del mercado. Geométricamente, la curva de indiferencia es tangente a la recta presupuestaria.

**Interpretación de $\lambda$:** el multiplicador de Lagrange mide la utilidad marginal del ingreso — cuánto aumenta la utilidad máxima si el ingreso sube marginalmente. Formalmente, por el teorema de la envolvente: $\lambda = \partial v / \partial w$, donde $v(\mathbf{p}, w)$ es la función de utilidad indirecta.

### 2.3 Condiciones Kuhn-Tucker para soluciones esquina

Con restricciones de no-negatividad, las CPO generalizadas son:

$$\frac{\partial u}{\partial x_i} \leq \lambda p_i, \quad x_i \geq 0, \quad x_i\left(\frac{\partial u}{\partial x_i} - \lambda p_i\right) = 0$$

Un bien no se consume ($x_i^* = 0$) cuando su utilidad marginal al precio vigente es menor que $\lambda$: el bien es "demasiado caro" relativo al beneficio que provee.

### 2.4 La función de demanda marshalliana

La solución del UMP es la **demanda marshalliana** (u ordinaria o walrasiana) $\mathbf{x}(\mathbf{p}, w)$. Sus propiedades directas del UMP:

**Homogeneidad de grado cero:** $\mathbf{x}(\lambda\mathbf{p}, \lambda w) = \mathbf{x}(\mathbf{p}, w)$ para $\lambda > 0$. Solo importan los precios relativos y el ingreso real — sin ilusión monetaria.

**Ley de Walras:** $\mathbf{p} \cdot \mathbf{x}(\mathbf{p}, w) = w$. Con no-saciedad local, el consumidor gasta todo su ingreso.

**Simetría y negativo-semidefinitismo:** las propiedades de la demanda compensada se trasladan a la marshalliana vía la ecuación de Slutsky (ver sección 4).

### 2.5 La función de utilidad indirecta

La **función de utilidad indirecta** es el valor del problema maximizado:

$$v(\mathbf{p}, w) = u(\mathbf{x}(\mathbf{p}, w)) = \max_{\mathbf{x}} \{u(\mathbf{x}) : \mathbf{p} \cdot \mathbf{x} \leq w\}$$

Propiedades:
- Homogénea de grado cero en $(\mathbf{p}, w)$.
- Decreciente en precios y creciente en $w$.
- Quasiconvexa en $\mathbf{p}$ (no quasicóncava).

**Identidad de Roy:** la demanda marshalliana se recupera de la utilidad indirecta:

$$x_i(\mathbf{p}, w) = -\frac{\partial v / \partial p_i}{\partial v / \partial w}$$

La demanda del bien $i$ es la razón entre la utilidad marginal negativa de su precio y la utilidad marginal del ingreso. Roy permite recuperar demandas sin resolver el UMP directamente — útil en econometría cuando se especifica $v$ directamente.

---

## 3. El problema de minimización de gasto (EMP)

### 3.1 Formulación

El dual del UMP pregunta: ¿cuál es el gasto mínimo necesario para alcanzar un nivel de utilidad $\bar{u}$?

$$\min_{\mathbf{x} \geq 0} \mathbf{p} \cdot \mathbf{x} \quad \text{s.a.} \quad u(\mathbf{x}) \geq \bar{u}$$

### 3.2 La demanda hicksiana (compensada)

La demanda hicksiana $h(\mathbf{p}, \bar{u})$ proviene del EMP, mientras que la marshalliana proviene del UMP. Los dos problemas son duales matemáticos, y el teorema de dualidad provee métodos para probar las relaciones entre ellos. 

La demanda hicksiana mantiene la utilidad constante: aísla el **efecto sustitución** eliminando el efecto ingreso. Sus propiedades:

- Homogénea de grado cero en $\mathbf{p}$.
- La propia pendiente es no positiva: $\partial h_i / \partial p_i \leq 0$ — la demanda compensada siempre cumple la ley de la demanda.
- Simétrica: $\partial h_i / \partial p_j = \partial h_j / \partial p_i$ — el efecto compensado cruzado es simétrico.

La demanda hicksiana aísla el efecto sustitución suponiendo que el consumidor es compensado con exactamente suficiente ingreso adicional tras el alza de precio para comprar alguna cesta sobre la misma curva de indiferencia. Si la demanda hicksiana es más inclinada que la marshalliana, el bien es normal; de lo contrario, es inferior. 

### 3.3 La función de gasto

La **función de gasto** $e(\mathbf{p}, \bar{u})$ es el valor del problema minimizado:

$$e(\mathbf{p}, \bar{u}) = \mathbf{p} \cdot h(\mathbf{p}, \bar{u}) = \min_\mathbf{x} \{\mathbf{p} \cdot \mathbf{x} : u(\mathbf{x}) \geq \bar{u}\}$$

Propiedades:
- Homogénea de grado uno en $\mathbf{p}$: si todos los precios se duplican, el gasto mínimo se duplica.
- Creciente en $\bar{u}$ y en $\mathbf{p}$.
- Cóncava en $\mathbf{p}$.

**Lema de Shephard:** si la función de utilidad $u(\mathbf{x})$ es localmente no saciada y estrictamente convexa, entonces por el lema de Shephard $h(\mathbf{p}, u) = \nabla_\mathbf{p} e(\mathbf{p}, u)$.  La demanda compensada del bien $i$ es simplemente la derivada del gasto mínimo respecto al precio $p_i$ — resultado directo del teorema de la envolvente aplicado al EMP.

### 3.4 La dualidad entre UMP y EMP

Las funciones de utilidad indirecta $v(\mathbf{p}, w)$ y de gasto $e(\mathbf{p}, \bar{u})$ son inversas la una de la otra como funciones de su segundo argumento:

$$e(\mathbf{p}, v(\mathbf{p}, w)) = w \qquad v(\mathbf{p}, e(\mathbf{p}, \bar{u})) = \bar{u}$$

Y las demandas se relacionan:

$$h(\mathbf{p}, \bar{u}) = \mathbf{x}(\mathbf{p}, e(\mathbf{p}, \bar{u})) \qquad \mathbf{x}(\mathbf{p}, w) = h(\mathbf{p}, v(\mathbf{p}, w))$$

En el óptimo del consumidor, la demanda marshalliana a ingreso $w$ coincide con la hicksiana al nivel de utilidad que ese ingreso permite alcanzar, y viceversa. Esta dualidad es la estructura algebraica que subyace a toda la teoría del consumidor.

---

## 4. La ecuación de Slutsky

### 4.1 Derivación

La ecuación de Slutsky relaciona los cambios en la demanda marshalliana (no compensada) con los cambios en la demanda hicksiana (compensada). El lado derecho de la ecuación iguala el cambio en la demanda del bien $i$ manteniendo la utilidad fija menos la cantidad del bien $j$ demandada multiplicada por el cambio en la demanda del bien $i$ cuando la riqueza cambia. El primer término representa el efecto sustitución y el segundo el efecto ingreso. 

Diferenciando la identidad $h_i(\mathbf{p}, u) = x_i(\mathbf{p}, e(\mathbf{p}, u))$ respecto a $p_j$ y usando el lema de Shephard ($\partial e / \partial p_j = h_j = x_j$ en el óptimo):

$$\underbrace{\frac{\partial h_i}{\partial p_j}}_{\text{efecto sustitución}} = \underbrace{\frac{\partial x_i}{\partial p_j}}_{\text{efecto total}} + \underbrace{x_j \frac{\partial x_i}{\partial w}}_{\text{efecto ingreso}}$$

Reordenando:

$$\frac{\partial x_i}{\partial p_j} = \frac{\partial h_i}{\partial p_j} - x_j \frac{\partial x_i}{\partial w}$$

Esta es la **ecuación de Slutsky**: el efecto precio total sobre la demanda marshalliana es la suma del efecto sustitución (compensado) más el efecto ingreso. El efecto sustitución siempre tiene el signo predicho por la ley de la demanda ($\partial h_i / \partial p_i \leq 0$); el efecto ingreso puede ser positivo o negativo.

### 4.2 La matriz de Slutsky

Apilando las ecuaciones de Slutsky para todos los bienes, se obtiene la **matriz de Slutsky** $S(\mathbf{p}, w)$ con entradas $s_{ij} = \partial h_i / \partial p_j = \partial x_i / \partial p_j + x_j \partial x_i / \partial w$.

Propiedades de $S$:
- **Simétrica:** $s_{ij} = s_{ji}$ — los efectos sustitución cruzados son simétricos. Esta es la restricción más importante de la teoría del consumidor; es testeable y sirve para verificar la racionalidad.
- **Negativa semidefinida:** $\mathbf{v}^T S \mathbf{v} \leq 0$ para todo $\mathbf{v}$. Implica que los efectos propios son no positivos: $s_{ii} \leq 0$.
- **$S \cdot \mathbf{p} = \mathbf{0}$:** consecuencia de la homogeneidad de grado cero.

### 4.3 Clasificación de bienes

| Tipo | Definición | Condición |
|---|---|---|
| **Normal** | $\partial x_i / \partial w > 0$ | La demanda sube con el ingreso |
| **Inferior** | $\partial x_i / \partial w < 0$ | La demanda cae con el ingreso |
| **Giffen** | $\partial x_i / \partial p_i > 0$ | Demanda sube cuando su precio sube |
| **Sustitutos brutos** | $\partial x_i / \partial p_j > 0$ | Efecto total de precio cruzado positivo |
| **Complementos brutos** | $\partial x_i / \partial p_j < 0$ | Efecto total de precio cruzado negativo |
| **Sustitutos netos** | $\partial h_i / \partial p_j > 0$ | Efecto sustitución cruzado positivo |
| **Complementos netos** | $\partial h_i / \partial p_j < 0$ | Efecto sustitución cruzado negativo |

Un bien Giffen es necesariamente inferior (efecto ingreso negativo suficientemente grande como para dominar el efecto sustitución negativo). Un bien inferior no es necesariamente Giffen. Los ejemplos empíricos de bienes Giffen son escasos; Jensen y Miller (2008) documentaron el caso de arroz y trigo en hogares pobres chinos.

---

## 5. Elasticidades

### 5.1 Las elasticidades fundamentales

La **elasticidad-precio de la demanda** mide la sensibilidad porcentual de la cantidad demandada ante un cambio porcentual en el precio propio:

$$\varepsilon_{ii} = \frac{\partial x_i}{\partial p_i} \cdot \frac{p_i}{x_i}$$

Para bienes normales, $\varepsilon_{ii} < 0$. La demanda es:
- **Elástica** si $|\varepsilon_{ii}| > 1$: el cambio porcentual en cantidad supera al del precio.
- **Inelástica** si $|\varepsilon_{ii}| < 1$.
- **Unitariamente elástica** si $|\varepsilon_{ii}| = 1$.

La **elasticidad-ingreso** mide la sensibilidad ante cambios en el ingreso:

$$\varepsilon_{iw} = \frac{\partial x_i}{\partial w} \cdot \frac{w}{x_i}$$

$\varepsilon_{iw} > 0$: bien normal; $\varepsilon_{iw} < 0$: bien inferior; $\varepsilon_{iw} > 1$: bien de lujo.

La **elasticidad cruzada** mide el efecto del precio de otro bien:

$$\varepsilon_{ij} = \frac{\partial x_i}{\partial p_j} \cdot \frac{p_j}{x_i}$$

### 5.2 Las restricciones sobre elasticidades

De la homogeneidad de grado cero y la ley de Walras se derivan restricciones que las elasticidades deben satisfacer:

**Ecuación de Euler (homogeneidad):** para cada bien $i$:

$$\sum_j \varepsilon_{ij} + \varepsilon_{iw} = 0$$

La suma de todas las elasticidades precio más la elasticidad ingreso es cero. Si el ingreso y todos los precios suben en la misma proporción, la demanda no cambia.

**Identidades de Cournot y Engel (Ley de Walras):**

$$\sum_i s_i \varepsilon_{ij} = -s_j \quad \text{(Cournot)} \qquad \sum_i s_i \varepsilon_{iw} = 1 \quad \text{(Engel)}$$

donde $s_i = p_i x_i / w$ es la participación del bien $i$ en el gasto. La identidad de Engel dice que el promedio ponderado de las elasticidades ingreso (con pesos en el gasto) es uno — si el ingreso sube 1%, el gasto total sube 1%.

### 5.3 La ecuación de Slutsky en elasticidades

La ecuación de Slutsky puede reescribirse en términos de elasticidades: $\varepsilon_p = \varepsilon_p^h - s_j \varepsilon_w$, donde $\varepsilon_p$ es la elasticidad-precio no compensada, $\varepsilon_p^h$ es la compensada, $\varepsilon_w$ la elasticidad ingreso y $s_j$ la participación en el gasto. 

---

## 6. Medidas de bienestar del consumidor

### 6.1 Excedente del consumidor y sus limitaciones

El **excedente del consumidor** es el área debajo de la curva de demanda marshalliana y por encima del precio:

$$CS = \int_p^\infty x(q, w) dq$$

Es una medida de bienestar intuitiva pero imprecisa: depende de la utilidad marginal del ingreso, que no es constante a lo largo de la curva marshalliana. Es exacta solo con utilidad cuasilineal (sin efecto ingreso).

### 6.2 Variación compensatoria y variación equivalente

Las medidas exactas de bienestar usan la función de gasto:

**Variación compensatoria (VC):** ingreso adicional que el consumidor necesitaría recibir (o pagar) a los nuevos precios para quedar en el mismo nivel de utilidad que antes del cambio:

$$VC = e(\mathbf{p}^1, u^0) - e(\mathbf{p}^0, u^0) = e(\mathbf{p}^1, u^0) - w$$

Cuando los precios cambian de $\mathbf{p}^0$ a $\mathbf{p}^1$, el consumidor necesita un ingreso mínimo de $e(\mathbf{p}^1, u^0)$ para alcanzar la misma utilidad. La variación compensatoria es la diferencia entre ese ingreso mínimo y el ingreso actual. 

**Variación equivalente (VE):** ingreso que el consumidor estaría dispuesto a aceptar (o pagar) a los precios originales en lugar de que ocurra el cambio:

$$VE = e(\mathbf{p}^1, u^1) - e(\mathbf{p}^0, u^1) = w - e(\mathbf{p}^0, u^1)$$

Ambas medidas son exactas en el sentido de que eliminan el sesgo del efecto ingreso. Se calculan como áreas bajo la curva de demanda hicksiana a distintos niveles de utilidad. El CS está entre VC y VE para cambios de precio de bienes normales.

### 6.3 Exceso de carga (deadweight loss)

El **exceso de carga** de un impuesto es la pérdida de bienestar sobre y por encima del ingreso fiscal recaudado. Aproximando con elasticidades:

$$DWL \approx \frac{1}{2} \varepsilon_p^h \frac{t^2}{p} x$$

donde $t$ es el impuesto por unidad y $\varepsilon_p^h < 0$ es la elasticidad compensada. El exceso de carga es proporcional al cuadrado del impuesto (los impuestos pequeños tienen pérdidas cuadráticas) y a la elasticidad compensada (bienes más elásticos generan más distorsión).

---

## 7. Demanda agregada

### 7.1 El problema de la agregación

La demanda de mercado es la suma de las demandas individuales: $X_i(\mathbf{p}, \mathbf{w}) = \sum_h x_i^h(\mathbf{p}, w^h)$. El problema es que la demanda de mercado depende de la distribución del ingreso $\mathbf{w} = (w^1, \ldots, w^H)$, no solo del ingreso agregado $W = \sum_h w^h$.

La demanda agregada puede escribirse como función solo de $\mathbf{p}$ y $W$ (sin depender de la distribución) si y solo si todos los consumidores tienen **curvas de Engel paralelas y lineales** — lo que requiere preferencias homotéticas o cuasilineales.

### 7.2 La ley de Gorman

Gorman (1953) demostró que la demanda agregada puede tratarse como si proviniera de un agente representativo si y solo si las funciones de gasto individuales tienen la forma:

$$e^h(\mathbf{p}, u^h) = a^h(\mathbf{p}) + b(\mathbf{p}) u^h$$

donde $b(\mathbf{p})$ es común a todos los consumidores. En este caso, la distribución del ingreso no importa para la demanda agregada — solo el ingreso total. Este es el fundamento del agente representativo en macroeconomía, y sus condiciones son bastante restrictivas.

### 7.3 Propiedades de la demanda agregada

La demanda de mercado hereda la homogeneidad de grado cero y la ley de Walras de las demandas individuales. Sin embargo, la simetría y negativo-semidefinitismo de la matriz de Slutsky **no** se preservan en la agregación bajo condiciones generales — la demanda de mercado puede exhibir patrones que ningún consumidor individual exhibiría. El teorema de Sonnenschein-Mantel-Debreu establece que básicamente cualquier función continua que satisfaga homogeneidad y Walras puede ser una demanda de mercado.

---

## 8. Funciones de utilidad específicas: resumen de resultados

Con **Cobb-Douglas** $u = x_1^\alpha x_2^{1-\alpha}$:
- Marshalliana: $x_1 = \alpha w / p_1$, $x_2 = (1-\alpha)w / p_2$.
- Participaciones de gasto constantes: $p_i x_i / w = \alpha_i$.
- Función de gasto: $e = \bar{u} \cdot p_1^\alpha p_2^{1-\alpha} / [\alpha^\alpha (1-\alpha)^{1-\alpha}]$.
- Elasticidad-precio propia: $-1$ (unitariamente elástica).
- Elasticidad ingreso: $1$ (bien normal).

Con **CES** $u = [\alpha x_1^\rho + (1-\alpha)x_2^\rho]^{1/\rho}$:
- Elasticidad de sustitución constante: $\sigma = 1/(1-\rho)$.
- Cobb-Douglas es el caso límite $\rho \to 0$ ($\sigma \to 1$).
- Sustitutos perfectos: $\rho = 1$ ($\sigma \to \infty$).
- Complementos perfectos: $\rho \to -\infty$ ($\sigma \to 0$).

Con **cuasilineal** $u = v(x_1) + x_2$:
- Sin efecto ingreso sobre $x_1$: $\partial x_1 / \partial w = 0$.
- CS = VC = VE (medida exacta de bienestar).
- Utilidad marginal del ingreso constante.

---

## Referencias

- Vial, B. & Zurita, F. *Microeconomía*. Ediciones UC.
- Nicholson, W. (2008). *Teoría Microeconómica: Principios Básicos y Aplicaciones*. Cengage Learning.
- Mas-Colell, A., Whinston, M. & Green, J. (1995). *Microeconomic Theory*. Oxford University Press. Caps. 2–3.
- Deaton, A. & Muellbauer, J. (1980). *Economics and Consumer Behavior*. Cambridge University Press.
- Jensen, R.T. & Miller, N.H. (2008). *Giffen Behavior and Subsistence Consumption*. AER.