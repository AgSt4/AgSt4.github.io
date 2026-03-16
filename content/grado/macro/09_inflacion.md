---
title: "Nivel de Precios e Inflación"
date: 2026-03-15
draft: false
tags: ["macroeconomía", "inflación", "teoría cuantitativa", "señoreaje", "Dornbusch", "política monetaria", "EAE2220"]
description: "Teoría cuantitativa, modelo monetario del nivel de precios, expectativas racionales, costos de la inflación, hiperinflación y el modelo de overshooting de Dornbusch."
---

**Curso:** Macroeconomía II (EAE2220)  
**Referencia principal:** De Gregorio (2007) caps. 14–15 · Walsh (2010) cap. 2 · Dornbusch (1976)

---

## 1. La ecuación cuantitativa del dinero

### 1.1 De identidad a teoría

La ecuación cuantitativa — o ecuación de intercambio — es en sí misma no controversial: puede verse como una identidad contable que define residualmente la velocidad como la razón entre el producto nominal y la oferta de dinero.  La ecuación es:

$$MV = PY$$

donde $M$ es la oferta de dinero, $V$ la velocidad de circulación, $P$ el nivel de precios e $Y$ el producto real. Asumiendo adicionalmente que $Y$ es exógeno (determinado por factores reales), que $V$ es constante, y que $M$ es exógena y controlada por el banco central, la ecuación se convierte en una teoría que dice que la inflación puede controlarse fijando la tasa de crecimiento de $M$. 

Tomando tasas de crecimiento logarítmicas:

$$\hat{M} + \hat{V} = \pi + \hat{Y}$$

Si $\hat{V} = 0$ (velocidad estable):

$$\pi = \hat{M} - \hat{Y}$$

La inflación es la tasa de crecimiento monetario en exceso del crecimiento real. Esta es la proposición central del monetarismo: cambios en la tasa de crecimiento del dinero tienen efectos sobre la tasa de inflación, mientras que las consecuencias reales de corto plazo son ambiguas. El crecimiento económico de largo plazo es en gran medida independiente de la dinámica monetaria. 

### 1.2 La evidencia de largo plazo

La relación dinero-inflación es robusta en muestras largas y de alta inflación. Resultados de panel muestran que la relación de largo plazo entre exceso de crecimiento monetario e inflación se sostiene con datos suficientemente largos, con una velocidad de ajuste promedio de alrededor de dos años en países industriales, consistente con la predicción friedmaniana de "rezagos largos y variables". 

Sin embargo, en décadas recientes el cambio estructural — coincidiendo con la Gran Moderación y cambios en tecnología de pagos — ha llevado a un colapso de la relación predicha por la teoría cuantitativa.  El episodio post-2008 es ilustrativo: entre 2008 y 2013 la oferta monetaria en Estados Unidos creció en promedio 33%, lo que dado el crecimiento del producto y velocidad constante debería haber generado una inflación de 31%. La inflación observada fue menor al 2%.  Los bancos acumularon reservas en vez de expandir el crédito, colapsando el multiplicador monetario. Este episodio motivó el abandono de metas de agregados monetarios en favor de metas de inflación.

---

## 2. Modelo monetario del nivel de precios

### 2.1 Versión estática

El modelo monetario del nivel de precios combina la ecuación cuantitativa con una función de demanda por dinero. Con demanda log-lineal:

$$m - p = \phi y - \lambda i$$

donde $m = \ln M$, $p = \ln P$, $y = \ln Y$, $\phi > 0$ y $\lambda > 0$. Despejando el nivel de precios:

$$p = m - \phi y + \lambda i$$

El nivel de precios sube con la oferta monetaria y la tasa nominal, y cae con el producto real. Usando la ecuación de Fisher $i = r + \pi^e$ y dado que $r$ es determinado por el sector real:

$$p = m - \phi y + \lambda(r + \pi^e)$$

El nivel de precios depende de las expectativas de inflación: si los agentes esperan más inflación, la demanda por dinero cae (saldos reales caen), lo que eleva el nivel de precios hoy. Las expectativas son auto-cumplidas en equilibrio.

### 2.2 Versión dinámica con expectativas racionales

La versión dinámica incorpora expectativas racionales sobre el nivel de precios futuro. La condición de equilibrio monetario en cada período es:

$$p_t = m_t - \phi y_t + \lambda E_t[p_{t+1}] - \lambda p_t + \lambda r$$

Reordenando y tomando la solución hacia adelante (forward solution):

$$p_t = (1-\lambda)\sum_{j=0}^{\infty} \left(\frac{\lambda}{1+\lambda}\right)^j E_t[m_{t+j} - \phi y_{t+j}]$$

El nivel de precios hoy es el valor presente descontado de todos los fundamentos monetarios futuros esperados. Esta es la implicancia clave del modelo de expectativas racionales: **el nivel de precios hoy depende de toda la trayectoria esperada de la política monetaria futura**, no solo de la oferta de dinero corriente.

La implicancia de política es relevante: anunciar una expansión monetaria futura eleva el nivel de precios hoy, incluso antes de que la expansión ocurra. La credibilidad y las expectativas son tan importantes como los instrumentos actuales.

---

## 3. Impuesto inflación, señoreaje y sus costos

### 3.1 El señoreaje como fuente de financiamiento

El señoreaje es el ingreso real que obtiene el gobierno de crear dinero:

$$\sigma_t = \frac{\dot{M}_t}{P_t} = \mu_t \cdot m_t$$

donde $\mu_t = \dot{M}/M$ es la tasa de expansión monetaria y $m_t = M/P$ son los saldos reales. En estado estacionario con inflación constante $\pi = \mu - g$:

$$\sigma = \pi \cdot m(\pi)$$

El señoreaje es el producto de la tasa del "impuesto" ($\pi$, que erosiona el valor real del dinero) por la "base imponible" ($m$, los saldos reales). La demanda por saldos reales es decreciente en la inflación: $m'(\pi) < 0$.

### 3.2 La curva de Laffer del señoreaje

El señoreaje como función de $\pi$ tiene forma de joroba — la curva de Laffer del señoreaje. Diferenciando:

$$\frac{d\sigma}{d\pi} = m(\pi) + \pi \cdot m'(\pi) = m(\pi)\left(1 + \frac{\pi \cdot m'(\pi)}{m(\pi)}\right) = m(\pi)(1 - |\varepsilon_m|)$$

donde $\varepsilon_m = -\pi m'/m > 0$ es la elasticidad (en valor absoluto) de los saldos reales respecto a la inflación. El señoreaje se maximiza cuando $|\varepsilon_m| = 1$ (elasticidad unitaria). Para $|\varepsilon_m| < 1$ (baja inflación), más inflación aumenta el señoreaje. Para $|\varepsilon_m| > 1$ (alta inflación), más inflación destruye la base más de lo que gana la tasa — el señoreaje cae.

Las hiperinflaciones ocurren cuando el gobierno intenta extraer señoreaje en la zona descendente de la curva de Laffer monetaria, generando una espiral inestable. Sargent (1982) documentó que las grandes hiperinflaciones de la posguerra europea (Alemania, Austria, Hungría, Polonia) terminaron de forma abrupta con reformas fiscales y monetarias coordinadas — la inflación era fundamentalmente un fenómeno fiscal, no puramente monetario.

### 3.3 Costos de bienestar de la inflación

La inflación tiene costos reales, incluso cuando es perfectamente anticipada:

**Costos de suela de zapatos (shoe-leather costs):** la inflación es un impuesto sobre los saldos reales → los agentes reducen sus tenencias de dinero → realizan más viajes al banco → mayor costo de tiempo y recursos. Formalmente, la pérdida de bienestar es el área bajo la curva de demanda por dinero entre cero y $i = r + \pi$. Las estimaciones empíricas de estos costos son relativamente pequeños — menores al 1% del PIB a las tasas de inflación históricamente observadas en países avanzados. 

**Costos de menú:** las firmas deben cambiar sus listas de precios con mayor frecuencia → costos administrativos directos. En el modelo de Calvo, la inflación también distorsiona la dispersión relativa de precios porque no todas las firmas ajustan simultáneamente.

**Distorsiones fiscales:** la inflación interactúa con el sistema tributario no indexado. Las tasas marginales de impuesto al ingreso suben en términos reales (bracket creep), y los impuestos sobre ganancias de capital gravan rentabilidades nominales en vez de reales.

**Costos de redistributivos e incertidumbre:** la inflación no anticipada redistribuye riqueza de acreedores a deudores (reduce el valor real de las deudas nominales fijas). La incertidumbre sobre la inflación futura eleva la prima de riesgo en las tasas de interés nominales de largo plazo.

**Costos de crecimiento:** la evidencia sugiere que inflaciones moderadas (bajo 10%) tienen efectos pequeños sobre el crecimiento, pero inflaciones altas sí lo reducen significativamente. Fischer (1993) documenta que la relación es negativa y no lineal — el umbral no está bien identificado pero la literatura sugiere entre 10% y 20% anual.

### 3.4 La regla de Friedman óptima

El óptimo de política en el modelo MIU es la **regla de Friedman**: fijar $i = 0$, equivalente a una deflación a tasa $\pi = -r$. Con $i = 0$, el costo de oportunidad de mantener dinero es cero → los agentes están saciados de liquidez → el costo de suela de zapatos desaparece. La regla es el óptimo de primer orden pero difícilmente implementable: requiere deflación sostenida y puede generar problemas en el límite inferior cero de las tasas nominales.

---

## 4. Tipo de cambio e inflación

### 4.1 Conceptos de tipo de cambio

- **Tipo de cambio nominal ($E$):** precio de la moneda extranjera en términos de moneda doméstica (pesos por dólar). Un aumento en $E$ es una **depreciación** de la moneda doméstica.
- **Tipo de cambio real ($q$):** $q = EP^*/P$, donde $P^*$ es el nivel de precios externo. Mide la competitividad real de la economía.
- **Tipo de cambio efectivo:** promedio ponderado por comercio de los tipos de cambio bilaterales.

### 4.2 Paridad del poder de compra (PPP)

La hipótesis de PPP absoluta establece que $q = 1$: los precios de los mismos bienes deben ser iguales entre países en términos de una moneda común. La PPP relativa es más débil: los cambios en el tipo de cambio nominal reflejan los diferenciales de inflación:

$$\hat{E} = \pi - \pi^*$$

La evidencia respalda la PPP como tendencia de largo plazo (el tipo de cambio real es estacionario) pero con desviaciones persistentes de corto y mediano plazo. Las desviaciones se explican por el **efecto Balassa-Samuelson**: los países con mayor productividad en el sector transable tienen niveles de precios más altos porque el sector no transable importa salarios altos del sector transable sin la correspondiente productividad.

### 4.3 Enfoque monetario del tipo de cambio (versión estática)

Combinando la condición de PPP con los modelos monetarios doméstico y externo:

$$e = (m - m^*) - \phi(y - y^*) + \lambda(i - i^*)$$

donde $e = \ln E$. El tipo de cambio nominal depende de la oferta relativa de dinero, el producto relativo y el diferencial de tasas de interés. Un aumento en $m$ deprecia la moneda doméstica proporcionalmente — la neutralidad monetaria se extiende al tipo de cambio en el largo plazo.

### 4.4 Versión con expectativas racionales

Aplicando la misma lógica de solución hacia adelante que en el modelo de precios:

$$e_t = (1-\lambda)\sum_{j=0}^{\infty}\left(\frac{\lambda}{1+\lambda}\right)^j E_t[f_{t+j}]$$

donde $f_t = (m_t - m_t^*) - \phi(y_t - y_t^*)$ son los fundamentos monetarios relativos. El tipo de cambio hoy descuenta toda la política monetaria relativa esperada. Los anuncios creíbles de política monetaria futura afectan el tipo de cambio hoy — el "efecto noticias" en el tipo de cambio.

---

## 5. El modelo de overshooting de Dornbusch (1976)

### 5.1 La pregunta y la solución

El modelo monetario estático predice que el tipo de cambio es tan estable como los fundamentos monetarios. Pero en los datos, los tipos de cambio son mucho más volátiles que los precios de bienes o los agregados monetarios — una de las regularidades empíricas más robustas de la macroeconomía internacional.

El modelo de Dornbusch — "Expectations and Exchange Rate Dynamics" (1976) — marca el nacimiento de la macroeconomía internacional moderna. Rogoff lo describe como uno de los papers más influyentes en economía en el último cuarto del siglo XX. 

La respuesta de Dornbusch es que la volatilidad cambiaria es una consecuencia racional de la diferencia en velocidades de ajuste: **los mercados financieros ajustan instantáneamente; los mercados de bienes ajustan lentamente** (precios rígidos en el corto plazo). El insight central es que los rezagos de ajuste en algunas partes de la economía inducen volatilidad compensatoria en otras: cuando una variable exógena cambia, el efecto de corto plazo sobre el tipo de cambio puede ser mayor que el efecto de largo plazo, por lo que el tipo de cambio sobrepasa transitoriamente su nuevo valor de equilibrio de largo plazo. 

### 5.2 Estructura del modelo

El modelo combina tres ingredientes:

**1. Paridad descubierta de tasas de interés (UIP):**

$$i = i^* + E_t[\dot{e}]$$

El diferencial de tasas de interés doméstico vs. externo iguala la depreciación esperada. Si $i > i^*$, los inversores esperan que la moneda doméstica se deprecie para compensar el mayor retorno.

**2. Precios rígidos en el corto plazo:**

$$\dot{p} = \pi(y^d - \bar{y}), \quad \pi > 0$$

Los precios se ajustan gradualmente en función del exceso de demanda. En el largo plazo, $p$ alcanza su valor de equilibrio consistente con el nivel de dinero.

**3. Demanda de dinero:**

$$m - p = \phi y - \lambda i$$

### 5.3 El resultado de overshooting

Considere un aumento permanente no anticipado en $M$ (reducción de $i$ de largo plazo). El ajuste opera en dos velocidades:

**Corto plazo (instantáneo):** $P$ no puede ajustarse → los saldos reales $M/P$ suben → $i$ cae para vaciar el mercado monetario → por UIP, $i < i^*$ implica que los inversores esperan **apreciación futura** → el tipo de cambio debe depreciarse **más** que su nuevo valor de largo plazo hoy para que la apreciación posterior sea consistente con UIP.

**Largo plazo:** $P$ sube gradualmente hasta que los saldos reales vuelvan a su nivel original → $i$ vuelve a $i^*$ → el tipo de cambio se aprecia desde su valor de overshooting hasta el nuevo paridad de largo plazo.

Formalmente, el tipo de cambio de overshooting es:

$$e_0 = \bar{e} + \left(\frac{1}{\lambda} + \frac{1}{\pi\phi}\right)(m - \bar{m})$$

donde $\bar{e}$ es el tipo de cambio de largo plazo. El factor $\left(\frac{1}{\lambda} + \frac{1}{\pi\phi}\right) > 1$ es el **coeficiente de overshooting**: el tipo de cambio se mueve más que proporcionalmente respecto al cambio en los fundamentos monetarios. Cuanto más rígidos son los precios (menor $\pi$) y menor la elasticidad de la demanda de dinero a la tasa de interés (menor $\lambda$), mayor el overshooting.

### 5.4 Implicancias y evidencia

El modelo asume precios de bienes rígidos en el corto plazo pero flexibles en el largo, arbitraje en mercados de activos vía UIP, y expectativas de tipo de cambio racionales. Estas características — sticky prices + rational expectations — son los dos ingredientes centrales de la macroeconomía moderna. 

La implicancia de política es reveladora: la volatilidad cambiaria no es evidencia de irracionalidad ni de mercados ineficientes — es una respuesta racional óptima a la asimetría en velocidades de ajuste. Intentar suprimir la volatilidad cambiaria mediante intervención puede ser contraproducente si no se atacan las rigideces subyacentes.

La evidencia empírica directa es mixta: muchos estudios VAR encuentran que la respuesta del tipo de cambio a shocks monetarios no es consistente con overshooting, observando en cambio una apreciación gradual. Sin embargo, estudios que imponen restricciones de neutralidad de largo plazo para identificar los shocks encuentran que los puzzles desaparecen y el overshooting es consistente con los datos. 

### 5.5 El traspaso del tipo de cambio a precios (pass-through)

Un corolario importante para economías abiertas es el **pass-through**: cuánto de una depreciación del tipo de cambio se traspasa a precios domésticos. El pass-through completo implica PPP inmediata y neutralidad monetaria instantánea. En la práctica:

- El pass-through es parcial e incompleto en el corto plazo: los importadores absorben parte de la depreciación en márgenes.
- El pass-through ha disminuido en economías con baja inflación y bancos centrales creíbles — la credibilidad de la meta de inflación rompe el mecanismo indexatorio.
- Para Chile, la evidencia muestra pass-through de alrededor de 15-25% al año y casi completo en 3-4 años.

---

## 6. Inflación moderada e hiperinflación

### 6.1 La anatomía de las hiperinflaciones

Cagan (1956) definió operacionalmente la hiperinflación como inflación mensual superior al 50% (equivalente a ~13.000% anual). Los episodios históricos más estudiados son:

| País | Período | Inflación máxima mensual |
|---|---|---|
| Alemania | 1922–1923 | ~29.500% (noviembre 1923) |
| Hungría | 1945–1946 | ~41.900.000.000.000.000% |
| Zimbabwe | 2007–2008 | ~79.600.000.000% |
| Venezuela | 2016–2019 | ~1.700.000% anual |

Todas las hiperinflaciones tienen un denominador común: **déficits fiscales insostenibles financiados con señoreaje**. La secuencia típica es: déficit fiscal → monetización → inflación → erosión de la base tributaria real → mayor déficit → mayor monetización.

### 6.2 El fin de las hiperinflaciones: Sargent (1982)

Sargent documentó que las grandes hiperinflaciones europeas de los 20 terminaron de forma abrupta y con poco costo real — la razón de sacrificio fue sorprendentemente baja. La clave fue que las estabilizaciones eran **reformas fiscales creíbles**: el gobierno eliminó el déficit primario (reduciendo el requerimiento de señoreaje) y creó una institución monetaria independiente que comprometió no financiar déficits futuros.

La implicancia es radical: la inflación es un fenómeno fiscal tanto como monetario. Sin la reforma fiscal subyacente, ningún anuncio monetario es creíble — las expectativas de inflación no se anclan. Con la reforma fiscal, las expectativas se ajustan instantáneamente y la hiperinflación colapsa. Este resultado conecta directamente con la teoría fiscal del nivel de precios y con el debate sobre independencia de bancos centrales.

---

## 7. Síntesis: determinantes del nivel de precios en el corto y largo plazo

| Horizonte | Determinante del nivel de precios | Determinante del tipo de cambio |
|---|---|---|
| **Muy corto plazo** | Fijo (rigidez nominal) | Expectativas + paridad de intereses |
| **Corto plazo** | Demanda agregada (IS-LM) | Overshooting (Dornbusch) |
| **Mediano plazo** | Brecha de producto + expectativas (NKPC) | Ajuste hacia PPP |
| **Largo plazo** | Oferta de dinero (TQM) | Fundamentos monetarios relativos |

---

## Referencias

- Fisher, I. (1911). *The Purchasing Power of Money*. Macmillan.
- Cagan, P. (1956). *The Monetary Dynamics of Hyperinflation*. En Friedman (ed.), *Studies in the Quantity Theory of Money*.
- Sargent, T. (1982). *The End of Four Big Inflations*. En Hall (ed.), *Inflation: Causes and Effects*.
- Dornbusch, R. (1976). *Expectations and Exchange Rate Dynamics*. JPE.
- Fischer, S. (1993). *The Role of Macroeconomic Factors in Growth*. Journal of Monetary Economics.
- Friedman, M. (1969). *The Optimum Quantity of Money*. Aldine.
- Walsh, C.E. (2010). *Monetary Theory and Policy*. MIT Press. Cap. 2.
- De Gregorio, J. (2007). *Macroeconomía: Teoría y Políticas*. Caps. 14–15.
- Rogoff, K. (2002). *Dornbusch's Overshooting Model After Twenty-Five Years*. IMF Working Paper.