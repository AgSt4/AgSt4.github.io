---
title: "Crecimiento Económico"
date: 2026-03-16
draft: false
tags: ["macroeconomía", "crecimiento", "Solow", "crecimiento endógeno", "EAE2210"]
description: "Modelo neoclásico, regla de oro, crecimiento endógeno y contabilidad del crecimiento. Apunte basado en EAE2210 — Macroeconomía I."
---

**Curso:** Macroeconomía I (EAE2210) · **Profesor:** Emilio Depetris-Chauvin  
**Referencia principal:** De Gregorio (2007) caps. 1–4 · Barro & Sala-i-Martin (2004)

---

## 0. ¿Qué es el crecimiento económico?

El **crecimiento económico** es el aumento sostenido del producto real (PIB) de una economía a lo largo del tiempo. En el contexto de este curso (**Macroeconomía I — Economía Real Cerrada**), nos enfocamos en el estudio del largo plazo: qué determina que la capacidad productiva de un país se expanda y permita mejorar los niveles de vida de la población.

A diferencia del análisis de corto plazo (fluctuaciones o ciclos económicos), donde el foco está en la demanda agregada y el uso de la capacidad instalada, la teoría del crecimiento estudia la **oferta agregada**: cómo la acumulación de factores (capital y trabajo) y las mejoras en la eficiencia (tecnología) desplazan la frontera de producción.

Este bloque es fundamental porque pequeñas diferencias en las tasas de crecimiento anual, sostenidas por décadas, generan disparidades masivas en el bienestar material de los países (el efecto del interés compuesto).

---

## 1. Regularidades empíricas del crecimiento

Antes de modelar, conviene anclar los modelos en los hechos estilizados que cualquier teoría del crecimiento debe poder explicar. Kaldor (1961) documentó las siguientes regularidades para economías desarrolladas:

1. El producto per cápita crece a una tasa aproximadamente constante en el largo plazo.
2. El stock de capital per cápita crece a una tasa aproximadamente constante.
3. La tasa de retorno al capital es relativamente estable en el tiempo.
4. La razón capital/producto es relativamente estable.
5. Las participaciones del trabajo y capital en el ingreso son aproximadamente constantes.
6. Existen grandes diferencias en las tasas de crecimiento entre países.

El sexto hecho es el más relevante para la pregunta de fondo: **¿por qué algunos países son ricos y otros pobres, y por qué la brecha persiste?** Los modelos de crecimiento buscan responder esto.

---

## 2. El modelo neoclásico de Solow-Swan

### 2.1 Supuestos y estructura

El modelo de Solow (1956) es el punto de partida canónico. Supuestos centrales:

- Economía cerrada, un bien, competencia perfecta.
- Función de producción $Y = F(K, AL)$ con retornos constantes a escala (RCS): $F(\lambda K, \lambda AL) = \lambda Y$.
- $A$ es tecnología que aumenta la eficiencia del trabajo (*labor-augmenting* o progreso técnico de Harrod-neutral), crece a tasa exógena $g$.
- La población (y trabajo) crece a tasa exógena $n$.
- Los hogares ahorran una fracción constante $s$ del ingreso.
- El capital se deprecia a tasa $\delta$.

La función de producción más usada es Cobb-Douglas:

$$Y = K^\alpha (AL)^{1-\alpha}, \quad 0 < \alpha < 1$$

### 2.2 Dinámica en términos per cápita efectivos

Definiendo $k \equiv K/AL$ (capital por trabajador efectivo) e $y \equiv Y/AL$, la ecuación fundamental del modelo es:

$$\dot{k} = sf(k) - (n + g + \delta)k$$

donde $f(k) = k^\alpha$ con Cobb-Douglas. La interpretación es directa: el capital por trabajador efectivo crece cuando el ahorro/inversión $sf(k)$ supera el *capital de reposición* $(n+g+\delta)k$, que debe cubrir depreciación, crecimiento poblacional y progreso técnico.

### 2.3 Estado estacionario

El estado estacionario $k^*$ satisface $\dot{k} = 0$:

$$sf(k^*) = (n + g + \delta)k^*$$

En estado estacionario:
- $k$, $y$ son constantes → el capital y producto **por trabajador efectivo** no crecen.
- El capital y producto **por trabajador** crecen a tasa $g$.
- El capital y producto **agregados** crecen a tasa $n + g$.

La tasa de crecimiento del producto per cápita en el largo plazo es enteramente determinada por $g$, que es **exógena**. Esta es la limitación central del modelo: no explica de dónde viene el progreso tecnológico.

### 2.4 Dinámica de transición y convergencia

Fuera del estado estacionario, la economía converge monótonamente a $k^*$. Si $k < k^*$, la productividad marginal del capital es alta → alta inversión → convergencia hacia arriba. Esto implica **convergencia condicional**: países con los mismos parámetros $(s, n, g, \delta)$ convergen al mismo estado estacionario, y los más pobres crecen más rápido en la transición.

La evidencia empírica respalda convergencia condicional pero no absoluta. Países con estructuras institucionales y tasas de ahorro distintas tienen distintos $k^*$ — la condicionalidad importa.

### 2.5 Efectos de política

Un aumento permanente en la tasa de ahorro $s$:
- **Sube el nivel** del estado estacionario $k^*$ e $y^*$.
- **No altera la tasa de crecimiento** de largo plazo (que sigue siendo $g$).
- Genera crecimiento transitorio durante la convergencia al nuevo $k^*$.

Esto tiene implicancias de política importantes: las políticas que aumentan el ahorro o la inversión tienen efectos de nivel pero no de tasa en el largo plazo. Solo el progreso tecnológico mueve la tasa de crecimiento sostenido.

---

## 3. La regla de oro de la acumulación

### 3.1 Consumo en estado estacionario

El consumo por trabajador efectivo en estado estacionario es:

$$c^* = f(k^*) - (n + g + \delta)k^*$$

Este consumo depende de $k^*$, que a su vez depende de $s$. ¿Existe una tasa de ahorro óptima que maximiza $c^*$?

### 3.2 La condición de la regla de oro

Maximizando $c^*$ respecto a $k^*$, la condición de primer orden da la **regla de oro de Phelps (1961)**:

$$f'(k^*_{RO}) = n + g + \delta$$

Es decir, en el óptimo la productividad marginal del capital debe igualar la tasa de reposición. Con Cobb-Douglas: $\alpha k^{-(1-\alpha)} = n + g + \delta$, lo que determina $k^*_{RO}$.

La tasa de ahorro de la regla de oro es $s_{RO} = \alpha$ (con Cobb-Douglas), que coincide con la participación del capital en el ingreso. En la práctica, muchas economías tienen tasas de ahorro por debajo de $s_{RO}$ (*subacumulación de capital*), aunque la sobreacumulación dinámica es posible en teoría.

### 3.3 Eficiencia dinámica

Una economía con $k^* > k^*_{RO}$ sobreacumula capital: reduce consumo presente y futuro innecesariamente. Es **dinámicamente ineficiente**. Reducir la tasa de ahorro aumentaría el bienestar intergeneracional. La condición de Abel et al. (1989) para eficiencia dinámica es que la rentabilidad del capital supere el crecimiento del producto, lo que se verifica empíricamente en la mayoría de las economías desarrolladas.

---

## 4. Crecimiento endógeno

### 4.1 La insatisfacción con Solow

El modelo neoclásico tiene dos problemas estructurales:

1. La tasa de crecimiento de largo plazo depende de $g$, que es exógena y no explicada.
2. Predice convergencia absoluta que los datos no respaldan uniformemente.

La literatura de crecimiento endógeno, iniciada por Romer (1986) y Lucas (1988), busca que $g$ emerja endógenamente de las decisiones de los agentes.

### 4.2 Modelo AK: retornos constantes al capital agregado

El modelo AK es la versión más simple. Supone función de producción:

$$Y = AK$$

donde $A$ es una constante que captura la productividad total. La clave es que **no hay rendimientos decrecientes al capital a nivel agregado**. La justificación es que las externalidades del capital (aprendizaje, spillovers de conocimiento) compensan los rendimientos privados decrecientes.

La tasa de crecimiento del consumo (con optimización intertemporal) es:

$$\frac{\dot{C}}{C} = \frac{1}{\sigma}(A - \rho - \delta)$$

donde $\sigma$ es la elasticidad de sustitución intertemporal y $\rho$ la tasa de descuento. Crucialmente, la tasa de crecimiento depende de $A$, $\rho$ y $\sigma$ — todos parámetros potencialmente influenciables por política. Un subsidio a la inversión que eleve $A$ aumenta permanentemente la tasa de crecimiento, a diferencia del modelo de Solow donde solo afecta el nivel.

### 4.3 Modelos con externalidades basados en el conocimiento

Romer (1986) formaliza la idea de que el capital conocimiento genera externalidades positivas. Cada firma individual enfrenta rendimientos decrecientes, pero a nivel agregado el conocimiento acumulado por todas las firmas eleva la productividad de cada una.

La función de producción de la firma $i$ es:

$$Y_i = AK_i^\alpha L_i^{1-\alpha} \cdot \bar{K}^\phi$$

donde $\bar{K}$ es el stock agregado de capital (que la firma individual toma como dado). Si $\alpha + \phi = 1$, la economía agrega rendimientos constantes al capital y la tasa de crecimiento es endógena. El equilibrio descentralizado es subóptimo porque las firmas no internalizan su contribución a $\bar{K}$: hay un argumento para subsidiar la inversión o I+D.

### 4.4 Modelos de progreso técnico (Romer 1990)

El modelo más completo de Romer (1990) distingue tres sectores: producción de bienes finales, producción de insumos intermedios (variedades), e I+D. El crecimiento proviene de la expansión del número de variedades de insumos, financiada por empresas que buscan rentas monopólicas. La **no rivalidad** de las ideas (una idea puede usarse simultáneamente por múltiples agentes) es la propiedad fundamental que genera rendimientos crecientes a nivel agregado manteniendo competencia a nivel de firma.

Implicación de política: los derechos de propiedad intelectual son un instrumento para incentivar la innovación, pero al precio de crear distorsiones monopólicas. El diseño óptimo de la política de innovación requiere balancear estos efectos.

---

## 5. Contabilidad del crecimiento

### 5.1 Descomposición de Solow

Dado $Y = AK^\alpha L^{1-\alpha}$, tomando logaritmos y diferenciando:

$$\frac{\dot{Y}}{Y} = \frac{\dot{A}}{A} + \alpha\frac{\dot{K}}{K} + (1-\alpha)\frac{\dot{L}}{L}$$

Reordenando, el **residuo de Solow** (o TFP, Total Factor Productivity) es:

$$\frac{\dot{A}}{A} = \frac{\dot{Y}}{Y} - \alpha\frac{\dot{K}}{K} - (1-\alpha)\frac{\dot{L}}{L}$$

El residuo captura todo el crecimiento no explicado por la acumulación de factores. En EE.UU., históricamente alrededor de la mitad del crecimiento del producto per cápita se atribuye a TFP.

### 5.2 El problema de la "medida de nuestra ignorancia"

Solow mismo llamó al residuo "una medida de nuestra ignorancia". TFP captura no solo progreso tecnológico sino también mejoras en la eficiencia de asignación, economías de escala, capital humano no medido, y errores de medición. Mankiw, Romer y Weil (1992) mostraron que incorporar capital humano al modelo de Solow reduce sustancialmente el residuo y mejora la capacidad de explicar diferencias de ingreso entre países.

---

## 6. Convergencia: la evidencia

La hipótesis de convergencia tiene dos versiones:

- **Convergencia absoluta (β-convergencia):** países más pobres crecen incondicionalmente más rápido. No respaldada para la muestra global.
- **Convergencia condicional:** países más pobres crecen más rápido *dado* un mismo estado estacionario. Respaldada empíricamente (Barro & Sala-i-Martin 1992).

La **σ-convergencia** (reducción de la dispersión del ingreso entre países) es un concepto complementario. Puede haber β-convergencia sin σ-convergencia si hay shocks que aumentan la dispersión.

La evidencia reciente es más matizada: la convergencia de los "tigres asiáticos" coexiste con divergencia en partes de África Subsahariana. Esto sugiere que los parámetros estructurales del estado estacionario — instituciones, educación, apertura — importan más que la posición inicial de capital.

---

## Referencias

- Solow, R. (1956). *A Contribution to the Theory of Economic Growth*. QJE.
- Romer, P. (1986). *Increasing Returns and Long-Run Growth*. JPE.
- Romer, P. (1990). *Endogenous Technological Change*. JPE.
- Lucas, R. (1988). *On the Mechanics of Economic Development*. JME.
- Mankiw, N. G., Romer, D. & Weil, D. (1992). *A Contribution to the Empirics of Economic Growth*. QJE.
- Barro, R. & Sala-i-Martin, X. (2004). *Economic Growth*. MIT Press. Caps. 1–4.
- De Gregorio, J. (2007). *Macroeconomía: Teoría y Políticas*. Caps. 5–7.