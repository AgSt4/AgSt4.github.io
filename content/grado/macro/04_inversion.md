---
title: "Inversión"
date: 2026-03-15
draft: false
tags: ["macroeconomía", "inversión", "q de Tobin", "costos de ajuste", "irreversibilidad", "EAE2210"]
description: "Costo de uso del capital, q de Tobin, costos de ajuste, impuestos, irreversibilidad y opciones reales. Apunte basado en EAE2210 — Macroeconomía I."
---

**Curso:** Macroeconomía I (EAE2210) · **Profesor:** Emilio Depetris-Chauvin  
**Referencia principal:** De Gregorio (2007) cap. 11 · Romer (2012) cap. 8 · Dixit & Pindyck (1994)

---

## 1. La demanda por capital y el costo de uso

### 1.1 El problema estático de la firma

El punto de partida es el modelo neoclásico de Jorgenson (1963). La firma maximiza beneficios eligiendo capital $K$ y trabajo $L$:

$$\max_{K,L} \; F(K,L) - wL - c_K K$$

donde $w$ es el salario real y $c_K$ el **costo de uso del capital** (user cost of capital). La condición de primer orden para el capital es:

$$F_K(K^*, L^*) = c_K$$

La productividad marginal del capital debe igualar su costo de uso. ¿Qué es $c_K$?

### 1.2 El costo de uso del capital

El costo de uso captura el costo de tener una unidad de capital por un período. Incluye tres componentes:

1. **Costo de oportunidad financiero:** invertir en capital en vez de en el activo libre de riesgo implica costo $rp_K$, donde $p_K$ es el precio del bien de capital.
2. **Depreciación:** el capital se desgasta a tasa $\delta$, con costo $\delta p_K$.
3. **Ganancia/pérdida de capital:** si el precio del capital cambia, $-\dot{p}_K$.

Sumando:

$$c_K = p_K(r + \delta - \hat{p}_K)$$

donde $\hat{p}_K = \dot{p}_K/p_K$ es la tasa de cambio del precio del capital. Si $p_K$ es constante: $c_K = p_K(r + \delta)$.

El stock de capital deseado $K^*$ se obtiene invirtiendo la condición $F_K = c_K$. Con Cobb-Douglas $F = AK^\alpha L^{1-\alpha}$:

$$K^* = \left(\frac{\alpha A}{c_K}\right)^{1/(1-\alpha)} L$$

Un aumento en la tasa de interés real $r$ eleva $c_K$ y reduce $K^*$. Esto es el canal neoclásico de transmisión de política monetaria a la inversión.

### 1.3 El problema dinámico: la ecuación de acumulación

El stock de capital evoluciona según:

$$\dot{K} = I - \delta K$$

donde $I$ es la inversión bruta. En el modelo neoclásico sin fricciones, la firma ajusta instantáneamente $K$ a $K^*$: si $K < K^*$, invierte todo lo necesario de inmediato. Esto implica que la demanda de inversión es infinitamente elástica al costo de uso — irreal, y contradicho por los datos.

---

## 2. La q de Tobin y la evaluación de proyectos

### 2.1 Intuición y definición

Tobin (1969) propone un criterio alternativo basado en precios de mercado:

$$q \equiv \frac{\text{Valor de mercado del capital instalado}}{\text{Costo de reposición del capital}}$$

La regla de inversión es simple:
- $q > 1$: el mercado valora el capital más de lo que cuesta instalarlo → invertir.
- $q < 1$: el capital vale menos en el mercado que lo que costaría reemplazarlo → desinvertir o no invertir.
- $q = 1$: indiferencia en el margen.

### 2.2 q marginal vs. q promedio

La distinción de Hayashi (1982) es fundamental para la aplicabilidad empírica. La q marginal es el valor de mercado de una unidad adicional de capital dividido por su costo de reposición. La q promedio es el valor de mercado del capital existente dividido por su costo de reposición. Hayashi demostró que bajo competencia perfecta y retornos constantes a escala, la q marginal es igual a la q promedio , lo que hace a la teoría empíricamente operativa: se puede medir q con datos de mercado accionario sin necesidad de conocer la productividad marginal directamente.

Formalmente, la q de mercado es el valor presente del flujo de beneficios por unidad de capital que la firma generará desde el período corriente al futuro infinito . Si la firma puede vender acciones por más de lo que cuesta una unidad de capital, conviene emitir acciones, comprar capital y quedarse con la diferencia — el incentivo a invertir es directo.

### 2.3 Limitaciones empíricas de la q

La q promedio observable explica sorprendentemente poco de la variación en la inversión en los datos. Las razones documentadas son:

- **Errores de medición del stock de capital:** los valores contables del capital difieren sistemáticamente de los valores económicos.
- **Fricciones financieras:** la q no captura la restricción de financiamiento externo.
- **No convexidad de los costos de ajuste:** la q de Tobin es suficiente estadístico solo bajo costos de ajuste convexos, supuesto cuestionable a nivel de planta.

Fazzari, Hubbard y Petersen (1988) documentaron que el flujo de caja tiene poder predictivo adicional sobre la inversión una vez controlado por q — evidencia de restricciones de liquidez que el modelo neoclásico no captura.

---

## 3. Costos de ajuste

### 3.1 Motivación

Si la inversión puede ajustarse sin costo, la firma llevaría $K$ a $K^*$ instantáneamente. En la realidad, instalar capital nuevo implica costos adicionales: interrupciones productivas, entrenamiento, instalación. Estos son los **costos de ajuste**, introducidos formalmente por Lucas y Prescott (1971).

### 3.2 El modelo con costos de ajuste convexos

La firma maximiza el valor presente de beneficios netos de costos de ajuste:

$$V = \int_0^\infty e^{-rt}\left[F(K,L) - wL - I - \frac{\theta}{2}\left(\frac{I}{K}\right)^2 K\right]dt$$

donde $\frac{\theta}{2}(I/K)^2 K$ es el costo de ajuste convexo: instalar más capital a la vez es proporcionalmente más costoso.

La condición de optimalidad da la ecuación de movimiento para la q de Tobin:

$$\dot{q} = rq - F_K - \frac{\theta}{2}\left(\frac{I}{K}\right)^2 + \theta\frac{I}{K}\left(\frac{I}{K}\right)$$

Y la regla de inversión óptima resulta:

$$\frac{I}{K} = \frac{q-1}{\theta}$$

La inversión es proporcional a $(q-1)$: solo si $q > 1$ la firma invierte, y cuánto invierte depende inversamente de $\theta$ (los costos de ajuste). Costos altos suavizan la respuesta de la inversión a cambios en las condiciones.

### 3.3 Implicancias

Los costos de ajuste generan **dinámica gradual**: la firma no salta a $K^*$ de inmediato sino que ajusta suavemente a lo largo del tiempo. Esto es consistente con la evidencia de que la inversión agregada es suave y autocorrelacionada. Sin embargo, a nivel de planta, la inversión es lumpy — episodios de alta inversión separados por períodos de inacción — lo que sugiere costos de ajuste no convexos a nivel microeconómico que se promedian en el agregado.

---

## 4. Impuestos e inversión

### 4.1 El costo de uso ajustado por impuestos

Los impuestos corporativos alteran el costo de uso del capital. El modelo estándar de Hall-Jorgenson incluye tres instrumentos fiscales principales:

- **Tasa de impuesto corporativo $\tau$:** reduce el flujo de beneficios después de impuestos.
- **Depreciación fiscal $d$:** la deducción por depreciación genera un escudo fiscal de valor presente $\tau z$ por unidad de capital, donde $z = \int_0^\infty e^{-rs}d(s)ds$.
- **Crédito a la inversión (ITC):** un crédito directo $k$ sobre el gasto en inversión.

El costo de uso ajustado es:

$$c_K = \frac{(1-k)(1-\tau z)}{1-\tau} \cdot p_K(r+\delta)$$

Un aumento en la tasa de depreciación fiscal (que eleva $z$) reduce el costo de uso y estimula la inversión. Este es el canal por el que reformas tributarias que aceleran la depreciación contable tienen efectos reales. La evidencia de Zwick y Mahon (2017) con datos de firmas en EE.UU. documenta efectos significativos de los incentivos de depreciación sobre la inversión, especialmente en firmas con restricciones de liquidez.

### 4.2 La paradoja del financiamiento

El tratamiento fiscal de la deuda vs. el equity también importa. En muchos sistemas tributarios, los intereses de deuda son deducibles pero los dividendos no — lo que sesga el financiamiento de la inversión hacia deuda. Esto conecta con la estructura de capital óptima y la irrelevancia de Modigliani-Miller, que se rompe en presencia de impuestos.

---

## 5. Incertidumbre e irreversibilidad: opciones reales

### 5.1 El problema de la irreversibilidad

El modelo neoclásico trata la inversión como perfectamente reversible: si las condiciones empeoran, la firma vende el capital al mismo precio que lo compró. En la realidad, la inversión es **parcial o totalmente irreversible**: el capital instalado tiene un valor de liquidación menor que su costo de instalación (hay un wedge entre precio de compra y precio de venta).

La capacidad de diferir una inversión irreversible puede afectar profundamente la decisión de invertir. El motivo es que una firma con oportunidad de invertir está sosteniendo una opción análoga a una opción de compra financiera: tiene el derecho, pero no la obligación, de adquirir un activo en algún momento futuro de su elección. Cuando la firma hace el gasto de inversión irreversible, ejerce — o "mata" — su opción de invertir, renunciando a la posibilidad de esperar nueva información. 

Este **valor de opción de espera** es un costo de oportunidad que debe incluirse en el costo total de invertir, y que la regla del VPN estándar ignora.

### 5.2 El enfoque de opciones reales (Dixit-Pindyck, 1994)

El criterio convencional es invertir cuando q iguala o supera la unidad. El criterio de opciones reales es más exigente: q debe superar la unidad por un margen suficiente, alcanzando un valor crítico $q^* > 1$. 

Formalmente, con incertidumbre sobre la rentabilidad futura $V$ que sigue un movimiento browniano geométrico:

$$dV = \alpha V \, dt + \sigma V \, dz$$

La firma enfrenta la decisión de invertir $I$ (costo hundido) para obtener un activo de valor $V$. El valor de la opción de inversión $F(V)$ satisface la ecuación diferencial de Bellman:

$$\frac{1}{2}\sigma^2 V^2 F'' + \alpha V F' - rF = 0$$

La solución da un umbral de inversión $V^*$ tal que la firma invierte si y solo si $V \geq V^*$, donde:

$$V^* = \frac{\beta}{\beta-1} I, \quad \beta = \frac{1}{2} - \frac{\alpha}{\sigma^2} + \sqrt{\left(\frac{\alpha}{\sigma^2} - \frac{1}{2}\right)^2 + \frac{2r}{\sigma^2}} > 1$$

El factor $\beta/(\beta-1) > 1$ es el **multiplicador de opciones**: la firma exige un premio sobre el VPN cero antes de invertir. Este multiplicador aumenta con $\sigma$ (más incertidumbre → mayor valor de esperar) y disminuye con $r$ (mayor tasa de descuento → menor valor de la opción de espera).

### 5.3 Implicancias para la política económica

La teoría de opciones reales tiene implicancias importantes que el modelo neoclásico estándar no captura:

**Incertidumbre reduce la inversión:** un aumento en la volatilidad $\sigma$ eleva $V^*$, haciendo la inversión más difícil de justificar. Guiso y Parigi (1999) encuentran una relación negativa entre inversión e incertidumbre; las firmas con mayor incertidumbre percibida son menos sensibles a incrementos en la demanda esperada y por tanto invierten menos. 

**Políticas de estabilización tienen valor:** reducir la volatilidad macroeconómica no solo es deseable por bienestar sino que tiene efectos reales sobre la acumulación de capital.

**La histéresis de la inversión:** la presencia de costos de entrada y salida (irreversibilidad en ambas direcciones) genera una **banda de inacción**: la firma no invierte aunque $q > 1$ si está dentro de la banda, y no desinvierte aunque $q < 1$. Esto explica por qué la inversión no responde simétricamente a expansiones y contracciones.

**El efecto de la política monetaria es asimétrico:** reducir la incertidumbre (forward guidance creíble, regímenes de metas de inflación) puede estimular la inversión más que bajar la tasa de interés, al reducir el valor de la opción de espera.

---

## 6. Evidencia empírica

La literatura empírica sobre inversión tiene varios resultados robustos:

- **La q explica poco:** la q de Tobin observable tiene $R^2$ típicamente bajos (20-30%) en regresiones de inversión. Esto motivó décadas de investigación sobre por qué.
- **El flujo de caja importa:** Fazzari, Hubbard y Petersen (1988) documentaron que la inversión de firmas con restricciones financieras es más sensible al flujo de caja que la de firmas sin restricciones, controlando por q. Esto es inconsistente con mercados de capitales perfectos.
- **La inversión es lumpy a nivel de planta:** Cooper y Haltiwanger (2006) documentaron que la inversión a nivel de establecimiento industrial ocurre en episodios de gran inversión separados por períodos de inactividad, consistente con costos de ajuste no convexos.
- **Los incentivos tributarios funcionan:** Cummins, Hassett y Hubbard (1994) usaron reformas tributarias como variación exógena en el costo de uso para identificar elasticidades de inversión al costo de capital, encontrando efectos significativos.
- **La incertidumbre tiene efectos reales:** Bloom (2009) documentó que shocks de incertidumbre (medidos por volatilidad del mercado accionario) generan caídas temporales en inversión y empleo, consistente con la teoría de opciones reales.

---

## 7. Síntesis: los modelos y sus predicciones

| Modelo | Determinante central | Dinámica | Limitación |
|---|---|---|---|
| Neoclásico (Jorgenson) | Costo de uso $c_K$ | Ajuste instantáneo | Irrealista, sin dinámica |
| q de Tobin | Valor de mercado relativo | Gradual (con costos de ajuste) | q promedio ≠ q marginal empíricamente |
| Costos de ajuste convexos | $q - 1$ | Suave y continua | Lumpy a nivel micro |
| Opciones reales (Dixit-Pindyck) | Umbral $V^*$ con opción de espera | Inacción + inversión discreta | Difícil de estimar estructuralmente |

---

## Referencias

- Jorgenson, D.W. (1963). *Capital Theory and Investment Behavior*. AER.
- Tobin, J. (1969). *A General Equilibrium Approach to Monetary Theory*. JMCB.
- Lucas, R. & Prescott, E. (1971). *Investment Under Uncertainty*. Econometrica.
- Hayashi, F. (1982). *Tobin's Marginal q and Average q: A Neoclassical Interpretation*. Econometrica.
- Fazzari, S., Hubbard, R.G. & Petersen, B. (1988). *Financing Constraints and Corporate Investment*. BPEA.
- Dixit, A. & Pindyck, R. (1994). *Investment Under Uncertainty*. Princeton University Press.
- Abel, A. & Eberly, J. (1994). *A Unified Model of Investment Under Uncertainty*. AER.
- Cooper, R. & Haltiwanger, J. (2006). *On the Nature of Capital Adjustment Costs*. RES.
- Bloom, N. (2009). *The Impact of Uncertainty Shocks*. Econometrica.
- De Gregorio, J. (2007). *Macroeconomía: Teoría y Políticas*. Cap. 11.