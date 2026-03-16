---
title: "Mercado del Trabajo"
date: 2026-03-15
draft: false
tags: ["macroeconomía", "trabajo", "desempleo", "salarios de eficiencia", "búsqueda y emparejamiento", "EAE2210"]
description: "Tasa natural, desempleo friccional, rigideces salariales, modelo de Shapiro-Stiglitz y modelo de búsqueda y emparejamiento de Mortensen-Pissarides."
---

**Curso:** Macroeconomía I (EAE2210) · **Profesor:** Emilio Depetris-Chauvin  
**Referencia principal:** De Gregorio (2007) cap. 10 · Pissarides (2000) · Cahuc, Carcillo & Zylberberg (2014)

---

## 1. Definiciones y conceptos básicos

El mercado del trabajo en macroeconomía se analiza en términos de stocks y flujos. Los stocks relevantes son:

- **Ocupados ($E$):** trabajan al menos una hora en el período de referencia.
- **Desocupados ($U$):** no trabajan, están disponibles y buscan activamente empleo.
- **Inactivos ($I$):** no trabajan ni buscan trabajo.
- **Fuerza laboral ($L$):** $L = E + U$.

Las tasas de interés son:

$$\text{Tasa de desempleo} = \frac{U}{L}, \qquad \text{Tasa de participación} = \frac{L}{PET}$$

donde $PET$ es la población en edad de trabajar.

El mercado del trabajo no vacía instantáneamente. Incluso en equilibrio existe desempleo positivo por razones estructurales e institucionales. La pregunta central del capítulo es: **¿por qué en equilibrio hay desempleo involuntario persistente?**

---

## 2. Tasa natural de desempleo y desempleo friccional

### 2.1 El modelo de flujos de Friedman-Phelps

La tasa natural de desempleo ($u^*$) es aquella consistente con el equilibrio del mercado laboral en el largo plazo, donde las presiones inflacionarias son constantes. No es una constante biológica — varía entre países y en el tiempo según factores estructurales.

En estado estacionario, los flujos hacia el desempleo igualan los flujos hacia el empleo:

$$s \cdot E = f \cdot U$$

donde $s$ es la tasa de separación (fracción de ocupados que pierde el empleo por unidad de tiempo) y $f$ es la tasa de encontrar empleo. Dado que $E = L - U$:

$$s(L - U) = fU \implies u^* = \frac{U}{L} = \frac{s}{s + f}$$

La tasa natural sube cuando aumenta $s$ (más despidos, más rotación) o cae $f$ (más difícil encontrar empleo). Las políticas que afectan $u^*$ son las que alteran estos flujos: indemnizaciones por despido, seguros de desempleo, costo de búsqueda.

### 2.2 Desempleo friccional

El desempleo friccional surge porque encontrar empleo toma tiempo incluso cuando hay vacantes disponibles. Las causas son:

- **Información imperfecta:** trabajadores y firmas no se conocen instantáneamente.
- **Heterogeneidad:** los trabajos difieren en requerimientos; los trabajadores difieren en habilidades.
- **Costos de movilidad:** geográfica, sectorial, ocupacional.

El desempleo friccional es en cierta medida eficiente: permite mejor *match* entre trabajadores y puestos. Un seguro de desempleo eleva $u^*$ no porque sea ineficiente per se, sino porque reduce el costo de rechazar ofertas y extiende el período de búsqueda, lo que en equilibrio aumenta la calidad de los emparejamientos pero también la tasa de desempleo.

---

## 3. Rigideces salariales y desempleo estructural

El desempleo estructural es más persistente que el friccional: surge de desajustes entre las habilidades disponibles y las demandadas, o de rigideces que impiden que los salarios vacíen el mercado.

### 3.1 Salario mínimo

El caso más directo. Si el salario mínimo $\bar{w}$ supera el salario de equilibrio competitivo $w^*$, la demanda laboral cae y la oferta sube, generando exceso de oferta (desempleo). El efecto sobre el bienestar es ambiguo: los trabajadores que conservan el empleo ganan, los que lo pierden (o nunca entran) pierden.

La evidencia empírica es más matizada que el modelo simple sugiere: Card y Krueger (1994) encontraron que aumentos moderados del salario mínimo no reducen el empleo en mercados con poder monopsónico de las firmas. La estructura del mercado importa.

### 3.2 Sindicatos e insiders-outsiders

Los sindicatos negocian salarios por encima del mercado para sus miembros (*insiders*). Los *outsiders* (desempleados) no participan en la negociación. El resultado es un salario de negociación $w^N > w^*$ con desempleo persistente de los outsiders. El modelo de Lindbeck y Snower (1988) formaliza esta dinámica y explica por qué el desempleo puede ser histéresis-dependiente: shocks transitorios que aumentan el desempleo generan más outsiders, que luego no tienen poder para reducir salarios.

---

## 4. Modelo de salarios de eficiencia: Shapiro-Stiglitz (1984)

### 4.1 La intuición

El modelo de salarios de eficiencia parte de una premisa de información asimétrica: las firmas no pueden observar el esfuerzo de los trabajadores sin costo. Si el salario iguala el de mercado, un trabajador despedido por no esforzarse puede inmediatamente conseguir otro empleo al mismo salario — el despido no lo castiga. Entonces, racionalmente, no se esfuerza.

La solución: las firmas pagan un salario **por encima** del de mercado ($w^* > w^{comp}$) para que el despido sea costoso. El desempleo resultante cumple la función de **dispositivo disciplinador**: tener empleo tiene valor precisamente porque encontrar otro no es inmediato.

### 4.2 Estructura del modelo

Hay $N$ trabajadores y $L$ firmas. Los trabajadores pueden estar en tres estados: empleados y esforzándose ($E$), empleados y sin esforzarse/shirking ($S$), o desempleados ($U$).

La utilidad del trabajador es $u(w, e) = w - e$, donde $e \in \{0, \bar{e}\}$.

Los valores de los estados son ecuaciones de activo. Para un trabajador esforzándose:

$$rV_E = w - \bar{e} - b(V_E - V_U)$$

Para un trabajador sin esforzarse (que puede ser detectado con probabilidad $q$ y despedido):

$$rV_S = w - (b + q)(V_S - V_U)$$

Para un desempleado que encuentra empleo con tasa $a$:

$$rV_U = z + a(V_E - V_U)$$

donde $r$ es la tasa de descuento, $b$ la tasa de separación exógena, $z$ el ingreso de desempleo.

### 4.3 La condición de no-shirking (NSC)

El trabajador no se esfuerza si $V_S \geq V_E$. La firma quiere $V_E \geq V_S$, es decir:

$$w - \bar{e} - b(V_E - V_U) \geq w - (b+q)(V_E - V_U)$$

Simplificando, la NSC requiere:

$$V_E - V_U \geq \frac{\bar{e}}{q}$$

El trabajador se esfuerza si el valor de estar empleado supera en al menos $\bar{e}/q$ el valor de estar desempleado. Resolviendo el sistema de ecuaciones de activo, el salario mínimo que evita shirking es:

$$w^* = z + \bar{e} + \frac{\bar{e}}{q}\left(r + b + a\right)$$

donde $a = \frac{bL}{N-L}$ en estado estacionario (tasa de encontrar empleo depende del desempleo). El salario de eficiencia sube cuando: el esfuerzo requerido $\bar{e}$ es mayor, la tasa de monitoreo $q$ es menor (más difícil detectar shirking), o la tasa de desempleo es baja (fácil encontrar otro empleo).

### 4.4 Equilibrio y consecuencias

En equilibrio, todas las firmas pagan el mismo $w^*$ y hay desempleo involuntario positivo. El desempleo hace que perder el trabajo sea costoso, funcionando como dispositivo disciplinador: un desempleado no puede convencer a una firma de contratarlo a un salario menor al de equilibrio porque la firma anticipa que shirkeará una vez contratado. 

Implicancias importantes:

- **El equilibrio es ineficiente:** cada firma paga demasiado poco trabajo porque enfrenta el costo privado de contratar, pero genera una externalidad positiva: más empleo reduce $V_E - V_U$ para todas las firmas (hace el shirking más atractivo), lo que lleva a que todas deban subir salarios. Hay demasiado poco empleo en equilibrio.
- **Los salarios son rígidos a la baja:** si la demanda laboral cae, los salarios no pueden reducirse para mantener el empleo, porque al caer el salario la probabilidad de shirking sube; el desempleo debe aumentar para restaurar la disciplina. 
- **El desempleo es involuntario:** los trabajadores desempleados preferirían trabajar al salario vigente pero no pueden comprometerse creíblemente a no shirkenar a un salario menor.

---

## 5. Modelos de búsqueda y emparejamiento: Mortensen-Pissarides

### 5.1 Motivación

El modelo de salarios de eficiencia endogeniza el salario pero trata el proceso de búsqueda como una tasa exógena $a$. El modelo de Mortensen-Pissarides (1994, Nobel 2010) endogeniza el proceso de búsqueda y formación de matches.

### 5.2 La función de matching

El número de nuevos emparejamientos por unidad de tiempo es:

$$M = m(U, V)$$

donde $U$ es el número de desempleados buscando trabajo y $V$ el número de vacantes. La función $m$ tiene retornos constantes a escala: $m(\lambda U, \lambda V) = \lambda m(U,V)$.

Se define la **tightness del mercado laboral**:

$$\theta = \frac{V}{U}$$

Las tasas de transición son:
- Trabajador encuentra empleo: $f(\theta) = m(U,V)/U = m(1, \theta)$ — creciente en $\theta$.
- Firma llena vacante: $q(\theta) = m(U,V)/V = m(1/\theta, 1)$ — decreciente en $\theta$.

Un mercado más tenso ($\theta$ alto, muchas vacantes por desempleado) facilita a los trabajadores pero dificulta a las firmas.

### 5.3 Determinación del salario: bargaining de Nash

Los salarios se determinan por negociación de Nash entre el trabajador y la firma. El salario divide el excedente del match:

$$w = \beta(y + cV/q(\theta)) + (1-\beta)z$$

donde $\beta \in (0,1)$ es el poder de negociación del trabajador, $y$ la productividad, $c$ el costo de mantener una vacante, y $z$ el valor de desempleo. El salario sube cuando: aumenta la productividad, aumenta $\theta$ (más oportunidades para el trabajador), o aumenta el poder de negociación.

### 5.4 Equilibrio y la curva de Beveridge

El equilibrio del modelo determina simultáneamente $\theta^*$ y $u^*$. La **curva de Beveridge** es la relación negativa entre desempleo y vacantes en estado estacionario:

$$u = \frac{s}{s + f(\theta)}$$

Desplazamientos de la curva de Beveridge (no movimientos a lo largo) reflejan cambios en la eficiencia del proceso de matching — por ejemplo, mayor desajuste estructural entre habilidades disponibles y demandadas desplaza la curva hacia afuera (más desempleo para cualquier nivel de vacantes).

### 5.5 Eficiencia y la regla de Hosios

El equilibrio descentralizado no es necesariamente eficiente. La condición de Hosios (1990) establece que el equilibrio es eficiente si y solo si el poder de negociación del trabajador $\beta$ iguala la elasticidad de la función de matching respecto al desempleo. Si $\beta$ es muy alto, los trabajadores capturan demasiado del excedente y las firmas abren pocas vacantes (subempleo). Si $\beta$ es muy bajo, hay exceso de vacantes. Esto provee una justificación teórica para intervención en la negociación salarial.

---

## 6. Síntesis: tipos de desempleo y política

| Tipo | Causa | Política relevante |
|---|---|---|
| **Friccional** | Tiempo de búsqueda, información imperfecta | Bolsas de trabajo, reducción de costos de búsqueda |
| **Estructural** | Desajuste habilidades/vacantes, rigideces | Capacitación, flexibilidad salarial |
| **Por salarios de eficiencia** | Información asimétrica, monitoring costoso | Mejorar tecnologías de monitoreo |
| **Cíclico** | Caída en demanda agregada | Política macroeconómica contracíclica |

La tasa natural recoge los tres primeros. Las políticas de mercado de trabajo (*active labor market policies*) buscan reducir la friccional y estructural; la política macroeconómica maneja la cíclica.

---

## Referencias

- Shapiro, C. & Stiglitz, J. (1984). *Equilibrium Unemployment as a Worker Discipline Device*. AER.
- Mortensen, D. & Pissarides, C. (1994). *Job Creation and Job Destruction in the Theory of Unemployment*. RES.
- Pissarides, C. (2000). *Equilibrium Unemployment Theory*. MIT Press. Caps. 1–2.
- De Gregorio, J. (2007). *Macroeconomía: Teoría y Políticas*. Cap. 10.
- Cahuc, P., Carcillo, S. & Zylberberg, A. (2014). *Labor Economics*. MIT Press.
- Card, D. & Krueger, A. (1994). *Minimum Wages and Employment: A Case Study*. AER.