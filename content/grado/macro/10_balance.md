---
title: "Cuentas Externas y Balanza de Pagos"
date: 2026-03-15
draft: false
tags: ["macroeconomía internacional", "balanza de pagos", "cuenta corriente", "enfoque intertemporal", "Obstfeld-Rogoff", "EAE3210"]
description: "Cuentas nacionales en economía abierta, enfoque intertemporal de la cuenta corriente, economías de dotación y con producción, ajuste en economías grandes y pequeñas, déficit gemelo."
---

**Curso:** Macroeconomía Internacional (EAE3210) — Posgrado  
**Referencia principal:** Obstfeld & Rogoff (1996) caps. 1–2 · Schmitt-Grohé, Uribe & Woodford (2022) · Krugman, Melitz & Obstfeld (2015)

---

## 1. Cuentas nacionales en economía abierta

### 1.1 Las identidades fundamentales

La contabilidad nacional en economía abierta organiza el análisis en torno a tres conceptos que conviene distinguir con precisión:

**Producto Interno Bruto (PIB):** valor de la producción generada dentro del territorio, independiente de la nacionalidad de los factores:

$$Y = C + I + G + NX$$

**Producto Nacional Bruto (PNB):** valor del ingreso recibido por residentes nacionales, incluyendo renta neta de factores desde el exterior ($RF$):

$$PNB = Y + RF = C + I + G + CC$$

**Ingreso Nacional Disponible (YND):** PNB más transferencias netas recibidas ($TR$):

$$YND = PNB + TR$$

La cuenta corriente es la diferencia entre el ingreso nacional disponible y la absorción doméstica:

$$CC = YND - (C + I + G) = S_N - I$$

donde $S_N = YND - C - G$ es el ahorro nacional. Esta identidad — **la CC es el exceso de ahorro sobre inversión** — es el punto de partida del enfoque intertemporal.

### 1.2 La posición de inversión internacional y la dinámica de activos externos

Sea $B_t$ la posición de activos externos netos al inicio del período $t$ (positivo si el país es acreedor neto). El ingreso de la inversión es $r_t B_t$, de modo que:

$$CC_t = NX_t + r_t B_t$$

La acumulación de activos externos sigue:

$$B_{t+1} = B_t + CC_t = (1 + r_t)B_t + NX_t$$

La **restricción presupuestaria intertemporal del país** se obtiene iterando esta ecuación e imponiendo la condición de no-Ponzi ($\lim_{T\to\infty} B_{T+1}/(1+r)^T \geq 0$):

$$B_0 = -\sum_{t=0}^{\infty} \frac{NX_t}{(1+r)^t}$$

Los pasivos externos netos iniciales deben cubrirse con el valor presente de los superávit comerciales futuros. Esta condición es la restricción que disciplina la sostenibilidad externa — el análogo de la RPI del gobierno para el sector externo del país.

### 1.3 Medición correcta de la CC

Las medidas contables convencionales de la CC son imperfectas. En términos económicos, la CC debería capturar el cambio en los activos externos netos reales, corrigiendo tanto por ganancias y pérdidas de capital sobre el stock existente como por la erosión inflacionaria del valor real de los activos nominales denominados en moneda extranjera.  En la práctica, las estadísticas oficiales de CC omiten las ganancias de capital — lo que puede ser cuantitativamente importante en períodos de volatilidad cambiaria o de precios de activos.

---

## 2. El enfoque intertemporal de la cuenta corriente

### 2.1 El marco conceptual

El enfoque intertemporal ve el saldo de cuenta corriente como el resultado de decisiones forward-looking de ahorro e inversión. Este enfoque extiende el enfoque de absorción al reconocer que las decisiones privadas de ahorro e inversión resultan de cálculos dinámicos basados en expectativas sobre crecimiento futuro de la productividad, demandas de gasto público, tasas de interés reales, y similares. 

La implicancia central es que los desequilibrios de CC no son necesariamente un problema: son el resultado óptimo de decisiones de suavización del consumo y acumulación de capital de agentes que tienen acceso a los mercados internacionales de capital. El análisis normativo requiere preguntarse no si hay déficit sino si ese déficit refleja decisiones racionales dadas las fricciones existentes.

### 2.2 Economía de dotación: el modelo canónico

#### Setup

Los intercambios de recursos a través del tiempo se denominan comercio intertemporal. Gran parte de la acción macroeconómica en una economía abierta está conectada con este comercio intertemporal, que se mide por la cuenta corriente de la balanza de pagos. 

Consideramos el modelo de dos períodos de Obstfeld & Rogoff (1996, cap. 1) en su versión más limpia: economía pequeña y abierta, sin inversión, sin gobierno, con un bien.

El consumidor representativo maximiza:

$$U = u(C_1) + \beta u(C_2), \quad \beta = \frac{1}{1+\rho}$$

sujeto a la restricción presupuestaria intertemporal:

$$C_1 + \frac{C_2}{1+r} = Y_1 + \frac{Y_2}{1+r} + (1+r)B_0 \equiv W$$

donde $W$ es la riqueza de ciclo de vida. La condición de primer orden es la ecuación de Euler:

$$u'(C_1) = \beta(1+r)u'(C_2)$$

Con CRRA $u(C) = C^{1-\sigma}/(1-\sigma)$:

$$\frac{C_2}{C_1} = [\beta(1+r)]^{1/\sigma}$$

#### La CC en la economía de dotación

La cuenta corriente del período 1 es:

$$CC_1 = Y_1 + rB_0 - C_1$$

El agente tiene déficit de CC si el consumo óptimo supera el ingreso disponible (quiere traer consumo del futuro); superávit si quiere trasladar consumo hacia el futuro.

El comercio intertemporal hace posible un perfil de consumo menos irregular en el tiempo. Los gains from trade intertemporales se obtienen cuando la tasa autárquica de interés difiere de la tasa mundial: si la tasa autárquica doméstica es menor que la mundial, el país exporta bienes presentes (presta, tiene superávit) y obtiene bienes futuros; si es mayor, importa bienes presentes (se endeuda, tiene déficit). 

#### Shocks transitorios vs. permanentes

Este es el resultado central del modelo de dotación con horizonte finito:

**Shock positivo transitorio** ($Y_1 \uparrow$, $Y_2$ sin cambio):

La riqueza $W$ sube menos que $Y_1$ (el shock no afecta $Y_2$). El consumidor suaviza: $C_1$ sube menos que $Y_1$. El exceso de ingreso sobre consumo genera **superávit de CC**. El país exporta el ingreso transitorio como ahorro externo.

**Shock positivo permanente** ($Y_1$ e $Y_2$ suben proporcionalmente):

La riqueza sube en la misma proporción que $Y_1$. El consumidor ajusta $C_1$ en la misma magnitud. **La CC no cambia**. El shock permanente no genera comercio intertemporal.

**Shock a la tasa de interés mundial** ($r \uparrow$):

- Efecto sustitución: $C_1$ cae, $C_2$ sube → mejora CC.
- Efecto ingreso: si $B_0 > 0$ (acreedor), el ingreso sube → $C_1$ sube → deteriora CC.
- El signo neto depende de la posición externa neta.

La generalización es inmediata: en equilibrio, un país incurrirá en déficit de CC si su ingreso corriente cae por debajo de su ingreso permanente, o equivalentemente, cuando el retorno doméstico al capital es más alto que el costo de endeudarse internacionalmente. 

---

## 3. Economía con producción e inversión

### 3.1 El problema de la firma

Incorporando producción, la firma elige el stock de capital $K_2$ para el período 2 maximizando el valor presente de los beneficios:

$$\max_{K_2} \; F(K_2, L) - I - \frac{1}{1+r}[F(K_2, L) + (1-\delta)K_2]$$

donde $I = K_2 - (1-\delta)K_1$ es la inversión. La condición de primer orden:

$$F_K(K_2) = r + \delta$$

La productividad marginal del capital iguala el costo de uso — idéntico al resultado del modelo neoclásico cerrado, pero ahora $r$ es la tasa mundial.

### 3.2 La CC con inversión

La CC del período 1 es:

$$CC_1 = S_1 - I_1 = [Y_1 + rB_0 - C_1 - G_1] - I_1$$

La CC es el exceso de ahorro doméstico sobre inversión. Las implicancias de política son directas:

- Un aumento en la productividad futura esperada eleva $K_2^*$ → aumenta $I_1$ → deteriora la CC en el período 1, pero genera superávit en el período 2 cuando la mayor producción financie la deuda. Este es el patrón de los países en desarrollo que reciben IED.

- Un shock positivo transitorio de productividad corriente eleva el ahorro más que la inversión → mejora la CC.

- Un shock permanente de productividad eleva simultáneamente la inversión y el consumo deseado → el efecto sobre la CC es ambiguo y depende de las elasticidades.

### 3.3 El resultado de Glick-Rogoff (1995)

Glick y Rogoff (1995) distinguen empíricamente entre shocks de productividad globales y específicos de cada país. Un shock global afecta la productividad marginal del capital en todos los países simultáneamente, lo que altera la tasa de interés mundial pero no la CC de ningún país individualmente. Un shock específico de un país, en cambio, mueve la inversión doméstica sin alterar la tasa mundial, generando variación en la CC. 

Este resultado tiene implicancias para la interpretación de los datos: la correlación entre productividad y CC puede ser baja no porque el enfoque intertemporal falle, sino porque los shocks identificados en los datos son primariamente globales.

---

## 4. Ajuste de la CC: economías pequeñas y grandes

### 4.1 Economía pequeña abierta (EOAP)

En una economía pequeña, $r$ está dado por el mundo. Los cambios en ahorro e inversión domésticos no afectan $r$: toda la presión de ajuste recae sobre la CC. El modelo predice desequilibrios de CC amplios ante shocks persistentes de productividad — más de lo observado en los datos.

### 4.2 Economía grande: equilibrio mundial

Cuando el país es grande (EE.UU., China, la eurozona), sus decisiones de ahorro e inversión afectan la tasa de interés mundial. El equilibrio requiere vaciar el mercado mundial de fondos prestables:

$$S^H + S^F = I^H + I^F$$

donde $H$ y $F$ denotan el país doméstico y el resto del mundo. Un aumento en el ahorro doméstico reduce $r^*$, lo que estimula la inversión mundial y suaviza el superávit de CC doméstico comparado con el caso de economía pequeña.

La implicancia para los **desequilibrios globales** (global imbalances) es relevante: el superávit persistente de China y el déficit persistente de EE.UU. en los 2000 coexistieron con tasas reales mundiales bajas — consistente con el modelo de dos países donde el exceso de ahorro chino deprimió la tasa real global. Bernanke (2005) denominó esto el "saving glut" asiático.

### 4.3 Los puzzles del enfoque intertemporal

A pesar del atractivo conceptual del enfoque intertemporal, las cuentas corrientes reales no se mueven tanto como la teoría estándar predice. El puzzle de Feldstein-Horioka — la alta correlación entre ahorro e inversión domésticos — es una manifestación de cuentas corrientes "pegajosas". 

Los puzzles documentados incluyen:

**Puzzle de Feldstein-Horioka (1980):** la correlación ahorro-inversión es cercana a 0.9 en países OCDE, implicando que casi todo el ahorro adicional se invierte domésticamente. Si los mercados de capital fueran perfectamente integrados, esta correlación debería ser cero.

**Paradoja de Lucas (1990):** el capital no fluye masivamente de países ricos a pobres como el modelo predice (donde la productividad marginal del capital debería ser mucho mayor). Las explicaciones incluyen riesgo soberano, asimetría de información, diferencias en capital humano e instituciones.

**Volatilidad excesiva del tipo de cambio:** la CC no es tan volátil como el modelo predice, pero el tipo de cambio es mucho más volátil que los fundamentos. Meese y Rogoff (1983) documentaron que ningún modelo estructural predice el tipo de cambio mejor que un random walk fuera de muestra — uno de los resultados más robustos y molestos de la macroeconomía internacional.

---

## 5. El déficit gemelo

### 5.1 La identidad

De la identidad $CC = S_N - I$, desagregando el ahorro nacional:

$$CC = \underbrace{(S_{\text{priv}} - I)}_{\text{superávit privado}} + \underbrace{(T - G)}_{\text{superávit fiscal}}$$

Un deterioro del balance fiscal ($T - G$ cae) deteriora la CC en la misma magnitud si y solo si el sector privado no ajusta su ahorro ni su inversión. Este es el argumento de los **déficits gemelos**: déficit fiscal → déficit de CC.

### 5.2 La equivalencia ricardiana como caso límite

Si la equivalencia ricardiana se cumple exactamente, un déficit fiscal financiado con deuda no afecta la CC: los hogares aumentan su ahorro en anticipación de impuestos futuros, compensando exactamente la caída en el ahorro público. La identidad se mantiene contablemente, pero el movimiento en $T - G$ es exactamente offset por el movimiento en $S_{\text{priv}}$.

En este caso extremo, el déficit fiscal no afecta la tasa de interés real, la inversión ni la CC. La política fiscal es irrelevante para la posición externa.

### 5.3 El caso intermedio: evidencia

La realidad está entre los dos extremos. La evidencia empírica, resumida en Kim y Roubini (2008), muestra que:

- En economías avanzadas, el offset del ahorro privado es parcial: un aumento de 1% del PIB en el déficit fiscal deteriora la CC entre 0.2% y 0.5% del PIB — lejos del 1:1 del modelo sin equivalencia ricardiana y lejos del 0 de la equivalencia perfecta.
- En economías emergentes, el vínculo es más fuerte porque la equivalencia ricardiana falla más (restricciones de liquidez más prevalentes).
- El canal de tipo de cambio importa: un déficit fiscal puede apreciar el tipo de cambio real (vía mayor demanda de no transables), deteriorando la competitividad y la balanza comercial.

### 5.4 El caso de EE.UU. en los 2000

El episodio paradigmático es la coexistencia de déficit fiscal creciente (efecto Bush tax cuts + gasto en guerras) y déficit de CC creciente en EE.UU. entre 2001 y 2007. El déficit de CC alcanzó 6% del PIB en 2006. Sin embargo, el vínculo causal es discutido: el ahorro privado también cayó en el período, sugiriendo que el desahorro privado (boom inmobiliario, riqueza financiera) fue al menos tan importante como el déficit fiscal.

---

## 6. Sostenibilidad de la cuenta corriente

### 6.1 La condición de solvencia

Un déficit de CC es sostenible si la trayectoria de activos externos netos satisface la condición de no-Ponzi. En la práctica, esto requiere que la razón deuda externa neta/PIB sea estacionaria — es decir, que los superávit primarios externos futuros sean suficientes para servir la deuda acumulada.

La condición de estabilización de la razón deuda externa/PIB ($b = B/Y$, con $B < 0$ para deudor):

$$\Delta b = (r - g)|b| - nx$$

donde $nx = NX/Y$ es la balanza comercial como fracción del PIB y $g$ es la tasa de crecimiento. Si $r > g$, el país necesita superávit comercial para estabilizar su posición externa.

### 6.2 Criterios prácticos de sostenibilidad

El FMI y los bancos centrales usan distintos umbrales empíricos:

- **Razón deuda externa/PIB:** niveles por sobre 60-80% en economías emergentes son señales de alerta.
- **Razón déficit CC/PIB:** déficits persistentes sobre 4-5% del PIB se consideran potencialmente insostenibles, aunque el umbral depende fuertemente de si el déficit financia inversión productiva o consumo.
- **Estructura de la deuda:** deuda de corto plazo y denominada en moneda extranjera eleva la vulnerabilidad.
- **Activos de reserva:** reservas internacionales bajas respecto a la deuda de corto plazo (ratio de Greenspan-Guidotti < 1) son un indicador de vulnerabilidad ante sudden stops.

### 6.3 Sudden stops y ajuste abrupto

Stocks crecientes de pasivos externos netos pueden representar un problema de sostenibilidad ya en el mediano plazo y aumentan la probabilidad de sudden stops y paradas abruptas de flujos de capital. 

El sudden stop (Calvo, 1998) es la interrupción abrupta de los flujos de capital hacia una economía. Si un país financia un déficit de CC de 5% del PIB con flujos externos y estos se detienen, el ajuste requerido es de 5 puntos del PIB casi instantáneamente. Las opciones son: recesión (cae $C + I$), depreciación real (mejora $NX$), o una combinación. La velocidad del ajuste y sus costos reales dependen de:

- Flexibilidad del tipo de cambio: un tipo de cambio flexible permite la depreciación real vía el tipo nominal; un tipo fijo requiere deflación interna, más costosa.
- Grado de dolarización: la deuda en moneda extranjera genera efectos hoja de balance cuando la moneda se deprecia.
- Acceso a liquidez internacional: líneas de crédito contingente del FMI reducen el costo del ajuste.

---

## 7. Síntesis: el enfoque intertemporal como paradigma

El enfoque intertemporal provee una fundación consistente y coherente para el análisis de política en economía abierta. Como tal, debería suplir las versiones expandidas del modelo IS-LM de Mundell-Fleming que actualmente proveen el paradigma dominante usado por bancos centrales, ministerios de finanzas y agencias económicas internacionales. 

Sin embargo, los puzzles empíricos — Feldstein-Horioka, paradoja de Lucas, exceso de suavidad de la CC — muestran que el modelo base necesita extensiones: fricciones en mercados de capital, heterogeneidad de agentes, mercados incompletos y asimetrías de información. La agenda de investigación de las últimas dos décadas ha avanzado en incorporar estas fricciones en marcos de equilibrio general estocástico abiertos (DSGE abiertos), manteniendo la disciplina intertemporal como núcleo.

---

## Referencias

- Obstfeld, M. & Rogoff, K. (1994). *The Intertemporal Approach to the Current Account*. NBER WP 4893.
- Obstfeld, M. & Rogoff, K. (1996). *Foundations of International Macroeconomics*. MIT Press. Caps. 1–2.
- Schmitt-Grohé, S., Uribe, M. & Woodford, M. (2022). *International Macroeconomics*. Princeton University Press.
- Glick, R. & Rogoff, K. (1995). *Global versus Country-Specific Productivity Shocks and the Current Account*. JME.
- Feldstein, M. & Horioka, C. (1980). *Domestic Saving and International Capital Flows*. EJ.
- Calvo, G. (1998). *Capital Flows and Capital-Market Crises: The Simple Economics of Sudden Stops*. Journal of Applied Economics.
- Meese, R. & Rogoff, K. (1983). *Empirical Exchange Rate Models of the Seventies: Do They Fit Out of Sample?* JIE.
- Bernanke, B. (2005). *The Global Saving Glut and the U.S. Current Account Deficit*. Sandridge Lecture.
- Kim, S. & Roubini, N. (2008). *Twin Deficit or Twin Divergence? Fiscal Policy, Current Account, and Real Exchange Rate in the U.S.* JIE.
- Krugman, P., Melitz, M. & Obstfeld, M. (2015). *International Finance: Theory and Policy*. 10ma ed.