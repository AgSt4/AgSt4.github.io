---
title: "Política Fiscal: Gasto Público, Impuestos y Deuda"
date: 2026-03-15
draft: false
tags: ["macroeconomía", "política fiscal", "equivalencia ricardiana", "sostenibilidad fiscal", "impuestos óptimos", "EAE2210"]
description: "Restricción presupuestaria intertemporal, sostenibilidad de la deuda, equivalencia ricardiana, el problema de Ramsey e impuestos óptimos."
---

**Curso:** Macroeconomía I (EAE2210) · **Profesor:** Emilio Depetris-Chauvin  
**Referencia principal:** De Gregorio (2007) cap. 12 · Barro (1979, 1989) · Blanchard (2017) caps. 22–23

---

## 1. La restricción presupuestaria del gobierno

### 1.1 Restricción por período

El gobierno tiene tres fuentes de financiamiento para su gasto: impuestos, emisión de deuda y señoreaje. La restricción presupuestaria por período es:

$$G_t + r_t B_t = T_t + (B_{t+1} - B_t) + \Delta M_t / P_t$$

donde $G_t$ es el gasto público (excluido el pago de intereses), $r_t B_t$ son los intereses sobre la deuda $B_t$, $T_t$ son los ingresos tributarios y $\Delta M_t/P_t$ es el señoreaje. Ignorando el señoreaje por ahora:

$$B_{t+1} - B_t = G_t + r_t B_t - T_t = \text{Déficit primario} + r_t B_t$$

El **déficit primario** es $G_t - T_t$ (gasto menos recaudación, sin intereses). El déficit total o fiscal incluye además el servicio de la deuda.

### 1.2 Restricción presupuestaria intertemporal (RPI)

Iterando hacia adelante la restricción por período y aplicando la condición de no-Ponzi (el gobierno no puede financiar deuda con deuda indefinidamente):

$$B_t = \sum_{s=0}^{\infty} \frac{T_{t+s} - G_{t+s}}{(1+r)^{s+1}}$$

La deuda vigente debe ser igual al valor presente de todos los superávit primarios futuros. Esta es la **restricción presupuestaria intertemporal del gobierno**: el valor presente del gasto público debe ser igual al valor presente de los impuestos más los activos iniciales.

En términos del PIB, definiendo $b_t = B_t/Y_t$ la razón deuda/PIB:

$$b_{t+1} = \frac{1+r}{1+g} b_t + d_t$$

donde $g$ es la tasa de crecimiento del PIB y $d_t = (G_t - T_t)/Y_t$ es el déficit primario como fracción del PIB. Si $r > g$, un déficit primario nulo no es suficiente para estabilizar $b$ — se requiere superávit primario. Si $r < g$, la economía puede sostener déficits primarios moderados indefinidamente.

La condición $r$ vs. $g$ es central en la discusión contemporánea sobre sostenibilidad fiscal. Blanchard (2019) argumentó que en economías avanzadas con $r < g$ persistente, el costo fiscal de la deuda pública es menor de lo que los modelos estándar sugieren — generando un debate activo sobre los límites de la política fiscal expansiva.

---

## 2. Sostenibilidad de la deuda pública

### 2.1 ¿Cuándo es sostenible la deuda?

La deuda es **sostenible** cuando el gobierno puede cumplir su RPI sin recurrir a ajustes fiscales drásticos, default o monetización. Formalmente, la razón deuda/PIB no debe crecer explosivamente.

La dinámica de $b_t$ depende de tres variables:

$$\Delta b_t = (r - g) b_{t-1} + d_t$$

- Si $(r-g)b_{t-1} + d_t > 0$: la deuda crece.
- Si $(r-g)b_{t-1} + d_t = 0$: la deuda se estabiliza. El superávit primario requerido para estabilizar es $d^* = -(r-g)b$.
- Si $r > g$ y $b > 0$: se necesita superávit primario solo para mantener la razón deuda/PIB constante.

### 2.2 El análisis de sostenibilidad fiscal

El ejercicio estándar de sostenibilidad consiste en calcular el **superávit primario requerido** para estabilizar la deuda al nivel actual:

$$\tilde{d} = (r - g) b$$

Si el superávit primario corriente $-d_t < \tilde{d}$, existe una brecha fiscal que requiere ajuste. El Fondo Monetario Internacional y el Banco Mundial usan variantes de este marco en sus evaluaciones de artículo IV.

Las crisis de deuda soberana típicamente involucran situaciones donde los mercados perciben que la brecha fiscal es insalvable sin default o inflación — lo que eleva la tasa de interés exigida $r$, empeorando la dinámica y pudiendo generar equilibrios múltiples (crisis de confianza self-fulfilling).

### 2.3 El rol del señoreaje

El gobierno puede también monetizar deuda: el banco central compra bonos públicos creando dinero. El señoreaje es:

$$\text{Señoreaje} = \frac{\Delta M}{P} = \frac{\Delta M}{M} \cdot \frac{M}{P} = \mu \cdot m$$

donde $\mu$ es la tasa de crecimiento monetario y $m$ son los saldos reales. El señoreaje tiene un límite: más allá de cierto punto, la inflación reduce la demanda de dinero $m$ y la recaudación de señoreaje cae — la **curva de Laffer del señoreaje**. La hiperinflación emerge cuando el gobierno intenta financiar déficits crecientes con señoreaje en un contexto de demanda de dinero que colapsa.

---

## 3. Equivalencia Ricardiana

### 3.1 El argumento de Barro (1974)

La proposición de equivalencia ricardiana sostiene que los consumidores son forward-looking e internalizan la restricción presupuestaria del gobierno en sus decisiones de consumo. Esto lleva al resultado de que, para un patrón dado de gasto público, el método de financiamiento no afecta las decisiones de consumo de los agentes y por tanto no cambia la demanda agregada. 

La lógica es directa en el modelo de dos períodos. El gobierno reduce impuestos hoy en $\Delta T$ y financia la diferencia con deuda, prometiendo subir impuestos mañana en $(1+r)\Delta T$. El consumidor racional anticipa la suba futura de impuestos: su riqueza de ciclo de vida no cambia, porque el valor presente del flujo de impuestos es idéntico bajo ambos esquemas. Por tanto, no cambia su consumo — aumenta su ahorro privado exactamente en $\Delta T$ para pagar los impuestos futuros.

Cambiar de financiamiento con impuestos a financiamiento con deuda aumenta el ahorro privado exactamente en la misma cantidad que cae el ahorro público, dejando el ahorro nacional sin cambios. 

Formalmente, la RPI del gobierno garantiza que:

$$\frac{T_1}{1} + \frac{T_2}{1+r} = \frac{G_1}{1} + \frac{G_2}{1+r} + B_0(1+r)$$

Dado $G_1, G_2$ fijos, el valor presente de los impuestos está determinado. La distribución temporal (impuestos hoy vs. mañana) es irrelevante para la riqueza del consumidor.

### 3.2 Los supuestos que sostienen la equivalencia

La discusión de Barro considera cuatro objeciones teóricas principales a la equivalencia ricardiana: vidas finitas, mercados de capital imperfectos, incertidumbre sobre impuestos futuros y rentas, y los efectos distorsionadores de la tributación. 

Cada supuesto es cuestionable:

**Horizonte infinito / altruismo intergeneracional:** Barro asume que los hogares actúan como dinastías con altruismo hacia sus hijos, efectivamente infinitamente vividos. Si los agentes tienen horizonte finito y no se preocupan por las generaciones futuras, la deuda pública redistribuye carga impositiva entre generaciones — los vivos hoy se benefician y las generaciones futuras pagan. Weil (1987) muestra que con nuevas generaciones sin vínculos altruistas hacia los actuales, la equivalencia falla.

**Mercados de capital perfectos:** si los consumidores enfrentan restricciones de liquidez, una rebaja tributaria hoy (financiada con deuda) aumenta su ingreso disponible corriente y eleva el consumo — la equivalencia falla. Los hogares que quisieran endeudarse pero no pueden usan la rebaja como sustituto del crédito privado.

**Impuestos no distorsionadores:** la equivalencia asume impuestos de suma alzada. Con impuestos distorsionadores (sobre ingreso o consumo), el timing importa porque altera los precios relativos trabajo/ocio y consumo presente/futuro.

**Certeza sobre impuestos futuros:** los consumidores deben saber que la deuda hoy implica impuestos mañana. Con incertidumbre sobre quién pagará o cuándo, el efecto riqueza puede ser positivo.

### 3.3 La evidencia empírica

La evidencia es mixta y metodológicamente difícil. Los tests más directos buscan si el consumo responde a cambios en déficit fiscales controlando por gasto público. Bernheim (1987) y Carroll et al. encuentran evidencia contra la equivalencia — el consumo responde al ingreso disponible corriente más de lo predicho. Por otro lado, Barro argumenta que la equivalencia ricardiana es una aproximación de primer orden útil, y que la evidencia sobre tasas de interés, consumo, ahorro y déficits de cuenta corriente es en general consistente con el enfoque ricardiano como benchmark. 

El consenso pragmático es que la equivalencia no se cumple exactamente, pero tampoco el multiplicador keynesiano de textbook. Los multiplicadores fiscales empíricos (Ramey, 2011; Blanchard y Leigh, 2013) se estiman entre 0,5 y 1,5 dependiendo del estado del ciclo, el régimen monetario y el tipo de instrumento fiscal — lejos tanto del cero ricardiano como del multiplicador keynesiano sin crowding-out.

---

## 4. El problema de Ramsey: impuestos óptimos

### 4.1 La pregunta

El problema de Ramsey (1927) — formalizado para finanzas públicas por Diamond y Mirrlees (1971) — pregunta: dado que el gobierno debe recaudar una cantidad fija $R$ de impuestos, ¿cómo debe estructurarlos para minimizar la pérdida de bienestar (exceso de carga)?

### 4.2 La regla de Ramsey (regla de elasticidades inversas)

Con impuestos sobre bienes y mercados perfectamente competitivos, el resultado central es la **regla de elasticidades inversas**: el impuesto óptimo sobre cada bien debe ser inversamente proporcional a su elasticidad-precio de la demanda:

$$\frac{t_i}{p_i} \propto \frac{1}{|\varepsilon_i|}$$

Los bienes con demanda inelástica (necesidades básicas, medicamentos) deben gravarse más porque la distorsión que introduce el impuesto es menor — la cantidad demandada cae poco. Los bienes con demanda elástica (bienes de lujo con sustitutos cercanos) deben gravarse menos.

Una formulación equivalente es la **regla de Ramsey-Boiteux**: el impuesto óptimo reduce la demanda compensada de todos los bienes en la misma proporción. Esto garantiza que la distorsión se distribuye homogéneamente.

### 4.3 Implicancias para el impuesto al capital

Una extensión importante es la pregunta sobre el impuesto óptimo al capital. Chamley (1986) y Judd (1985) demostraron que en el modelo de Ramsey con agentes infinitamente vividos, **la tasa óptima de impuesto al capital es cero en el largo plazo**. La intuición es que un impuesto sobre el capital es equivalente a un impuesto sobre el consumo futuro, y gravar el consumo futuro más que el presente distorsiona la asignación intertemporal sin límite — la distorsión se acumula en el tiempo.

Barro argumenta que las tasas de impuesto deben suavizarse en el tiempo (*tax smoothing*), y que los impuestos deben fijarse en función del gasto público permanente antes que el corriente. La deuda pública es el instrumento clave para suavizar impuestos: debe usarse para amortiguar los déficits y superávits resultantes. 

Este resultado de Chamley-Judd fue cuestionado recientemente por Straub y Werning (2020), quienes muestran que bajo supuestos más generales sobre preferencias, el impuesto óptimo al capital puede ser positivo incluso en el largo plazo — el debate está abierto.

### 4.4 Tax smoothing (Barro, 1979)

El principio de suavización de impuestos aplica la lógica del ingreso permanente al gobierno. Ante un gasto transitoriamente alto (una guerra, una pandemia), el gobierno no debe subir los impuestos en la misma magnitud del gasto: debe endeudarse y distribuir la carga tributaria en el tiempo. Esto minimiza la distorsión acumulada porque la pérdida de eficiencia de los impuestos es convexa en la tasa — mejor dos períodos con tasa $\bar{t}$ que un período con $2\bar{t}$ y otro con 0.

La implicancia es que el déficit óptimo en recesiones no es keynesiano (estímulo de demanda) sino de suavización de impuestos: el gasto no cae con el ingreso porque los impuestos tampoco deben caer tanto como el ingreso. El estabilizador automático emerge de la suavización, no del multiplicador.

---

## 5. Efectos macroeconómicos de la política fiscal

### 5.1 El modelo neoclásico básico

En el modelo neoclásico (sin rigideces nominales), un aumento del gasto público $G$ financiado con impuestos de suma alzada tiene los siguientes efectos:

- **Efecto riqueza negativo:** los hogares son más pobres en valor presente → reducen consumo y aumentan oferta laboral.
- **Demanda de trabajo aumenta:** el gasto público eleva el producto y la demanda de trabajo.
- **El resultado neto:** el producto sube menos que $\Delta G$ (multiplicador < 1), el consumo cae, el empleo y el salario real dependen de las elasticidades.

Financiado con deuda bajo equivalencia ricardiana: mismo resultado (el consumo cae anticipando impuestos futuros). Sin equivalencia ricardiana: el efecto riqueza es menor → el consumo cae menos → el multiplicador puede ser mayor que 1.

### 5.2 El multiplicador fiscal: qué dice la evidencia

La magnitud del multiplicador fiscal es una de las preguntas más debatidas en macroeconomía aplicada. Los puntos de acuerdo son:

- El multiplicador es mayor en recesiones que en expansiones (Auerbach y Gorodnichenko, 2012).
- El multiplicador es mayor cuando la política monetaria no contrarresta el estímulo (zero lower bound).
- El multiplicador del gasto es mayor que el de rebajas tributarias para hogares de alto ingreso, y menor que el de transferencias a hogares con restricciones de liquidez.
- El tipo de gasto importa: inversión pública tiene multiplicadores mayores que gasto corriente en el largo plazo.

Blanchard y Leigh (2013) documentaron que el FMI sistematicamente subestimó los multiplicadores durante la austeridad fiscal post-2010 en Europa, generando ajustes más recesivos de lo proyectado — un caso paradigmático de las consecuencias de asumir multiplicadores bajos en contextos de ZLB.

---

## 6. Síntesis

| Pregunta | Modelo neoclásico | Keynesiano | Evidencia |
|---|---|---|---|
| ¿Importa el timing de impuestos? | No (equivalencia ricardiana) | Sí (restricciones de liquidez) | Parcialmente — depende del agente |
| ¿Cuál es el multiplicador del gasto? | < 1 (crowding out) | > 1 | 0.5–1.5 según contexto |
| ¿Impuesto óptimo al capital? | 0 en largo plazo (Chamley-Judd) | Positivo (redistribución) | Debate abierto |
| ¿Cómo manejar deuda transitoria? | Tax smoothing (endeudarse) | Estímulo fiscal | Consistentes en recesiones profundas |

---

## Referencias

- Barro, R.J. (1974). *Are Government Bonds Net Wealth?* JPE.
- Barro, R.J. (1979). *On the Determination of the Public Debt*. JPE.
- Barro, R.J. (1989). *The Ricardian Approach to Budget Deficits*. JEP.
- Ramsey, F.P. (1927). *A Contribution to the Theory of Taxation*. EJ.
- Diamond, P. & Mirrlees, J. (1971). *Optimal Taxation and Public Production*. AER.
- Chamley, C. (1986). *Optimal Taxation of Capital Income in General Equilibrium*. Econometrica.
- Blanchard, O. (2019). *Public Debt and Low Interest Rates*. AER.
- Blanchard, O. & Leigh, D. (2013). *Growth Forecast Errors and Fiscal Multipliers*. AER.
- Auerbach, A. & Gorodnichenko, Y. (2012). *Measuring the Output Responses to Fiscal Policy*. AEJ: Economic Policy.
- Straub, L. & Werning, I. (2020). *Positive Long-Run Capital Taxation: Chamley-Judd Revisited*. AER.
- De Gregorio, J. (2007). *Macroeconomía: Teoría y Políticas*. Cap. 12.