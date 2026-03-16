---
title: "Dinero: Naturaleza, Oferta y Demanda"
date: 2026-03-15
draft: false
tags: ["macroeconomía", "dinero", "demanda por dinero", "Baumol-Tobin", "señoreaje", "EAE2220"]
description: "Funciones del dinero, multiplicadores monetarios, hojas de balance, modelo de Baumol-Tobin, dinero en la función de utilidad y cash-in-advance."
---

**Curso:** Macroeconomía II (EAE2220)  
**Referencia principal:** De Gregorio (2007) caps. 13–14 · Walsh (2010) caps. 2–3 · McCallum (1989)

---

## 1. La naturaleza del dinero

### 1.1 Funciones del dinero

El dinero cumple tres funciones clásicas que lo distinguen de cualquier otro activo:

- **Medio de cambio:** facilita transacciones eliminando la necesidad de doble coincidencia de deseos del trueque. Es la función más fundamental — sin ella, el dinero no existiría.
- **Unidad de cuenta:** denominador común para expresar precios relativos. Reduce de $n(n-1)/2$ a $n-1$ el número de precios necesarios en una economía con $n$ bienes.
- **Reserva de valor:** permite trasladar poder de compra en el tiempo. Es la función más débil: cualquier activo con retorno positivo domina al dinero como reserva de valor, lo que plantea la pregunta central de por qué se demanda dinero en equilibrio.

La tensión entre la primera y la tercera función genera el problema central de la teoría monetaria: el dinero es necesario para transacciones (domina en liquidez) pero es dominado como activo (paga tasa de retorno cero o negativa en términos reales con inflación). Los modelos de demanda por dinero son distintas formalizaciones de este trade-off.

### 1.2 Medidas empíricas: los agregados monetarios

Los bancos centrales definen distintos agregados según la liquidez de los instrumentos incluidos:

| Agregado | Contenido | Liquidez |
|---|---|---|
| **M0 / Base monetaria** | Billetes + monedas + reservas bancarias en BC | Máxima |
| **M1** | M0 + depósitos a la vista | Alta |
| **M2** | M1 + depósitos de ahorro + depósitos a plazo corto | Media |
| **M3** | M2 + instrumentos del mercado monetario + otros | Baja |

La distinción importa para la política monetaria: el banco central controla directamente la base monetaria, pero el crédito y los depósitos amplían los medios de pago a través del multiplicador monetario.

---

## 2. Oferta de dinero

### 2.1 Base monetaria y creación de dinero

La **base monetaria** ($H$) es el pasivo del banco central que sirve como dinero de alto poder: billetes y monedas en circulación más reservas de los bancos comerciales depositadas en el banco central.

$$H = C + R$$

donde $C$ son los billetes y monedas en circulación y $R$ las reservas bancarias totales.

El dinero amplio ($M$) incluye además los depósitos del público:

$$M = C + D$$

donde $D$ son los depósitos bancarios.

### 2.2 El multiplicador monetario

Definiendo la razón reservas/depósitos $\rho = R/D$ (determinada por regulación y decisiones de los bancos) y la razón efectivo/depósitos $c = C/D$ (determinada por las preferencias del público):

$$M = \frac{1+c}{\rho+c} \cdot H \equiv \mu \cdot H$$

El factor $\mu = (1+c)/(\rho+c)$ es el **multiplicador monetario**. Como $\rho < 1$, se tiene $\mu > 1$: cada peso de base monetaria genera más de un peso de dinero amplio.

El multiplicador cae cuando:
- Los bancos aumentan reservas voluntarias (mayor $\rho$): ante incertidumbre, los bancos prefieren liquidez.
- El público prefiere efectivo a depósitos (mayor $c$): en crisis financieras, la preferencia por efectivo sube drásticamente.

Durante la Crisis Financiera Global de 2008-09, la Fed expandió masivamente la base monetaria pero el multiplicador colapsó porque los bancos acumularon reservas excedentes — el dinero "se quedó en el banco central". Esto ilustra que la expansión monetaria vía base no garantiza expansión del crédito.

### 2.3 Hojas de balance

**Banco Central:**

| Activos | Pasivos |
|---|---|
| Reservas internacionales | Billetes y monedas en circulación |
| Crédito interno neto al gobierno | Reservas bancarias (encaje) |
| Crédito al sistema financiero | Bonos del BC (esterilización) |
| Otros activos | Patrimonio |

**Banco Comercial:**

| Activos | Pasivos |
|---|---|
| Reservas en BC (encaje) | Depósitos a la vista |
| Préstamos | Depósitos a plazo |
| Inversiones en valores | Créditos interbancarios |
| Otros activos | Patrimonio |

La creación de dinero ocurre cuando un banco otorga un préstamo: el banco acredita la cuenta del prestatario (crea un depósito) sin reducir otros depósitos. Los depósitos son un pasivo del banco; el préstamo es un activo. El dinero se crea endógenamente con el crédito — esta es la visión post-keynesiana que complementa la visión exógena del multiplicador.

### 2.4 Señoreaje

El banco central obtiene ingresos de señoreaje al emitir dinero que no paga intereses pero que el público demanda. El señoreaje real es:

$$\sigma = \frac{\dot{M}}{P} = \mu \cdot m$$

donde $\mu = \dot{M}/M$ es la tasa de crecimiento monetario y $m = M/P$ son los saldos reales. A largo plazo, $\mu = \pi$ (la inflación iguala el crecimiento monetario en exceso del crecimiento real). El señoreaje es equivalente a un **impuesto inflación**: los tenedores de dinero pierden poder de compra a tasa $\pi$ sobre sus saldos reales.

La curva de Laffer del señoreaje tiene forma de joroba: más inflación inicialmente aumenta los ingresos del gobierno, pero más allá de cierto punto destruye la base imponible (los saldos reales $m$ caen más que proporcionalmente). Las hiperinflaciones ocurren cuando el gobierno intenta financiar déficits crecientes en la zona descendente de esta curva.

---

## 3. Demanda por dinero

### 3.1 El enfoque de Keynes: tres motivos

Keynes identificó tres motivos para demandar dinero:

- **Motivo transacciones:** necesidad de efectivo para cubrir gastos corrientes entre recepciones de ingreso.
- **Motivo precaución:** buffer ante gastos inesperados o emergencias.
- **Motivo especulación:** el dinero como activo de bajo riesgo en una cartera, cuya demanda sube cuando se esperan caídas en el precio de los bonos (alzas de tasas).

La función de demanda keynesiana agrega estos motivos:

$$L = L(Y, i), \quad L_Y > 0, \quad L_i < 0$$

Esta es la curva LM en forma reducida. El modelo de Baumol-Tobin provee las microfundaciones del motivo transacciones; el modelo de portafolio de Tobin provee las del motivo especulación.

### 3.2 El modelo de Baumol-Tobin (1952/1956)

#### Estructura del modelo

El modelo de Baumol-Tobin formaliza la demanda transaccional de dinero a partir del trade-off entre la liquidez provista por mantener dinero (la capacidad de realizar transacciones) y el interés sacrificado por mantener activos en forma de dinero que no paga intereses. 

El agente recibe ingreso nominal $PY$ al inicio del período y lo gasta a tasa constante a lo largo del período. Tiene la opción de mantener todo en efectivo (sin retorno) o depositar parte en bonos que pagan tasa nominal $i$ y retirar en $n$ visitas al banco, cada una con costo fijo $P\delta$ (costo de transacción en términos reales $\delta$).

Si el agente retira $Z = PY/n$ en cada visita, su saldo promedio de efectivo es $Z/2 = PY/(2n)$. El costo de oportunidad de mantener ese efectivo es $i \cdot PY/(2n)$ y el costo de transacción total es $n \cdot P\delta$. 

El costo total es:

$$CT = i \cdot \frac{PY}{2n} + n \cdot P\delta$$

Minimizando respecto a $n$:

$$\frac{\partial CT}{\partial n} = -\frac{iPY}{2n^2} + P\delta = 0 \implies n^* = \sqrt{\frac{iY}{2\delta}}$$

El saldo promedio óptimo de dinero (demanda por dinero real) es:

$$m^d = \frac{M^d}{P} = \frac{Y}{2n^*} = \frac{1}{2}\sqrt{\frac{2\delta Y}{i}} = \sqrt{\frac{\delta Y}{2i}}$$

Esta es la **fórmula de la raíz cuadrada** de Baumol-Tobin. Sus propiedades:

- **Elasticidad ingreso = 1/2:** la demanda por dinero crece menos que proporcionalmente con el ingreso — hay economías de escala en la gestión de efectivo.
- **Elasticidad tasa de interés = -1/2:** la demanda por dinero cae con la tasa nominal, pero de forma inelástica.
- **El costo de transacción $\delta$ eleva la demanda:** mayor fricción de acceso al sistema financiero → más conviene mantener efectivo.

La elasticidad ingreso de 1/2 y la elasticidad de tasa de interés de -1/2 son los resultados canónicos del modelo, fundamentales para calibrar la curva LM. 

#### Limitaciones

El modelo de Baumol-Tobin provee una explicación microeconómica para la forma de la función de demanda por dinero, pero es generalmente demasiado estilizado para incluirse en modelos macroeconómicos modernos, en particular los modelos DSGE.  La razón es que trata el ingreso como determinístico y los costos de transacción como fijos — supuestos que no sobreviven a la extensión a ambientes estocásticos y de equilibrio general.

### 3.3 Modelos de equilibrio general: MIU y CIA

Para integrar la demanda de dinero en modelos de equilibrio general, se usan dos enfoques reducidos:

#### Dinero en la función de utilidad (MIU — Sidrauski, 1967)

En el modelo MIU, el dinero entra directamente en la función de utilidad de los agentes, capturando los 'servicios de liquidez' provistos por el dinero.  La función de utilidad es:

$$U = \sum_{t=0}^{\infty} \beta^t u(C_t, m_t)$$

donde $m_t = M_t/P_t$ son los saldos reales y $u_{m} > 0$: más dinero aumenta la utilidad (reduce el tiempo de búsqueda, facilita transacciones).

La condición de óptimo para los saldos reales iguala la utilidad marginal del dinero al costo de oportunidad:

$$\frac{u_m(C,m)}{u_C(C,m)} = \frac{i}{1+i}$$

La demanda por dinero depende negativamente de la tasa nominal $i$ (el costo de oportunidad de mantener dinero en vez de bonos) y positivamente del consumo $C$. El resultado es una demanda por dinero de la forma:

$$m = L(C, i), \quad L_C > 0, \quad L_i < 0$$

La **regla de Friedman** emerge como óptimo de política: si $i = 0$ (tasa nominal cero, equivalente a deflación a la tasa de descuento real), la utilidad marginal del dinero iguala su costo de oportunidad nulo — los agentes están saciados de liquidez y la economía alcanza el óptimo de Pareto respecto a la provisión de dinero.

#### Cash-in-advance (CIA — Clower, 1967)

En el modelo CIA, los agentes están restringidos a realizar un volumen de transacciones igual o menor que sus tenencias de dinero.  La restricción es:

$$P_t C_t \leq M_t$$

El consumo no puede exceder los saldos reales. Esta es una restricción de liquidez dura: a diferencia del MIU donde el dinero es deseable, aquí es técnicamente necesario.

La condición de optimalidad genera la misma demanda reducida $m = C$ (la restricción es activa en equilibrio), pero con implicancias distintas para los costos del bienestar de la inflación: la inflación actúa como un impuesto sobre el consumo (no solo sobre los saldos reales), lo que hace el costo de bienestar de la inflación mayor en el CIA que en el MIU.

#### Comparación de enfoques

| Modelo | Motivo para demandar dinero | Costo de bienestar de inflación | Uso |
|---|---|---|---|
| Baumol-Tobin | Costos de transacción | Moderado | Microfundamentos parciales |
| MIU | Servicios de liquidez en utilidad | Moderado | DSGE modernos |
| CIA | Restricción tecnológica estricta | Alto | Modelos con énfasis en liquidez |

---

## 4. La ecuación cuantitativa y el vínculo dinero-precios

La ecuación cuantitativa de Fisher es:

$$MV = PY$$

donde $V = PY/M$ es la **velocidad de circulación del dinero**. Tomando tasas de crecimiento:

$$\hat{M} + \hat{V} = \pi + \hat{Y}$$

Si $\hat{V} \approx 0$ (velocidad estable) y $\hat{Y}$ es exógeno en el largo plazo:

$$\pi \approx \hat{M} - \hat{Y}$$

La inflación es un fenómeno monetario en el largo plazo — la proposición central del monetarismo. La evidencia de largo plazo sobre muestras amplias de países respalda esta relación, aunque en el corto plazo la velocidad de circulación es variable y la relación se debilita.

La demanda por dinero estable es condición necesaria para que la política monetaria basada en metas de agregados funcione. La inestabilidad de la velocidad después de 1975 — documentada en la evidencia de Friedman y Schwartz y las revisiones posteriores — fue la razón principal por la que los bancos centrales abandonaron las metas de agregados monetarios y migraron hacia metas de inflación.

---

## 5. Relación con el resto del curso

Este capítulo es la base para todo lo que sigue en Macroeconomía II:

- **Curva LM:** es la condición de equilibrio en el mercado monetario $m^d(Y,i) = m^s$. La forma de $m^d$ (elástica o inelástica a $i$) determina la pendiente de LM y la potencia relativa de la política monetaria vs. fiscal.
- **Teoría cuantitativa:** nexo entre crecimiento monetario, inflación y señoreaje — base del análisis de hiperinflaciones.
- **Regla de Friedman:** el óptimo de política monetaria en modelos con dinero en utilidad o CIA.
- **Política monetaria en ZLB:** cuando $i \to 0$, la demanda por dinero se vuelve perfectamente elástica (trampa de liquidez keynesiana) y la política monetaria convencional pierde efectividad.

---

## Referencias

- Baumol, W. (1952). *The Transactions Demand for Cash: An Inventory Theoretic Approach*. QJE.
- Tobin, J. (1956). *The Interest Elasticity of the Transactions Demand for Cash*. RES.
- Sidrauski, M. (1967). *Rational Choice and Patterns of Growth in a Monetary Economy*. AER.
- Clower, R. (1967). *A Reconsideration of the Microfoundations of Monetary Theory*. Western EJ.
- Friedman, M. (1969). *The Optimum Quantity of Money*. En *The Optimum Quantity of Money and Other Essays*. Aldine.
- Walsh, C.E. (2010). *Monetary Theory and Policy*. MIT Press. Caps. 2–3.
- De Gregorio, J. (2007). *Macroeconomía: Teoría y Políticas*. Caps. 13–14.
- McCallum, B.T. (1989). *Monetary Economics: Theory and Policy*. Macmillan.