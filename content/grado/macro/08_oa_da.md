---
title: "Oferta Agregada, Demanda Agregada y Ciclos Económicos"
date: 2026-03-15
draft: false
tags: ["macroeconomía", "ciclos económicos", "curva de Phillips", "IS-LM", "rigideces nominales", "Lucas", "Calvo", "EAE2220"]
description: "Ciclos económicos, modelo de Lucas, rigideces de precios y salarios, modelos de Fischer-Taylor-Calvo, oferta y demanda agregada, curva de Phillips y ajuste macroeconómico."
---

**Curso:** Macroeconomía II (EAE2220)  
**Referencia principal:** De Gregorio (2007) caps. 16–18 · Blanchard (2017) caps. 7–10 · Romer (2012) cap. 6

---

## 1. Ciclos económicos: caracterización empírica

### 1.1 Tendencia, ciclo y brecha de producto

El producto observado $Y_t$ puede descomponerse en un componente de tendencia $Y_t^*$ (el producto potencial) y un componente cíclico:

$$\tilde{y}_t = \frac{Y_t - Y_t^*}{Y_t^*} \approx \ln Y_t - \ln Y_t^*$$

La **brecha de producto** $\tilde{y}_t$ mide la desviación del producto respecto a su nivel de pleno empleo. La brecha es positiva en expansiones (producto sobre el potencial) y negativa en recesiones. Su estimación es uno de los ejercicios más polémicos de la macroeconomía aplicada: el producto potencial no es observable y distintos métodos (filtro de Hodrick-Prescott, función de producción, modelos estructurales) arrojan estimaciones divergentes con implicancias de política muy distintas.

### 1.2 Hechos estilizados de los ciclos

Los ciclos económicos en economías modernas tienen regularidades documentadas:

- **Persistencia:** las recesiones y expansiones duran varios trimestres. El producto exhibe correlación serial positiva fuerte.
- **Covarianzas:** el consumo es procíclico y menos volátil que el producto; la inversión es procíclica y más volátil; el empleo es procíclico; los salarios reales son levemente procíclicos o acíclicos; la inflación es rezagadamente procíclica.
- **Asimetría:** las recesiones tienden a ser más abruptas y cortas que las expansiones, que son más graduales y largas.
- **El dinero es procíclico y adelantado:** los agregados monetarios tienden a crecer antes de las expansiones — debatido si es causa o efecto (Friedman y Schwartz vs. endogeneidad del dinero).

### 1.3 Ciclos clásicos y keynesianos

La literatura distingue dos conceptos de ciclo:

- **Ciclo clásico:** fluctuaciones del nivel del producto. Una recesión es una caída absoluta del PIB.
- **Ciclo keynesiano (brecha):** fluctuaciones del producto respecto al potencial. Una recesión puede ocurrir incluso con crecimiento positivo si el producto crece menos que el potencial.

La distinción importa para la política: el ciclo keynesiano justifica intervención incluso en economías que no se contraen absolutamente.

---

## 2. Teorías nuevoclásicas: el modelo de Lucas

### 2.1 La crítica al keynesianismo tradicional

Lucas (1972, 1976) atacó dos frentes del consenso keynesiano prevalente:

1. **La curva de Phillips como trade-off explotable:** la correlación negativa inflación-desempleo observada en los 60 no es una relación estructural sino un equilibrio condicionado a expectativas. Si el banco central intenta explotar el trade-off sistemáticamente, las expectativas se ajustan y el trade-off desaparece.

2. **La crítica de Lucas:** los parámetros de los modelos econométricos de ecuaciones simultáneas (estilo Klein-Goldberger) no son invariantes a cambios de política, porque los agentes ajustan sus expectativas y comportamiento ante las nuevas reglas. Los modelos deben fundarse en parámetros estructurales de preferencias y tecnologías.

### 2.2 El modelo de islas de Lucas (1972)

Lucas formaliza cómo las fricciones de **información imperfecta** pueden generar no-neutralidad monetaria a corto plazo incluso con agentes racionales.

El modelo supone productores en "islas" aisladas que observan el precio de su propio bien $p_i$ pero no el nivel general de precios $P$. Cuando observan un alza en $p_i$, no saben si se debe a:

- Un shock de demanda relativo (solo sube su bien → deben producir más).
- Un shock monetario agregado (suben todos los precios → no deben producir más).

La función de oferta de Lucas resulta:

$$Y_i = Y_i^n + b(p_i - E[P|p_i])$$

donde $E[P|p_i]$ es la expectativa del nivel de precios dado el precio observado. Agregando:

$$Y = Y^n + b(P - P^e)$$

Esta es la **curva de oferta agregada de Lucas**: el producto supera el potencial solo cuando el nivel de precios supera las expectativas. La pendiente $b$ depende de la **varianza del dinero relativa a la varianza de los shocks reales**: si la varianza monetaria es alta, los productores atribuyen más las alzas de precios a causas monetarias y responden menos → $b$ es pequeño y la OA es más vertical.

La implicancia notable es la **proposición de ineficacia de la política**: solo los shocks monetarios *no anticipados* tienen efectos reales. La política monetaria sistemática (anticipada) es completamente neutral incluso en el corto plazo.

### 2.3 La crítica empírica al modelo de Lucas

El modelo de Lucas predice que países con alta variabilidad monetaria (donde los agentes deberían ser más escépticos sobre los shocks de precios) deberían tener curvas de OA más planas. Lucas (1973) encontró soporte empírico para esta predicción. Sin embargo:

- Taylor (1980) argumentó que los contratos de salarios sobrepuestos generan inercia real que el modelo de Lucas no captura.
- La evidencia de que la política monetaria tiene efectos reales incluso cuando es anticipada (Romer y Romer, 1989) es difícil de reconciliar con el modelo.
- El supuesto de que los agentes no observan variables agregadas fácilmente disponibles (índice de precios) es cuestionable.

---

## 3. Modelos nuevokeynesanos: rigideces nominales

### 3.1 ¿Por qué las rigideces nominales importan?

Los economistas a mediados de los 90 comenzaron a introducir rigideces nominales de precios en los modelos de ciclos de negocios, dando origen a los modelos DSGE neokeynesianos. De este programa de investigación emergió la curva de Phillips neokeynesiana, que relaciona inflación actual y esperada no con la tasa de desempleo sino con una medida del costo marginal agregado. 

La intuición es simple: si los precios son rígidos en el corto plazo, los cambios en la demanda nominal se traducen en cambios en el producto real antes de ajustarse en precios. El dinero no es neutral a corto plazo.

### 3.2 El modelo de Fischer (1977) y contratos escalonados

Fischer formaliza la rigidez salarial mediante contratos de salario nominal fijados de antemano por dos períodos, con los contratos escalonados en el tiempo (la mitad se renueva cada período).

Los trabajadores del sector $i$ fijan el salario nominal en $t-1$ para el período $t$ basándose en las expectativas de precios:

$$w_{it} = E_{t-1}[P_t] + \alpha(E_{t-1}[Y_t] - Y^n)$$

El resultado es que la política monetaria **anticipada** sí tiene efectos reales en el modelo de Fischer, a diferencia del modelo de Lucas. Esto se debe al escalonamiento: cuando el banco central anuncia una expansión, los contratos ya firmados no pueden ajustarse, por lo que el salario real cae y el empleo sube.

La **crítica de Lucas** se aplica aquí solo parcialmente: los parámetros de los contratos (frecuencia de ajuste, sensibilidad a expectativas) sí son estructurales y no cambian con la política, a diferencia de los modelos de forma reducida.

### 3.3 El modelo de Calvo (1983)

Calvo introduce la forma más influyente de modelar rigideces de precios. Cada firma puede reajustar su precio en cada período con probabilidad $(1-\phi)$, independientemente de cuándo fue el último ajuste. Con probabilidad $\phi$ el precio permanece fijo.

El precio óptimo que fija una firma que puede ajustar en $t$ es el promedio ponderado de los precios que quisiera fijar en todos los períodos futuros en que el precio permanezca fijo:

$$p_t^* = (1-\beta\phi)\sum_{k=0}^{\infty}(\beta\phi)^k E_t[\hat{p}_{t+k}^*]$$

donde $\hat{p}^*$ es el precio óptimo flexible. El nivel de precios agrega los precios de firmas que ajustaron y las que no:

$$P_t = \phi P_{t-1} + (1-\phi)p_t^*$$

Combinando estas condiciones y log-linearizando, se obtiene la **curva de Phillips neokeynesiana (NKPC)**:

$$\pi_t = \beta E_t[\pi_{t+1}] + \kappa \hat{x}_t$$

donde $\pi_t$ es la inflación, $\hat{x}_t$ es la brecha de producto (o más precisamente, el costo marginal real), y:

$$\kappa = \frac{(1-\phi)(1-\beta\phi)}{\phi}$$

El parámetro $\kappa$ es la pendiente de la NKPC: cuánto responde la inflación a la brecha. Cuando $\phi \to 1$ (precios casi completamente rígidos), $\kappa \to 0$ y la inflación no responde al producto. Cuando $\phi \to 0$ (precios completamente flexibles), $\kappa \to \infty$ y la curva de Phillips es vertical.

El supuesto de Calvo es fundamentalmente un truco de agregación: con ajuste de Calvo, el nivel de precios agregado es una combinación convexa del precio óptimo de reset y el nivel de precios rezagado. Cuanto mayor es $\phi$, más lentamente se mueve el nivel de precios agregado. 

La NKPC tiene dos propiedades centrales que la distinguen de la curva de Phillips tradicional:

1. **Forward-looking:** la inflación depende de la inflación *esperada futura*, no de la rezagada. La credibilidad de la política monetaria importa directamente.
2. **Función del costo marginal:** la variable de presión de demanda es el costo marginal real (aproximado por la brecha de producto), no el desempleo.

### 3.4 Taylor vs. Calvo

Taylor (1979, 1980) propone contratos de duración fija (todos duran $N$ períodos) en lugar de la duración aleatoria de Calvo. El modelo de menu costs es numéricamente casi idéntico a la NKPC de Calvo para una parametrización apropiada del parámetro de pendiente $\kappa$.  La diferencia práctica entre Calvo y Taylor es menor de lo que sugiere la diferencia en supuestos: ambos generan inercia inflacionaria y no-neutralidad monetaria de horizonte similar.

---

## 4. Oferta y demanda agregada: el modelo OA-DA

### 4.1 La demanda agregada

La curva de demanda agregada (DA) se deriva del modelo IS-LM. Un aumento en el nivel de precios $P$ reduce los saldos reales $M/P$ → sube la tasa de interés → cae la inversión y el consumo → cae el producto. La DA es negativamente inclinada en el espacio $(Y, P)$.

Desplazamientos de la DA:
- **Hacia la derecha:** expansión fiscal ($\uparrow G$ o $\downarrow T$), expansión monetaria ($\uparrow M$), mayor optimismo privado.
- **Hacia la izquierda:** contracción fiscal o monetaria, caída en confianza.

El modelo dinámico moderno reformula la DA en el espacio $(Y, \pi)$: cuando el banco central observa mayor inflación, sube su tasa de política suficientemente para elevar la tasa de interés real, reduciendo la demanda agregada. La DA dinámica tiene pendiente negativa en el espacio inflación-producto. 

### 4.2 La oferta agregada de corto plazo (OACP)

Con rigideces nominales, la OACP es positivamente inclinada: un nivel de precios mayor que el esperado reduce el salario real (dado que los salarios nominales son rígidos) → aumenta la demanda de trabajo → sube el producto.

La especificación estándar es:

$$Y = Y^n + \alpha(P - P^e), \quad \alpha > 0$$

Esta es la oferta agregada de Lucas/Friedman-Phelps. En el corto plazo, $P^e$ está dado por las expectativas formadas el período anterior. En el largo plazo, $P^e = P$ y la OALP es vertical en $Y^n$.

Con la NKPC, la OACP en términos inflación-producto es:

$$\pi_t = \pi_t^e + \kappa(Y_t - Y_t^n)$$

La pendiente $\kappa$ refleja cuán rígidos son los precios: más rigidez → OACP más plana → shocks de demanda tienen más efecto sobre el producto y menos sobre la inflación.

### 4.3 La oferta agregada de largo plazo (OALP)

En el largo plazo, todas las rigideces se disuelven: los precios y salarios se ajustan completamente, las expectativas son correctas en promedio, y el producto converge al nivel natural $Y^n$ determinado por la tecnología y los factores. La OALP es vertical.

La distinción corto/largo plazo no es temporal sino conceptual: el "corto plazo" es el horizonte en que las rigideces nominales son vinculantes; el "largo plazo" es el horizonte en que se han disuelto.

### 4.4 Equilibrio de corto y largo plazo

**Equilibrio de corto plazo:** intersección de DA y OACP. Determina $(Y_{CP}, P_{CP})$ con $Y_{CP} \neq Y^n$ posible.

**Ajuste hacia el largo plazo:** si $Y_{CP} > Y^n$ (brecha positiva), los salarios y precios suben → OACP se desplaza hacia arriba → el producto cae hacia $Y^n$. El proceso opera a través de la revisión de expectativas de inflación.

**Equilibrio de largo plazo:** intersección de DA y OALP. $Y = Y^n$, la inflación es determinada solo por la política monetaria.
 
---

## 5. La curva de Phillips: historia e interpretaciones

### 5.1 La curva original (Phillips, 1958)

Phillips documentó en 1958 una relación empírica negativa entre inflación salarial y desempleo en el Reino Unido entre 1861 y 1957. La relación fue rápidamente generalizada a inflación de precios y usada como menú de política: los gobiernos podían "comprar" menos desempleo a costa de más inflación. 

### 5.2 La curva de Phillips aumentada por expectativas (Phelps-Friedman, 1968)

Phelps y Friedman, independientemente, argumentaron que la curva de Phillips original confunde efectos nominales y reales. La relación relevante no es entre inflación y desempleo sino entre **inflación sorpresa** y desempleo. La curva aumentada por expectativas es:

$$\pi_t = \pi_t^e + \lambda(u^* - u_t) + \varepsilon_t$$

donde $u^*$ es la tasa natural de desempleo. En el largo plazo $\pi_t = \pi_t^e$, lo que implica $u_t = u^*$: **no existe trade-off inflación-desempleo en el largo plazo**. La curva de Phillips de largo plazo es vertical en $u^*$.

La implicancia de política fue devastadora para el consenso keynesiano: no hay nivel de inflación que pueda mantener permanentemente el desempleo bajo la tasa natural. Los intentos de explotar el trade-off solo generan inflación creciente (aceleración inflacionaria) — predicción confirmada por la estanflación de los 70.

### 5.3 La NKPC y el debate sobre su pendiente

La curva de Phillips neokeynesiana reemplaza el desempleo por la brecha de producto y las expectativas adaptativas por expectativas racionales forward-looking:

$$\pi_t = \beta E_t[\pi_{t+1}] + \kappa \hat{x}_t$$

Un debate empírico importante es la **pendiente de la curva de Phillips**. La evidencia post-2000 sugiere que la curva se ha aplanado: la inflación responde menos a la brecha de producto que en décadas anteriores. Las hipótesis son:

- **Mayor credibilidad de los bancos centrales:** expectativas de inflación bien ancladas reducen la inercia inflacionaria.
- **Globalización:** la competencia de importaciones limita el poder de fijación de precios doméstico.
- **Mayor concentración de mercados:** una entrada más costosa reduce el número de firmas, eleva el markup y reduce la tasa de pass-through, aplanando la pendiente de la NKPC. 
- **Cambios en la frecuencia de ajuste de precios:** la digitalización puede haber aumentado la frecuencia de ajuste, alterando $\kappa$.

La "inflación faltante" durante la Gran Recesión (la inflación no cayó tanto como la brecha de producto predecía) y la "desinflación faltante" son los dos episodios empíricos que más tensionan la NKPC estándar. 

---

## 6. Desempleo, inflación y ajuste macroeconómico

### 6.1 La Ley de Okun

La Ley de Okun provee el puente empírico entre la brecha de producto y el desempleo:

$$u_t - u^* \approx -\frac{1}{2}\tilde{y}_t$$

Por cada 2 puntos porcentuales de brecha negativa de producto, el desempleo sube aproximadamente 1 punto porcentual. El coeficiente de Okun varía entre países y en el tiempo — es una regularidad empírica, no una ley teórica.

### 6.2 Dinámica de ajuste

Considerando una economía inicialmente en equilibrio que sufre un shock de demanda positivo (expansión monetaria no anticipada):

1. **Corto plazo:** DA se desplaza a la derecha → producto sube sobre el potencial ($\tilde{y} > 0$) → inflación sube moderadamente (dependiendo de la pendiente de la OACP).
2. **Ajuste:** la brecha positiva presiona los salarios al alza → costos suben → OACP se desplaza hacia arriba.
3. **Largo plazo:** el producto regresa a $Y^n$, pero a un nivel de precios más alto. La inflación vuelve a la meta si la política monetaria es creíble.

La velocidad de este ajuste depende de:
- La **pendiente de la OACP** (rigidez de precios).
- La **credibilidad del banco central** (si el BC es creíble, las expectativas de inflación se anclan y el ajuste es más rápido y menos costoso en producto).
- La **frecuencia de revisión de contratos** (modelos de Fischer/Taylor/Calvo).

### 6.3 El costo de desinflación: la razón de sacrificio

Reducir la inflación requiere generar una brecha negativa de producto — una recesión. La **razón de sacrificio** mide cuántos puntos porcentuales de producto (o desempleo acumulado) se necesitan por cada punto porcentual de reducción de inflación.

Con expectativas racionales y perfecta credibilidad, la razón de sacrificio podría ser cero: si el banco central anuncia creíblemente una inflación más baja, las expectativas se ajustan inmediatamente y no se necesita recesión. En la práctica, la credibilidad es imperfecta y las rigideces de contratos impiden el ajuste instantáneo. Las estimaciones empíricas para distintos países dan razones de sacrificio entre 1 y 5 — la desinflación siempre tiene costos reales, aunque menores cuando la política es creíble y la transición es gradual.

---

## 7. Síntesis: neoclásicos vs. neokeynesianos

| Dimensión | Neolásico (Lucas) | Neokeynesiano (Calvo) |
|---|---|---|
| Fuente de no-neutralidad | Información imperfecta | Rigideces nominales |
| Efectividad de política anticipada | Nula | Positiva en corto plazo |
| Curva de Phillips | Expectativas racionales, pendiente determinada por varianza monetaria | NKPC forward-looking, pendiente $\kappa$ |
| Ajuste de expectativas | Instantáneo (racionales) | Gradual (contratos) |
| Política óptima | Reglas fijas, varianza monetaria mínima | Metas de inflación, estabilización de brecha |
| Fallo empírico principal | No captura inercia real con política anticipada | Inflación faltante, pendiente variable |

---

## Referencias

- Lucas, R.E. (1972). *Expectations and the Neutrality of Money*. JET.
- Lucas, R.E. (1973). *Some International Evidence on Output-Inflation Trade-offs*. AER.
- Lucas, R.E. (1976). *Econometric Policy Evaluation: A Critique*. Carnegie-Rochester Conference.
- Phelps, E. (1968). *Money Wage Dynamics and Labor Market Equilibrium*. JPE.
- Friedman, M. (1968). *The Role of Monetary Policy*. AER.
- Fischer, S. (1977). *Long-Term Contracts, Rational Expectations, and the Optimal Money Supply Rule*. JPE.
- Taylor, J.B. (1979). *Staggered Wage Setting in a Macro Model*. AER.
- Calvo, G. (1983). *Staggered Prices in a Utility-Maximizing Framework*. JME.
- Clarida, R., Galí, J. & Gertler, M. (1999). *The Science of Monetary Policy*. JEL.
- Blanchard, O. (2017). *Macroeconomics*. 7ma ed. Caps. 7–10.
- De Gregorio, J. (2007). *Macroeconomía: Teoría y Políticas*. Caps. 16–18.
- Romer, D. (2012). *Advanced Macroeconomics*. 4ta ed. Cap. 6.