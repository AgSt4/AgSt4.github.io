---
title: "Poder de Mercado y Monopolio"
date: 2026-03-15
draft: false
tags: ["microeconomía", "monopolio", "poder de mercado", "discriminación de precios", "monopolio natural", "Lerner", "EAE2110", "EAE2130"]
description: "Fuentes del poder de mercado, optimización del monopolista, índice de Lerner, pérdida irrecuperable, discriminación de precios de primer, segundo y tercer grado, monopolio natural y regulación."
---

**Cursos:** Microeconomía I (EAE2110) · Competencia y Mercados (EAE2130)  
**Referencia principal:** Vial & Zurita — *Microeconomía* · Nicholson (2008) · Peppal, Richards & Norman (2006) · Tirole (1988)

---

## 1. El poder de mercado: definición y fuentes

### 1.1 ¿Qué es el poder de mercado?

Una firma tiene **poder de mercado** cuando puede influir sobre el precio de su producto — cuando enfrenta una curva de demanda con pendiente negativa en lugar de una perfectamente elástica. El caso extremo es el **monopolio**: un único vendedor en el mercado sin sustitutos cercanos.

La brecha entre precio y costo marginal se expresa frecuentemente como markup o índice de Lerner, que mide el grado de poder de mercado. 

### 1.2 Fuentes del poder de mercado

El poder de mercado surge de **barreras de entrada** que impiden a rivales competir:

**Barreras estructurales:**
- **Economías de escala:** costos medios decrecientes hacen que una sola firma sea más eficiente que muchas — el caso del monopolio natural.
- **Ventajas de costo:** acceso privilegiado a insumos, tecnología superior, curvas de aprendizaje.
- **Costos hundidos:** inversiones irrecuperables que disuaden la entrada (planta específica, I+D).

**Barreras legales e institucionales:**
- **Patentes y derechos de autor:** protegen innovaciones durante un plazo determinado.
- **Licencias y concesiones:** el gobierno otorga derechos exclusivos (servicios públicos, espectro radioeléctrico).
- **Regulación de entrada:** industrias con requisitos de habilitación costosos.

**Barreras estratégicas:**
- **Exceso de capacidad:** la firma incumbente construye capacidad excedente para amenazar crediblemente con guerra de precios ante la entrada.
- **Diferenciación de productos:** la lealtad de marca eleva el costo de cambio para los consumidores.
- **Contratos exclusivos:** acuerdos que bloquean el acceso de rivales a distribuidores o insumos.

---

## 2. El monopolista de precio único

### 2.1 La condición de maximización de beneficios

El monopolista elige $q$ para maximizar:

$$\pi = p(q) \cdot q - C(q)$$

donde $p(q)$ es la demanda inversa. La CPO es:

$$\frac{d\pi}{dq} = p(q) + q \cdot p'(q) - C'(q) = MR(q) - MC(q) = 0$$

El **ingreso marginal** tiene dos componentes: el precio recibido por la unidad adicional ($p$) más el efecto precio sobre las unidades existentes ($qp' < 0$). Dado que $p' < 0$, se tiene $MR < p$ para todo $q > 0$.

Con demanda lineal $p = a - bq$:

$$TR = aq - bq^2 \implies MR = a - 2bq$$

La curva de $MR$ tiene la misma ordenada al origen que la demanda pero el doble de pendiente. El monopolista maximiza en $MR = MC$, produciendo $q^M < q^{CP}$ y cobrando $p^M > MC$.

### 2.2 El índice de Lerner

El **índice de Lerner** mide el markup como fracción del precio:

$$L = \frac{p - MC}{p} \in [0, 1]$$

El índice de Lerner oscila entre 0 (competencia perfecta, donde $P = MC$) y 1 (poder de mercado extremo con markup muy grande). Para el monopolista de precio único, el índice se relaciona con la elasticidad de demanda: $L = 1/|\varepsilon_D|$ en la cantidad elegida. 

De la CPO: $MR = p(1 + 1/\varepsilon_D) = MC$, despejando:

$$\frac{p - MC}{p} = -\frac{1}{\varepsilon_D} = \frac{1}{|\varepsilon_D|}$$

Una firma con demanda altamente elástica (muchos sustitutos) tiene poco poder de mercado y un índice de Lerner bajo. Una firma con demanda inelástica (pocos sustitutos) puede mantener un markup mayor. 

**Corolario:** el monopolista siempre opera en el tramo elástico de la demanda ($|\varepsilon_D| > 1$, $L < 1$). Si estuviera en el tramo inelástico, $MR < 0 < MC$ — podría subir el precio y aumentar tanto el ingreso como reducir los costos simultáneamente.

### 2.3 La regla de pricing óptimo

Reescribiendo la condición $MR = MC$:

$$p = \frac{MC}{1 + 1/\varepsilon_D} = \frac{MC \cdot |\varepsilon_D|}{|\varepsilon_D| - 1}$$

El factor $|\varepsilon_D|/(|\varepsilon_D| - 1) > 1$ es el **multiplicador de markup**. Crece cuando la demanda es menos elástica — mercados con pocos sustitutos permiten precios más altos sobre el costo marginal.

### 2.4 Análisis de bienestar: la pérdida irrecuperable del monopolio

Comparando con el óptimo competitivo ($p = MC$):

- El monopolista produce $q^M < q^{CP}$: hay unidades donde $p^D > MC$ que no se producen.
- El monopolista produce demasiado poco output — la pérdida irrecuperable estándar. Esto genera ineficiencia asignativa: el mix equivocado de bienes se produce; demasiado poco del bien monopolizado y demasiado de otros bienes. Hay redistribución de riqueza de los consumidores a los dueños del monopolio. 

El desglose del bienestar:

$$\Delta EC = -(A + B) \quad \Delta EP = +(A - C) \quad DWL = -(B + C)$$

donde $A$ es el rectángulo de transferencia de excedente (de consumidores al monopolista) y $B + C$ es el triángulo de Harberger — pérdida irrecuperable neta.

La transferencia de bienestar de consumidores al dueño del monopolio podría contrarrestarse con redistribución gubernamental; así que quizás no debería considerarse como un golpe contra el monopolio. El problema real es el DWL — valor que nadie captura. 

**La magnitud del DWL:** con demanda lineal $p = a - bq$ y $MC = c$:

$$DWL = \frac{1}{2} \cdot (p^M - MC) \cdot (q^{CP} - q^M) = \frac{(a-c)^2}{8b}$$

La pérdida es proporcional al cuadrado de la diferencia entre precio competitivo y costo marginal — mercados donde el markup es grande tienen pérdidas sociales cuadráticamente mayores.

---

## 3. Discriminación de precios

La discriminación de precios requiere tres condiciones: poder de mercado, capacidad de segmentar compradores (por tipo o cantidad), y ausencia de arbitraje entre segmentos.

### 3.1 Discriminación de primer grado (perfecta)

La discriminación perfecta de precios elimina la pérdida irrecuperable y produce la cantidad eficiente, pero el monopolista captura todo el excedente del consumidor — los consumidores no están mejor que siendo excluidos del mercado. 

El monopolista cobra a cada consumidor exactamente su disposición a pagar $p^D(q)$. El ingreso marginal coincide con la demanda inversa: $MR = p^D(q)$. La condición de optimización da $q^{PD} = q^{CP}$ — la cantidad eficiente.

El bienestar:
- $DWL = 0$: todas las unidades donde $p^D > MC$ se producen.
- $EC = 0$: el monopolista extrae todo el excedente del consumidor.
- $EP = EC^{CP} + EP^{CP}$: el excedente total se redistribuye completamente al monopolista.

La discriminación de primer grado siempre tendrá como resultado un nivel de output Pareto eficiente ya que la disposición marginal a pagar iguala el costo marginal. 

En la práctica es irrealizable (requiere conocer perfectamente cada disposición a pagar), pero aproximaciones incluyen subastas, negociación individual y algoritmos de personalización de precios.

### 3.2 Discriminación de segundo grado

La discriminación de segundo grado — también llamada **precios no lineales** o **self-selection** — no requiere identificar el tipo de cada consumidor. El monopolista ofrece un **menú de contratos** y los consumidores se autoseleccionan.

**Tarifa de dos partes:** el consumidor paga un cargo fijo $F$ (por acceder al mercado) más un precio por unidad $p$. El monopolista elige $F$ y $p$ para maximizar beneficios. Con consumidores homogéneos, el óptimo es $p = MC$ (precio eficiente) y $F = CS(p)$ (extrae todo el excedente). Con consumidores heterogéneos, el problema se vuelve el de diseño de contratos bajo selección adversa — la tarifa óptima equilibra la extracción de renta con la eficiencia.

**Descuentos por cantidad:** el precio por unidad cae con la cantidad adquirida. Los consumidores de alta valoración compran más a precios más bajos; los de baja valoración compran menos a precios más altos. La firma extrae más excedente que con precio único sin necesitar identificar los tipos.

**Bundling (venta en paquete):** vender bienes en paquetes puede ser más rentable que venderlos por separado cuando las valoraciones están correlacionadas negativamente. Si el consumidor A valora el bien 1 en $\$10$ y el bien 2 en $\$2$, y el consumidor B los valora en $\$2$ y $\$10$ respectivamente, venderlos juntos a $\$12$ extrae más excedente que venderlos por separado.

### 3.3 Discriminación de tercer grado

El monopolista identifica grupos de consumidores con distintas elasticidades de demanda y cobra precios distintos a cada grupo (estudiantes vs. adultos, mercado doméstico vs. exportación).

Maximizando beneficios con dos segmentos $\{1, 2\}$:

$$\max_{q_1, q_2} p_1(q_1)q_1 + p_2(q_2)q_2 - C(q_1 + q_2)$$

Las CPO dan:

$$MR_1(q_1) = MR_2(q_2) = MC(q_1 + q_2)$$

El ingreso marginal debe igualarse entre segmentos y al costo marginal. Usando la relación $MR_i = p_i(1 + 1/\varepsilon_i)$:

$$p_1\left(1 + \frac{1}{\varepsilon_1}\right) = p_2\left(1 + \frac{1}{\varepsilon_2}\right)$$

Si $|\varepsilon_1| > |\varepsilon_2|$ (segmento 1 más elástico), entonces $p_1 < p_2$: el segmento más elástico paga menos. El grupo menos elástico (pocas alternativas) soporta mayor precio. 

**Análisis de bienestar de la discriminación de tercer grado:**

El excedente total puede subir o bajar relativo al precio uniforme del monopolio. Sube cuando el segmento de menor precio expande el output suficientemente para compensar cualquier reducción en el segmento de mayor precio. Cae cuando la segmentación principalmente redistribuye el excedente existente sin generar nuevos intercambios. Una regla útil: la discriminación de tercer grado tiende a aumentar el bienestar cuando abre un segmento de mercado que habría sido completamente excluido bajo precio uniforme. 

---

## 4. El monopolio natural y la regulación

### 4.1 Definición y origen

Un **monopolio natural** existe cuando la función de producción tiene rendimientos crecientes a escala en todo el rango de demanda relevante — el costo medio es decreciente en todo el output que el mercado demanda. Una sola firma puede abastecer el mercado a menor costo que dos o más firmas divididas.

Los monopolios naturales típicamente capturan economías de escala porque la cantidad maximizadora de beneficios está en la porción descendente de su curva de costo medio total de largo plazo. Estas empresas usualmente tienen costos de arranque extremadamente altos pero costo marginal de producción muy bajo. Los proveedores de electricidad son un ejemplo primario. 

### 4.2 El problema regulatorio

El precio es alto: los consumidores pierden bienestar y la sociedad enfrenta pérdidas irrecuperables. Si la competencia fuera posible, el precio se fijaría al costo marginal. Pero hay un problema mayor con este resultado: el precio está por debajo de los costos medios, y cualquier empresa que cobre el precio competitivo sería forzada a salir del negocio. El monopolio natural se considera una falla de mercado ya que no hay buena solución de mercado. 

Las opciones regulatorias:

**Precio al costo marginal:** $p^{MC} = MC$ — eficiente asignativamente pero genera pérdidas para la firma (ya que $MC < CMe$ en el monopolio natural). Requiere subsidio fiscal para mantener la firma operando.

**Precio al costo medio:** $p^{AC} = CMe$ — la firma cubre exactamente sus costos (beneficio económico cero). Hay DWL residual (menor que el monopolio no regulado) pero la firma es autosustentable. Es la regulación de **tasa de retorno justa**.

**Precio de Ramsey-Boiteux:** si la firma produce múltiples bienes, la regulación óptima fija precios que minimizan la pérdida de eficiencia sujeta a la restricción de beneficio cero. Los markups sobre costo marginal son inversamente proporcionales a las elasticidades — la misma regla de Ramsey de impuestos óptimos.

**Franquicia competitiva (Demsetz):** en vez de regular, el gobierno puede subastar el derecho a ser el monopolio natural — la competencia por el mercado reemplaza la competencia en el mercado. El licitante que ofrece el menor precio gana la concesión. Con suficientes postores, el precio converge al costo medio.

### 4.3 Regulación por incentivos

La regulación de tasa de retorno tiene el problema del **efecto Averch-Johnson**: si la firma puede obtener retorno garantizado sobre su capital, tiene incentivo a usar exceso de capital — sobreacumula el factor cuyo costo le es reembolsado. Los mecanismos de regulación por incentivos buscan resolver este problema:

**Price cap:** el regulador fija un techo de precio que cae en el tiempo a tasa $X$ (capturando ganancias de productividad esperadas). La firma retiene las ganancias si es más eficiente que lo esperado — tiene incentivos a reducir costos.

**Yardstick competition:** el precio permitido se basa en el costo de firmas comparables, no de la firma regulada misma. Elimina el incentivo a inflar costos.

---

## 5. Monopolio con demandas relacionadas

### 5.1 Sustitutos y complementos

Cuando el monopolista vende múltiples bienes con demandas relacionadas, la fijación óptima de precios debe internalizar los efectos cruzados.

Con dos bienes $i$ y $j$, la condición de maximización de beneficios para el bien $i$:

$$MR_i = p_i + q_i \frac{\partial p_i}{\partial q_i} + q_j \frac{\partial p_j}{\partial q_i} = MC_i$$

El tercer término captura el efecto cruzado: si los bienes son **sustitutos** ($\partial p_j / \partial q_i < 0$), producir más de $i$ reduce el ingreso del bien $j$. El monopolista multiproducto fija precios más altos en sustitutos de lo que haría un monopolista que solo vende uno de ellos — internaliza el canibalismo.

Si los bienes son **complementos** ($\partial p_j / \partial q_i > 0$), producir más de $i$ eleva el ingreso de $j$. El monopolista tiene incentivo a fijar precios más bajos en el bien complementario — subsidia las "navajas" para vender más "cuchillas" (la estrategia de Gillette).

### 5.2 El monopolio de bien durable

El **problema de Coase** surge cuando el monopolio vende un bien durable: los consumidores anticipan que el monopolista reducirá el precio en el futuro para vender a quienes tienen menor disposición a pagar. Si los consumidores esperan precios futuros más bajos, esperan en vez de comprar hoy — el monopolista pierde poder de mercado sobre sí mismo.

En el límite (transacciones instantáneas), el precio del monopolista converge al competitivo — la **conjetura de Coase**. Las soluciones incluyen: comprometerse a no reducir precios (garantía de precio), arrendar en vez de vender, o destruir capacidad productiva para comprometerse a no expandir output.

---

## 6. Síntesis: comparación entre estructuras de mercado

| Dimensión | Competencia perfecta | Monopolio precio único | Monopolio discriminador (1°) |
|---|---|---|---|
| Condición de optimización | $P = MC$ | $MR = MC$, $P > MC$ | $P^D(q) = MC$ |
| Cantidad | $Q^{CP}$ (máxima) | $Q^M < Q^{CP}$ | $Q^{CP}$ |
| Precio | $P = MC$ | $P^M > MC$ | Variable (= DAP de cada consumidor) |
| Excedente del consumidor | Máximo | Reducido | Cero |
| Pérdida irrecuperable | Cero | $B + C > 0$ | Cero |
| Índice de Lerner | 0 | $1/|\varepsilon_D| > 0$ | Variable |
| Eficiencia asignativa | Sí | No | Sí |
| Eficiencia distributiva | Sí | Transferencia a monopolista | No (monopolista captura todo) |

---

## Referencias

- Vial, B. & Zurita, F. *Microeconomía*. Ediciones UC.
- Nicholson, W. (2008). *Teoría Microeconómica*. Cengage. Cap. 15–16.
- Peppal, L., Richards, D. & Norman, G. (2006). *Organización Industrial*. Thompson. Caps. 3–6.
- Tirole, J. (1988). *The Theory of Industrial Organization*. MIT Press. Caps. 1–3.
- Lerner, A. (1934). *The Concept of Monopoly and the Measurement of Monopoly Power*. RES.
- Averch, H. & Johnson, L. (1962). *Behavior of the Firm under Regulatory Constraint*. AER.
- Demsetz, H. (1968). *Why Regulate Utilities?* Journal of Law and Economics.
- Coase, R. (1972). *Durability and Monopoly*. Journal of Law and Economics.
- Mas-Colell, A., Whinston, M. & Green, J. (1995). *Microeconomic Theory*. Oxford. Cap. 12.