---
title: "Tipo de Cambio Real"
date: 2026-03-15
draft: false
tags: ["macroeconomía internacional", "tipo de cambio real", "Balassa-Samuelson", "transables", "no transables", "EAE3210"]
description: "Definición y determinantes del tipo de cambio real en el corto y largo plazo. Modelo de transables y no transables. Efecto Balassa-Samuelson. Evidencia empírica y el PPP puzzle."
---

**Curso:** Macroeconomía Internacional (EAE3210) — Posgrado  
**Referencia principal:** Obstfeld & Rogoff (1996) caps. 4 · Krugman, Melitz & Obstfeld (2015) · De Gregorio, Giovannini & Wolf (1994)

---

## 1. Definición y conceptos

### 1.1 El tipo de cambio real bilateral

El **tipo de cambio real (TCR)** mide el precio relativo de la canasta de bienes de un país respecto al de otro, expresado en la misma moneda:

$$q = \frac{EP^*}{P}$$

donde $E$ es el tipo de cambio nominal (unidades de moneda doméstica por extranjera), $P^*$ el nivel de precios externo y $P$ el doméstico. Un aumento en $q$ es una **depreciación real** — los bienes domésticos se abaratan relativos a los externos — y mejora la competitividad de las exportaciones.

En logaritmos:

$$\ln q = e + p^* - p$$

donde letras minúsculas denotan logaritmos. La variación del TCR es:

$$\hat{q} = \hat{E} + \pi^* - \pi$$

El TCR se deprecia cuando la inflación doméstica supera la suma de la depreciación nominal más la inflación externa; se aprecia en el caso contrario.

### 1.2 El tipo de cambio real efectivo (TCRE)

En la práctica, cada país comercia con múltiples socios. El **TCRE** es el promedio ponderado de los TCR bilaterales, con pesos proporcionales a la participación de cada socio en el comercio:

$$\ln q^{eff} = \sum_j w_j (e_j + p_j^* - p)$$

donde $w_j$ es el peso del socio $j$. El TCRE es el indicador estándar de competitividad externa utilizado por bancos centrales y organismos internacionales.

### 1.3 Relación con la PPP

La PPP absoluta establece que $q = 1$ — todos los bienes tienen el mismo precio en términos de una moneda común. La PPP relativa es más débil: $\hat{q} = 0$, es decir, el TCR no tiene tendencia. Si la PPP se cumple, el TCR es constante en el largo plazo y la política de tipo de cambio nominal no tiene efectos reales persistentes.

La pregunta central de este capítulo es: **¿qué determina las desviaciones del TCR respecto a la PPP, y por qué son persistentes?**

---

## 2. El modelo de bienes transables y no transables

### 2.1 La distinción fundamental

La literatura descompone los bienes en dos sectores:

- **Transables (T):** bienes que se comercian internacionalmente. Su precio doméstico está disciplinado por la competencia externa: la **ley de un solo precio** se aplica aproximadamente, $P_T = EP_T^*$.
- **No transables (N):** bienes y servicios que no se comercian internacionalmente — construcción, servicios personales, educación, salud — ya sea por costos de transporte prohibitivos o por naturaleza intrínsecamente local. Su precio se determina por condiciones domésticas de oferta y demanda.

### 2.2 El nivel de precios agregado

El nivel de precios es un promedio ponderado de los precios de transables y no transables:

$$p = \alpha p_T + (1-\alpha) p_N$$

donde $\alpha$ es la participación del gasto en transables. Análogamente para el exterior:

$$p^* = \alpha p_T^* + (1-\alpha) p_N^*$$

Dado que $p_T = e + p_T^*$ (ley de un solo precio), el TCR se reduce a:

$$q = e + p^* - p = (1-\alpha)[(p_N^* - p_T^*) - (p_N - p_T)]$$

El **TCR depende enteramente de los precios relativos de no transables en cada país**. La PPP falla en la medida en que los precios relativos $p_N - p_T$ difieren entre países. Esta es la formalización precisa de por qué la PPP no se cumple: países con precios relativos de no transables más altos tienen niveles de precios más altos en términos de una moneda común.

### 2.3 Determinantes del precio relativo de no transables

¿Qué determina $p_N - p_T$? En equilibrio, el precio relativo de no transables iguala la relación de costos marginales de producción. Con un solo factor (trabajo) y competencia perfecta:

$$p_N - p_T = w - a_N - (w - a_T) = a_T - a_N$$

donde $a_i = \ln(PMgL_i)$ es el log de la productividad laboral en cada sector. **El precio relativo de no transables es creciente en la productividad del sector transable y decreciente en la del sector no transable**.

La intuición es directa: si la productividad en transables sube, los salarios nominales suben (por arbitraje laboral entre sectores); pero el sector no transable no puede absorber los salarios más altos con mayor productividad, por lo que debe subir sus precios para mantener rentabilidad.

---

## 3. El efecto Balassa-Samuelson

### 3.1 El mecanismo

El modelo de Balassa-Samuelson formaliza fuerzas directas: mayor crecimiento de la productividad en el sector transable tiende a elevar los costos de insumos locales y por tanto los precios de los bienes no transables. Dado que los precios de los transables tienden a igualarse entre países, esto eleva el nivel de precios doméstico, lo que equivale a una apreciación del tipo de cambio real. 

Formalmente, sustituyendo en la expresión del TCR:

$$q = (1-\alpha)[(a_{T}^* - a_{N}^*) - (a_T - a_N)]$$

El TCR se deprecia cuando el diferencial de productividad transable/no-transable es mayor en el exterior que en el país doméstico. Los países con **alta productividad relativa en transables** tienen TCR apreciados — sus niveles de precios son altos en términos de una moneda común.

El efecto Balassa-Samuelson explica la tendencia sistemática de los países ricos a tener niveles de precios más altos que los países pobres cuando se expresan en la misma moneda. Esta regularidad empírica se conoce como el "Penn effect", documentado por Heston y Summers. 

### 3.2 Implicancias para el crecimiento y la convergencia

Para economías en desarrollo con convergencia de productividad hacia países avanzados, el modelo predice:

1. **Apreciación secular del TCR:** a medida que la productividad en transables crece más rápido que en el exterior (convergencia), el salario real sube, los precios de no transables suben y el TCR se aprecia.
2. **Inflación diferencial:** incluso con tipo de cambio fijo, los países convergentes tendrán inflación mayor que el ancla. La diferencia es exactamente el Balassa-Samuelson: $\pi - \pi^* = (1-\alpha)\Delta(a_T - a_N)$.
3. **Implicancias para la eurozona:** los países de Europa del Este al integrarse a la UE tenían productividades en transables mucho menores. La convergencia implicaba apreciación real y, bajo tipo de cambio fijo al euro, inflación diferencial.

La evidencia para seis países de Europa Central muestra presencia del efecto Balassa-Samuelson en todos los países. Sin embargo, el tamaño del efecto es relativamente pequeño: los diferenciales de productividad explican en promedio solo entre 0.2 y 2.0 puntos porcentuales de los diferenciales de inflación anuales, considerablemente menos que los diferenciales observados. El efecto Balassa-Samuelson es real pero no suficiente para explicar la totalidad de la apreciación real observada. 

### 3.3 El efecto en el corto plazo

En el corto plazo, con rigideces de precios y salarios, la transmisión del modelo no opera instantáneamente. Un shock de productividad en transables no eleva los precios de no transables de inmediato — requiere ajuste salarial, que puede ser lento. Las estimaciones de la vida media de las desviaciones del TCR son consistentes con esto.

---

## 4. Determinantes del TCR en el corto plazo

El modelo de Balassa-Samuelson es una teoría de largo plazo. En el corto plazo, otros factores dominan:

### 4.1 Shocks de demanda y política monetaria

Con precios rígidos, un shock de demanda positivo (expansión fiscal o monetaria) eleva el gasto doméstico, incluyendo sobre no transables. El precio relativo de no transables sube → TCR se aprecia. Este es el canal de gasto que conecta la política macroeconómica con el TCR:

- Expansión fiscal → apreciación real (mayor demanda de no transables domésticos).
- Expansión monetaria → depreciación nominal + inflación → TCR ambiguo (overshooting sugiere depreciación real transitoria).

### 4.2 Términos de intercambio

Los términos de intercambio también influyen en el tipo de cambio real bajo ciertas condiciones, además del diferencial de productividad. El diferencial de productividad laboral ejerce un efecto significativo sobre el tipo de cambio real vía su influencia en el precio relativo de los bienes no transables. 

Un alza en el precio de las exportaciones (mejora de los términos de intercambio) genera un efecto riqueza que eleva la demanda de no transables → apreciación real. Para economías exportadoras de materias primas (Chile, Australia, Canadá), la correlación entre el precio del commodity exportado y el TCR es una regularidad empírica robusta — la "moneda commodity".

Para Chile, el TCR y el precio del cobre tienen una correlación negativa marcada: cuando el cobre sube, el peso se aprecia en términos reales. Este mecanismo opera principalmente vía el canal de ingresos (mayor ingreso nacional eleva la demanda de no transables) y parcialmente vía el tipo de cambio nominal.

### 4.3 Flujos de capital y posición externa neta

Entradas de capital generan apreciación real a través de dos canales:
- **Canal nominal:** el banco central puede dejarse apreciar la moneda nominal.
- **Canal de demanda:** las entradas de capital financian mayor gasto doméstico → mayor demanda de no transables → precios relativos suben.

La posición de inversión internacional neta (PII) es un determinante de largo plazo del TCR de equilibrio: países con PII positiva (acreedores netos) pueden sostener TCR más apreciados porque el ingreso de la inversión externa financia importaciones sin necesidad de superávit comercial.

### 4.4 Rigideces y política cambiaria

Las estimaciones de la vida media de las desviaciones del TCR respecto a su media —típicamente entre 3 y 5 años— sugieren el "PPP puzzle" de Rogoff (1996): son demasiado largas para ser producidas por shocks monetarios bajo rigideces nominales plausibles, pero demasiado cortas para reflejar solo shocks reales de alta persistencia. 

Este puzzle sugiere que ningún modelo individual explica completamente la dinámica del TCR: los shocks monetarios explican la volatilidad de corto plazo pero no la persistencia; los shocks reales (Balassa-Samuelson, términos de intercambio) explican las tendencias de largo plazo pero no la volatilidad.

---

## 5. El PPP puzzle y la evidencia empírica

### 5.1 Estacionariedad del TCR

La pregunta econométrica fundamental es si el TCR es estacionario — es decir, si revierte a un valor de largo plazo. La PPP implica reversión a la media; la PPP no aplica implica raíz unitaria.

Los mercados de transables perfectamente competitivos y sin fricciones justifican pensar en la PPP como el principal determinante del tipo de cambio en el largo plazo. Pero las diferencias persistentes en los sectores transable/no transable de las economías tienden a afectar los niveles de precios de formas que alteran el equilibrio PPP — el fundamento de la hipótesis Harrod-Balassa-Samuelson. 

La evidencia con datos de panel (más poder estadístico que series individuales) sí respalda la reversión a la media del TCR, pero con vida media de 3-5 años — suficientemente larga como para que las desviaciones sean económicamente significativas por períodos prolongados.

### 5.2 El Penn effect

Hay una fuerte relación positiva entre niveles de precios y PIB per cápita, a veces conocida como el "Penn effect". A pesar de la simplicidad y atractivo de la teoría, se reconoce ampliamente que el modelo de Balassa-Samuelson no se desempeña bien en explicar los movimientos de corto y mediano plazo de los tipos de cambio reales. 

El Penn effect en corte transversal es robusto: países más ricos tienen niveles de precios más altos sistemáticamente. Sin embargo, la contribución cuantitativa de Balassa-Samuelson para explicar este patrón es disputada. Estimaciones de la elasticidad del TCR respecto al diferencial de productividad varían entre 0.1 y 0.4 según el estudio, menor que el valor teórico de 1 predicho por el modelo simple.

### 5.3 El desafío de la evidencia reciente

Para el período post-1985, se encuentra una relación negativa robusta entre la productividad en el sector transable y el tipo de cambio real en una muestra de países OCDE, incluso controlando por los términos de intercambio. Esto es opuesto a la predicción de Balassa-Samuelson y sugiere que el marco teórico estándar necesita modificaciones. 

Una explicación es el **home bias en consumo**: si la mayor productividad en transables reduce el precio doméstico de esos bienes relativamente más que el externo (por mayor participación en el consumo doméstico), la apreciación real puede no materializarse o incluso revertirse.

Usando Estados Unidos como país de referencia, los diferenciales de productividad laboral entre el sector transable y no transable son determinantes significativos del tipo de cambio real en el largo plazo para economías en desarrollo. Los términos de intercambio también influyen significativamente. 

---

## 6. Misalignment y política cambiaria

### 6.1 El concepto de TCR de equilibrio

El TCR de equilibrio es el nivel consistente con equilibrio interno (producto en su potencial) y externo (cuenta corriente sostenible). La brecha entre el TCR observado y el de equilibrio es el **misalignment**.

Los métodos para estimar el TCR de equilibrio incluyen:
- **BEER (Behavioural Equilibrium Exchange Rate):** regresión del TCR sobre sus fundamentos (productividad relativa, términos de intercambio, activos externos netos, diferencial de gasto público).
- **FEER (Fundamental Equilibrium Exchange Rate):** el TCR consistente con equilibrios interno y externo simultáneos — enfoque del FMI.
- **DEER (Desired Equilibrium Exchange Rate):** variante que incorpora objetivos normativos de cuenta corriente.

### 6.2 Implicancias para política

La discusión sobre misalignment es central en dos debates contemporáneos:

**Manipulación cambiaria:** si un país mantiene deliberadamente su moneda subvaluada (TCR depreciado) para ganar competitividad, genera un subsidio implícito a sus exportaciones y un impuesto a sus importaciones. China fue acusada recurrentemente de esto en los 2000. El debate es si la intervención cambiaria constituye manipulación según los criterios del FMI (artículo IV) o simplemente gestión legítima de la volatilidad.

**Competitividad y ajuste en la eurozona:** los países periféricos de la eurozona (Grecia, España, Portugal) acumularon TCR apreciados en la década de los 2000 por inflaciones diferenciales sobre Alemania. Sin tipo de cambio nominal, el ajuste requería deflación interna — reducción de precios y salarios nominales — proceso lento y costoso que contribuyó a la severidad de la crisis europea post-2010.

---

## 7. Síntesis: determinantes del TCR según horizonte

| Horizonte | Determinantes principales | Canal | Modelo de referencia |
|---|---|---|---|
| **Muy corto** | Expectativas, flujos de capital especulativos | Tipo de cambio nominal | UIP, overshooting |
| **Corto** | Política monetaria, rigideces de precios | Nominal + precios rígidos | Mundell-Fleming, Dornbusch |
| **Mediano** | Términos de intercambio, flujos de capital, política fiscal | Demanda de no transables | IS-LM abierto, BEER |
| **Largo** | Productividad relativa transables/no transables, PII | Costos relativos de producción | Balassa-Samuelson |

La evidencia empírica sugiere que ningún modelo es suficiente por sí solo: el TCR es determinado por una jerarquía de fuerzas donde la dominancia relativa de cada factor depende del horizonte temporal. La volatilidad de corto plazo es primariamente financiera; la tendencia de largo plazo es primariamente real.

---

## Referencias

- Balassa, B. (1964). *The Purchasing Power Parity Doctrine: A Reappraisal*. JPE.
- Samuelson, P. (1964). *Theoretical Notes on Trade Problems*. REStat.
- De Gregorio, J., Giovannini, A. & Wolf, H. (1994). *International Evidence on Tradables and Nontradables Inflation*. European Economic Review.
- Rogoff, K. (1996). *The Purchasing Power Parity Puzzle*. JEL.
- Lane, P. & Milesi-Ferretti, G.M. (2004). *The Transfer Problem Revisited: Net Foreign Assets and Real Exchange Rates*. REStat.
- Berka, M., Devereux, M. & Engel, C. (2018). *Real Exchange Rates and Sectoral Productivity in the Eurozone*. AER.
- Obstfeld, M. & Rogoff, K. (1996). *Foundations of International Macroeconomics*. MIT Press. Cap. 4.
- Krugman, P., Melitz, M. & Obstfeld, M. (2015). *International Finance: Theory and Policy*. 10ma ed. Caps. 16–17.
- Schmitt-Grohé, S., Uribe, M. & Woodford, M. (2022). *International Macroeconomics*. Princeton University Press.