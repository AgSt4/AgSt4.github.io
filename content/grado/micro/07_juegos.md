---
title: "Teoría de Juegos"
date: 2026-03-15
draft: false
tags: ["microeconomía", "teoría de juegos", "Nash", "perfección en subjuegos", "juegos repetidos", "dilema del prisionero", "EAE2120"]
description: "Juegos estáticos y equilibrio de Nash, dominancia, juegos dinámicos con información perfecta, inducción hacia atrás, perfección en subjuegos, juegos repetidos y el teorema folk."
---

**Curso:** Microeconomía II (EAE2120)  
**Referencia principal:** Vial & Zurita — *Microeconomía* · Osborne (2004) · Gibbons (1992) · Mas-Colell, Whinston & Green (1995) caps. 7–9

---

## 1. El marco de la teoría de juegos

### 1.1 Motivación y alcance

La teoría microeconómica estándar modela decisiones de agentes que toman precios como dados — sus elecciones no afectan el entorno. La **teoría de juegos** modela situaciones de **interacción estratégica**: el bienestar de cada agente depende no solo de sus propias acciones sino de las acciones de los demás. Cada agente toma sus decisiones anticipando las decisiones de los otros.

Los campos de aplicación son vastos: oligopolio, negociación, diseño de mecanismos, política, relaciones internacionales, biología evolutiva. El resultado central — el equilibrio de Nash — es el concepto de equilibrio más influyente de las ciencias sociales del siglo XX.

### 1.2 Elementos de un juego

Un juego en forma normal (o estratégica) es una tripleta $\Gamma = (N, \{S_i\}, \{u_i\})$:

- **Jugadores:** $N = \{1, 2, \ldots, n\}$.
- **Conjuntos de estrategias:** $S_i$ es el conjunto de estrategias disponibles para el jugador $i$. Un **perfil de estrategias** es $\mathbf{s} = (s_1, \ldots, s_n) \in S = \prod_i S_i$.
- **Funciones de pago:** $u_i: S \to \mathbb{R}$ asigna un pago a cada perfil de estrategias.

La distinción entre **estrategia** y **acción** es crucial en juegos dinámicos: una estrategia es un plan completo de contingencias que especifica qué hacer en cada nodo de decisión posible del árbol del juego, incluso en nodos que nunca se alcanzarán bajo el plan propio.

---

## 2. Juegos estáticos: equilibrio de Nash

### 2.1 Dominancia estricta y su eliminación iterada

La estrategia $s_i$ **domina estrictamente** a $s_i'$ si $u_i(s_i, \mathbf{s}_{-i}) > u_i(s_i', \mathbf{s}_{-i})$ para todo $\mathbf{s}_{-i} \in S_{-i}$. Un jugador racional nunca juega una estrategia estrictamente dominada.

La **eliminación iterada de estrategias estrictamente dominadas (EIEED)** elimina sucesivamente las estrategias dominadas, usando el conocimiento de que los demás tampoco juegan estrategias dominadas. Con conocimiento común de racionalidad, el resultado de la EIEED es la única predicción racional si el proceso converge a un perfil único.

Sin embargo, la EIEED raramente elimina todo y en general deja un conjunto grande de perfiles como candidatos. Se necesita un concepto de equilibrio más restrictivo.

### 2.2 La mejor respuesta

La **mejor respuesta** del jugador $i$ ante el perfil de los demás $\mathbf{s}_{-i}$:

$$BR_i(\mathbf{s}_{-i}) = \arg\max_{s_i \in S_i} u_i(s_i, \mathbf{s}_{-i})$$

Es la correspondencia que mapea cada perfil de los rivales a las estrategias óptimas del jugador $i$. Con estrategias continuas y $u_i$ cóncava en $s_i$, $BR_i$ es una función diferenciable — la **función de reacción** o **función de mejor respuesta**.

### 2.3 El equilibrio de Nash

**Definición (Nash, 1950):** Un perfil de estrategias $\mathbf{s}^* = (s_1^*, \ldots, s_n^*)$ es un **equilibrio de Nash (EN)** si para cada jugador $i$:

$$u_i(s_i^*, \mathbf{s}_{-i}^*) \geq u_i(s_i, \mathbf{s}_{-i}^*) \quad \forall s_i \in S_i$$

Equivalentemente: $s_i^* \in BR_i(\mathbf{s}_{-i}^*)$ para todo $i$. Ningún jugador tiene incentivo a desviarse unilateralmente dado lo que hacen los demás.

El EN es una condición de **consistencia de creencias**: cada jugador juega su mejor respuesta a sus creencias sobre los rivales, y esas creencias son correctas en equilibrio. No requiere coordinación explícita — es el resultado de un proceso de introspección racional con conocimiento común de las estrategias de los rivales.

**Teorema de existencia (Nash, 1950):** Todo juego finito tiene al menos un equilibrio de Nash en estrategias mixtas.

La prueba usa el teorema del punto fijo de Kakutani sobre la correspondencia de mejor respuesta $BR: S \to S$, que mapea el simplex en sí mismo y tiene grafo cerrado con valores convexos.

### 2.4 Estrategias mixtas

Una **estrategia mixta** $\sigma_i \in \Delta(S_i)$ es una distribución de probabilidad sobre las estrategias puras de $i$. El pago esperado es $u_i(\boldsymbol{\sigma}) = \sum_\mathbf{s} \left(\prod_i \sigma_i(s_i)\right) u_i(\mathbf{s})$.

En un EN en estrategias mixtas, el jugador $i$ es indiferente entre todas las estrategias puras en el soporte de $\sigma_i^*$: si una estrategia pura fuera estrictamente mejor, sería óptimo jugarla con probabilidad 1 — contradicción con la mezcla óptima. La condición de indiferencia es la clave para calcular los equilibrios mixtos.

**Interpretación:** la estrategia mixta puede interpretarse como (a) aleatorización deliberada, (b) frecuencias en una población que juega puras, o (c) incertidumbre del rival sobre qué estrategia pura jugará el agente. La interpretación (c) es la más satisfactoria para predicciones de conducta individual.

### 2.5 Ejemplos canónicos

**El dilema del prisionero:**

|  | Cooperar | Desertar |
|---|---|---|
| **Cooperar** | $(3, 3)$ | $(0, 4)$ |
| **Desertar** | $(4, 0)$ | $(1, 1)$ |

Desertar domina estrictamente a cooperar para ambos jugadores. El EN único es (Desertar, Desertar) con pagos $(1,1)$ — Pareto-inferior a (Cooperar, Cooperar) con $(3,3)$. El dilema del prisionero captura la tragedia de los comunes: la racionalidad individual lleva a un resultado colectivamente subóptimo.

**La batalla de los sexos:**

|  | Ópera | Fútbol |
|---|---|---|
| **Ópera** | $(2, 1)$ | $(0, 0)$ |
| **Fútbol** | $(0, 0)$ | $(1, 2)$ |

Dos EN en estrategias puras: (Ópera, Ópera) y (Fútbol, Fútbol). Un tercer EN en estrategias mixtas: J1 juega Ópera con probabilidad $2/3$; J2 juega Ópera con probabilidad $1/3$. La multiplicidad de equilibrios refleja el problema de coordinación — el juego tiene intereses comunes (ambos prefieren coordinar) pero conflicto sobre el punto de coordinación.

**Piedra, papel, tijeras:**

Sin EN en estrategias puras. El único EN es la mezcla uniforme $(1/3, 1/3, 1/3)$ para ambos jugadores — resultado del teorema de Nash para juegos de suma cero.

---

## 3. Juegos dinámicos con información perfecta

### 3.1 La forma extensiva

Un juego dinámico se representa en **forma extensiva** (árbol del juego):
- **Nodos de decisión:** puntos donde un jugador elige.
- **Ramas:** las acciones disponibles en cada nodo.
- **Nodos terminales:** resultados del juego con pagos.
- **Función de jugador:** asigna a cada nodo de decisión el jugador que actúa.

Un juego tiene **información perfecta** si cada jugador conoce toda la historia del juego al momento de actuar — cada nodo de decisión es un singleton en el conjunto de información. Sin información perfecta, los nodos se agrupan en conjuntos de información donde el jugador no puede distinguir entre los nodos del conjunto.

### 3.2 El problema de los EN no creíbles

Los juegos dinámicos en forma normal pueden tener equilibrios de Nash que dependen de **amenazas no creíbles** — compromisos que nunca serían óptimos ejecutar si se llegara al nodo relevante.

**Ejemplo — juego de entrada:**

Una firma incumbente (I) y una entrante (E). E decide Entrar o No Entrar; si entra, I decide Luchar o Acomodar.

Pagos: (Entrar, Acomodar) = $(1, 1)$; (Entrar, Luchar) = $(-1, -1)$; (No Entrar, ·) = $(0, 2)$.

El perfil (No Entrar; Luchar si entra) es un EN: dado que I amenaza con luchar, E no entra; dado que E no entra, I no necesita actuar. Pero la amenaza de luchar es **no creíble**: si E entra, luchar da $-1$ a I mientras acomodar da $1$. Una firma racional siempre acomodaría. El EN basado en la amenaza no creíble no predice correctamente el comportamiento.

Los perfiles de estrategias que representan equilibrios perfectos en subjuegos excluyen la posibilidad de acciones como amenazas no creíbles usadas para "asustar" a un entrante. Si el incumbente amenaza con iniciar una guerra de precios, está amenazando con bajar sus precios a un nivel que resultaría en pérdidas para ambas partes — una amenaza que el entrante racional reconoce como no creíble. 

### 3.3 Inducción hacia atrás

La inducción hacia atrás es un método para encontrar el equilibrio perfecto en subjuegos resolviendo el juego desde la última decisión hacia atrás hasta la primera. Permite encontrar estrategias óptimas en cada subjuego, considerando todos los puntos de decisión secuencialmente. 

El algoritmo:
1. Identificar los nodos de decisión **terminales** (los inmediatamente anteriores a los nodos terminales del árbol).
2. En cada uno de estos nodos, el jugador correspondiente elige la acción que maximiza su pago.
3. Reemplazar esos subárboles por los pagos de la elección óptima.
4. Repetir hacia atrás hasta el nodo raíz.

La inducción hacia atrás produce el único equilibrio perfecto en subjuegos en juegos de información perfecta y horizonte finito.

Aplicado al juego de entrada: en el subárbol de I, la acción óptima es Acomodar (pago $1 > -1$). Sustituyendo, E compara Entrar (pago $1$) con No Entrar (pago $0$) — elige Entrar. El equilibrio único por inducción hacia atrás es (Entrar; Acomodar).

### 3.4 El equilibrio perfecto en subjuegos (SPE)

Un equilibrio de Nash es perfecto en subjuegos si prescribe un equilibrio de Nash en cada subjuego posible del juego original. Esto asegura que las estrategias son creíbles en toda la extensión del juego, eliminando amenazas no creíbles. 

**Definición:** Un subjuego es una parte del árbol del juego que: (i) comienza en un nodo de decisión singleton, (ii) contiene todos los nodos sucesores, y (iii) contiene el árbol completo de información de esos nodos. El juego completo siempre es un subjuego de sí mismo.

Un perfil de estrategias $\mathbf{s}^*$ es un **equilibrio perfecto en subjuegos (EPS)** si constituye un EN en cada subjuego del juego.

El primer juego tiene tres equilibrios de Nash pero solo uno es consistente con la inducción hacia atrás. Los otros dos equilibrios de Nash no son perfectos en subjuegos: cada uno falla en inducir Nash en algún subjuego. 

**Relación con inducción hacia atrás:** en juegos de información perfecta y horizonte finito, el EPS coincide con el resultado de la inducción hacia atrás. En juegos con información imperfecta, la inducción hacia atrás no aplica directamente — se usa el concepto más general de EPS.

### 3.5 El juego del ultimátum

El juego del ultimátum ilustra la tensión entre predicción teórica y evidencia empírica. J1 propone una división $(x, 1-x)$ de una unidad; J2 acepta o rechaza. Si rechaza, ambos reciben cero.

Considerando la elección y respuesta del J2 dado cualquier propuesta de J1, la racionalidad formal prescribe que J2 aceptaría cualquier pago mayor o igual a cero. Por inducción hacia atrás, J1 debería proponer dar a J2 la cantidad mínima posible y quedarse el resto. 

El EPS único es que J1 ofrece $\varepsilon \to 0$ y J2 acepta. Empíricamente, las personas rechazan ofertas menores al 20-30% y los proponentes típicamente ofrecen cercano al 50% — evidencia de preferencias por equidad que el modelo de maximización de pagos monetarios no captura.

---

## 4. Aplicaciones económicas de juegos dinámicos

### 4.1 Stackelberg: liderazgo en cantidades

En el duopolio de Stackelberg, la firma 1 elige su cantidad $q_1$ primero (observablemente); la firma 2 responde eligiendo $q_2(q_1)$ tras observar $q_1$.

El EPS se resuelve por inducción hacia atrás. En el segundo período, J2 maximiza:

$$\max_{q_2} (a - q_1 - q_2 - c)q_2 \implies q_2^*(q_1) = \frac{a-c-q_1}{2}$$

En el primer período, J1 maximiza anticipando la respuesta de J2:

$$\max_{q_1} (a - q_1 - q_2^*(q_1) - c)q_1 = \max_{q_1} \frac{(a-c-q_1)q_1}{2}$$

$$\implies q_1^S = \frac{a-c}{2}, \quad q_2^S = \frac{a-c}{4}$$

El líder produce más que en Cournot ($q_1^C = (a-c)/3$) y que el seguidor — la **ventaja del primer movimiento**. La cantidad total es mayor y el precio menor que en Cournot: el liderazgo mejora la eficiencia relativa al equilibrio simultáneo.

### 4.2 El juego de negociación de Rubinstein

En el juego de negociación de ofertas alternantes (Rubinstein, 1982), dos jugadores se alternan haciendo propuestas de división de una unidad. Si se rechaza una oferta, el siguiente jugador hace una contraoferta, con un factor de descuento $\delta \in (0,1)$ por período.

El EPS único es que J1 propone dar a J2 exactamente suficiente para inducir aceptación: J2 acepta si su oferta es al menos $\delta$ veces lo que J2 obtendría siendo el próximo proponente. El único subgame perfect equilibrium tiene J1 proponer $x^* = 1/(1+\delta)$ para sí mismo, y J2 acepta inmediatamente. 

Con $\delta \to 1$ (agentes pacientes), la división tiende a $(1/2, 1/2) $ — el resultado Nash de negociación. La ventaja del primer proponente desaparece cuando la paciencia es perfecta.

---

## 5. Juegos repetidos

### 5.1 El dilema del prisionero repetido finito

Para juegos repetidos finitos con número fijo y conocido de períodos, si el juego de etapa tiene un único equilibrio de Nash, el único EPS del juego repetido es jugar el equilibrio del juego de etapa en cada ronda. 

La lógica es la **inducción hacia atrás**: en el período final $T$, no hay períodos futuros, por lo que ambos jugadores desertan (el único EN del juego de etapa). Anticipando esto, en $T-1$ no hay reputación que mantener — también desertan. El argumento se repite hacia atrás hasta el período 1.

**Resultado:** en el dilema del prisionero repetido finito, la única estrategia SPE es desertar en todos los períodos — la cooperación no puede sostenerse como equilibrio.

Este resultado es el **desmoronamiento** (*unraveling*) del juego finito: la imposibilidad de cooperar en el último período contamina todos los anteriores.

### 5.2 Juegos repetidos infinitamente

Con horizonte infinito o fecha de fin desconocida, la inducción hacia atrás no aplica. La **tasa de descuento** $\delta \in (0,1)$ representa cuánto valora el jugador los pagos futuros.

El pago descontado de una secuencia de pagos $\{g_t\}_{t=0}^\infty$ es:

$$V = \sum_{t=0}^\infty \delta^t g_t = g_0 + \delta g_1 + \delta^2 g_2 + \cdots$$

Con un pago constante $g$ para siempre: $V = g/(1-\delta)$.

### 5.3 La estrategia de gatillo (trigger strategy)

La estrategia de gatillo más simple es el **Grim Trigger**:
- Cooperar en el período 1.
- Cooperar en el período $t$ si en todos los períodos anteriores ambos jugadores cooperaron.
- Desertar para siempre si alguno desertó en algún período pasado.

**¿Puede sostenerse la cooperación como EPS con Grim Trigger?**

El pago de cooperar siempre:

$$V^C = \frac{g^C}{1-\delta}$$

El pago de desviarse hoy (obteniendo $g^D > g^C$ hoy, luego recibiendo $g^{DD}$ para siempre por el castigo):

$$V^D = g^D + \frac{\delta g^{DD}}{1-\delta}$$

La cooperación es sostenible si $V^C \geq V^D$:

$$\frac{g^C}{1-\delta} \geq g^D + \frac{\delta g^{DD}}{1-\delta} \implies \delta \geq \frac{g^D - g^C}{g^D - g^{DD}} \equiv \bar{\delta}$$

La cooperación se sostiene cuando el factor de descuento supera el umbral $\bar{\delta}$: los jugadores son suficientemente pacientes como para que el beneficio de la relación continua supere la ganancia inmediata de desertar.

Para el dilema del prisionero con pagos $(3,3)$, $(4,0)$, $(0,4)$, $(1,1)$:

$$\bar{\delta} = \frac{4-3}{4-1} = \frac{1}{3}$$

Para $\delta \geq 1/3$, la cooperación es sostenible con Grim Trigger. La cooperación en juegos iterados solo es posible cuando el número de rondas es infinito o desconocido. 

### 5.4 El teorema folk

El teorema folk generaliza el resultado anterior. Define el **pago de minmax** $\underline{v}_i$ como el pago mínimo que los demás jugadores pueden forzar sobre $i$:

$$\underline{v}_i = \min_{\mathbf{s}_{-i}} \max_{s_i} u_i(s_i, \mathbf{s}_{-i})$$

El conjunto de pagos **factibles** $F$ es la envoltura convexa de los pagos alcanzables con algún perfil de estrategias puras. El conjunto de pagos **individualmente racionales** son los que superan el minmax de cada jugador.

**Teorema Folk:** En un juego repetido infinitamente, para cualquier vector de pagos factible e individualmente racional $\mathbf{v}$, existe un $\bar{\delta} < 1$ tal que para todo $\delta \geq \bar{\delta}$, $\mathbf{v}$ puede sostenerse como pago de un EPS.

Si una firma se desvía, puede obtener $m$ en ese período, y obtendrá cero para siempre después. Si es suficientemente paciente ($\delta \geq \bar{\delta}(n)$), la colusión puede sustentarse. Las comparativas estáticas sobre el factor de descuento crítico muestran cómo varía con la demanda y el número de firmas. 

El teorema folk implica **multiplicidad de equilibrios** en juegos repetidos: prácticamente cualquier comportamiento razonable — cooperación, colusión, castigos — puede sostenerse como equilibrio si los agentes son suficientemente pacientes. El modelo no predice un resultado único sino un rango.

### 5.5 El problema de la paradoja de la cadena de tiendas

Para $K=1$ tienda, la perfección en subjuegos elimina el mal EN. Para $K$ grande, ¿no es más razonable pensar que la cadena establecerá una reputación de ser agresiva? Si vemos que la cadena lucha contra los primeros 10 competidores, ¿es razonable que el siguiente entre? Es decir, si vemos que se viola el supuesto de conocimiento común de racionalidad secuencial, ¿importa esto? 

La **paradoja de la cadena de tiendas** de Selten muestra que la inducción hacia atrás en el juego de entrada repetido finito predice siempre acomodar — incluso con 100 entrantes potenciales. Pero intuitivamente, pelear contra los primeros entrantes para establecer reputación parece racional. La resolución requiere introducir información incompleta sobre el tipo del incumbente (Kreps & Wilson, 1982).

---

## 6. Síntesis: conceptos de equilibrio y sus relaciones

| Concepto | Contexto | Condición | Refinamiento de |
|---|---|---|---|
| **Estrategia dominante** | Cualquier juego | Mejor respuesta a cualquier perfil rival | — |
| **EIEED** | Cualquier juego | Superviven estrategias no dominadas | — |
| **Equilibrio de Nash** | Juego estático | Mejor respuesta mutua | EIEED |
| **EN Perfecto en subjuegos** | Juego dinámico | Nash en cada subjuego | EN |
| **EN Bayesiano Perfecto** | Info. incompleta | Nash + consistencia bayesiana | EPS |

La jerarquía es: toda estrategia dominante es EN, todo EPS es EN, pero no todo EN es EPS. Los refinamientos eliminan equilibrios basados en amenazas no creíbles o creencias inconsistentes.

---

## Referencias

- Nash, J. (1950). *Equilibrium Points in N-Person Games*. PNAS.
- Nash, J. (1951). *Non-Cooperative Games*. Annals of Mathematics.
- Selten, R. (1965). *Spieltheoretische Behandlung eines Oligopolmodells mit Nachfrageträgheit*. Zeitschrift für die gesamte Staatswissenschaft.
- Rubinstein, A. (1982). *Perfect Equilibrium in a Bargaining Model*. Econometrica.
- Kreps, D. & Wilson, R. (1982). *Sequential Equilibria*. Econometrica.
- Fudenberg, D. & Tirole, J. (1991). *Game Theory*. MIT Press. Caps. 1–5.
- Osborne, M. (2004). *An Introduction to Game Theory*. Oxford University Press.
- Gibbons, R. (1992). *Game Theory for Applied Economists*. Princeton University Press.
- Mas-Colell, A., Whinston, M. & Green, J. (1995). *Microeconomic Theory*. Oxford. Caps. 7–9.
- Vial, B. & Zurita, F. *Microeconomía*. Ediciones UC.