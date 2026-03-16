---
title: "Equilibrio Parcial en Competencia Perfecta"
date: 2026-03-15
draft: false
tags: ["microeconomía", "competencia perfecta", "equilibrio parcial", "excedente", "incidencia tributaria", "pérdida irrecuperable", "EAE2110"]
description: "Equilibrio competitivo, análisis de bienestar, excedente del consumidor y productor, intervenciones de política: impuestos, subsidios, precio mínimo y precio máximo."
---

**Curso:** Microeconomía I (EAE2110) · **Profesora:** María Luisa Vergara  
**Referencia principal:** Vial & Zurita — *Microeconomía* · Nicholson (2008) · Mas-Colell, Whinston & Green (1995) cap. 10

---

## 1. El modelo de competencia perfecta

### 1.1 Los supuestos

El modelo de competencia perfecta describe un mercado en que:

1. **Precio-aceptantes:** ningún agente individual tiene influencia sobre el precio de mercado — tanto firmas como consumidores toman $p$ como dado.
2. **Bien homogéneo:** el producto de todas las firmas es idéntico desde la perspectiva del consumidor.
3. **Libre entrada y salida:** en el largo plazo, las firmas pueden entrar o salir del mercado sin costos hundidos.
4. **Información perfecta:** todos los agentes conocen precios y calidades.

Bajo estos supuestos, el precio de mercado emerge del proceso competitivo como la única variable de coordinación entre oferentes y demandantes.

### 1.2 La firma precio-aceptante

Una firma precio-aceptante enfrenta una curva de demanda perfectamente elástica a $p$ — puede vender cualquier cantidad al precio de mercado, pero nada a un precio superior. Su problema es elegir $q$ para maximizar beneficios:

$$\max_q \pi = pq - C(q)$$

La CPO es $p = CMg(q)$: el precio iguala el costo marginal. La firma expande la producción mientras cada unidad adicional genere ingresos mayores a sus costos. La condición de segundo orden requiere $CMg'(q) \geq 0$ en el óptimo.

La **función de oferta individual** es la relación $q^*(p)$ obtenida de invertir $p = CMg(q)$:

$$q^*(p) = CMg^{-1}(p)$$

Es el segmento de la curva de $CMg$ por encima del mínimo del costo variable medio (en el corto plazo) o del costo medio total (en el largo plazo).

---

## 2. El equilibrio de mercado

### 2.1 Condición de equilibrio

El equilibrio de mercado es el par $(p^*, Q^*)$ que vacía el mercado:

$$Q^D(p^*) = Q^S(p^*)$$

donde $Q^D$ es la demanda agregada y $Q^S = \sum_h q_h^*(p)$ la oferta agregada. El precio $p^*$ es el único precio al que los planes de compradores y vendedores son mutuamente consistentes.

### 2.2 Equilibrio de largo plazo

En el largo plazo con libre entrada, los beneficios económicos se agotan. Si $\pi > 0$, nuevas firmas entran → la oferta aumenta → $p$ cae hasta que $\pi = 0$. Si $\pi < 0$, firmas salen → la oferta cae → $p$ sube hasta que $\pi = 0$. El equilibrio de largo plazo requiere:

$$p^{LP} = CMe_{min} = CMg$$

El precio de largo plazo iguala el mínimo del costo medio total. En este punto, la firma no tiene incentivo a entrar ni a salir — la curva de oferta de largo plazo de la industria es perfectamente elástica a $p^{LP}$ si las firmas son idénticas.

Con firmas heterogéneas, las firmas con menores costos generan **rentas económicas** (cuasi-rentas): el precio de mercado supera su costo medio mínimo. La entrada empuja el precio hasta el costo mínimo de la firma marginal — la menos eficiente que aún opera.

---

## 3. Análisis de bienestar: excedentes

### 3.1 Excedente del consumidor

El **excedente del consumidor (EC)** es la diferencia entre la disposición a pagar de los consumidores y el precio efectivamente pagado. Geométricamente, es el área bajo la curva de demanda y sobre el precio de equilibrio:

$$EC = \int_0^{Q^*} P^D(q) dq - p^* Q^*$$

donde $P^D(q)$ es la demanda inversa. El EC mide la ganancia neta de los consumidores de participar en el mercado — cuánto valoran el bien por encima de lo que pagan.

Con demanda lineal $P^D = a - bQ$:

$$EC = \frac{1}{2}(a - p^*)Q^* = \frac{(a-p^*)^2}{2b}$$

### 3.2 Excedente del productor

El **excedente del productor (EP)** es la diferencia entre el ingreso recibido y el costo variable de producción — el área sobre la curva de oferta y bajo el precio:

$$EP = p^* Q^* - \int_0^{Q^*} CMg(q) dq = p^* Q^* - CV(Q^*)$$

El EP equivale al beneficio económico más los costos fijos irrecuperables. En el largo plazo sin costos fijos, $EP = \pi$.

### 3.3 Excedente total y eficiencia

El **excedente total (ET)** o bienestar social es la suma del excedente del consumidor y del productor:

$$ET = EC + EP = \int_0^{Q^*}[P^D(q) - CMg(q)]dq$$

El equilibrio competitivo maximiza el ET. La prueba es directa: para cualquier $Q < Q^*$, existe una unidad donde $P^D > CMg$ — un agente que valora la unidad más de lo que cuesta producirla — por lo que producirla aumenta el ET. Para $Q > Q^*$, $CMg > P^D$ y producir esa unidad reduce el ET. El punto $Q^*$ donde $P^D = CMg$ es el único que agota las ganancias de intercambio.

Este resultado es el **primer teorema del bienestar** en equilibrio parcial: el equilibrio competitivo asigna eficientemente en el sentido de Pareto, dado que maximiza el excedente total.

---

## 4. Intervenciones del gobierno

Las intervenciones del gobierno alteran el equilibrio competitivo y redistribuyen el excedente. El análisis de bienestar evalúa sistemáticamente estas redistribuciones y la pérdida irrecuperable asociada.

### 4.1 Impuestos

#### El cuña fiscal

Un impuesto por unidad $t$ sobre productores introduce una brecha entre el precio que paga el consumidor $p_c$ y el precio que recibe el productor $p_p$:

$$p_c - p_p = t$$

La condición de equilibrio del mercado con impuesto es $Q^D(p_c) = Q^S(p_p) = Q^S(p_c - t)$. Gráficamente, la curva de oferta se desplaza hacia arriba en $t$.

#### Incidencia tributaria

El impuesto introduce una cuña entre el precio del consumidor y el del productor. Es un resultado contraintuitivo que no importa si el consumidor o el productor paga el impuesto — al final, ni la carga del impuesto ni la pérdida irrecuperable dependen de quién envía el ingreso tributario al gobierno. 

La **fracción de traspaso** (pass-through fraction) determina cuánto del impuesto recae sobre los consumidores:

$$PTF = \frac{p_c - p_c^0}{t} = \frac{\varepsilon_S}{\varepsilon_S - \varepsilon_D} \in [0,1]$$

donde $\varepsilon_S > 0$ y $\varepsilon_D < 0$ son las elasticidades de oferta y demanda. La fracción complementaria $1 - PTF = -\varepsilon_D/(\varepsilon_S - \varepsilon_D)$ recae sobre los productores.

**Casos extremos:**

| Configuración | Incidencia | Intuición |
|---|---|---|
| Oferta perfectamente elástica ($\varepsilon_S \to \infty$) | 100% consumidores | Productores no pueden absorber ningún impuesto sin salir del mercado |
| Oferta perfectamente inelástica ($\varepsilon_S = 0$) | 100% productores | La cantidad no puede ajustarse; los productores absorben todo |
| Demanda perfectamente elástica ($\varepsilon_D \to -\infty$) | 100% productores | Consumidores tienen sustitutos perfectos; no pagarán más |
| Demanda perfectamente inelástica ($\varepsilon_D = 0$) | 100% consumidores | Consumidores pagan cualquier precio — sin alternativas |

El principio general: **la carga tributaria recae más sobre el lado menos elástico del mercado**. Quien puede ajustar mejor su comportamiento escapa más de la incidencia.

#### Pérdida irrecuperable (Harberger triangle)

El impuesto reduce la cantidad transada de $Q^*$ a $Q^t < Q^*$. Las unidades $[Q^t, Q^*]$ que ya no se transan tenían $P^D > CMg$ — generaban excedente positivo. Este excedente se pierde irreparablemente: no es capturado por el gobierno ni por ningún agente.

La pérdida irrecuperable es la reducción del bienestar social total causada por la distorsión del comportamiento de compradores y vendedores. Los compradores tienden a consumir menos cuando el impuesto eleva el precio, y los vendedores producen menos cuando el impuesto reduce el precio que reciben. Como resultado, el tamaño total del mercado cae por debajo del óptimo. 

La **pérdida irrecuperable** es el área del triángulo de Harberger:

$$DWL = \frac{1}{2}(p_c - p_p)\Delta Q = \frac{1}{2} \cdot t \cdot \Delta Q$$

Aproximando con elasticidades (fórmula de Harberger):

$$DWL \approx -\frac{1}{2} \cdot \frac{\varepsilon_D \varepsilon_S}{\varepsilon_S - \varepsilon_D} \cdot \frac{t^2}{p^*} \cdot Q^*$$

Propiedades importantes del DWL:
- Proporcional al **cuadrado** del impuesto: duplicar el impuesto cuadruplica la pérdida irrecuperable. La introducción de un impuesto pequeño tiene una pérdida irrecuperable de "segundo orden" proporcional a $\Delta\tau^2$, no a $\Delta\tau$. 
- Creciente en las elasticidades: mercados más elásticos tienen mayor DWL por la misma tasa impositiva.
- Con oferta o demanda perfectamente inelástica: $DWL = 0$ — el impuesto no distorsiona la cantidad y es puro traslado de excedente.

#### El análisis completo de bienestar

| Concepto | Cambio |
|---|---|
| Excedente del consumidor | $\Delta EC = -(A + B)$ |
| Excedente del productor | $\Delta EP = -(C + D)$ |
| Ingreso fiscal | $G = A + C$ |
| Cambio en bienestar total | $\Delta ET = -(B + D)$ |

Donde $A$ y $C$ son los rectángulos de traslado (redistribución desde consumidores y productores al gobierno) y $B + D$ es el triángulo de Harberger (pérdida irrecuperable neta).

### 4.2 Subsidios

Un subsidio por unidad $s$ es matemáticamente un impuesto negativo: introduce una cuña $p_c - p_p = -s$, de modo que el consumidor paga menos y el productor recibe más de lo que pagaría en equilibrio competitivo.

El subsidio eleva la cantidad transada de $Q^*$ a $Q^s > Q^*$. Las unidades adicionales tienen $CMg > P^D$ — cuestan más de lo que valen para los consumidores. El gasto del gobierno en el subsidio supera la ganancia en excedentes:

$$DWL = \frac{1}{2} \cdot s \cdot \Delta Q > 0$$

El subsidio tiene el efecto opuesto al impuesto: reduce el precio que pagan los consumidores y sube el que reciben los productores, expandiendo la cantidad. Sin embargo, también genera pérdida irrecuperable porque induce producción donde el costo marginal supera el beneficio marginal. 

La incidencia del subsidio entre consumidores y productores sigue la misma lógica del impuesto: el lado menos elástico captura mayor fracción del subsidio.

### 4.3 Precio máximo (techo de precio)

Un **precio máximo** $\bar{p} < p^*$ fijado por debajo del precio de equilibrio:

- Reduce la cantidad ofrecida a $Q^S(\bar{p}) < Q^*$.
- Genera exceso de demanda: $Q^D(\bar{p}) > Q^S(\bar{p})$.
- La cantidad efectivamente transada es $Q' = \min\{Q^D(\bar{p}), Q^S(\bar{p})\} = Q^S(\bar{p})$.

El análisis de bienestar:
- El EC puede subir o bajar: los consumidores que compran ganan por el precio menor, pero algunos consumidores que habrían comprado a $p^*$ ya no pueden — hay racionamiento.
- El EP siempre cae: los productores reciben menos y venden menos.
- El DWL es el triángulo correspondiente a las unidades $[Q', Q^*]$.

Un precio máximo no es una transferencia pura de productores a consumidores — ambas partes pierden excedente por la reducción de la cantidad. El excedente total ha disminuido: no es una suma cero sino una pérdida neta. 

Adicionalmente, el precio máximo requiere algún mecanismo de racionamiento (colas, lotería, relaciones personales) que puede tener costos adicionales no capturados en el análisis estático.

### 4.4 Precio mínimo (piso de precio)

Un **precio mínimo** $\underline{p} > p^*$ fijado por encima del equilibrio:

- Genera exceso de oferta: $Q^S(\underline{p}) > Q^D(\underline{p})$.
- La cantidad transada es $Q' = Q^D(\underline{p}) < Q^*$.
- Requiere un mecanismo de asignación entre productores que compiten por los compradores disponibles.

El análisis es simétrico al precio máximo: el EP puede subir o bajar; el EC siempre cae; el DWL es positivo. El caso paradigmático es el **salario mínimo**, que es un precio mínimo en el mercado laboral.

### 4.5 Resumen comparativo de intervenciones

| Intervención | Cantidad | Precio consumidor | Precio productor | EC | EP | DWL |
|---|---|---|---|---|---|---|
| Impuesto | $\downarrow$ | $\uparrow$ | $\downarrow$ | $\downarrow$ | $\downarrow$ | $> 0$ |
| Subsidio | $\uparrow$ | $\downarrow$ | $\uparrow$ | $\uparrow$ | $\uparrow$ | $> 0$ |
| Precio máximo | $\downarrow$ | $\downarrow$ | $\downarrow$ | $?$ | $\downarrow$ | $> 0$ |
| Precio mínimo | $\downarrow$ | $\uparrow$ | $\uparrow$ | $\downarrow$ | $?$ | $> 0$ |

Todas las intervenciones generan DWL positivo en ausencia de externalidades — el equilibrio competitivo sin intervención es el único que maximiza el excedente total.

---

## 5. Elasticidades e incidencia: intuición adicional

Para un mercado más elástico, un cambio de precio causa una mayor reducción en la cantidad, por lo tanto una política en un mercado más elástico causará mayor pérdida irrecuperable. En el mercado americano, donde la demanda es más elástica, los consumidores soportan una menor carga del impuesto. 

La intuición es que la elasticidad mide la capacidad de ajuste: quien puede ajustar mejor (más elástico) transfiere más la carga al otro lado. El lado inelástico tiene pocas alternativas y absorbe más del impuesto — pero también genera menos distorsión en la cantidad.

Este trade-off entre equidad (cargar al lado inelástico, que suele ser el de menores ingresos para bienes necesarios) y eficiencia (menores elasticidades implican menor DWL) está en el corazón de la discusión de política tributaria óptima — que la regla de Ramsey formaliza.

---

## 6. El equilibrio parcial como herramienta de análisis

El **equilibrio parcial** analiza un mercado ignorando los efectos sobre los demás — toma como dados los precios de todos los otros bienes y factores. Es una simplificación legítima cuando:

- El mercado analizado es pequeño relativo a la economía.
- No hay fuertes complementariedades o sustituibilidades con otros mercados.
- El ingreso del consumidor no cambia significativamente.

Cuando estas condiciones no se cumplen — por ejemplo, en un impuesto al petróleo que afecta el transporte, la energía y los salarios simultáneamente — se requiere el análisis de **equilibrio general** para capturar todos los efectos.

La limitación principal del análisis de excedentes en equilibrio parcial es que el excedente del consumidor con la curva marshalliana no es una medida exacta de bienestar cuando el bien consume una fracción significativa del ingreso (efecto ingreso relevante). Las medidas exactas son la variación compensatoria y la variación equivalente, que usan la demanda hicksiana.

---

## Referencias

- Vial, B. & Zurita, F. *Microeconomía*. Ediciones UC.
- Nicholson, W. (2008). *Teoría Microeconómica*. Cengage. Caps. 12–14.
- Mas-Colell, A., Whinston, M. & Green, J. (1995). *Microeconomic Theory*. Oxford. Cap. 10.
- Harberger, A. (1964). *The Measurement of Waste*. AER Papers and Proceedings.
- Hines, J.R. (1999). *Three Sides of Harberger Triangles*. JEP.
- Chetty, R., Looney, A. & Kroft, K. (2009). *Salience and Taxation: Theory and Evidence*. AER.
- Varian, H. (1992). *Microeconomic Analysis*. Norton. Cap. 13.