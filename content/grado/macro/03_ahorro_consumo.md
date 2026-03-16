---
title: "Consumo y Ahorro"
date: 2026-03-15
draft: false
tags: ["macroeconomía", "consumo", "ahorro", "ingreso permanente", "ciclo de vida", "EAE2210"]
description: "Función keynesiana, modelo de dos períodos, restricciones de liquidez, ciclo de vida, ingreso permanente, camino aleatorio y ahorro precautorio."
---

**Curso:** Macroeconomía I (EAE2210) · **Profesor:** Emilio Depetris-Chauvin  
**Referencia principal:** De Gregorio (2007) caps. 8–9 · Romer (2012) cap. 7 · Deaton (1992)

---

## 1. La función de consumo keynesiana

El punto de partida histórico es la función de consumo de Keynes (1936):

$$C = c_0 + c_1 Y, \quad 0 < c_1 < 1$$

donde $c_0 > 0$ es el consumo autónomo y $c_1$ la propensidad marginal a consumir (PMC). Las propiedades que Keynes postulaba:

1. El consumo es función del ingreso **corriente**.
2. La PMC es positiva y menor a uno.
3. La PMC decrece con el ingreso (los ricos ahorran más).

Esta especificación tiene implicancias inmediatas para el multiplicador keynesiano, pero enfrenta problemas empíricos serios. Kuznets (1946) documentó que en series de tiempo largas la razón consumo/ingreso es aproximadamente constante, lo que es inconsistente con una PMC decreciente. Este hecho estilizado motivó las teorías modernas del consumo.

---

## 2. El modelo de dos períodos

### 2.1 Estructura y restricción presupuestaria

El modelo de dos períodos es la unidad básica de análisis intertemporal. El consumidor vive dos períodos, recibe ingresos $Y_1$ e $Y_2$, y elige $C_1$ y $C_2$ para maximizar utilidad. La restricción presupuestaria de cada período es:

$$C_1 + S = Y_1, \qquad C_2 = Y_2 + (1+r)S$$

donde $S$ es el ahorro en el período 1 y $r$ la tasa de interés real. Combinando, la **restricción presupuestaria intertemporal (RPI)**:

$$C_1 + \frac{C_2}{1+r} = Y_1 + \frac{Y_2}{1+r} \equiv W$$

El lado derecho $W$ es la riqueza de ciclo de vida en valor presente. El consumidor elige un plan $(C_1, C_2)$ sobre la recta presupuestaria con pendiente $-(1+r)$.

### 2.2 Optimización

Con función de utilidad separable en el tiempo:

$$U = u(C_1) + \frac{1}{1+\rho}u(C_2)$$

donde $\rho > 0$ es la tasa de preferencia por el presente (impaciencia), la condición de primer orden es la **ecuación de Euler**:

$$u'(C_1) = \frac{1+r}{1+\rho}u'(C_2)$$

La ecuación de Euler es la condición central de cualquier modelo de consumo intertemporal: iguala el costo marginal de reducir consumo hoy (utilidad marginal sacrificada) al beneficio de hacerlo (utilidad marginal futura ponderada por el retorno). Con utilidad CRRA $u(C) = \frac{C^{1-\sigma}-1}{1-\sigma}$:

$$\frac{C_2}{C_1} = \left(\frac{1+r}{1+\rho}\right)^{1/\sigma}$$

donde $1/\sigma$ es la **elasticidad de sustitución intertemporal (EIS)**. Si $r = \rho$, el consumidor iguala consumo en ambos períodos (suavización perfecta). Si $r > \rho$ (el mercado compensa bien la espera), el consumidor desplaza consumo hacia el futuro; cuánto depende de $\sigma$.

### 2.3 Efectos sobre el consumo

- **Aumento en $Y_1$ transitorio:** sube $W$ en la unidad. El consumidor lo distribuye entre ambos períodos → PMC < 1. No consume todo el ingreso transitorio hoy.
- **Aumento en $Y_1$ permanente** (sube $Y_1$ e $Y_2$ igualmente): la PMC se acerca a 1.
- **Aumento en $r$:** efecto sustitución (consumo futuro más barato → menos $C_1$) + efecto ingreso si es acreedor neto (positivo sobre $C_1$). El signo neto depende de la posición financiera neta del agente.

---

## 3. Restricciones de liquidez

El modelo canónico supone que el consumidor puede pedir prestado libremente a la tasa $r$. Si esto no es posible — ya sea por fricciones del mercado de crédito o asimetrías de información — el consumidor enfrenta una restricción de liquidez:

$$S \geq -\bar{B} \quad \text{(o en el caso extremo: } C_1 \leq Y_1\text{)}$$

Cuando la restricción de liquidez es activa, el consumidor querría consumir más hoy pero no puede. Consecuencias:

- La ecuación de Euler deja de describir el consumo: $u'(C_1) > \frac{1+r}{1+\rho}u'(C_2)$.
- La PMC respecto al ingreso corriente sube: transferencias de ingresos hoy tienen efecto mayor sobre el consumo que predicho por el modelo sin fricciones.
- Los estímulos fiscales temporales son más efectivos de lo que el modelo perfecto predice.

La evidencia de exceso de sensibilidad del consumo al ingreso corriente (Flavin, 1981) es consistente con restricciones de liquidez prevalentes, especialmente en hogares jóvenes y de bajos ingresos.

---

## 4. Teoría del ciclo de vida (Modigliani-Brumberg, 1954)

### 4.1 La intuición

El ingreso varía sistemáticamente a lo largo de la vida: bajo en juventud, alto en madurez, cero en retiro. Si los individuos son racionales y con visión de largo plazo, suavizan el consumo a lo largo del ciclo de vida, ahorrando durante los años de mayor ingreso para financiar el retiro. 

### 4.2 El modelo

Con $T$ períodos de vida, $R$ períodos de trabajo (ingreso $Y$) y $T - R$ períodos de retiro (ingreso 0), la RPI es:

$$\sum_{t=1}^{T} \frac{C_t}{(1+r)^{t-1}} = \sum_{t=1}^{R} \frac{Y_t}{(1+r)^{t-1}} + A_0$$

donde $A_0$ es la riqueza inicial. Si $r = \rho$ y el consumidor quiere suavizar perfectamente:

$$C^* = \frac{W}{T} = \frac{R \cdot \bar{Y} + A_0}{T}$$

La PMC respecto a la riqueza total es $1/T$ — pequeña para horizontes largos. La PMC respecto al ingreso corriente depende de cuántos períodos de trabajo quedan.

### 4.3 Implicancias

- **Perfil de ahorro en forma de joroba:** ahorro negativo en juventud, positivo en madurez, negativo en retiro.
- **Efecto riqueza:** cambios en precios de activos (acciones, vivienda) afectan el consumo a través de $A_0$.
- **Política fiscal:** el impacto del déficit fiscal depende de si el consumidor percibe el cambio como transitorio o permanente, y de su horizonte de vida.

La evidencia empírica muestra que el perfil de consumo en el ciclo de vida tiene forma de joroba: sube en la juventud, alcanza su peak en la madurez y declina antes del retiro. Esto no es completamente consistente con el modelo estándar de ciclo de vida bajo mercados completos, que predice un perfil monótono cuando la tasa de descuento iguala la tasa de interés.  La explicación más plausible involucra ahorro precautorio ante incertidumbre de ingreso que declina con la edad.

---

## 5. Teoría del ingreso permanente (Friedman, 1957)

### 5.1 Ingreso permanente y transitorio

Friedman distingue entre:

- **Ingreso permanente ($Y^P$):** valor presente del flujo esperado de ingresos futuros — lo que el agente puede gastar sosteniblemente.
- **Ingreso transitorio ($Y^T$):** componente temporal, no repetible.

La hipótesis es que el consumo depende solo del ingreso permanente:

$$C = \alpha Y^P, \quad 0 < \alpha < 1$$

La PMC respecto al ingreso transitorio es aproximadamente cero: un bono fiscal único, una herencia inesperada o una pérdida de empleo temporal tiene poco efecto sobre el consumo si el agente percibe el cambio como no permanente.

### 5.2 Reconciliación con Kuznets

La hipótesis resuelve la paradoja de Kuznets: en series largas, el ingreso observado $\approx$ ingreso permanente (las fluctuaciones transitorias promedian a cero), por lo que la razón $C/Y$ es constante. En corte transversal, los ricos tienen ingreso permanente alto pero también pueden tener ingresos transitorios altos que inflan $Y$ sin aumentar proporcionalmente $C$ — la razón $C/Y$ parece caer con $Y$ en el corte transversal, aunque no en el largo plazo.

---

## 6. El modelo del camino aleatorio: Hall (1978)

### 6.1 La implicancia central

Hall (1978) demostró que si los consumidores optimizan intertemporalmente bajo expectativas racionales, la utilidad marginal del consumo sigue un camino aleatorio. Bajo supuestos estándar, el consumo mismo sigue aproximadamente un camino aleatorio: ninguna variable disponible en $t$ — salvo el consumo corriente — debería predecir el consumo futuro. 

Formalmente, la ecuación de Euler con expectativas racionales implica:

$$C_{t+1} = C_t + \varepsilon_{t+1}$$

donde $\varepsilon_{t+1}$ es un ruido blanco no predecible en $t$. Esta es la implicancia testeable clave: **solo las sorpresas de ingreso mueven el consumo**.

### 6.2 Exceso de sensibilidad y exceso de suavidad

La evidencia empírica presenta dos anomalías respecto al modelo de Hall:

- **Exceso de sensibilidad** (Flavin, 1981): el consumo responde al ingreso corriente predecible, lo que no debería ocurrir bajo expectativas racionales. Flavin mostró que los cambios pasados en el ingreso actual son significativos al predecir el consumo futuro, contradiciendo la predicción del camino aleatorio.  Interpretación: restricciones de liquidez o miopía.

- **Exceso de suavidad** (Deaton, 1987): si los cambios en el ingreso son muy persistentes, las innovaciones al consumo deberían ser más volátiles que las del ingreso; en los datos el consumo es más suave de lo predicho.  Interpretación: los consumidores no responden completamente a noticias de ingreso — posiblemente porque no las perciben como permanentes.

Estas dos anomalías son difíciles de reconciliar simultáneamente con el modelo estándar, lo que ha motivado extensiones con restricciones de liquidez, formación de hábitos y agentes heterogéneos.

---

## 7. Consumo bajo incertidumbre: ahorro precautorio

### 7.1 Prudencia y la tercera derivada

El modelo de certeza equivalente supone que la incertidumbre no altera el nivel de consumo — solo su distribución. Esto requiere utilidad cuadrática. Con utilidad más general (en particular $u''' > 0$, es decir, **prudencia** en el sentido de Kimball, 1990), la incertidumbre sobre el ingreso futuro genera ahorro adicional: el **ahorro precautorio**.

Intuitivamente: si el ingreso futuro es incierto, el consumidor reduce el consumo presente para acumular un buffer contra estados adversos. La magnitud del ahorro precautorio depende del coeficiente de prudencia relativa $-Cu'''/u''$.

### 7.2 El modelo de buffer stock (Carroll, 1997)

Carroll (1997) formaliza el ahorro precautorio en un modelo de ciclo de vida con incertidumbre de ingreso no asegurable. Los consumidores mantienen un stock de riqueza de amortiguación (*buffer stock*) que les permite suavizar consumo ante shocks negativos de ingreso. Los resultados son consistentes con modelos de buffer stock donde los motivos precautorios reducen significativamente la disposición de consumidores prudentes a consumir de ingreso futuro incierto. 

En equilibrio de buffer stock, el consumo crece a una tasa determinada por la impaciencia, la tasa de interés y la incertidumbre — no por el ingreso permanente solamente. Esto explica la correlación positiva entre crecimiento del consumo e ingreso observada en los datos sin necesitar restricciones de liquidez.

---

## 8. Equilibrio general en una economía de dotación

Hasta aquí el análisis es de equilibrio parcial: se toma $r$ como dado. En equilibrio general, la tasa de interés se determina endógenamente para vaciar el mercado de bienes.

**Economía cerrada:** el ahorro agregado debe igualar la inversión. Si no hay inversión (economía de dotación pura), el mercado de bienes requiere $C = Y$ en cada período. La tasa de interés de equilibrio es aquella que hace consistente la elección óptima de consumo con esta restricción de vaciado.

**Economía abierta:** la economía puede tener superávit o déficit de cuenta corriente. La cuenta corriente es el ahorro nacional neto: $CA = Y - C - G - I$. Un déficit de cuenta corriente significa que el país consume más de lo que produce, financiado por entradas de capital externo. La dinámica de la cuenta corriente refleja decisiones de suavización intertemporal: un shock transitorio negativo genera déficit (el país pide prestado al exterior); un shock permanente no genera déficit (el ingreso permanente cae con el ingreso).

---

## 9. Síntesis: comparación de modelos

| Modelo | Variable clave | PMC ingreso transitorio | PMC ingreso permanente | Anomalías |
|---|---|---|---|---|
| Keynesiano | Ingreso corriente | $c_1 < 1$ | $c_1$ | No distingue transitorios/permanentes |
| Ciclo de vida | Riqueza de ciclo de vida | $\approx 1/T$ | $\approx 1$ | Perfil en joroba, legados |
| Ingreso permanente | $Y^P$ | $\approx 0$ | $\alpha$ | Exceso de sensibilidad |
| Camino aleatorio | Sorpresas de ingreso | $\approx 0$ | $\approx 1$ | Exceso de sensibilidad y suavidad |
| Buffer stock | $Y^P$ + incertidumbre | Baja | Moderada | Correlación consumo-ingreso |

---

## Referencias

- Keynes, J.M. (1936). *The General Theory of Employment, Interest and Money*. Cap. 8–10.
- Modigliani, F. & Brumberg, R. (1954). *Utility Analysis and the Consumption Function*. En Kurihara (ed.).
- Friedman, M. (1957). *A Theory of the Consumption Function*. Princeton University Press.
- Hall, R.E. (1978). *Stochastic Implications of the Life Cycle–Permanent Income Hypothesis*. JPE.
- Flavin, M. (1981). *The Adjustment of Consumption to Changing Expectations About Future Income*. JPE.
- Carroll, C.D. (1997). *Buffer-Stock Saving and the Life Cycle/Permanent Income Hypothesis*. QJE.
- Deaton, A. (1992). *Understanding Consumption*. Oxford University Press.
- De Gregorio, J. (2007). *Macroeconomía: Teoría y Políticas*. Caps. 8–9.