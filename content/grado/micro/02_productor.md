---
title: "Teoría de la Producción y Oferta"
date: 2026-03-15
draft: false
tags: ["microeconomía", "producción", "costos", "oferta", "dualidad", "Shephard", "Hotelling", "EAE2110"]
description: "Tecnología y funciones de producción, CMP, función de costos, lema de Shephard, PMP, función de beneficios, lema de Hotelling, función de oferta y dualidad producción-costo."
---

**Curso:** Microeconomía I (EAE2110) · **Profesora:** María Luisa Vergara  
**Referencia principal:** Vial & Zurita — *Microeconomía* · Nicholson (2008) · Mas-Colell, Whinston & Green (1995) caps. 5–6

---

## 1. Tecnología

### 1.1 El conjunto de producción

La firma transforma insumos $\mathbf{z} \in \mathbb{R}^N_+$ en producto $q \in \mathbb{R}_+$. La **tecnología** queda completamente descrita por el **conjunto de posibilidades de producción**:

$$Y = \{(\mathbf{z}, q) \in \mathbb{R}^{N+1} : q \text{ es producible con } \mathbf{z}\}$$

Una representación equivalente es el **conjunto de requisitos de insumos** para producir al menos $q$:

$$V(q) = \{\mathbf{z} \in \mathbb{R}^N_+ : (\mathbf{z}, q) \in Y\}$$

Propiedades estándar de $V(q)$:
- **No vacío** para $q$ en el rango factible.
- **Libre disposición:** si $\mathbf{z} \in V(q)$ y $\mathbf{z}' \geq \mathbf{z}$, entonces $\mathbf{z}' \in V(q)$ — insumos adicionales nunca reducen lo producible.
- **Convexidad:** si $\mathbf{z}, \mathbf{z}' \in V(q)$, entonces $\alpha\mathbf{z} + (1-\alpha)\mathbf{z}' \in V(q)$ — combinaciones de planes factibles son factibles. Implica isocuantas convexas hacia el origen.

### 1.2 La función de producción

Cuando la frontera de $V(q)$ puede describirse como una función, la **función de producción** $f: \mathbb{R}^N_+ \to \mathbb{R}_+$ satisface:

$$q^* = f(\mathbf{z}) \equiv \max\{q : \mathbf{z} \in V(q)\}$$

Es el nivel máximo de producto alcanzable con el vector de insumos $\mathbf{z}$.

### 1.3 Productividades marginales e isocuantas

La **productividad marginal** del insumo $i$ es:

$$PM_i = \frac{\partial f}{\partial z_i} > 0$$

Mide cuánto adicional se produce con una unidad más del insumo $i$, manteniendo los demás fijos. Con libre disposición y no-saciedad técnica, $PM_i > 0$.

La **isocuanta** para nivel $\bar{q}$ es el conjunto $\{\mathbf{z} : f(\mathbf{z}) = \bar{q}\}$ — todas las combinaciones de insumos que producen exactamente $\bar{q}$. Su pendiente es la **tasa marginal de sustitución técnica**:

$$TMST_{ij} = -\frac{dz_j}{dz_i}\bigg|_{f=\bar{q}} = \frac{PM_i}{PM_j}$$

La TMST mide cuántas unidades del insumo $j$ puede reemplazar una unidad del insumo $i$ sin alterar el producto. Con isocuantas convexas, la TMST es decreciente en $z_i/z_j$ — la ley de la TMST decreciente, análoga a la TMS decreciente del consumidor.

### 1.4 Rendimientos a escala

Los **rendimientos a escala** caracterizan cómo responde el producto cuando todos los insumos se escalan proporcionalmente. Para $\lambda > 1$:

- **Rendimientos constantes a escala (RCE):** $f(\lambda\mathbf{z}) = \lambda f(\mathbf{z})$.
- **Rendimientos crecientes a escala (RCrE):** $f(\lambda\mathbf{z}) > \lambda f(\mathbf{z})$.
- **Rendimientos decrecientes a escala (RDE):** $f(\lambda\mathbf{z}) < \lambda f(\mathbf{z})$.

Con RCE, la función de producción es homogénea de grado 1. El **teorema de Euler** implica que $\sum_i z_i \cdot PM_i = q$ — el producto se agota exactamente al pagar a cada insumo su productividad marginal, lo que conecta con la distribución funcional del ingreso en mercados competitivos.

### 1.5 Elasticidad de sustitución

La **elasticidad de sustitución** $\sigma$ mide la sensibilidad de la razón de insumos ante cambios en la TMST, manteniendo el producto constante:

$$\sigma = \frac{d\ln(z_j/z_i)}{d\ln(TMST_{ij})}$$

Para la función CES $f = [\alpha z_1^\rho + (1-\alpha)z_2^\rho]^{1/\rho}$, $\sigma = 1/(1-\rho)$ es constante. Los casos límite son: $\rho \to 0$ ($\sigma = 1$, Cobb-Douglas), $\rho = 1$ ($\sigma \to \infty$, sustitutos perfectos) y $\rho \to -\infty$ ($\sigma = 0$, complementos perfectos).

### 1.6 Funciones de producción canónicas

**Cobb-Douglas:** $f = Az_1^\alpha z_2^\beta$
- Rendimientos: constantes si $\alpha + \beta = 1$; crecientes si $> 1$; decrecientes si $< 1$.
- Elasticidades de producto de cada insumo son $\alpha$ y $\beta$ — constantes.
- $\sigma = 1$.

**Leontief:** $f = \min\{z_1/a, z_2/b\}$
- Insumos complementarios perfectos; no hay sustitución.
- $\sigma = 0$.

**Lineal:** $f = az_1 + bz_2$
- Sustitutos perfectos.
- $\sigma \to \infty$.

---

## 2. El problema de minimización de costos (CMP)

### 2.1 Formulación

El problema de minimización de costos involucra derivar funciones de demanda condicional de factores y la función de costos.  Dados precios de insumos $\mathbf{w} \gg 0$ y nivel de producto objetivo $q$:

$$\min_{\mathbf{z} \geq 0} \mathbf{w} \cdot \mathbf{z} \quad \text{s.a.} \quad f(\mathbf{z}) \geq q$$

El CMP es el dual de la teoría del productor, análogo al EMP del consumidor con $q$ en lugar de $\bar{u}$.

### 2.2 Condiciones de primer orden (solución interior)

El Lagrangiano es:

$$\mathcal{L} = \mathbf{w} \cdot \mathbf{z} - \lambda[f(\mathbf{z}) - q]$$

Las CPO son:

$$w_i = \lambda \frac{\partial f}{\partial z_i} \quad \forall i, \qquad f(\mathbf{z}) = q$$

Dividiendo las CPO para dos insumos:

$$\frac{w_i}{w_j} = \frac{PM_i}{PM_j} = TMST_{ij}$$

La condición de optimalidad iguala la razón de precios de insumos con la TMST: la tasa técnica de sustitución debe igualar la tasa de sustitución del mercado. Geométricamente, la isocuanta es tangente a la isocosto.

**Interpretación de $\lambda$:** el multiplicador es el **costo marginal** — cuánto sube el costo mínimo si se exige producir una unidad adicional. Por el teorema de la envolvente: $\lambda = \partial C / \partial q \equiv MC$.

### 2.3 Demanda condicional de factores

La solución del CMP es la **demanda condicional de factores** $\mathbf{z}(\mathbf{w}, q)$: los insumos óptimos para producir $q$ al menor costo posible. Se llama "condicional" porque condiciona en el nivel de producto — no depende del precio del output.

Propiedades:
- Homogénea de grado cero en $\mathbf{w}$: si todos los precios de insumos se duplican, la combinación óptima de insumos no cambia — solo el costo total.
- La demanda propia es no creciente en el precio propio: $\partial z_i / \partial w_i \leq 0$.
- Simetría: $\partial z_i / \partial w_j = \partial z_j / \partial w_i$.

### 2.4 La función de costos

La **función de costos** es el valor minimizado del CMP:

$$C(\mathbf{w}, q) = \mathbf{w} \cdot \mathbf{z}(\mathbf{w}, q) = \min_\mathbf{z}\{\mathbf{w} \cdot \mathbf{z} : f(\mathbf{z}) \geq q\}$$

Propiedades de $C(\mathbf{w}, q)$:
- **Homogénea de grado 1 en $\mathbf{w}$:** si todos los precios de insumos se duplican, el costo mínimo se duplica.
- **No decreciente en $\mathbf{w}$ y en $q$:** más caro o más producto nunca reduce el costo mínimo.
- **Cóncava en $\mathbf{w}$:** la firma se beneficia de la variabilidad en precios porque puede reasignar insumos — $\nabla^2_\mathbf{w} C \leq 0$.
- Refleja completamente la tecnología: la función de producción puede recuperarse de $C$.

### 2.5 El lema de Shephard para el productor

En teoría del productor, el lema de Shephard interpreta la función de costos — que minimiza los gastos de producción para un producto fijo — en términos de demandas condicionales de factores. Muestra cómo las variaciones en los precios de insumos afectan los costos mínimos, destacando las posibilidades de sustitución entre factores mientras se mantiene el producto constante. 

Formalmente:

$$z_i(\mathbf{w}, q) = \frac{\partial C(\mathbf{w}, q)}{\partial w_i}$$

La demanda condicional del insumo $i$ es la derivada parcial de la función de costos respecto al precio de ese insumo. Resultado directo del teorema de la envolvente aplicado al CMP — análogo exacto del lema de Shephard del consumidor con $e(\mathbf{p}, \bar{u})$.

### 2.6 Estructura de costos

Definiciones estándar:

$$CT(q) = C(\mathbf{w}, q) \quad \text{(costo total)}$$
$$CF = C(\mathbf{w}, 0) \quad \text{(costo fijo)}$$
$$CV(q) = C(\mathbf{w}, q) - CF \quad \text{(costo variable)}$$
$$CMg(q) = \frac{\partial C}{\partial q} = \lambda \quad \text{(costo marginal)}$$
$$CMe(q) = \frac{C(q)}{q} \quad \text{(costo medio total)}$$
$$CVMe(q) = \frac{CV(q)}{q} \quad \text{(costo variable medio)}$$

Relaciones clave:
- $CMg < CMe \implies CMe$ decrece; $CMg > CMe \implies CMe$ crece.
- $CMg$ corta $CMe$ y $CVMe$ en sus mínimos.
- En el largo plazo no hay costos fijos: $CT = CV$.

### 2.7 Rendimientos a escala y estructura de costos

Los rendimientos a escala de la función de producción se reflejan en la función de costos:

| Rendimientos | Costo marginal vs. medio | Estructura de costos |
|---|---|---|
| Constantes | $CMg = CMe$ | Costo total lineal en $q$ |
| Crecientes | $CMg < CMe$ (CMe decreciente) | Economías de escala |
| Decrecientes | $CMg > CMe$ (CMe creciente) | Deseconomías de escala |

Las **economías de escala** se miden por la elasticidad del costo respecto al producto:

$$\varepsilon_{Cq} = \frac{\partial C / C}{\partial q / q} = \frac{CMg}{CMe}$$

$\varepsilon_{Cq} < 1$ implica economías de escala (RCrE); $\varepsilon_{Cq} > 1$ implica deseconomías (RDE).

---

## 3. El problema de maximización de beneficios (PMP)

### 3.1 Formulación

El problema de maximización de beneficios involucra derivar la función de oferta del producto, la función de beneficios y las funciones de demanda incondicional de factores. 

Dados el precio del producto $p > 0$ y los precios de insumos $\mathbf{w} \gg 0$:

$$\max_{q \geq 0, \mathbf{z} \geq 0} pq - \mathbf{w} \cdot \mathbf{z} \quad \text{s.a.} \quad f(\mathbf{z}) \geq q$$

Equivalentemente, dado que la restricción será activa en el óptimo:

$$\max_{q \geq 0} pq - C(\mathbf{w}, q)$$

### 3.2 Condiciones de primer orden

La CPO de primer orden:

$$p = \frac{\partial C}{\partial q} = CMg(\mathbf{w}, q)$$

**El precio del producto iguala el costo marginal.** Esta es la condición central de la teoría de la firma competitiva: la firma expande la producción mientras el ingreso marginal (el precio) supere el costo marginal, e iguala ambos en el óptimo.

La condición de segundo orden requiere $\partial^2 C / \partial q^2 \geq 0$ — el costo marginal debe ser no decreciente en el óptimo. Esto requiere que la función de producción sea estrictamente cóncava (RDE) o que existan costos fijos que generen una curva de CMg en forma de U.

### 3.3 La función de oferta

La solución del PMP es la **función de oferta** $q^*(p, \mathbf{w})$: la cantidad que maximiza beneficios a cada precio. Se obtiene invirtiendo la condición $p = CMg(q)$ para despejar $q$.

Propiedades de $q^*(p, \mathbf{w})$:
- **Homogénea de grado cero en $(p, \mathbf{w})$:** si todos los precios (producto e insumos) se duplican, la cantidad óptima no cambia — solo los beneficios nominales.
- **No decreciente en $p$:** $\partial q^* / \partial p \geq 0$ — la **ley de la oferta**. Más precio incentiva más producción.
- **No creciente en $w_i$:** $\partial q^* / \partial w_i \leq 0$ — insumos más caros reducen la producción óptima.

### 3.4 La decisión de operar: precio de cierre

En el corto plazo con costos fijos irrecuperables, la firma opera si el ingreso cubre los costos variables: $p \geq CVMe(q^*)$. Si $p < CVMe$, la firma cierra porque opera generaría más pérdidas que no operar.

En el largo plazo, la firma sale del mercado si $p < CMe(q^*)$ — si no cubre la totalidad de sus costos incluyendo el retorno normal al capital.

**El punto de cierre** es el mínimo de la curva de $CVMe$; el **punto de equilibrio** es el mínimo de la curva de $CMe$. La curva de oferta de corto plazo es el segmento de $CMg$ por encima del mínimo de $CVMe$.

### 3.5 La función de beneficios

La **función de beneficios** es el valor maximizado del PMP:

$$\pi(p, \mathbf{w}) = pq^*(p,\mathbf{w}) - C(\mathbf{w}, q^*(p,\mathbf{w}))$$

Propiedades:
- Homogénea de grado 1 en $(p, \mathbf{w})$: si todos los precios se duplican, los beneficios se duplican.
- No decreciente en $p$ y no creciente en $\mathbf{w}$.
- **Convexa en $(p, \mathbf{w})$:** la firma puede siempre al menos hacer lo que hacía antes cuando los precios cambian — los beneficios no caen proporcionalmente a la distancia desde el punto original.

### 3.6 El lema de Hotelling

Hotelling (1932) nos proveyó el lema de Hotelling y la monotonicidad cíclica. El lema de Hotelling establece que $(x, y) \in \partial\pi(p,w)$ si y solo si $(x,y)$ maximiza los beneficios a precios $(p,w)$. 

Para la firma competitiva con función de beneficios diferenciable:

$$q^*(p, \mathbf{w}) = \frac{\partial \pi}{\partial p} \qquad z_i(p, \mathbf{w}) = -\frac{\partial \pi}{\partial w_i}$$

La oferta óptima es la derivada de los beneficios respecto al precio del producto; la demanda incondicional de cada insumo es (menos) la derivada de los beneficios respecto al precio de ese insumo. Resultado directo del teorema de la envolvente aplicado al PMP.

La **demanda incondicional de factores** $z_i(p, \mathbf{w})$ difiere de la condicional $z_i(\mathbf{w}, q)$ en que no condiciona en el nivel de producto — depende también de $p$ porque el nivel de producción se determina endógenamente en el PMP.

---

## 4. La dualidad producción-costo

### 4.1 La estructura dual

El teorema de la envolvente provee una relación directa entre problemas primal y dual de optimización. Diferenciando la función de costos respecto a los precios de insumos genera el vector de demandas condicionales de factores que minimizan costos. 

La dualidad completa entre producción y costos establece que existe una correspondencia uno-a-uno entre funciones de producción con propiedades regulares y funciones de costos con propiedades regulares. La función de producción puede recuperarse completamente de la función de costos:

$$f(\mathbf{z}) = \max_q\{q : C(\mathbf{w}, q) \leq \mathbf{w} \cdot \mathbf{z} \; \forall \mathbf{w} \gg 0\}$$

Esta dualidad tiene implicancias prácticas importantes: es posible especificar y estimar funciones de costos flexibles directamente de los datos de costo y precios de insumos, sin necesidad de conocer la función de producción subyacente.

### 4.2 El triángulo de dualidad

Anidados dentro del proceso están el lema de Shephard, el lema de Hotelling, relaciones matemáticas directas e indirectas, y otros elementos que contribuyen a la dinámica del proceso. 

Las relaciones de dualidad se organizan en tres vértices:

$$\boxed{f(\mathbf{z})} \xrightarrow{\text{CMP}} \boxed{C(\mathbf{w}, q)} \xrightarrow{\text{Shephard}} \boxed{z_i(\mathbf{w}, q)}$$

$$\boxed{f(\mathbf{z})} \xrightarrow{\text{PMP}} \boxed{\pi(p, \mathbf{w})} \xrightarrow{\text{Hotelling}} \boxed{q^*(p,\mathbf{w}), z_i(p,\mathbf{w})}$$

El CMP y el PMP son dos rutas alternativas hacia las mismas elecciones óptimas de la firma. En el óptimo del PMP, $q^* = q^*(p,\mathbf{w})$ y las demandas incondicionales coinciden con las condicionales evaluadas en ese $q^*$: $z_i(p,\mathbf{w}) = z_i(\mathbf{w}, q^*(p,\mathbf{w}))$.

---

## 5. Estática comparativa: efectos de cambios en precios

### 5.1 Efectos sobre la oferta

De la condición de optimalidad $p = CMg(\mathbf{w}, q^*)$:

$$\frac{\partial q^*}{\partial p} = \frac{1}{\partial CMg / \partial q} = \frac{1}{C_{qq}} > 0$$

La oferta es creciente en el precio — la ley de la oferta — con magnitud inversamente proporcional a la pendiente del costo marginal.

$$\frac{\partial q^*}{\partial w_i} = -\frac{C_{qw_i}}{C_{qq}}$$

El signo depende de $C_{qw_i} = \partial CMg / \partial w_i$: si el insumo $i$ es más utilizado en los niveles de producción altos (insumo "variable"), un alza en $w_i$ eleva el CMg y reduce $q^*$.

### 5.2 La ley del insumo demandado

De la convexidad de $\pi$ en $(p, \mathbf{w})$ y el lema de Hotelling:

$$\frac{\partial z_i}{\partial w_i} = -\frac{\partial^2 \pi}{\partial w_i^2} \leq 0$$

La demanda incondicional de cada insumo es no creciente en su propio precio — **ley de la demanda del insumo**. Es la contraparte productiva de la ley de la demanda del consumidor, y se deriva directamente de la convexidad de la función de beneficios.

### 5.3 Simetría de efectos cruzados

De la convexidad de $\pi$:

$$\frac{\partial z_i}{\partial w_j} = -\frac{\partial^2 \pi}{\partial w_i \partial w_j} = \frac{\partial z_j}{\partial w_i}$$

Los efectos cruzados sobre la demanda de insumos son simétricos — análogo exacto de la simetría de la matriz de Slutsky.

---

## 6. Oferta agregada

La **oferta de mercado** es la suma horizontal de las ofertas individuales de las $H$ firmas:

$$Q^S(p, \mathbf{w}) = \sum_{h=1}^H q_h^*(p, \mathbf{w})$$

En el largo plazo con libre entrada, el número de firmas es endógeno. Si todas las firmas son idénticas con costo mínimo $\bar{p}$, la oferta de largo plazo es perfectamente elástica a $p = \bar{p}$ — el precio iguala el mínimo de la curva de costo medio de largo plazo. En el corto plazo con factores fijos, la oferta tiene pendiente positiva finita.

La **elasticidad-precio de la oferta** es:

$$\varepsilon_S = \frac{\partial Q^S}{\partial p} \cdot \frac{p}{Q^S} = \frac{p}{Q^S \cdot C_{qq}}$$

Es más alta cuando el costo marginal es poco sensible a cambios en la cantidad (tecnologías más flexibles) y en el largo plazo respecto al corto (mayor capacidad de ajuste).

---

## 7. Funciones específicas: resumen

Con **Cobb-Douglas** $f = z_1^\alpha z_2^\beta$ con $\alpha + \beta < 1$ (RDE):
- Demanda condicional: $z_i(\mathbf{w}, q) = A_i(\alpha, \beta, w_1, w_2) \cdot q^{1/(\alpha+\beta)}$.
- Función de costos: $C(\mathbf{w}, q) = B(\alpha, \beta) \cdot w_1^{\alpha/(\alpha+\beta)} w_2^{\beta/(\alpha+\beta)} \cdot q^{1/(\alpha+\beta)}$.
- Elasticidad costo-producto: $1/(\alpha+\beta) > 1$ con RDE.

Con **Leontief** $f = \min\{z_1/a, z_2/b\}$:
- Demandas condicionales: $z_1 = aq$, $z_2 = bq$ — proporciones fijas independientes de precios.
- Función de costos: $C(\mathbf{w}, q) = (aw_1 + bw_2)q$ — lineal en $q$.

Con **CES** $f = [\alpha z_1^\rho + (1-\alpha)z_2^\rho]^{1/\rho}$:
- Función de costos: $C(\mathbf{w}, q) = [\alpha^{\sigma} w_1^{1-\sigma} + (1-\alpha)^{\sigma} w_2^{1-\sigma}]^{1/(1-\sigma)} \cdot q$.
- Demanda condicional: $z_i \propto (w_i/p_i)^{-\sigma} q$.

---

## Referencias

- Vial, B. & Zurita, F. *Microeconomía*. Ediciones UC.
- Nicholson, W. (2008). *Teoría Microeconómica*. Cengage Learning.
- Mas-Colell, A., Whinston, M. & Green, J. (1995). *Microeconomic Theory*. Oxford University Press. Caps. 5–6.
- Shephard, R.W. (1953). *Cost and Production Functions*. Princeton University Press.
- Hotelling, H. (1932). *Edgeworth's Taxation Paradox and the Nature of Demand and Supply Functions*. JPE.
- Varian, H. (1992). *Microeconomic Analysis*. 3ra ed. Norton.
- Levin, J. & Milgrom, P. (2004). *Producer Theory*. Stanford lecture notes.