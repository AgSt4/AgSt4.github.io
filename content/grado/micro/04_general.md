---
title: "Equilibrio General en Competencia Perfecta"
date: 2026-03-15
draft: false
tags: ["microeconomía", "equilibrio general", "Pareto", "Edgeworth", "teoremas del bienestar", "Arrow-Debreu", "EAE2110"]
description: "Economía de intercambio puro, caja de Edgeworth, optimalidad de Pareto, equilibrio walrasiano, primer y segundo teorema del bienestar, equilibrio con producción."
---

**Curso:** Microeconomía I (EAE2110) · **Profesora:** María Luisa Vergara  
**Referencia principal:** Vial & Zurita — *Microeconomía* · Mas-Colell, Whinston & Green (1995) caps. 15–17 · Arrow & Debreu (1954)

---

## 1. Del equilibrio parcial al equilibrio general

El análisis de equilibrio parcial estudia un mercado en aislamiento — tomando como dados los precios y cantidades en todos los demás. Esta abstracción es útil para muchos propósitos pero ignora las interdependencias entre mercados: un impuesto al petróleo afecta no solo ese mercado sino el transporte, la energía, los salarios y el precio de prácticamente todos los bienes.

El **equilibrio general** estudia simultáneamente todos los mercados. La pregunta central es: ¿existe un vector de precios $\mathbf{p}^*$ que vacía simultáneamente todos los mercados, y qué propiedades de eficiencia tiene la asignación resultante?

Walras (1874) fue el primero en formular el estado del sistema económico como la solución de un sistema de ecuaciones simultáneas representando la demanda de bienes por parte de los consumidores, la oferta por parte de los productores, y la condición de equilibrio de que oferta iguale demanda en cada mercado. Sin embargo, no proveyó argumentos concluyentes de que ese sistema tiene solución.  La existencia del equilibrio walrasiano tuvo que esperar hasta Arrow y Debreu (1954).

---

## 2. La economía de intercambio puro

### 2.1 El modelo

La economía más simple de equilibrio general elimina la producción: los agentes solo intercambian dotaciones iniciales. Hay $I$ consumidores, $L$ bienes, y el consumidor $i$ tiene:
- Dotación inicial $\boldsymbol{\omega}^i \in \mathbb{R}^L_+$
- Preferencias representadas por $u^i(\mathbf{x}^i)$

La dotación agregada es $\bar{\boldsymbol{\omega}} = \sum_i \boldsymbol{\omega}^i$. Una **asignación** $(\mathbf{x}^1, \ldots, \mathbf{x}^I)$ es **factible** si:

$$\sum_i x^i_l \leq \bar{\omega}_l \quad \forall l = 1,\ldots,L$$

No se pueden consumir más bienes de los disponibles en la dotación agregada.

### 2.2 La caja de Edgeworth

Para el caso de dos consumidores ($I=2$) y dos bienes ($L=2$), la **caja de Edgeworth** representa gráficamente el conjunto completo de asignaciones factibles. La caja de Edgeworth, presentada originalmente en *Mathematical Psychics* (1881) y desarrollada en su forma familiar por Pareto (1906) y Bowley, permite representar todas las asignaciones factibles y las preferencias de ambos consumidores en un único diagrama. 

La caja tiene dimensiones $\bar{\omega}_1 \times \bar{\omega}_2$. Las asignaciones del consumidor 1 se leen desde la esquina inferior-izquierda; las del consumidor 2, desde la esquina superior-derecha (rotadas 180°). Las curvas de indiferencia de ambos consumidores se superponen en el mismo diagrama.

**La dotación inicial** es un punto específico en la caja. El intercambio lleva la economía a otra asignación dentro de la caja, manteniendo la factibilidad.

### 2.3 Optimalidad de Pareto

Una asignación $(\mathbf{x}^1, \ldots, \mathbf{x}^I)$ es **Pareto óptima** si no existe otra asignación factible $(\mathbf{x}'^1, \ldots, \mathbf{x}'^I)$ tal que $u^i(\mathbf{x}'^i) \geq u^i(\mathbf{x}^i)$ para todo $i$ con al menos una desigualdad estricta.

Intuitivamente: una asignación es Pareto óptima si es imposible mejorar a alguien sin empeorar a algún otro. No es un criterio de equidad — puede ser Pareto óptima una asignación muy desigual donde un agente tiene todo. Es un criterio de no-desperdicio: en una asignación no Pareto óptima hay ganancias de intercambio sin explotar.

**Condición de optimalidad:** con preferencias diferenciables y soluciones interiores, la optimalidad de Pareto requiere que las TMS sean iguales entre todos los consumidores para cualquier par de bienes:

$$TMS^i_{lk} = TMS^j_{lk} \quad \forall i,j \in I, \quad \forall l,k \in L$$

Si las TMS difieren, existe un intercambio mutuamente beneficioso — una contradicción con la optimalidad.

La herramienta matemática central es el teorema del hiperplano separador. Si los conjuntos de consumo preferido de todos los agentes (conjuntos estrictamente superiores a la asignación Pareto óptima) no se intersectan con el conjunto de asignaciones factibles, un hiperplano separador los divide — y su pendiente define los precios de equilibrio. 

**La curva de contrato** es el lugar geométrico de todas las asignaciones Pareto óptimas en la caja de Edgeworth — la curva donde las curvas de indiferencia de ambos consumidores son tangentes (TMS iguales). En el interior de la caja, la curva de contrato es la "lente" de intercambios mutuamente beneficiosos reducida a sus fronteras.

---

## 3. El equilibrio walrasiano

### 3.1 Definición

Un **equilibrio walrasiano** (o competitivo) es un par $(\mathbf{p}^*, \mathbf{x}^*)$ de precios y asignaciones tal que:

1. **Optimización individual:** para cada consumidor $i$, $\mathbf{x}^{*i}$ resuelve:
$$\max_{\mathbf{x}^i} u^i(\mathbf{x}^i) \quad \text{s.a.} \quad \mathbf{p}^* \cdot \mathbf{x}^i \leq \mathbf{p}^* \cdot \boldsymbol{\omega}^i$$

2. **Vaciado de mercados:** para cada bien $l$:
$$\sum_i x^{*i}_l = \sum_i \omega^i_l = \bar{\omega}_l$$

El ingreso de cada consumidor es el valor de su dotación a los precios de equilibrio: $w^i = \mathbf{p}^* \cdot \boldsymbol{\omega}^i$.

### 3.2 La ley de Walras

Con no-saciedad local, cada consumidor gasta todo su ingreso (la restricción presupuestaria es activa). Sumando sobre todos los consumidores:

$$\sum_i \mathbf{p} \cdot \mathbf{x}^i = \sum_i \mathbf{p} \cdot \boldsymbol{\omega}^i \implies \mathbf{p} \cdot \sum_i (\mathbf{x}^i - \boldsymbol{\omega}^i) = 0$$

Definiendo el exceso de demanda agregado $z_l(\mathbf{p}) = \sum_i (x^i_l - \omega^i_l)$, la **ley de Walras** establece:

$$\mathbf{p} \cdot \mathbf{z}(\mathbf{p}) = 0 \quad \forall \mathbf{p}$$

El valor del exceso de demanda agregado es cero a cualquier vector de precios — no solo en equilibrio. Corolario: si $L-1$ mercados están en equilibrio, el mercado $L$ también lo está automáticamente. El $L$-ésimo precio es redundante; se puede normalizar sin pérdida de generalidad (por ejemplo, $p_L = 1$).

### 3.3 Existencia del equilibrio: Arrow-Debreu (1954)

En 1954, McKenzie y el par Arrow y Debreu probaron independientemente la existencia de equilibrios generales invocando el teorema del punto fijo de Kakutani sobre los puntos fijos de una función continua desde un conjunto compacto y convexo hacia sí mismo. En el enfoque de Arrow-Debreu, la convexidad es esencial porque tales teoremas de punto fijo son inaplicables a conjuntos no convexos. 

Los supuestos necesarios para la existencia son:

- Preferencias continuas, estrictamente monótonas y convexas.
- Dotaciones estrictamente positivas para todos los consumidores.
- Conjuntos de producción convexos (cuando hay producción).

La prueba construye una función de exceso de demanda $\mathbf{z}(\mathbf{p})$ continua y homogénea de grado cero, y aplica el teorema del punto fijo para encontrar $\mathbf{p}^*$ tal que $\mathbf{z}(\mathbf{p}^*) \leq 0$.

Aunque generalmente (asumiendo convexidad) existe un equilibrio y será eficiente, las condiciones bajo las cuales será único son mucho más fuertes. El teorema de Sonnenschein-Mantel-Debreu establece que la función de exceso de demanda agregado hereda solo ciertas propiedades de las funciones de demanda individuales — continuidad, homogeneidad de grado cero, ley de Walras y comportamiento en el borde cuando los precios se acercan a cero — y que estas son las únicas restricciones reales que se pueden esperar de una función de exceso de demanda agregada. 

Este es el resultado conocido como "anything goes": la unicidad y estabilidad del equilibrio requieren supuestos adicionales fuertes más allá de los que garantizan existencia.

---

## 4. Los teoremas fundamentales del bienestar

### 4.1 Primer teorema del bienestar

**Teorema (Arrow-Debreu, 1951):** Si $(\mathbf{p}^*, \mathbf{x}^*)$ es un equilibrio walrasiano y las preferencias son localmente no saciadas, entonces $\mathbf{x}^*$ es Pareto óptima.

**Prueba:** Suponga por contradicción que $\mathbf{x}^*$ no es Pareto óptima. Existe entonces una asignación factible $\mathbf{x}'$ con $u^i(\mathbf{x}'^i) \geq u^i(\mathbf{x}^{*i})$ para todo $i$ y estrictamente mayor para algún $j$.

- Para el consumidor $j$: como $u^j(\mathbf{x}'^j) > u^j(\mathbf{x}^{*j})$ y $\mathbf{x}^{*j}$ maximiza $u^j$ sujeto al presupuesto, debe ser que $\mathbf{p}^* \cdot \mathbf{x}'^j > \mathbf{p}^* \cdot \boldsymbol{\omega}^j$.
- Para todo $i \neq j$: $u^i(\mathbf{x}'^i) \geq u^i(\mathbf{x}^{*i})$ implica $\mathbf{p}^* \cdot \mathbf{x}'^i \geq \mathbf{p}^* \cdot \boldsymbol{\omega}^i$ (por no-saciación local).

Sumando: $\mathbf{p}^* \cdot \sum_i \mathbf{x}'^i > \mathbf{p}^* \cdot \sum_i \boldsymbol{\omega}^i$. Pero la factibilidad exige $\sum_i \mathbf{x}'^i \leq \sum_i \boldsymbol{\omega}^i$, lo que implica $\mathbf{p}^* \cdot \sum_i \mathbf{x}'^i \leq \mathbf{p}^* \cdot \sum_i \boldsymbol{\omega}^i$. Contradicción. $\blacksquare$

El primer teorema formaliza la "mano invisible" de Adam Smith: el proceso descentralizado de precios lleva a una asignación eficiente sin coordinación central. La condición de localida no-saciación es débil — no requiere convexidad ni diferenciabilidad.

### 4.2 Segundo teorema del bienestar

**Teorema:** Si las preferencias son continuas, estrictamente convexas y monótonas, y $\mathbf{x}^*$ es una asignación Pareto óptima, entonces existe un vector de precios $\mathbf{p}$ tal que $(\mathbf{p}, \mathbf{x}^*)$ es un equilibrio walrasiano con transferencias apropiadas de dotaciones.

La prueba usa el teorema del hiperplano separador. Sea $(\mathbf{x}^*)$ una asignación Pareto óptima. Los conjuntos de consumo estrictamente preferidos a $\mathbf{x}^{*i}$ por cada consumidor no intersecan el conjunto de producciones netas factibles. Un hiperplano separador los divide — su pendiente define los precios $\mathbf{p}$. Con esos precios y dotaciones redistribuidas apropiadamente, cada consumidor maximiza su utilidad en $\mathbf{x}^{*i}$. 

El segundo teorema tiene implicancias de política fundamentales:

- **Separación entre eficiencia y equidad:** cualquier asignación Pareto óptima puede implementarse como equilibrio competitivo mediante transferencias de suma alzada que redistribuyan dotaciones. No hay trade-off entre eficiencia y equidad si se dispone del instrumento correcto (transferencias de suma alzada).
- **El rol de los precios:** los precios de equilibrio son las pendientes del hiperplano separador — reflejan las tasas de sustitución marginales en el óptimo social, coordinando la economía descentralizada.
- **Las limitaciones:** el teorema requiere convexidad (excluye economías de escala), que los mercados sean completos, y que las transferencias de suma alzada sean factibles — condiciones que raramente se cumplen todas simultáneamente en la práctica.

### 4.3 Interpretación conjunta

Los contenidos de ambos teoremas eran antiguas creencias en economía. Arrow y Debreu trataron recientemente esta cuestión con técnicas que permiten probar estas proposiciones. Esta afirmación es precisamente correcta; antes había creencias, ahora hay conocimiento. 

Los dos teoremas en conjunto describen la relación entre mercados y eficiencia:
- El **primer teorema** dice: si el mercado está en equilibrio, la asignación es eficiente.
- El **segundo teorema** dice: si queremos implementar una asignación eficiente específica, podemos usar el mercado redistribuyendo dotaciones.

El sistema de mercado es suficiente para la eficiencia (primer teorema) y necesario para implementarla (segundo teorema), bajo los supuestos del modelo.

---

## 5. Equilibrio general con producción

### 5.1 Estructura de la economía con producción

Se incorporan $J$ firmas. La firma $j$ tiene conjunto de producción $Y^j \subset \mathbb{R}^L$ — los vectores netos de producción factibles. El beneficio de la firma $j$ a precios $\mathbf{p}$ es:

$$\pi^j(\mathbf{p}) = \max_{\mathbf{y}^j \in Y^j} \mathbf{p} \cdot \mathbf{y}^j$$

Las firmas son de propiedad privada: el consumidor $i$ posee una participación $\theta^{ij} \geq 0$ en la firma $j$, con $\sum_i \theta^{ij} = 1$. El ingreso del consumidor es la suma del valor de su dotación más los dividendos:

$$w^i(\mathbf{p}) = \mathbf{p} \cdot \boldsymbol{\omega}^i + \sum_j \theta^{ij} \pi^j(\mathbf{p})$$

### 5.2 Definición del equilibrio walrasiano con producción

Un equilibrio walrasiano es una tripleta $(\mathbf{p}^*, \mathbf{x}^*, \mathbf{y}^*)$ tal que:

1. Cada firma $j$ maximiza beneficios: $\mathbf{p}^* \cdot \mathbf{y}^{*j} \geq \mathbf{p}^* \cdot \mathbf{y}^j$ para todo $\mathbf{y}^j \in Y^j$.
2. Cada consumidor $i$ maximiza utilidad sujeto a su restricción presupuestaria con ingreso $w^i(\mathbf{p}^*)$.
3. Vaciado de mercados: $\sum_i \mathbf{x}^{*i} = \sum_i \boldsymbol{\omega}^i + \sum_j \mathbf{y}^{*j}$.

### 5.3 Condiciones de optimalidad con producción

La optimalidad de Pareto en una economía con producción requiere la igualdad de TMS entre consumidores y la igualdad entre TMS y tasa marginal de transformación (TMT):

$$TMS^i_{lk} = TMT_{lk} \quad \forall i, \quad \forall l,k$$

La **TMT** mide cuánto del bien $l$ debe sacrificarse para producir una unidad más del bien $k$. En equilibrio competitivo, las firmas igualan $p_l = CMg_l$, por lo que $TMT_{lk} = p_l/p_k$. Los consumidores igualan $TMS^i_{lk} = p_l/p_k$. La igualdad se satisface automáticamente en equilibrio.

Los teoremas del bienestar se mantienen sin modificación con producción. Cualquier equilibrio competitivo es Pareto eficiente (primer teorema). Con convexidad, cualquier asignación Pareto eficiente puede ser descentralizada por mercados competitivos tras transferencias de suma alzada apropiadas (segundo teorema). 

---

## 6. Limitaciones del modelo Arrow-Debreu

Greenwald y Stiglitz (1986) demostraron que los teoremas fundamentales del bienestar no se sostienen si hay mercados incompletos o información imperfecta. El paper establece que un equilibrio competitivo de una economía con información asimétrica no es genéricamente ni siquiera eficiente en el sentido de Pareto restringido. Un gobierno que enfrenta las mismas restricciones de información que los agentes privados puede no obstante encontrar intervenciones que mejoren el bienestar en sentido de Pareto. 

Las fallas del modelo identifican cuándo los mercados no logran la eficiencia:

**Externalidades:** cuando las acciones de un agente afectan directamente a otros sin pasar por el sistema de precios, la condición $TMS = TMT$ falla para los bienes con externalidad — el precio no refleja el costo o beneficio social completo.

**Bienes públicos:** bienes no rivales y no excluyentes no pueden provisionarse eficientemente por el mercado — la provisión privada es insuficiente porque los agentes se comportan como free-riders.

**Información asimétrica:** sin un conjunto completo de mercados Arrow-Debreu, el primer teorema del bienestar generalmente no se sostiene. Hay potencialmente espacio para intervención gubernamental y las preguntas de política se vuelven no triviales. 

**Economías de escala:** la convexidad excluida por rendimientos crecientes implica que el equilibrio competitivo puede no existir — los monopolios naturales requieren regulación.

**Mercados incompletos:** si no existen mercados para todos los bienes contingentes (estados del mundo), la asignación del riesgo puede ser ineficiente incluso con preferencias convexas.

Estas fallas son el fundamento microeconómico de la intervención del gobierno — el tema del próximo capítulo sobre bienes públicos y externalidades.

---

## 7. El modelo Arrow-Debreu como fundamento de la economía moderna

La teoría de equilibrio general tanto estudia economías usando el modelo de precios de equilibrio como busca determinar bajo qué circunstancias se sostienen los supuestos del equilibrio general. La teoría alcanzó su forma moderna con el trabajo de McKenzie, Arrow y Debreu en los 1950s. La diferencia entre microeconomía y macroeconomía ya no es tan clara como solía ser, puesto que gran parte de la macroeconomía moderna ha enfatizado las fundaciones microeconómicas y ha construido modelos de equilibrio general de las fluctuaciones macroeconómicas. 

El modelo Arrow-Debreu extiende el concepto de bien para incluir entregas en distintas fechas y estados del mundo. Los precios de estados Arrow-Debreu definen el valor presente justo de los pagos contingentes y el reparto óptimo del riesgo entre agentes — constituyendo las microfundaciones de la valoración sin arbitraje en finanzas. 

---

## Referencias

- Arrow, K.J. & Debreu, G. (1954). *Existence of an Equilibrium for a Competitive Economy*. Econometrica.
- Debreu, G. (1959). *Theory of Value*. Yale University Press.
- Edgeworth, F.Y. (1881). *Mathematical Psychics*. Kegan Paul.
- Greenwald, B. & Stiglitz, J. (1986). *Externalities in Economies with Imperfect Information and Incomplete Markets*. QJE.
- Mas-Colell, A., Whinston, M. & Green, J. (1995). *Microeconomic Theory*. Oxford. Caps. 15–17.
- Vial, B. & Zurita, F. *Microeconomía*. Ediciones UC.
- Nicholson, W. (2008). *Teoría Microeconómica*. Cengage. Cap. 13.
- Levin, J. (2006). *General Equilibrium*. Stanford lecture notes.