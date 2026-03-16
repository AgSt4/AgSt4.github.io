---
title: "Bienes Públicos y Externalidades"
date: 2026-03-15
draft: false
tags: ["microeconomía", "externalidades", "bienes públicos", "Pigou", "Coase", "Samuelson", "Lindahl", "EAE2110"]
description: "Externalidades: ineficiencia de mercado, impuesto pigouviano, teorema de Coase. Bienes públicos: no-rivalidad y no-excludabilidad, problema del free rider, condición de Samuelson y equilibrio de Lindahl."
---

**Curso:** Microeconomía I (EAE2110) · **Profesora:** María Luisa Vergara  
**Referencia principal:** Vial & Zurita — *Microeconomía* · Mas-Colell, Whinston & Green (1995) cap. 11 · Pigou (1920) · Coase (1960) · Samuelson (1954)

---

## 1. Las fallas de mercado como punto de partida

El primer teorema del bienestar establece que el equilibrio competitivo es Pareto eficiente. Los bienes públicos y las externalidades son las dos categorías más importantes de **falla de mercado** que quiebran este resultado: en su presencia, el equilibrio de mercado no maximiza el bienestar social porque los precios no capturan todos los costos y beneficios relevantes.

Las externalidades y los bienes públicos son típicamente consistentes con la existencia del equilibrio general. Asumiendo continuidad, convexidad y la ley de Walras, el equilibrio general competitivo existirá bajo los supuestos usuales. El problema es con la eficiencia. En presencia de externalidades o bienes públicos, una asignación de equilibrio general puede no ser Pareto eficiente. Porque las externalidades y bienes públicos son típicamente asignados por mecanismos no-mercado, no hay razón para esperar que la asignación de equilibrio sea Pareto eficiente. 

---

## 2. Externalidades

### 2.1 Definición y taxonomía

Una **externalidad** existe cuando la acción de un agente afecta directamente el bienestar o las posibilidades de producción de otro agente, sin que esta afectación esté mediada por el sistema de precios. El elemento crucial es que el efecto no está incorporado en el precio de equilibrio.

Taxonomía:

| Tipo | Dirección | Ejemplo |
|---|---|---|
| **Negativa de producción** | Empresa → tercero | Planta química contamina río aguas abajo |
| **Positiva de producción** | Empresa → tercero | Apicultor beneficia a granjero vecino |
| **Negativa de consumo** | Consumidor → tercero | Fumador en espacio público |
| **Positiva de consumo** | Consumidor → tercero | Propietario cuida su jardín y mejora el vecindario |

### 2.2 La ineficiencia de mercado con externalidades

**Caso: externalidad negativa de producción**

Una firma produce $q$ generando un costo externo $d(q)$ sobre terceros. El mercado competitivo iguala precio a costo marginal privado:

$$p = CMgP(q^M)$$

El óptimo social iguala precio a costo marginal social:

$$p = CMgS(q^*) = CMgP(q^*) + d'(q^*)$$

Como $d'(q) > 0$, se tiene $CMgS > CMgP$ para cualquier $q > 0$, lo que implica $q^M > q^*$: el mercado produce en exceso relativo al óptimo social.

El mercado determina $Q^M$ tal que el costo marginal privado iguala el beneficio marginal privado. Pero este resultado no es Pareto eficiente porque ignora el costo marginal del daño. El nivel cero de contaminación no es necesariamente deseable — lo óptimo es internalizar el daño, no eliminarlo. 

La pérdida irrecuperable es el área entre $CMgS$ y $CMgP$ para las unidades $[q^*, q^M]$ — el exceso de costo social sobre beneficio social en ese rango de producción.

**Caso: externalidad positiva de consumo**

Un agente genera un beneficio externo $b(q)$ al consumir $q$. El mercado iguala su beneficio marginal privado al precio, sin considerar el beneficio que genera a terceros. La cantidad de mercado $q^M < q^*$ — subprovisión. El precio implícito del bien es demasiado alto relativo al costo marginal social.

### 2.3 El impuesto pigouviano

Pigou (1920) abogó por impuestos iguales al daño marginal sobre bienes producidos y consumidos que involucran externalidades negativas. 

El **impuesto pigouviano** $t$ corrige la externalidad haciendo que el agente privado internalice el costo (o beneficio) externo. Para una externalidad negativa, el impuesto óptimo se fija igual al daño marginal en el óptimo:

$$t^* = d'(q^*) = CMgS(q^*) - CMgP(q^*)$$

Con este impuesto, la condición de optimización privada $p = CMgP(q) + t$ coincide con la condición social $p = CMgS(q)$. La firma internaliza el costo externo que impone sobre terceros.

Para una externalidad positiva, el instrumento análogo es un **subsidio pigouviano** $s^* = b'(q^*)$: reducir el precio efectivo que enfrenta el agente para inducir mayor provisión.

**Limitaciones del enfoque pigouviano:**

Para implementar el impuesto pigouviano se necesita conocer las formas de la curva de beneficio marginal, del costo marginal privado y del daño marginal. La medición del daño marginal es especialmente problemática porque no se puede usar preferencias reveladas — no hay mercado, que es precisamente por qué existe la externalidad. 

Adicionalmente, el impuesto pigouviano no provee incentivo para instalar tecnologías de reducción — la firma simplemente paga el impuesto por cada unidad producida. En equilibrio es de segundo mejor porque no incentiva la adopción de tecnologías que reducen el daño por unidad producida. 

### 2.4 Regulación por cantidad: estándares y permisos transables

Alternativa al precio pigouviano: el regulador fija directamente la cantidad de externalidad permitida.

**Estándar de emisión:** límite directo sobre la cantidad de contaminación. Garantiza el objetivo cuantitativo pero no asegura que se alcance al menor costo social — distintas firmas tienen costos marginales de abatimiento diferentes.

**Permisos transables (cap-and-trade):** si se puede crear el mercado faltante, ese mercado implementará el nivel óptimo de la externalidad. El gobierno crea un mercado para el derecho a contaminar, y una vez creado el mercado faltante, el mercado funciona de forma que la asignación de equilibrio es Pareto eficiente. 

El sistema de permisos crea la eficiencia del impuesto pigouviano pero con la ventaja de garantizar la cantidad total de emisiones (el "cap"). Las firmas con costos de abatimiento bajos reducen emisiones y venden permisos; las de costos altos compran permisos. El equilibrio iguala los costos marginales de abatimiento entre todas las firmas — condición de eficiencia.

### 2.5 El teorema de Coase

Coase (1960) argumentó que el problema de las externalidades es fundamentalmente un problema de derechos de propiedad mal definidos — no de fallas de mercado que requieren intervención.

**Teorema de Coase (versión eficiencia):** si los derechos de propiedad están claramente asignados y los costos de transacción son cero, las partes negociarán de forma que se alcanza el nivel óptimo de la externalidad, independientemente de quién reciba los derechos. 

**Teorema de Coase (versión invarianza):** La asignación eficiente es la misma sin importar si los derechos se asignan a la víctima o al generador de la externalidad — solo cambia la distribución del ingreso.

**Ilustración con dos agentes:**

Firma genera contaminación $h$ que daña al consumidor. El óptimo social es $h^*$ que maximiza el excedente conjunto $\pi(h) + v(-h)$, donde $\pi$ son los beneficios de la firma y $v$ la utilidad del consumidor.

- Si el consumidor tiene derecho a un ambiente sin contaminación: la firma ofrece compensación por contaminar. Negocian hasta $h^*$ donde la ganancia marginal de la firma iguala el daño marginal al consumidor.
- Si la firma tiene derecho a contaminar libremente: el consumidor paga a la firma para que reduzca la contaminación. Negocian hasta $h^*$ donde el ahorro en daño del consumidor iguala el costo de oportunidad de la firma.

En ambos casos, $h^*$ es el resultado — la eficiencia es invariante a la asignación de derechos.

**Limitaciones del teorema de Coase:**

Para ser lógicamente correcto se necesitan supuestos restrictivos. Primero, los efectos secundarios deben ser bilaterales — aplica a casos que Coase investigó (ganado pisotea campos de un granjero, un edificio bloquea luz solar). No aplica a la contaminación en general donde hay múltiples víctimas. 

Las limitaciones prácticas principales son:

- **Costos de transacción positivos:** identificar a las partes, negociar y hacer cumplir el acuerdo tiene costos que pueden superar los beneficios.
- **Múltiples partes:** con muchos afectados, el problema del free rider emerge en la negociación — cada víctima espera que otros paguen.
- **Problema del hold-up:** una vez que otras partes han aceptado, la última puede exigir más compensación.
- **Asimetría de información:** las partes pueden mentir sobre la magnitud del daño o el beneficio.

El propio Coase escribió que mientras lo que se conoció como el teorema de Coase exploró las implicancias de costos de transacción cero, su intención real era usar ese constructo como trampolín para entender el mundo real de costos de transacción positivos, corporaciones, sistemas legales y acciones gubernamentales. 

### 2.6 La externalidad como mercado faltante

El problema de externalidades es frecuentemente llamado un problema de "mercado faltante". Si el mercado faltante se puede crear, ese mercado implementará el nivel óptimo de la externalidad. 

Esta perspectiva unifica las soluciones: el impuesto pigouviano crea el precio que el mercado faltante habría generado; el permiso transable crea directamente el mercado faltante; la solución de Coase negocia directamente los derechos que ese mercado asignaría. La raíz del problema es que los derechos de propiedad sobre el bien ambiental no están asignados — ningún agente puede cobrar por su uso.

---

## 3. Bienes públicos

### 3.1 Definición y clasificación

Un **bien público** se define por dos propiedades técnicas:

- **No-rivalidad:** el consumo del bien por un individuo no reduce la cantidad disponible para otros. La utilidad marginal de proveer el bien a un consumidor adicional es cero — el costo marginal de servir a un consumidor adicional es cero.
- **No-excludabilidad:** es imposible (o prohibitivamente costoso) excluir a individuos del consumo del bien una vez provisto.

La defensa nacional es un bien público: provee beneficios a todos los residentes de un país, es no-excluyente porque no puedes excluir a una persona de ser protegida por el ejército, y es no-rival porque el consumo de una persona no disminuye la efectividad de la defensa para otros. 

La clasificación completa de bienes:

| | **Rival** | **No-rival** |
|---|---|---|
| **Excluible** | Bien privado (alimento, ropa) | Bien de club (streaming, peaje) |
| **No-excluible** | Bien común (pesca, congestión) | Bien público puro (defensa, faro) |

Los bienes de club son no-rivales hasta el punto de congestión. Los bienes comunes son rivales pero no-excluibles — la "tragedia de los comunes" surge de la sobreexplotación.

### 3.2 El problema del free rider

Ningún grupo voluntariamente pagaría por el bien público. Pueden acceder al bien público incluso si no contribuyen — este es el equilibrio Nash. No es Pareto eficiente. El resultado de mercado lleva a la subprovisión del bien público. 

El problema del free rider puede formalizarse como un dilema del prisionero. Dos agentes deben decidir si contribuyen $c$ al bien público que genera beneficio $b > c$ para cada uno:

|  | Contribuye | No contribuye |
|---|---|---|
| **Contribuye** | $(b-c, b-c)$ | $(-c, b)$ |
| **No contribuye** | $(b, -c)$ | $(0, 0)$ |

Si $b > c$ pero $b - c < b$ (es decir, siempre), la estrategia dominante para cada agente es no contribuir — esperando que el otro provea el bien. El equilibrio Nash es $(0,0)$, que es Pareto-inferior a $(b-c, b-c)$.

La severidad del problema del free rider aumenta con el número de agentes: mientras más agentes haya, menor es la probabilidad de que cada uno sea pivotal, y mayor la tentación de esperar la contribución de los demás.

La condición de Samuelson para la provisión óptima de bienes públicos no se cumple debido al free riding. Los modelos de teoría de juegos (dilema del prisionero) ilustran cómo los incentivos individuales llevan a resultados colectivos subóptimos. El grado de subprovisión está influenciado por el número de potenciales beneficiarios, el costo de provisión y el valor percibido del bien público. 

### 3.3 La condición de Samuelson

¿Cuál es el nivel óptimo de provisión de un bien público? Samuelson (1954) derivó la condición de eficiencia para una economía con $I$ consumidores y un bien público $G$ cuya provisión cuesta $c(G)$.

Con utilidades $U^i(x^i, G)$ y restricción de recursos $\sum_i x^i + c(G) = \bar{\omega}$, el planificador social maximiza el bienestar. Las condiciones de primer orden dan la **condición de Samuelson**:

$$\sum_{i=1}^I TMS^i_{Gx} = TMT_{Gx} = c'(G)$$

La suma de las tasas marginales de sustitución entre el bien público y el privado debe igualar el costo marginal de provisión. Esta es la regla de eficiencia del bien público: a diferencia del bien privado donde $TMS^i = p$ para cada $i$, el bien público requiere que la suma de todas las TMS individuales iguale el costo marginal.

La intuición es que el bien público es consumido simultáneamente por todos los agentes, por lo que el beneficio marginal social de una unidad adicional es la suma de los beneficios marginales individuales — no el máximo ni el promedio, sino la suma.

### 3.4 El equilibrio de Lindahl

El equilibrio de Lindahl implementa la condición de Samuelson mediante **precios personalizados** para el bien público. La participación fiscal de cada agente en el costo del bien público se convierte en su precio individualizado. El equilibrio es el conjunto de precios tal que todas las personas demandan el mismo nivel del bien público. 

Formalmente, asignar a cada agente $i$ una participación $\tau^i$ en el costo tal que $\sum_i \tau^i = 1$. El agente $i$ elige $G$ para maximizar $U^i(x^i, G)$ sujeto a $x^i + \tau^i G = \omega^i$. El **equilibrio de Lindahl** es el par $(\tau^*, G^*)$ tal que todos los agentes demandan $G^*$ a las participaciones $\tau^*$.

El equilibrio de Lindahl resulta ser que implementa la asignación Pareto óptima del bien público.  En equilibrio, $\tau^{*i} = TMS^i_{Gx} / c'(G^*)$ — la participación de cada agente es proporcional a su valoración marginal, y la condición de Samuelson se cumple automáticamente.

**El problema de implementación:** la diferencia clave entre los equilibrios de Lindahl y los estándar es que no existe mecanismo descentralizado para llegar a los precios — no hay fuerzas de mercado. Cada agente tiene interés en fingir que valora poco el bien público para pagar menos. Cada agente tiene incentivos a revelar estratégicamente sus preferencias. 

Este es el **problema de revelación de preferencias**: para calcular los precios de Lindahl se necesita conocer $TMS^i$ de cada agente, pero los agentes tienen incentivos a subreportar su valoración.

### 3.5 Mecanismos de revelación y provisión privada

Se han propuesto distintos mecanismos para resolver el problema de revelación:

**Mecanismo de Clarke-Groves (mecanismo VCG):** diseñado para incentivar la revelación veraz. Cada agente reporta su valoración y paga un "impuesto de Clarke" igual al daño que impone sobre los demás. Bajo este mecanismo, reportar verazmente es la estrategia dominante. El costo es que el mecanismo puede no ser presupuestalmente balanceado — el recaudador puede tener superávit o déficit.

**Provisión voluntaria privada:** los agentes contribuyen voluntariamente al bien público. El resultado de Nash de este juego de contribuciones es subóptimo. Sin embargo, con suficiente heterogeneidad y preferencias altruistas, la subprovisión puede ser moderada. El modelo de "warm glow" de Andreoni (1990) — ahora visto como el modelo central de contribuciones caritativas — muestra que los agentes pueden derivar utilidad directa del acto de dar, no solo del nivel total del bien público. 

**Crowdfunding como solución coasiana:** uno de los mecanismos coasianos más puros hoy es el crowdfunding en internet, donde las reglas son ejecutadas por algoritmos computacionales y contratos legales. En Kickstarter, cada financiador autoriza un cargo de tarjeta de crédito pero no se transfiere dinero hasta que se alcanza la meta de financiamiento. La automatización y el internet reducen enormemente los costos de transacción para agregar recursos. 

---

## 4. Políticas públicas en presencia de externalidades y bienes públicos

### 4.1 El menú de instrumentos

Para externalidades negativas, los instrumentos disponibles se ordenan por su relación con el sistema de precios:

**Instrumentos de precio:**
- Impuesto pigouviano: correcto en teoría, difícil de calibrar.
- Subsidio a la reducción: equivalente al impuesto en incentivos pero con distribución diferente.

**Instrumentos de cantidad:**
- Estándares de emisión: garantizan el objetivo pero son ineficientes si los costos difieren entre firmas.
- Permisos transables: combinan certeza sobre la cantidad con eficiencia distributiva.

**Asignación de derechos:**
- Solución coasiana: eficiente si los costos de transacción son bajos y las partes son pocas.

Para bienes públicos:

- Provisión pública directa con financiamiento tributario.
- Subsidios a la provisión privada (internaliza la externalidad positiva).
- Mecanismos de revelación de preferencias.
- Regulación de bienes comunes (cuotas de pesca, licencias de extracción).

### 4.2 La comparación precio vs. cantidad bajo incertidumbre

Weitzman (1974) demostró que bajo incertidumbre sobre los costos de abatimiento, la elección entre instrumentos de precio (impuesto) y cantidad (permiso) depende de la forma de las curvas de beneficio y costo marginales:

- Si la curva de beneficio marginal es más plana que la de costo marginal: los instrumentos de precio son superiores — el error en la cantidad tiene costo pequeño pero el error en el precio tiene costo grande.
- Si la curva de beneficio marginal es más inclinada: los instrumentos de cantidad son superiores.

Para el cambio climático, la curva de daño marginal es relativamente plana en el corto plazo pero se vuelve muy inclinada cerca de los umbrales críticos — lo que sugiere preferir instrumentos de cantidad (compromisos de emisiones) cuando hay riesgo de cruzar umbrales irreversibles.

### 4.3 El problema de doble dividendo

El impuesto pigouviano genera ingresos fiscales que pueden usarse para reducir otros impuestos distorsionadores. La hipótesis del **doble dividendo** sugiere que el impuesto ambiental puede mejorar el bienestar por dos vías: corregir la externalidad (primer dividendo) y permitir reducir la distorsión de otros impuestos (segundo dividendo).

La evidencia empírica es mixta: el doble dividendo en su forma fuerte (los beneficios del segundo dividendo superan los costos de eficiencia del impuesto ambiental) generalmente no se sostiene, pero la forma débil (el impuesto ambiental es menos costoso que otros impuestos que recaudan lo mismo) sí tiene apoyo.

---

## 5. Síntesis: fallas de mercado y sus correcciones

| Falla | Causa | Consecuencia de mercado | Instrumento corrector |
|---|---|---|---|
| **Externalidad negativa** | Precio < costo social | Sobreproducción | Impuesto pigouviano, permiso transable |
| **Externalidad positiva** | Precio > beneficio social | Subproducción | Subsidio pigouviano |
| **Bien público** | No-rivalidad + no-excludabilidad | Subprovisión, free rider | Provisión pública, subsidio, mecanismo VCG |
| **Bien común** | Rivalidad + no-excludabilidad | Sobreexplotación | Cuotas, derechos de propiedad privada |
| **Derechos mal definidos** | Costos de transacción altos | Externalidades no internalizadas | Asignación clara de derechos (Coase) |

El análisis de bienes públicos y externalidades cierra el círculo de la microeconomía de primer año: los mercados son eficientes cuando los precios reflejan completamente los costos y beneficios sociales; cuando no lo hacen, la intervención puede mejorar el bienestar — pero el diseño del instrumento corrector requiere información que el propio problema de la falla de mercado hace difícil obtener.

---

## Referencias

- Pigou, A.C. (1920). *The Economics of Welfare*. Macmillan.
- Coase, R. (1960). *The Problem of Social Cost*. Journal of Law and Economics.
- Samuelson, P. (1954). *The Pure Theory of Public Expenditure*. REStat.
- Lindahl, E. (1919). *Just Taxation — A Positive Solution*. En Musgrave & Peacock (eds.).
- Weitzman, M. (1974). *Prices vs. Quantities*. RES.
- Andreoni, J. (1990). *Impure Altruism and Donations to Public Goods*. EJ.
- Greenwald, B. & Stiglitz, J. (1986). *Externalities in Economies with Imperfect Information*. QJE.
- Mas-Colell, A., Whinston, M. & Green, J. (1995). *Microeconomic Theory*. Oxford. Cap. 11.
- Vial, B. & Zurita, F. *Microeconomía*. Ediciones UC.