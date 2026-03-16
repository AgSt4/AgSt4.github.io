---
title: "Información Asimétrica"
date: 2026-03-15
draft: false
tags: ["microeconomía", "información asimétrica", "riesgo moral", "selección adversa", "señalización", "principal-agente", "EAE2120"]
description: "El problema principal-agente, riesgo moral con modelos discretos y continuos, selección adversa y el mercado de limones, autoselección y screening, señalización de Spence."
---

**Curso:** Microeconomía II (EAE2120)  
**Referencia principal:** Vial & Zurita — *Microeconomía* · Mas-Colell, Whinston & Green (1995) caps. 13–14 · Laffont & Martimort (2002)

---

## 1. La taxonomía de la información asimétrica

La información asimétrica emerge cuando los agentes en una transacción tienen distintos conjuntos de información relevante. El objetivo de la literatura principal-agente es analizar situaciones en que un contrato se firma bajo información asimétrica: cuando una parte conoce cosas relevantes que la otra ignora. 

La taxonomía estándar organiza los problemas según el **timing** de la asimetría:

| Problema | Timing | Información oculta | Ejemplo |
|---|---|---|---|
| **Selección adversa** | Pre-contractual | Tipo del agente | Vendedor conoce calidad del auto |
| **Riesgo moral** | Post-contractual | Acción del agente | Asegurado controla nivel de cuidado |
| **Señalización** | Pre-contractual (agente actúa) | Tipo del agente | Educación como señal de habilidad |
| **Screening** | Pre-contractual (principal actúa) | Tipo del agente | Menú de contratos para autoselección |

En teoría moderna de contratos, la "selección adversa" caracteriza modelos principal-agente en que el agente tiene información privada antes de que se firme el contrato. El "riesgo moral" caracteriza modelos donde hay información simétrica al momento de contratar — el agente puede volverse privadamente informado después. 

---

## 2. El problema del riesgo moral

### 2.1 El marco principal-agente

El **problema principal-agente** modela una relación en que:
- El **principal** (empleador, asegurador, accionista) contrata al **agente** (empleado, asegurado, gerente).
- El agente toma una acción $a$ (esfuerzo) que afecta el resultado $x$.
- El principal observa $x$ pero no $a$ directamente.
- El agente soporta la desutilidad del esfuerzo $c(a)$.

El resultado $x$ es estocástico: $x \sim F(x|a)$ con densidad $f(x|a)$. El principal diseña un contrato de pago $w(x)$ — salario contingente al output observado.

**Benchmark: primer mejor (información perfecta)**

Si el esfuerzo fuera observable y contractuable, el principal maximizaría el excedente conjunto eligiendo el esfuerzo eficiente $a^{FB}$ que maximiza $E[x|a] - c(a)$, y extraería toda la renta con un contrato de salario fijo.

### 2.2 Modelo discreto: dos acciones y dos resultados

El caso más simple ilustra la estructura esencial. El agente puede elegir esfuerzo alto $a_H$ o bajo $a_L$. El resultado puede ser $x_H$ (bueno) o $x_L$ (malo), con probabilidades $p_H > p_L$ bajo esfuerzo alto y $q_H < p_H$, $q_L > p_L$ bajo esfuerzo bajo.

El principal quiere implementar $a_H$. El contrato $\{w_H, w_L\}$ debe satisfacer:

**Restricción de participación (IR):** el agente prefiere aceptar el contrato a su reserva de utilidad $\bar{u}$:

$$p_H u(w_H) + p_L u(w_L) - c_H \geq \bar{u}$$

**Restricción de compatibilidad de incentivos (IC):** el agente prefiere $a_H$ a $a_L$:

$$p_H u(w_H) + p_L u(w_L) - c_H \geq q_H u(w_H) + q_L u(w_L) - c_L$$

Simplificando la IC:

$$(p_H - q_H)[u(w_H) - u(w_L)] \geq c_H - c_L$$

La diferencia en pagos debe ser suficiente para que el incremento en probabilidad de $x_H$ bajo esfuerzo alto compense el mayor costo. La IC requiere **dispersión salarial** — $w_H > w_L$ — para proveer incentivos.

**El trade-off fundamental:** el agente es averso al riesgo → prefiere $w_H = w_L$ (seguro completo). El principal quiere esfuerzo alto → necesita $w_H > w_L$ (incentivos). Con información perfecta puede dar seguro completo e implementar $a^{FB}$; con información imperfecta debe sacrificar seguro para generar incentivos. Esta es la **tensión entre aseguramiento e incentivos** — el resultado central de la teoría de contratos.

El contrato óptimo minimiza el costo de implementar $a_H$ sujeto a IR e IC. La solución tiene IR e IC ambas activas en el óptimo del principal con agente averso al riesgo:

$$p_H u(w_H) + p_L u(w_L) - c_H = \bar{u} \quad \text{(IR activa)}$$

$$(p_H - q_H)[u(w_H) - u(w_L)] = c_H - c_L \quad \text{(IC activa)}$$

### 2.3 Modelo continuo: el approach de primer orden

Con esfuerzo continuo $a \in [0, \bar{a}]$, el principal maximiza:

$$\max_{w(\cdot), a} \int [x - w(x)] f(x|a) dx$$

sujeto a IR: $\int u(w(x)) f(x|a) dx - c(a) \geq \bar{u}$

y IC: $a \in \arg\max_{a'} \int u(w(x)) f(x|a') dx - c(a')$

La IC es una restricción global complicada. El **approach de primer orden** la reemplaza por su condición necesaria de primer orden:

$$\int u(w(x)) f_a(x|a) dx = c'(a)$$

El contrato óptimo de segundo mejor (derivado por Mirrlees y Holmström) satisface la condición de pago punto a punto:

$$\frac{1}{u'(w^*(x))} = \lambda + \mu \frac{f_a(x|a)}{f(x|a)}$$

donde $\lambda$ es el multiplicador de IR y $\mu$ es el multiplicador de IC. El término $f_a/f$ es la **razón de verosimilitud** — mide cuánto más probable es el resultado $x$ bajo esfuerzo alto relativo al bajo.

**El principio de informatividad (Holmström, 1979):** el salario óptimo es una función creciente de la razón de verosimilitud $f_a(x|a)/f(x|a)$. Una señal adicional $y$ debe incluirse en el contrato si y solo si es **informativa** sobre el esfuerzo del agente condicional en $x$ — es decir, si $y$ no es independiente de $a$ dado $x$.

Corolarios del principio de informatividad:
- **Evaluación relativa:** si los CEOs de distintas firmas enfrentan shocks comunes del sector, sus pagos deberían depender del desempeño relativo a sus pares — el shock común es una señal útil sobre el desempeño relativo.
- **Señales de largo plazo:** si los esfuerzos hoy afectan las ganancias futuras, la compensación óptima debería incluir ganancias rezagadas.

### 2.4 Riesgo moral en el mercado de seguros

El riesgo moral surge cuando una parte, tras firmar el contrato, se comporta de forma diferente — usualmente más riesgosa — porque está protegida de las consecuencias de sus acciones. La aseguradora no puede monitorear perfectamente el comportamiento, llevando a toma de riesgo excesiva. 

El asegurado maximiza su utilidad esperada eligiendo nivel de cuidado $a$ (que reduce la probabilidad de siniestro). Con seguro completo $d = 1$, el asegurado no enfrenta ningún costo en el estado de pérdida — el nivel óptimo de cuidado privado es cero (mínimo). La aseguradora, anticipando esto, no puede ofrecer seguro completo a prima actuarialmente justa.

La solución es el **copago o deducible**: el asegurado soporta parte del costo del siniestro, restaurando los incentivos para el cuidado. El copago óptimo balancea incentivos (mayor copago → más cuidado) contra seguro (mayor copago → más riesgo soportado por el asegurado). La cobertura de segundo mejor es estrictamente menor que uno — el mismo trade-off entre incentivos y aseguramiento del modelo general.

---

## 3. El problema de la selección adversa

### 3.1 El mercado de limones: Akerlof (1970)

El ejemplo clásico de Akerlof (1970) ilustra el problema: el comprador de un auto usado tiene mucho menos información sobre el estado del vehículo que el vendedor. 

**El modelo:** Hay autos de calidad alta (peaches, valor $v_H$) y baja (lemons, valor $v_L < v_H$). La fracción de peaches es $\theta$. Los vendedores conocen la calidad de su auto; los compradores solo saben la distribución.

El precio de mercado refleja la calidad esperada: $p = \theta v_H + (1-\theta)v_L$.

**El colapso del mercado:** Si $v_H > p$ (los dueños de peaches valoran su auto más que el precio de mercado), los dueños de peaches no venden. El mercado se llena con lemons. Pero si los compradores anticipan esto, están dispuestos a pagar solo $v_L$. Los dueños de peaches definitivamente no venden a $v_L$.

En el equilibrio, solo se transan lemons a precio $v_L$ — o el mercado colapsa completamente si incluso los lemon owners valoran sus autos más que lo que los compradores están dispuestos a pagar. Como resultado, el mercado se domina por productos de baja calidad. 

El mecanismo es una **espiral descendente**: información asimétrica → precio refleja calidad promedio → vendedores de alta calidad salen → calidad promedio cae → precio cae → más vendedores de alta calidad salen. El mercado puede desaparecer completamente aunque hubiera ganancias de intercambio mutuamente beneficiosas.

**Aplicaciones:**

- Mercado de crédito: los bancos no pueden distinguir buenos y malos deudores → la tasa refleja el riesgo promedio → buenos deudores se van o pagan tasa ineficientemente alta.
- Mercado laboral: empleadores no observan la productividad → ofrecen salario promedio → los más productivos se van.
- Mercado de seguros de salud: aseguradoras no conocen el riesgo de cada asegurado → prima refleja riesgo promedio → los más sanos no compran → pool de riesgo empeora.

### 3.2 El modelo formal de selección adversa: dos tipos

El principal ofrece un contrato a un agente que puede ser de tipo $\theta_H$ (alta productividad) o $\theta_L < \theta_H$ (baja productividad), con probabilidades $\nu$ y $1-\nu$. El agente conoce su tipo; el principal no.

Con producción $q$ y contrato $(q, T)$ (cantidad producida y transferencia recibida), los pagos son:

- Agente tipo $\theta$: $U = T - c(q, \theta)$ donde $c_q > 0$, $c_{q\theta} < 0$ (el tipo alto tiene menor costo marginal).
- Principal: $\Pi = V(q) - T$.

**El primer mejor** con información perfecta: el principal extrae toda la renta imponiendo $T_i = c(q_i^{FB}, \theta_i)$ con $V'(q_i^{FB}) = c_q(q_i^{FB}, \theta_i)$.

**El segundo mejor** con información asimétrica: el principal ofrece un menú $\{(q_H, T_H), (q_L, T_L)\}$ para inducir autoselección. Las restricciones son:

**IR:** cada tipo acepta su contrato diseñado:

$$T_H - c(q_H, \theta_H) \geq 0$$
$$T_L - c(q_L, \theta_L) \geq 0$$

**IC:** cada tipo prefiere el contrato diseñado para él:

$$T_H - c(q_H, \theta_H) \geq T_L - c(q_L, \theta_H)$$
$$T_L - c(q_L, \theta_L) \geq T_H - c(q_H, \theta_L)$$

La **condición de cruce único (single-crossing)** es crucial: $\frac{\partial}{\partial\theta}\left(\frac{c_q}{U_T}\right) < 0$ — el costo relativo de producción cae con el tipo. Garantiza que las curvas de indiferencia se crucen una sola vez y que el menú tiene una solución ordenada.

**Resultado estándar del segundo mejor:**

1. **IR del tipo bajo y IC del tipo alto son las restricciones activas** — las demás son no vinculantes en el óptimo.
2. **El tipo alto recibe renta de información:** $U_H^{SB} = c(q_L^{SB}, \theta_H) - c(q_L^{SB}, \theta_L) > 0$ — la diferencia en costos de producir $q_L$ entre tipos es la renta que el principal debe dejar al tipo alto para evitar que se haga pasar por el tipo bajo.
3. **El tipo alto recibe la cantidad de primer mejor:** $q_H^{SB} = q_H^{FB}$ — no hay distorsión en la cima.
4. **El tipo bajo recibe cantidad distorsionada hacia abajo:** $q_L^{SB} < q_L^{FB}$ — la distorsión reduce la renta informacional del tipo alto.

El trade-off: **rentas vs. eficiencia**. Para extraer más renta del tipo alto (más eficiencia), el principal baja $q_L$, lo que distorsiona la eficiencia del tipo bajo.

### 3.3 Autoselección competitiva: Rothschild-Stiglitz (1976)

Con múltiples aseguradoras en competencia, Rothschild y Stiglitz demostraron que el equilibrio en un mercado de seguros con selección adversa es **un equilibrio separador** (si existe) donde:

- Los de alto riesgo obtienen cobertura completa.
- Los de bajo riesgo obtienen cobertura parcial (para evitar que los de alto riesgo imiten).

El resultado sorprendente: puede no existir equilibrio en Nash. Si hay muchos de bajo riesgo, una aseguradora puede desviar ofreciendo un contrato que atrae a los de bajo riesgo y es rentable — destruyendo el equilibrio separador. No emerge equilibrio agrupador (pooling) estable porque otra aseguradora puede ofrecer un contrato que solo atraiga a los de bajo riesgo.

---

## 4. Modelos de señalización

### 4.1 El modelo de Spence (1973)

En modelos de señalización, una parte elige cómo presentar información sobre sí misma a otra parte para reducir la asimetría de información. La formulación comenzó en 1973 con Spence a través de su modelo de señalización en el mercado laboral. 

**Setup:** Los trabajadores son de tipo alto ($\theta_H$, productividad $y_H$) o bajo ($\theta_L < \theta_H$, productividad $y_L$). Los empleadores no observan el tipo. Los trabajadores pueden adquirir educación $e$ con costo $c(e, \theta)$ donde $c_e > 0$ y $c_{e\theta} < 0$ (el tipo alto tiene menor costo marginal de educación — la **condición de cruce único**).

La educación no es productiva en el modelo de Spence — sirve solo como señal. Esta es la provocación: si la educación no crea productividad, ¿puede ser un equilibrio que los empleadores la usen como indicador de productividad?

### 4.2 Equilibrios separadores

Un **equilibrio separador** $e^*$ tiene los tipos altos eligiendo $e^* > 0$ y los tipos bajos eligiendo $e = 0$. Los empleadores pagan $w(e \geq e^*) = y_H$ y $w(e < e^*) = y_L$.

Las condiciones de equilibrio son las IC de ambos tipos:

**Tipo alto prefiere señalizar:** $y_H - c(e^*, \theta_H) \geq y_L$, es decir $c(e^*, \theta_H) \leq y_H - y_L$.

**Tipo bajo no quiere imitar:** $y_L \geq y_H - c(e^*, \theta_L)$, es decir $c(e^*, \theta_L) \geq y_H - y_L$.

La condición de cruce único garantiza que existe un rango $[e^{min}, e^{max}]$ donde ambas IC se satisfacen simultáneamente. Cualquier $e^* \in [e^{min}, e^{max}]$ sostiene un equilibrio separador — hay **multiplicidad**.

El **nivel mínimo de señalización** $e^{min}$ que satisface exactamente la IC del tipo bajo: $c(e^{min}, \theta_L) = y_H - y_L$. Este es el equilibrio separador Pareto-dominante (mínima pérdida social por señalización).

### 4.3 Equilibrios agrupadores y refinamientos

En un **equilibrio agrupador**, ambos tipos eligen el mismo nivel de educación $\bar{e}$ y reciben el salario de productividad promedio $\bar{w} = \nu y_H + (1-\nu) y_L$.

Condición para sostenimiento: ningún tipo quiere desviarse. El tipo alto no quiere señalizar más si el beneficio de ser identificado como alto no compensa el costo adicional de señal.

La multiplicidad de equilibrios es problemática. El **refinamiento D1 de Cho-Kreps** selecciona el equilibrio separador mínimo: si un tipo se desviara a $e' \notin \{0, e^*\}$, y solo el tipo alto podría beneficiarse de la desviación, el empleador debería actualizar sus creencias hacia el tipo alto. Este refinamiento elimina los equilibrios separadores con señalización excesiva.

### 4.4 Bienestar y crítica a la señalización

La señalización de Spence genera una externalidad negativa: al señalizar, los tipos altos elevan el umbral necesario para separarse — hacen más costoso para los tipos bajos imitar, pero esto no crea valor social. La señalización involucra a la parte informada demostrando su calidad o confiabilidad, como mostrar títulos universitarios en postulaciones laborales. 

Si la educación es puramente señalizadora (sin valor productivo), el equilibrio es Pareto-inferior a un mundo donde los tipos son perfectamente observables: los tipos altos obtienen el mismo salario $y_H$ pero incurren en costos de educación, mientras los tipos bajos obtienen $y_L$ en ambos mundos. La señalización es puro desperdicio social en este modelo extremo.

Sin embargo, la educación típicamente tiene valor productivo y señalizador simultáneamente — la pregunta empírica es la magnitud relativa de cada componente, debatida ampliamente en economía de la educación (Caplan, 2018, argumenta que la fracción señalizadora es grande; la literatura canónica de retornos a la educación toma el valor productivo como dominante).

---

## 5. Diseño de mecanismos y el principio de revelación

### 5.1 El principio de revelación directa

El **principio de revelación** establece que cualquier resultado implementable por algún mecanismo puede implementarse por un **mecanismo de revelación directa** — uno en que los agentes reportan sus tipos y el mecanismo asigna resultados directamente — donde reportar verazmente es un equilibrio.

Formalmente: si existe un mecanismo que implementa una asignación $\{q(\hat{\theta}), T(\hat{\theta})\}$, entonces existe un mecanismo de revelación directa que implementa la misma asignación donde reportar verazmente $\hat{\theta} = \theta$ es incentivo compatible.

La **condición de compatibilidad de incentivos** en el mecanismo directo:

$$U(\theta, \theta) \geq U(\theta', \theta) \quad \forall \theta, \theta'$$

donde $U(\hat{\theta}, \theta) = T(\hat{\theta}) - c(q(\hat{\theta}), \theta)$ es la utilidad del tipo $\theta$ cuando reporta $\hat{\theta}$.

El principio de revelación simplifica enormemente el diseño de mecanismos: en lugar de buscar el mecanismo óptimo en el espacio general de todos los juegos posibles, basta buscar en el espacio de mecanismos de revelación directa incentivo-compatibles.

### 5.2 La condición de envolvente

Diferenciando la condición de optimalidad del agente respecto a $\theta$ (teorema de la envolvente):

$$\frac{\partial U^*(\theta)}{\partial \theta} = -c_\theta(q(\theta), \theta)$$

La **renta de información** de cada tipo se determina completamente por la asignación de cantidades $q(\theta)$ — el principal no tiene libertad adicional para extraer rentas una vez fijada la asignación. La renta del tipo más bajo es cero (IR activa); la renta de cada tipo superior se integra hacia arriba.

Esta ecuación de envolvente implica que el diseño óptimo se reduce a elegir el perfil de cantidades $q(\theta)$ que maximiza el excedente total menos las rentas informacionales — la intuición es que las rentas son costosas para el principal y el costo es mayor para tipos con mayor diferencial de productividad.

---

## 6. Síntesis: los problemas de información y sus soluciones

| Problema | Timing | Agente actúa primero | Solución canónica | Costo social |
|---|---|---|---|---|
| **Riesgo moral** | Post-contractual | Sí (acción oculta) | Contrato incentivo (pay-for-performance) | Subóptimo aseguramiento |
| **Selección adversa** | Pre-contractual | No (tipo oculto) | Menú de contratos (screening) | Renta informacional + distorsión |
| **Señalización** | Pre-contractual | Sí (señal costosa) | Equilibrio separador | Costo de señal sin valor productivo |

Los tres problemas comparten la estructura: la información privada del agente le confiere **poder de negociación** — una renta que el principal no puede eliminar sin incurrir en costos de eficiencia. El diseño óptimo de contratos, mecanismos e instituciones puede mitigar pero no eliminar estos costos bajo asimetría de información.

---

## Referencias

- Akerlof, G. (1970). *The Market for Lemons*. QJE.
- Spence, M. (1973). *Job Market Signaling*. QJE.
- Mirrlees, J. (1971). *An Exploration in the Theory of Optimum Income Taxation*. RES.
- Holmström, B. (1979). *Moral Hazard and Observability*. Bell Journal of Economics.
- Rothschild, M. & Stiglitz, J. (1976). *Equilibrium in Competitive Insurance Markets*. QJE.
- Cho, I. & Kreps, D. (1987). *Signaling Games and Stable Equilibria*. QJE.
- Laffont, J.J. & Martimort, D. (2002). *The Theory of Incentives*. Princeton University Press.
- Mas-Colell, A., Whinston, M. & Green, J. (1995). *Microeconomic Theory*. Oxford. Caps. 13–14.
- Gibbons, R. (1992). *Game Theory for Applied Economists*. Princeton University Press.
- Vial, B. & Zurita, F. *Microeconomía*. Ediciones UC.