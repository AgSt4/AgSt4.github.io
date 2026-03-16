---
title: "Dinero, Tipo de Cambio, Tasa de Interés y Precios"
date: 2026-03-15
draft: false
tags: ["macroeconomía internacional", "tipo de cambio", "paridad de intereses", "Mundell-Fleming", "Dornbusch", "regímenes cambiarios", "EAE3210"]
description: "Enfoque de activos del tipo de cambio, paridades de interés y poder de compra, modelo monetario, Mundell-Fleming, overshooting de Dornbusch y regímenes cambiarios."
---

**Curso:** Macroeconomía Internacional (EAE3210) — Posgrado  
**Referencia principal:** Krugman, Melitz & Obstfeld (2015) caps. 13–15 · Schmitt-Grohé, Uribe & Woodford (2022) · Obstfeld & Rogoff (1996) cap. 8 · Dornbusch (1976)

---

## 1. El mercado de divisas: enfoque de activos

### 1.1 El tipo de cambio como precio de activo

El enfoque moderno del tipo de cambio lo trata como el precio relativo de dos activos monetarios — no simplemente como el precio que equilibra el flujo de exportaciones e importaciones. Esta perspectiva tiene implicancias fundamentales: los tipos de cambio se mueven con las expectativas sobre el futuro, no solo con los flujos corrientes, y su volatilidad es comparable a la de otras variables financieras.

La tasa de retorno de un depósito doméstico en términos de moneda doméstica es simplemente la tasa de interés nominal $i$. La tasa de retorno esperada de un depósito externo en términos de moneda doméstica tiene dos componentes: la tasa de interés externa $i^*$ más la depreciación esperada de la moneda doméstica $E_t[\hat{E}_{t+1}]$:

$$R^* = i^* + E_t\left[\frac{E_{t+1} - E_t}{E_t}\right]$$

donde $E_t$ es el tipo de cambio nominal (unidades de moneda doméstica por moneda extranjera). Un aumento en $E$ es una depreciación.

### 1.2 Paridad cubierta de tasas de interés (CIP)

La paridad cubierta (CIP) establece que la diferencia entre la tasa de interés doméstica y la externa iguala el premio forward:

$$i - i^* = \frac{F_t - E_t}{E_t}$$

donde $F_t$ es el tipo de cambio forward a un período. La CIP es una condición de no-arbitraje puro que no requiere supuestos sobre expectativas — solo que los mercados forward existan y funcionen. Tiene soporte empírico muy sólido en condiciones normales de mercado. Su violación durante la Crisis Financiera Global de 2008-09 fue una medida directa de las fricciones de liquidez y riesgo de contraparte en los mercados interbancarios internacionales.

### 1.3 Paridad descubierta de tasas de interés (UIP)

La paridad descubierta (UIP) reemplaza el tipo de cambio forward por la expectativa del tipo de cambio futuro:

$$i = i^* + E_t\left[\frac{E_{t+1} - E_t}{E_t}\right]$$

o aproximadamente en logaritmos:

$$i_t - i_t^* = E_t[e_{t+1}] - e_t \equiv E_t[\Delta e_{t+1}]$$

donde $e = \ln E$. La UIP es la condición de equilibrio en el mercado de activos externos: los inversores son indiferentes entre activos domésticos y externos cuando los retornos esperados se igualan. Es el bloque central de todos los modelos de tipo de cambio con perfecta movilidad de capital.

**La evidencia empírica sobre la UIP es problemática.** La UIP requiere perfecta competencia en bienes transables, mercados financieros profundos y libre movilidad de capital. Las condiciones limitan los casos que pueden usarse para examinar su validez.  Las regresiones estándar de Fama (1984) encuentran que el coeficiente sobre el diferencial de tasas predice el signo *opuesto* al que predice la UIP para horizontes cortos — el **puzzle de la prima forward**. Una moneda con tasa alta tiende a *apreciarse* en vez de depreciarse, lo que implica que estrategias de carry trade (endeudarse en monedas de baja tasa, invertir en monedas de alta tasa) generan retornos positivos sistemáticos inconsistentes con la UIP.

Sin embargo, hay evidencia a favor de la UIP a horizontes largos, condicional en acciones de política monetaria, para tipos de cambio dólar/euro y dólar/yen. Los movimientos de corto plazo del tipo de cambio tras sorpresas de política monetaria son consistentes con el overshooting de Dornbusch. 

### 1.4 El tipo de cambio de equilibrio bajo UIP

Usando la UIP de forma recursiva hacia adelante:

$$e_t = -\sum_{k=0}^{\infty}E_t[i_{t+k} - i_{t+k}^*] + \lim_{T\to\infty}E_t[e_{t+T}]$$

El tipo de cambio hoy es el valor presente del diferencial de tasas de interés esperado a lo largo de todo el futuro, más el valor terminal esperado. Dado que el tipo de cambio de largo plazo lo determina la PPP y el modelo monetario, los anuncios de política monetaria futura afectan el tipo de cambio presente — incluso antes de cualquier cambio en los fundamentos corrientes.

---

## 2. Tipo de cambio, precios y largo plazo

### 2.1 Paridad del poder de compra (PPP)

La **PPP absoluta** establece que bienes idénticos deben tener el mismo precio en todos los mercados cuando se expresan en la misma moneda:

$$P = EP^* \implies q \equiv \frac{EP^*}{P} = 1$$

donde $q$ es el tipo de cambio real. La **PPP relativa** es más débil: los cambios en el tipo de cambio nominal reflejan los diferenciales de inflación:

$$\hat{E} = \pi - \pi^*$$

La PPP absoluta falla sistemáticamente en el corto y mediano plazo: los precios de bienes no transables, los costos de transporte, las barreras comerciales y los efectos Balassa-Samuelson generan desviaciones persistentes. La PPP relativa tiene mejor soporte empírico como tendencia de largo plazo: el tipo de cambio real es estacionario con reversión lenta a la media, con una vida media de las desviaciones de 3-5 años.

El **efecto Balassa-Samuelson** explica por qué los países ricos tienen tipos de cambio reales apreciados sistemáticamente: la mayor productividad en el sector transable eleva los salarios en toda la economía, incluyendo el sector no transable donde la productividad no creció — elevando el nivel de precios relativo.

### 2.2 La ecuación de Fisher internacional

Combinando la UIP con la PPP relativa y la ecuación de Fisher doméstica ($i = r + \pi^e$):

$$i - i^* = \pi^e - \pi^{*e} \implies r = r^*$$

En el largo plazo con PPP y UIP, las tasas de interés reales se igualan entre países — la **paridad de Fisher internacional**. Esta es la condición de integración perfecta de mercados de capitales en términos reales: no puede haber oportunidades de arbitraje real sostenidas.

### 2.3 El modelo monetario del tipo de cambio

Combinando la condición de equilibrio monetario doméstico y externo con la PPP:

$$e_t = (m_t - m_t^*) - \phi(y_t - y_t^*) + \lambda(i_t - i_t^*)$$

Usando la ecuación de Fisher para el diferencial de tasas ($i - i^* = \pi^e - \pi^{*e}$) y la solución hacia adelante:

$$e_t = \frac{1}{1+\lambda}\sum_{j=0}^{\infty}\left(\frac{\lambda}{1+\lambda}\right)^j E_t[f_{t+j}]$$

donde $f_t = (m_t - m_t^*) - \phi(y_t - y_t^*)$ son los fundamentos monetarios relativos. El tipo de cambio actual descuenta toda la política monetaria relativa esperada. **La implicancia es que el tipo de cambio es esencialmente un activo especulativo que se mueve con noticias sobre fundamentos futuros**, no con fundamentos corrientes — lo que explica parte de su aparente volatilidad excesiva.

La evidencia empírica del modelo monetario es débil a corto plazo: Meese y Rogoff (1983) demostraron que ningún modelo estructural predice el tipo de cambio mejor que un random walk fuera de muestra, incluso a horizontes de un año. A largo plazo (5+ años), el modelo monetario recupera poder predictivo razonable.

---

## 3. El modelo de Mundell-Fleming

### 3.1 Estructura básica

El modelo de Dornbusch es una extensión dinámica del modelo Mundell-Fleming, o modelo IS-LM para economía abierta, que considera la existencia de dos mercados: el mercado de bienes y el mercado monetario. En una economía abierta hay dos condiciones de equilibrio a nivel internacional que relacionan la economía doméstica con el resto del mundo. 

El modelo Mundell-Fleming extiende el IS-LM al incorporar movilidad de capital y tipo de cambio. Sus tres bloques son:

**IS abierta:**
$$Y = C(Y-T) + I(i) + G + NX(e, Y, Y^*)$$

Las exportaciones netas dependen del tipo de cambio real (una depreciación, $e\uparrow$, mejora la competitividad y eleva $NX$), del ingreso doméstico (más ingreso → más importaciones) y del ingreso externo.

**LM:**
$$\frac{M}{P} = L(i, Y)$$

Equilibrio en el mercado monetario. Con precios rígidos en el corto plazo, $P$ está dado.

**Paridad de intereses (BP):**

Con perfecta movilidad de capital, la condición de equilibrio en el mercado de activos externos es la UIP simplificada (sin expectativas de depreciación en la versión estática):

$$i = i^*$$

Esta es la curva BP horizontal: la economía pequeña debe igualar la tasa mundial. Cualquier desviación genera flujos de capital que restauran el equilibrio.

### 3.2 Política fiscal y monetaria bajo tipo de cambio flexible

Con tipo de cambio **flexible** y perfecta movilidad de capital:

**Política monetaria: efectiva**

$M \uparrow$ → $i$ cae debajo de $i^*$ → salida de capitales → el tipo de cambio se deprecia ($E \uparrow$) → $NX$ mejora → IS se desplaza a la derecha → $Y$ sube hasta que $i = i^*$ de nuevo. La expansión monetaria opera completamente vía el tipo de cambio — el resultado de Mundell.

**Política fiscal: inefectiva (crowding out completo)**

$G \uparrow$ → IS se desplaza derecha → $i$ tiende a subir sobre $i^*$ → entrada de capitales → tipo de cambio se aprecia ($E \downarrow$) → $NX$ cae → IS se desplaza de regreso. El aumento en el gasto público es completamente desplazado por la caída en exportaciones netas. El multiplicador fiscal es cero bajo tipo de cambio flexible con perfecta movilidad de capital.

### 3.3 Política fiscal y monetaria bajo tipo de cambio fijo

Con tipo de cambio **fijo** ($E = \bar{E}$):

**Política monetaria: inefectiva**

$M \uparrow$ → $i$ cae debajo de $i^*$ → el BC debe vender reservas para defender $\bar{E}$ → $M$ cae de regreso → el efecto inicial se revierte completamente. La política monetaria pierde autonomía bajo tipo de cambio fijo con perfecta movilidad de capital.

**Política fiscal: efectiva**

$G \uparrow$ → $i$ tiende a subir → entrada de capitales → el BC compra divisas para defender $\bar{E}$ → $M$ sube endógenamente → LM se desplaza derecha → equilibrio con mayor $Y$ e $i = i^*$. El multiplicador fiscal es máximo bajo tipo de cambio fijo.

Esta es la **trinidad imposible** de Mundell: no es posible tener simultáneamente tipo de cambio fijo, perfecta movilidad de capital y política monetaria autónoma. Cualquier combinación de dos elimina la tercera.

---

## 4. El modelo de overshooting de Dornbusch (1976)

### 4.1 La pregunta

El modelo de Dornbusch es una teoría fundamental en macroeconomía internacional que describe cómo los tipos de cambio responden a perturbaciones monetarias en una economía abierta con tipo de cambio flexible. Desarrollado por Dornbusch en 1976, destaca que un aumento no anticipado en la oferta monetaria lleva a una depreciación inmediata y excesiva de la moneda doméstica — más allá de su nivel de equilibrio de largo plazo — debido al ajuste rápido de los mercados de activos relativo a la respuesta lenta de los mercados de bienes. 

### 4.2 Los tres bloques del modelo

**Mercado monetario (ajuste instantáneo):**
$$m - p = \phi y - \lambda i$$

**UIP con expectativas racionales:**
$$i = i^* + E_t[\dot{e}]$$

En el largo plazo $E_t[\dot{e}] = 0$ (el tipo de cambio está en su nivel de estado estacionario), por lo que $\bar{i} = i^*$.

**Mercado de bienes (ajuste gradual):**
$$\dot{p} = \pi(d - \bar{y}), \quad \pi > 0$$

donde la demanda agregada $d$ depende positivamente del tipo de cambio real $(e-p)$ y negativamente de la tasa de interés real.

### 4.3 El estado estacionario

En el largo plazo, los precios se ajustan completamente y se tiene PPP. Un aumento permanente de $m$ en $\Delta m$ genera:

$$\Delta \bar{p} = \Delta \bar{e} = \Delta m$$

Tanto los precios como el tipo de cambio suben proporcionalmente al dinero — neutralidad monetaria en el largo plazo.

### 4.4 La dinámica de overshooting

Ahora el ajuste de corto plazo. Ante un aumento no anticipado y permanente en $M$:

**En el mercado monetario** (instantáneo): $P$ es rígido → los saldos reales $M/P$ suben → $i$ debe caer para vaciar el mercado monetario → $i < i^*$.

**Por UIP**: $i < i^*$ implica que el mercado espera una **apreciación futura** de la moneda → el tipo de cambio debe estar *por encima* de su nivel de largo plazo hoy para que la apreciación posterior sea consistente con UIP.

**El resultado**: el tipo de cambio salta inmediatamente a $e_0 > \bar{e}$ — deprecia más allá del nuevo equilibrio de largo plazo. Luego se aprecia gradualmente mientras los precios suben y la tasa de interés retorna a $i^*$.

Formalmente, la solución del sistema da:

$$e_0 - \bar{e} = -\frac{1}{\lambda\mu}(m - \bar{m})$$

donde $\mu > 0$ es la raíz estable del sistema dinámico. El coeficiente $1/(\lambda\mu) > 1$ es el **coeficiente de overshooting**: la depreciación inicial supera la de largo plazo. Cuanto menor la elasticidad de la demanda de dinero a la tasa de interés $\lambda$ (el mercado monetario requiere un mayor caída en $i$ para ajustarse) y cuanto más lento el ajuste de precios (menor $\mu$), mayor el overshooting.

Una variable sufre overshooting si su reacción inicial a un shock es mayor que su respuesta de largo plazo. El overshooting del tipo de cambio es consecuencia directa de que los rezagos de ajuste en los mercados de bienes inducen volatilidad compensatoria en los mercados de activos. 

### 4.5 La evidencia empírica

Un shock de política monetaria contractivo tiene un efecto fuerte sobre el tipo de cambio, que se aprecia en el impacto. El efecto máximo ocurre dentro de 1-2 trimestres, y el tipo de cambio luego se deprecia gradualmente hacia la línea de base, consistente con la hipótesis de overshooting de Dornbusch. 

Sin embargo, la evidencia es sensible a la estrategia de identificación. En toda identificación razonable, los shocks de política monetaria generan grandes desviaciones de la UIP; esto implica que el overshooting no puede ser impulsado por el mecanismo de Dornbusch, y la fracción de la varianza del tipo de cambio explicada por shocks monetarios puede ser menor de lo que se encontró anteriormente. 

El consenso actual es que el overshooting existe pero su mecanismo exacto es más complejo que el modelo original, involucrando primas de riesgo variables, heterogeneidad de agentes y canales de hoja de balance.

---

## 5. Regímenes cambiarios y crisis de balanza de pagos

### 5.1 Clasificación de regímenes

Los regímenes cambiarios se ubican en un espectro entre dos extremos:

| Régimen | Descripción | Ejemplos |
|---|---|---|
| **Flotación libre** | El BC no interviene; $E$ determinado por mercado | EE.UU., eurozona, Chile (post-1999) |
| **Flotación administrada** | El BC interviene pero sin defender un nivel | La mayoría de emergentes |
| **Bandas cambiarias** | $E$ puede fluctuar dentro de un rango | Chile 1984-1999, ERM europeo |
| **Tipo de cambio fijo (peg)** | El BC defiende un nivel con reservas | Argentina 1991-2001, Hong Kong |
| **Currency board** | BC emite solo si tiene reservas que respaldan 1:1 | Bulgaria, Bosnia |
| **Dolarización / unión monetaria** | Sin moneda propia | Ecuador, eurozona |

La "trinidad imposible" de Mundell organiza la discusión: movilidad de capital perfecta + tipo de cambio fijo = sin política monetaria autónoma.

### 5.2 Modelos de crisis cambiaria de primera generación (Krugman, 1979)

El modelo de Krugman formaliza la crisis de balanza de pagos como consecuencia inevitable de una inconsistencia entre la política monetaria y el tipo de cambio fijo.

Un gobierno con déficit fiscal lo financia creando dinero a tasa $\mu > 0$. Simultáneamente, compromete defender el tipo de cambio en $\bar{E}$ usando reservas internacionales $R$. La inconsistencia: la expansión monetaria es incompatible con el tipo de cambio fijo, que requiere crecimiento monetario cero.

Con agentes racionales, el ataque especulativo ocurre *antes* de que las reservas se agoten. En el momento en que el tipo de cambio de flotación hipotético coincide con $\bar{E}$, los especuladores atacan en masa, agotan las reservas y fuerzan la devaluación. El tiempo del ataque es perfectamente predecible: las crisis de primera generación son devaluaciones anticipadas racionalmente.

### 5.3 Modelos de segunda generación (Obstfeld, 1994)

Obstfeld introduce la posibilidad de **equilibrios múltiples**: el gobierno tiene un trade-off entre los beneficios del tipo de cambio fijo (credibilidad, costos de transacción) y sus costos (pérdida de autonomía monetaria, posible recesión para defender la paridad).

El resultado clave: si los agentes creen que habrá devaluación, las tasas de interés suben (por UIP), el costo de defender la paridad sube, y el gobierno puede rendirse y devaluar — la creencia se autocumple. Si los agentes creen en la paridad, las tasas son bajas, el costo de defensa es bajo, y el gobierno la defiende — también se autocumple.

Con múltiples equilibrios, las crisis pueden ser fundamentally driven (primera generación) o self-fulfilling (segunda generación): ataques especulativos pueden ocurrir incluso con fundamentos sólidos si las expectativas coordinan en el equilibrio malo. La solución del modelo es la opacidad estratégica del banco central sobre su función de reacción — si los especuladores no saben cuándo el gobierno se rinde, el ataque es más difícil de coordinar.

### 5.4 Modelos de tercera generación: hoja de balance y contagio (1997–)

La Crisis Asiática de 1997-98 motivó una tercera generación de modelos que incorpora:

- **Descalce de monedas:** firmas y bancos con pasivos en dólares e ingresos en moneda local. Una depreciación deteriora simultáneamente los balances, contrae el crédito y profundiza la recesión.
- **Descalce de plazos:** deuda de corto plazo que financia activos de largo plazo. Una pérdida de confianza genera corridas que son eficientes ex post aunque hubieran sido ineficientes si no ocurrieran.
- **Contagio:** la crisis en un país afecta las expectativas sobre otros, vía canales comerciales, financieros o simplemente de información.

El modelo de Krugman (1999) de hoja de balance formaliza cómo una depreciación genera un espiral deflacionario: depreciación → deterioro de balances → caída del crédito → caída de la demanda → más depreciación. La política óptima bajo este canal es ambigua respecto al tipo de cambio: dejar depreciar amortigua el shock real pero daña los balances; defender el tipo de cambio protege los balances pero requiere altas tasas que también contraen la demanda.

---

## 6. Política macroeconómica bajo distintos regímenes: síntesis

| | **Tipo fijo + movilidad perfecta** | **Tipo flexible + movilidad perfecta** |
|---|---|---|
| **Política monetaria** | Inefectiva (BC pierde autonomía) | Efectiva (opera vía tipo de cambio) |
| **Política fiscal** | Efectiva (multiplicador máximo) | Inefectiva (crowding out vía TC) |
| **Absorción de shocks** | Requiere deflación interna o ajuste real | Tipo de cambio amortigua shocks |
| **Credibilidad nominal** | Alta (ancla cambiaria) | Depende de BC |
| **Vulnerabilidad a crisis** | Alta (ataques especulativos) | Baja (no hay reservas que atacar) |
| **Aplicación** | Países con alta exposición a moneda ancla | Economías con instituciones sólidas |

La elección óptima del régimen depende de las características de la economía: grado de apertura, diversificación de shocks, credibilidad institucional, grado de dolarización financiera y sincronía del ciclo económico con el país ancla. No existe régimen dominante para todos los contextos — la teoría del área monetaria óptima de Mundell es el marco analítico para evaluar estos trade-offs.

---

## Referencias

- Dornbusch, R. (1976). *Expectations and Exchange Rate Dynamics*. JPE.
- Mundell, R. (1963). *Capital Mobility and Stabilization Policy Under Fixed and Flexible Exchange Rates*. Canadian Journal of Economics.
- Fleming, J.M. (1962). *Domestic Financial Policies Under Fixed and Floating Exchange Rates*. IMF Staff Papers.
- Krugman, P. (1979). *A Model of Balance-of-Payments Crises*. JMCB.
- Obstfeld, M. (1994). *The Logic of Currency Crises*. Cahiers Économiques et Monétaires.
- Krugman, P. (1999). *Balance Sheets, the Transfer Problem, and Financial Crises*. IFDP.
- Fama, E. (1984). *Forward and Spot Exchange Rates*. JME.
- Meese, R. & Rogoff, K. (1983). *Empirical Exchange Rate Models of the Seventies*. JIE.
- Rogoff, K. (2002). *Dornbusch's Overshooting Model After Twenty-Five Years*. IMF WP 02/39.
- Obstfeld, M. & Rogoff, K. (1996). *Foundations of International Macroeconomics*. MIT Press. Cap. 8.
- Krugman, P., Melitz, M. & Obstfeld, M. (2015). *International Finance: Theory and Policy*. 10ma ed. Caps. 13–15.
- Schmitt-Grohé, S., Uribe, M. & Woodford, M. (2022). *International Macroeconomics*. Princeton University Press.