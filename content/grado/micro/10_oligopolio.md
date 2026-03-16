---
title: "Oligopolio"
date: 2026-03-15
draft: false
tags: ["microeconomía", "oligopolio", "Cournot", "Bertrand", "Stackelberg", "diferenciación", "colusión", "EAE2110", "EAE2130"]
description: "Modelos de Cournot, Bertrand y Stackelberg. La paradoja de Bertrand y sus resoluciones. Diferenciación horizontal de productos. Colusión y el dilema del prisionero del oligopolio."
---

**Cursos:** Microeconomía I (EAE2110) · Competencia y Mercados (EAE2130)  
**Referencia principal:** Vial & Zurita — *Microeconomía* · Peppal, Richards & Norman (2006) · Tirole (1988) · Mas-Colell, Whinston & Green (1995) cap. 12

---

## 1. El oligopolio como estructura de mercado

El **oligopolio** es la estructura de mercado donde pocas firmas compiten, cada una con suficiente tamaño como para que sus decisiones afecten el entorno estratégico de las demás. A diferencia de la competencia perfecta (donde cada firma es precio-aceptante) y el monopolio (donde hay un único vendedor), el oligopolio requiere análisis estratégico explícito: el beneficio de cada firma depende de las decisiones de sus rivales.

Los oligopolistas enfrentan curvas de demanda con pendiente negativa, lo que implica que el precio es una función de la cantidad total producida, lo que a su vez implica que el output de una firma afecta no solo el precio que recibe sino el precio que recibe su competidora. 

La pregunta central es cómo modelar la interdependencia estratégica. Los tres modelos canónicos difieren en la **variable estratégica** (cantidad o precio) y el **timing** (simultáneo o secuencial):

| Modelo | Variable | Timing | Resultado |
|---|---|---|---|
| **Cournot** | Cantidad | Simultáneo | Entre monopolio y competencia perfecta |
| **Bertrand** | Precio | Simultáneo | Competencia perfecta (paradoja) |
| **Stackelberg** | Cantidad | Secuencial | Líder ventaja, seguidor desventaja |

---

## 2. El modelo de Cournot

### 2.1 El setup

Cournot (1838) construyó funciones de beneficio para cada firma y usó diferenciación parcial para construir una función que representa la mejor respuesta de cada firma dado el nivel de output (exógeno) de la(s) otra(s) firma(s). 

Con dos firmas con bien homogéneo, demanda inversa $P(Q) = P(q_1 + q_2)$ y costos $C_i(q_i)$, la firma $i$ maximiza:

$$\pi_i = P(q_1 + q_2)q_i - C_i(q_i)$$

tomando como dada la cantidad $q_j$ de la rival — el **supuesto de Cournot**.

### 2.2 Las funciones de mejor respuesta

La CPO de la firma $i$:

$$P(Q) + q_i P'(Q) = C_i'(q_i)$$

$$MR_i = MC_i$$

El ingreso marginal de la firma $i$ incorpora el efecto precio sobre sus propias unidades: $MR_i = P + q_i P' < P$. Dado $q_j$, la firma $i$ elige $q_i$ que satisface esta condición — la **función de reacción** $q_i^*(q_j)$, que es decreciente en $q_j$ (las cantidades son **sustitutos estratégicos**: si el rival produce más, yo produzco menos).

Con demanda lineal $P = a - b(q_1 + q_2)$ y $MC_i = c$:

$$MR_i = a - bq_j - 2bq_i = c \implies q_i^*(q_j) = \frac{a-c-bq_j}{2b} = \frac{a-c}{2b} - \frac{q_j}{2}$$

Las funciones de reacción son líneas rectas con pendiente $-1/2$.

### 2.3 El equilibrio de Cournot-Nash

El equilibrio es la intersección de ambas funciones de reacción: $q_1^* = q_2^*(q_1^*)$ y $q_2^* = q_1^*(q_2^*)$. Por simetría con $c_1 = c_2 = c$:

$$q_i^C = \frac{a-c}{3b}, \quad Q^C = \frac{2(a-c)}{3b}, \quad P^C = \frac{a+2c}{3}$$

$$\pi_i^C = \frac{(a-c)^2}{9b}$$

La estabilidad del equilibrio es notable: si algún productor se desvía de él por error, será llevado de regreso. Esta idea de estabilidad fue tomada posteriormente y construida como descripción de equilibrios de Nash, de los cuales los equilibrios de Cournot son un subconjunto. 

### 2.4 Comparación con monopolio y competencia perfecta

Con $n$ firmas simétricas, el equilibrio de Cournot generalizado da:

$$Q^C = \frac{n(a-c)}{(n+1)b}, \quad P^C = \frac{a + nc}{n+1}$$

- $n = 1$: monopolio, $Q^M = (a-c)/2b$, $P^M = (a+c)/2$.
- $n = 2$: Cournot duopolio.
- $n \to \infty$: $Q \to (a-c)/b = Q^{CP}$, $P \to c = P^{CP}$.

En el oligopolio de Cournot, la cantidad total ofrecida es menor que el óptimo social pero mayor que la cantidad de monopolio.  El índice de Lerner del oligopolio de Cournot es $L = (P-MC)/P = -1/(n|\varepsilon_D|)$ — el poder de mercado cae con el número de firmas y la elasticidad de demanda.

### 2.5 El oligopolio de Cournot como dilema del prisionero

Si los beneficios se interpretan como pagos, la situación corresponde a un dilema del prisionero. Coludiendo, las firmas actuarían como un monopolista y dividirían cantidades y beneficios igualmente. La estructura de dilema del prisionero resulta del hecho de que la mitad del beneficio de monopolio es mayor que el beneficio del equilibrio Nash, y de que con desviación unilateral las firmas pueden aumentar sus beneficios sobre la mitad del monopolio. 

El equilibrio de Cournot es el único EN del juego estático — ninguna firma puede mejorar unilateralmente. Pero ambas firmas estarían mejor si coordinaran en la cantidad de monopolio. La colusión es mutuamente beneficiosa pero individualmente inestable — el mismo estructura del dilema del prisionero.

---

## 3. El modelo de Bertrand

### 3.1 La crítica de Bertrand a Cournot

Bertrand argumentó que cada firma debería maximizar sus beneficios seleccionando un nivel de precio que subcotice a sus competidoras cuando sus precios superan el costo marginal. 

En el modelo de Bertrand con bien homogéneo, las firmas eligen precios simultáneamente. La demanda sigue la regla del precio más bajo: la firma más barata se lleva todo el mercado; si cobran lo mismo, se dividen la demanda.

### 3.2 La paradoja de Bertrand

En el modelo de Bertrand, el precio competitivo sirve como equilibrio Nash. Si ambas firmas establecen un precio competitivo al costo marginal, ninguna obtiene beneficios. Si una firma alinea su precio al costo marginal mientras la otra sube su precio, esta última no gana nada, ya que los consumidores optan por la opción competitivamente priceada. No hay otro escenario de precios que alcance el equilibrio. 

Con dos firmas y bien homogéneo, el **único EN de Bertrand es $p_1^* = p_2^* = MC$** — el resultado de competencia perfecta con solo dos firmas. Este es el **resultado paradójico de Bertrand**: basta con dos firmas para alcanzar el outcome competitivo, independientemente del número mayor de firmas.

### 3.3 Las resoluciones de la paradoja

La paradoja emerge de supuestos muy específicos. Sus resoluciones identifican cuándo el mercado real se aleja del resultado de precio igual a costo marginal:

**Capacidad restringida (Bertrand-Edgeworth):** el modelo ignora restricciones de capacidad. Si una sola firma no tiene capacidad para abastecer todo el mercado, el resultado de "precio igual a costo marginal" puede no mantenerse. Con restricciones de capacidad, puede no existir ningún equilibrio en estrategias puras — la paradoja de Edgeworth. Sin embargo, en general existirá un equilibrio en estrategias mixtas. 

Si las firmas primero eligen capacidades y luego compiten en precios (modelo de Kreps-Scheinkman), el resultado es el equilibrio de Cournot — las capacidades funcionan como compromisos de cantidad.

**Diferenciación de productos:** cuando los bienes no son perfectamente homogéneos, los consumidores no se mueven instantáneamente al precio más bajo. La firma más cara retiene algunos clientes — una demanda residual positiva. El equilibrio Bertrand con productos diferenciados implica precios por encima del costo marginal.

**Costos asimétricos:** cuando el costo marginal de la firma 2 es mayor que el de la firma 1, la firma 2 solo puede fijar su precio igual a su costo marginal. La firma 1 puede elegir su precio entre su costo marginal y el costo marginal de la firma 2. Así, las firmas no fijarán necesariamente precio al costo marginal bajo costos asimétricos. 

**Repetición:** no coludiendo y cobrando costo marginal es el resultado no cooperativo y el único EN del modelo. Por tanto, pasando de un juego de movimiento simultáneo a un juego repetido con horizonte infinito, la colusión es posible por el teorema folk. 

---

## 4. El modelo de Stackelberg

### 4.1 Estructura secuencial

El modelo de Stackelberg considera firmas fijadoras de cantidades con producto idéntico que toman decisiones de output secuencialmente.  La firma 1 (líder) elige $q_1$ primero, de forma observable. La firma 2 (seguidor) observa $q_1$ y luego elige $q_2$.

El equilibrio se resuelve por inducción hacia atrás.

### 4.2 El equilibrio

El seguidor maximiza dado $q_1$: $q_2^*(q_1) = (a-c-bq_1)/(2b)$ — idéntico a la función de reacción de Cournot.

El líder anticipa la respuesta del seguidor y maximiza:

$$\pi_1 = P(q_1 + q_2^*(q_1))q_1 - cq_1 = \left(a - bq_1 - b\cdot\frac{a-c-bq_1}{2b}\right)q_1 - cq_1$$

$$= \frac{(a-c-bq_1)q_1}{2}$$

CPO: $q_1^S = (a-c)/(2b)$, $q_2^S = (a-c)/(4b)$.

Resultados:

$$Q^S = \frac{3(a-c)}{4b} > Q^C = \frac{2(a-c)}{3b}, \quad P^S < P^C$$

$$\pi_1^S = \frac{(a-c)^2}{8b} > \pi_i^C = \frac{(a-c)^2}{9b} > \pi_2^S = \frac{(a-c)^2}{16b}$$

La cantidad individual del líder de Stackelberg es mayor que en Cournot. La del seguidor es menor. La cantidad total es mayor en Stackelberg que en Cournot, lo que significa que el precio es menor. Como el resultado de Cournot es una de las opciones para el líder, sus beneficios deben ser mayores en Stackelberg. Y como tanto la cantidad producida como el precio recibido son menores para el seguidor comparado con Cournot, los beneficios deben ser menores. 

La **ventaja del primer movimiento** emerge de la capacidad del líder de comprometerse creíblemente a una cantidad alta — el seguidor solo puede acomodarse con una cantidad menor. La clave es que el compromiso sea **observable y creíble**: si el seguidor no observara la elección del líder, el juego colapsa al equilibrio de Cournot.

---

## 5. Diferenciación de productos

### 5.1 Bertrand con productos diferenciados

Con diferenciación, los consumidores no se mueven instantáneamente al precio más bajo — tienen preferencias por variedades. El modelo estándar con demanda lineal y diferenciación simétrica:

$$q_i = a - bp_i + dp_j, \quad d \in (0, b)$$

donde $d$ mide la sustituibilidad entre productos ($d \to 0$: bienes independientes; $d \to b$: bienes perfectos sustitutos). Las funciones de mejor respuesta en precios son crecientes (los precios son **complementos estratégicos**: si el rival sube su precio, yo también subo).

El equilibrio Nash en precios:

$$p_i^* = \frac{a + bc}{2b - d} > MC = c$$

El precio de equilibrio es mayor que el costo marginal — la diferenciación de productos restaura el poder de mercado y elimina la paradoja de Bertrand. Cuando $d \to 0$ el precio se acerca al de monopolio; cuando $d \to b$ el precio cae hacia $MC$.

### 5.2 Cantidad vs. precio como variable estratégica

Singh y Vives (1984) muestran que, con duopolio privado donde las firmas maximizan beneficios, y asumiendo demanda lineal y diferenciación de productos, un contrato de cantidad es la estrategia dominante para cada firma cuando los bienes son sustitutos. 

El resultado de Singh-Vives es notable: incluso con la opción de competir en precios, las firmas prefieren competir en cantidades cuando los bienes son sustitutos. La razón: comprometerse a una cantidad (rígida) es una postura más agresiva que comprometerse a un precio (flexible) — en el equilibrio, las firmas extraen más excedente compitiendo en cantidades.

Con bienes complementos, se invierte: la competencia en precios es la estrategia dominante.

### 5.3 El modelo de Hotelling: diferenciación horizontal

El modelo de ciudad lineal de Hotelling captura la diferenciación espacial (o de características). Los consumidores están distribuidos uniformemente en $[0,1]$. Dos firmas se ubican en $x_1$ y $x_2$. El consumidor en $z$ tiene costo de transporte $t|z - x_i|$ para comprar en la firma $i$.

El consumidor **indiferente** $\hat{z}$ satisface:

$$p_1 + t|\hat{z} - x_1| = p_2 + t|\hat{z} - x_2|$$

La firma $i$ captura el segmento de consumidores más cercanos a su ubicación. El equilibrio de precios Nash dado las ubicaciones es:

$$p_i^* = c + \frac{t(x_2 - x_1)(2 + x_1 + 1 - x_2)}{3}$$

Con ubicaciones en los extremos $x_1 = 0$, $x_2 = 1$ (máxima diferenciación):

$$p_1^* = p_2^* = c + t$$

El precio de equilibrio supera el costo marginal en $t$ — el parámetro de diferenciación. Mayor diferenciación (mayor $t$, o mayor distancia entre firmas) → mayor poder de mercado → precios más altos.

**La paradoja de Hotelling (mínima diferenciación):** en el juego de dos etapas donde primero se eligen ubicaciones y luego precios, el equilibrio predice máxima aglomeración — ambas firmas se ubican en el centro. La intuición es que alejarse del centro entrega mercado al rival. Esta predicción — estaciones de radio que convergen en géneros similares, partidos políticos que convergen al centro — captura una regularidad importante aunque el resultado estricto es frágil con más de dos firmas.

---

## 6. Colusión y cárteles

### 6.1 La inestabilidad de la colusión

Un cártel maximiza beneficios conjuntos produciendo la cantidad de monopolio $Q^M$ dividida entre los miembros. Pero cada firma tiene incentivo individual a desviarse: producir más de su cuota aumenta sus beneficios a expensas de los demás.

La teoría de juegos indica que los cárteles son inherentemente inestables. Cada miembro individual tiene incentivo a hacer trampa para obtener mayores beneficios en el corto plazo. El trampeo puede llevar al colapso del cártel. Con el colapso, las firmas revertirían a competir, lo que llevaría a menores beneficios. 

La estructura de dilema del prisionero resulta del hecho de que la mitad del beneficio de monopolio es mayor que el beneficio del equilibrio Nash, por un lado, y del hecho de que con desviación unilateral de las cantidades acordadas las firmas pueden aumentar sus beneficios sobre la mitad del monopolio, por otro. 

### 6.2 Colusión sostenible: el juego repetido

En el juego de Cournot repetido infinitamente, la colusión puede sostenerse con estrategia de gatillo (Grim Trigger): cooperar si todos cooperaron en el pasado; producir la cantidad Cournot para siempre si alguien se desvió.

La proposición es que si la tasa de descuento es "suficientemente alta", estas estrategias constituyen un EPS del juego de Cournot repetido infinitamente: en el período $t$, la firma $i$ juega $q_i^C = q^J$ (cantidad de cártel) si $q_{i,t-1} = q^J$ para ambas. Juega $q^*$ (Cournot) si $q_{i,t-1} \neq q^J$ para alguna. 

La condición para que la colusión sea sostenible:

$$\frac{\pi^M/2}{1-\delta} \geq \pi^D + \frac{\delta \pi^C}{1-\delta}$$

donde $\pi^M/2$ es el beneficio de cártel, $\pi^D$ el beneficio de desviación óptima, y $\pi^C$ el beneficio de Cournot. Simplificando:

$$\delta \geq \bar{\delta} = \frac{\pi^D - \pi^M/2}{\pi^D - \pi^C}$$

La colusión es más difícil de sostener cuando:
- **Más firmas:** mayor incentivo a desviarse y menor participación en los beneficios del cártel.
- **Demanda volátil:** dificultad de distinguir desviación de un shock negativo de demanda.
- **Baja frecuencia de interacción:** menor valor del futuro.
- **Asimetría de costos:** las firmas de bajo costo tienen mayor incentivo a desviarse.

### 6.3 Factores que facilitan la colusión

La **transparencia** de precios y cantidades facilita la detección de desviaciones — los mercados opacos dificultan sostener la colusión porque el castigo llega tarde. La **homogeneidad del producto** también facilita la colusión al simplificar el acuerdo.

La **licitación por contratos** (bid rigging) es una forma de colusión donde las firmas se turnan para ganar contratos presentando ofertas no competitivas. Es una de las formas de colusión más investigadas por las autoridades de competencia.

El **liderazgo de precios** es una forma de coordinación tácita sin acuerdo explícito: una firma dominante anuncia su precio y las demás lo siguen. No requiere comunicación directa — solo señales de precios observables.

---

## 7. Síntesis: comparación de modelos

| Modelo | Precio | Cantidad | Beneficio por firma | Bienestar |
|---|---|---|---|---|
| Monopolio | $(a+c)/2$ | $(a-c)/2b$ | $(a-c)^2/4b$ | Mínimo |
| Cournot ($n=2$) | $(a+2c)/3$ | $(a-c)/3b$ | $(a-c)^2/9b$ | Intermedio |
| Stackelberg (líder) | — | $(a-c)/2b$ | $(a-c)^2/8b$ | — |
| Stackelberg (seguidor) | — | $(a-c)/4b$ | $(a-c)^2/16b$ | — |
| Bertrand (homogéneo) | $c$ | $(a-c)/b$ | $0$ | Máximo |
| Comp. perfecta | $c$ | $(a-c)/b$ | $0$ | Máximo |

La jerarquía de precios es: $P^M > P^C > P^S > P^{Bertrand} = MC$.

La jerarquía de bienestar es el inverso: el resultado de Bertrand maximiza el excedente total; el monopolio lo minimiza; Cournot y Stackelberg están en el medio.

**¿Cuándo es aplicable cada modelo?**

La precisión del modelo de Cournot o Bertrand varía de industria en industria, dependiendo de cuán fácil sea ajustar los niveles de output. Si la capacidad y output pueden cambiarse fácilmente, Bertrand es generalmente un mejor modelo de competencia de duopolio. Si el output y la capacidad son difíciles de ajustar, entonces Cournot es generalmente un mejor modelo. 

---

## Referencias

- Cournot, A.A. (1838). *Recherches sur les Principes Mathématiques de la Théorie des Richesses*. Hachette.
- Bertrand, J. (1883). Reseña de Cournot (1838). *Journal des Savants*.
- Stackelberg, H. von (1934). *Marktform und Gleichgewicht*. Springer.
- Singh, N. & Vives, X. (1984). *Price and Quantity Competition in a Differentiated Duopoly*. RAND Journal.
- Hotelling, H. (1929). *Stability in Competition*. EJ.
- Kreps, D. & Scheinkman, J. (1983). *Quantity Precommitment and Bertrand Competition Yield Cournot Outcomes*. Bell Journal.
- Peppal, L., Richards, D. & Norman, G. (2006). *Organización Industrial*. Thompson. Caps. 7–10.
- Tirole, J. (1988). *The Theory of Industrial Organization*. MIT Press. Caps. 5–6.
- Mas-Colell, A., Whinston, M. & Green, J. (1995). *Microeconomic Theory*. Oxford. Cap. 12.
- Vial, B. & Zurita, F. *Microeconomía*. Ediciones UC.