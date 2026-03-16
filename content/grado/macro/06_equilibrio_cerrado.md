---
title: "Equilibrio Macroeconómico en una Economía Cerrada"
date: 2026-03-15
draft: false
tags: ["macroeconomía", "equilibrio", "ahorro", "inversión", "tasa de interés real", "EAE2210"]
description: "Equilibrio en el mercado de bienes, igualación ahorro-inversión y determinación de la tasa de interés real en una economía cerrada sin dinero."
---

**Curso:** Macroeconomía I (EAE2210) · **Profesor:** Emilio Depetris-Chauvin  
**Referencia principal:** De Gregorio (2007) caps. 2–3 · Barro (1997) caps. 3–4

---

## 1. El marco: una economía sin dinero

Este capítulo analiza el equilibrio macroeconómico en su versión más limpia: una economía cerrada, sin dinero y sin rigideces nominales. El objetivo es entender cómo se determinan simultáneamente el nivel de producción, el consumo, la inversión y la tasa de interés **real** en el largo plazo, antes de introducir la economía monetaria.

La ausencia de dinero no es un supuesto trivial: implica que los precios relativos son los únicos precios relevantes y que la tasa de interés que vacía el mercado es puramente real — no hay ilusión monetaria ni fricciones nominales que distorsionen las señales de precios.

---

## 2. La identidad ahorro-inversión

### 2.1 La contabilidad nacional como punto de partida

En una economía cerrada sin gobierno, la identidad del PIB por el lado del gasto es:

$$Y = C + I$$

El ahorro privado se define como el ingreso no consumido:

$$S \equiv Y - C = I$$

La identidad $S = I$ no es un resultado de equilibrio sino una **identidad contable**: ex post, el ahorro siempre iguala la inversión. Lo que la teoría debe explicar es el mecanismo por el cual esta identidad se sostiene ex ante — es decir, cómo las decisiones descentralizadas de ahorrantes e inversores se coordinan.

### 2.2 Con gobierno

Incorporando al gobierno con gasto $G$ e impuestos $T$:

$$Y = C + I + G$$

El ahorro nacional es la suma del ahorro privado y el ahorro público:

$$S_N = \underbrace{(Y - T - C)}_{S_{\text{privado}}} + \underbrace{(T - G)}_{S_{\text{público}}} = I$$

Un déficit fiscal $(T < G)$ reduce el ahorro público. Si el ahorro privado no lo compensa completamente (falla la equivalencia ricardiana), el ahorro nacional cae — y con él la inversión. Este es el canal de **crowding out** de la política fiscal sobre la inversión privada.

---

## 3. El mercado de fondos prestables

### 3.1 Oferta y demanda de ahorro

El equilibrio macroeconómico puede representarse como un mercado de **fondos prestables**, donde:

- **La oferta es el ahorro nacional:** depende positivamente de la tasa de interés real $r$. Una $r$ mayor hace más atractivo posponer consumo → más ahorro. La pendiente positiva es el efecto sustitución intertemporal.

- **La demanda es la inversión:** depende negativamente de $r$. Un $r$ mayor eleva el costo de uso del capital → reduce el stock de capital deseado $K^*$ → reduce la inversión. La curva de demanda de inversión es la productividad marginal del capital como función del stock.

El equilibrio determina $(r^*, I^* = S^*)$ simultáneamente.

### 3.2 La condición de equilibrio

Formalmente, el equilibrio requiere que el mercado de bienes vacíe:

$$Y = C(r, W) + I(r) + G$$

donde $C$ depende de la tasa de interés (efecto sustitución) y la riqueza $W$ (efecto ingreso), e $I$ depende negativamente de $r$. Dado $Y$ determinado por el lado de la oferta (función de producción con factores plenos), $r$ se ajusta para vaciar el mercado.

---

## 4. Determinación de la tasa de interés real

### 4.1 El equilibrio en el modelo de dos períodos

La forma más transparente de derivar la tasa de interés de equilibrio es el modelo de dotación de dos períodos con un agente representativo.

El consumidor maximiza:

$$U = u(C_1) + \frac{1}{1+\rho}u(C_2)$$

sujeto a la RPI: $C_1 + \frac{C_2}{1+r} = Y_1 + \frac{Y_2}{1+r}$

La condición de primer orden es la ecuación de Euler:

$$u'(C_1) = \frac{1+r}{1+\rho}u'(C_2)$$

El equilibrio de mercado de bienes requiere $C_t = Y_t$ en cada período (economía de dotación sin inversión). Sustituyendo:

$$u'(Y_1) = \frac{1+r^*}{1+\rho}u'(Y_2)$$

Despejando la tasa de interés de equilibrio:

$$1 + r^* = (1+\rho)\frac{u'(Y_1)}{u'(Y_2)}$$

Con utilidad CRRA $u(C) = C^{1-\sigma}/(1-\sigma)$:

$$1 + r^* = (1+\rho)\left(\frac{Y_2}{Y_1}\right)^{\sigma}$$

Este es el resultado central: **la tasa de interés real de equilibrio depende de la impaciencia $\rho$, el crecimiento del ingreso $(Y_2/Y_1)$ y la elasticidad de sustitución intertemporal $1/\sigma$**.

### 4.2 Interpretación de los determinantes

**Tasa de preferencia por el presente $\rho$:** un agente más impaciente exige mayor retorno para posponer consumo → $r^*$ sube con $\rho$.

**Crecimiento del ingreso $(Y_2/Y_1)$:** si el ingreso futuro es mayor que el presente, el agente quiere traer consumo al presente (endeudarse) → exceso de demanda de consumo presente → $r^*$ sube. Economías de alto crecimiento tienden a tener tasas reales más altas.

**Elasticidad de sustitución intertemporal $1/\sigma$:** determina cuánto responde el consumidor a los incentivos de la tasa de interés. Un $\sigma$ alto (baja EIS) significa que el consumidor suaviza mucho y la tasa de interés debe moverse bastante para equilibrar el mercado.

### 4.3 Con inversión: la ecuación de Fisher

Incorporando inversión al modelo, el equilibrio requiere que la productividad marginal del capital iguale la tasa de interés real más la depreciación:

$$F_K(K^*) = r^* + \delta$$

Esto es la **condición de eficiencia de la acumulación de capital** — la misma que el modelo de Solow en estado estacionario. La tasa de interés real de equilibrio es la productividad marginal del capital neta de depreciación.

En el estado estacionario del modelo de Ramsey (con optimización intertemporal y crecimiento):

$$r^* = \rho + \sigma g$$

donde $g$ es la tasa de crecimiento del consumo en estado estacionario. Esta es la **ecuación de Fisher modificada** o regla de Keynes-Ramsey: la tasa de interés real de equilibrio iguala la tasa de descuento más la compensación por el crecimiento del consumo ponderada por la curvatura de la utilidad.

---

## 5. Estática comparativa

### 5.1 Aumento en el gasto público transitorio

Un aumento transitorio en $G$ (financiado con impuestos, para mantener la RPI del gobierno):

- Reduce la riqueza de los hogares en el mismo monto → caída en el consumo privado.
- El ahorro nacional cae (mayor $G$, caída menos que proporcional en $C$).
- Exceso de demanda de bienes → $r^*$ sube para restablecer el equilibrio.
- El alza en $r^*$ reduce la inversión: **crowding out financiero**.

El resultado es que el producto no cambia (está determinado por la oferta), pero su composición cambia: más $G$, menos $C$ e $I$.

### 5.2 Aumento en el gasto público permanente

Un aumento permanente en $G$ reduce la riqueza permanente de los hogares más que uno transitorio. La caída en consumo es mayor. El efecto sobre $r^*$ depende del tamaño relativo de la caída en $S$ privado vs. el aumento en $G$:

- Si la equivalencia ricardiana se cumple exactamente: el ahorro privado cae en la misma magnitud que sube $G$ → $r^*$ no cambia y la inversión tampoco.
- Si la equivalencia falla parcialmente: $r^*$ sube y hay crowding out.

### 5.3 Mejora tecnológica (aumento en $A$)

Un aumento en la productividad total $A$ eleva la productividad marginal del capital → la demanda de inversión se desplaza hacia afuera. Para equilibrar:

- $r^*$ sube.
- La inversión sube (el efecto demanda domina).
- El consumo puede subir o bajar según el efecto riqueza (producción futura mayor) vs. el efecto sustitución (mayor $r^*$).

Con calibraciones estándar, el efecto riqueza domina y el consumo sube. Este resultado es central para entender los ciclos económicos en los modelos RBC: shocks tecnológicos positivos generan simultáneamente mayor producto, consumo, inversión y tasa de interés real.

### 5.4 Aumento en la tasa de ahorro / caída en $\rho$

Si los hogares se vuelven más pacientes (cae $\rho$):

- La oferta de ahorro se desplaza hacia la derecha.
- $r^*$ cae.
- La inversión sube → mayor acumulación de capital.
- En el largo plazo, el stock de capital y el producto per cápita son mayores.

Este es el mecanismo de Solow en el modelo con agentes optimizadores: más paciencia → más capital → más producto.

---

## 6. El tipo de interés real y la frontera de posibilidades de producción intertemporal

Una forma alternativa e intuitiva de visualizar el equilibrio es la **frontera de posibilidades de producción intertemporal (FPP intertemporal)**:

La economía puede sacrificar consumo presente para invertir y producir más en el futuro. La FPP intertemporal mapea las combinaciones $(C_1, C_2)$ alcanzables dado $Y_1$, la tecnología de inversión y la función de producción.

La pendiente de la FPP es $-(1 + PMK)$: por cada unidad sacrificada hoy, la economía obtiene $1 + PMK$ unidades mañana. El equilibrio ocurre donde la tasa marginal de sustitución intertemporal del consumidor iguala la tasa marginal de transformación intertemporal de la economía:

$$\frac{u'(C_1)}{u'(C_2)/(1+\rho)} = 1 + PMK = 1 + r^*$$

El mercado de capitales descentralizado implementa este óptimo: la tasa de interés real actúa como precio relativo intertemporal que coordina las decisiones de ahorrantes e inversores.

---

## 7. Relación con el resto del curso

Este capítulo es el núcleo del análisis de la economía real. Sus resultados se usarán repetidamente:

- **Crecimiento económico:** el estado estacionario de Solow-Ramsey satisface exactamente la condición $r^* = \rho + \sigma g$.
- **Consumo e inversión:** los modelos de consumo óptimo e inversión óptima son los bloques que oferta y demanda de fondos prestables.
- **Política fiscal:** los efectos de $G$ y $T$ sobre $r^*$ e $I$ son el crowding out financiero que limita el multiplicador fiscal en el modelo neoclásico.
- **Macroeconomía II:** cuando se introduce dinero, la tasa nominal $i = r^* + \pi^e$ (ecuación de Fisher), y la política monetaria afecta $r$ en el corto plazo pero no en el largo plazo donde se vuelve al equilibrio real.

---

## Referencias

- Barro, R. (1997). *Macroeconomía: Teoría y Política*. Caps. 3–4.
- De Gregorio, J. (2007). *Macroeconomía: Teoría y Políticas*. Caps. 2–3.
- Blanchard, O. (2017). *Macroeconomics*. 7ma ed. Cap. 3.
- Romer, D. (2012). *Advanced Macroeconomics*. 4ta ed. Cap. 2.
- Ramsey, F.P. (1928). *A Mathematical Theory of Saving*. EJ.