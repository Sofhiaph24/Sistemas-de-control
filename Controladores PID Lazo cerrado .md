# Diseño de Controladores PID en Lazo Cerrado

En el ámbito de la ingeniería mecatrónica, la implementación de sistemas de control es fundamental para garantizar la estabilidad y el rendimiento operativo de diversos procesos. Los controladores Proporcionales, Integrales y Derivativos (PID) constituyen una de las arquitecturas de control más extendidas y efectivas. No obstante, su desempeño óptimo depende críticamente de una sintonización adecuada, siendo los métodos en lazo cerrado particularmente relevantes para este propósito. La presente sección aborda el diseño de controladores PID mediante enfoques que permiten la identificación de las características dinámicas del sistema durante su operación en lazo cerrado, facilitando el ajuste de los parámetros del controlador para lograr una respuesta transitoria y estacionaria deseable. Se analizarán metodologías clave como el Método de Ziegler & Nichols y el Método del Relé, así como consideraciones operativas esenciales, incluyendo el fenómeno de *wind-up* y las estrategias para su mitigación, elementos críticos para la implementación exitosa de estos controladores en aplicaciones prácticas.

## 1. El Lazo Cerrado en la Sintonización de Controladores

El control en lazo cerrado es un principio fundamental en la automatización y la robótica, donde la señal de salida del sistema es realimentada al controlador para modular la acción de control. En el contexto del diseño de controladores PID en lazo cerrado, el enfoque se centra en la explotación de la interacción sistema-controlador para extraer información de proceso.

>🔑 *Lazo Cerrado:* Configuración de control en la cual la señal de salida de un sistema se compara con una señal de referencia (setpoint). La desviación resultante (error) es utilizada por el controlador para generar una acción de control que busca minimizar dicho error y mantener la salida del sistema próxima al valor deseado.

La sintonización en lazo cerrado implica la identificación de los parámetros dinámicos de la planta durante pruebas realizadas directamente bajo condiciones de operación en lazo cerrado. Esta aproximación es particularmente ventajosa en entornos industriales donde la interrupción del proceso para realizar pruebas en lazo abierto no es viable o es económicamente desfavorable. A partir de los datos obtenidos en estas pruebas, se procede a la determinación de los parámetros del controlador PID, con el objetivo de optimizar métricas de desempeño como el error en estado estacionario, el tiempo de respuesta y la amortiguación de oscilaciones.

## 2. Métodos de Sintonización en Lazo Cerrado

La sintonización de un controlador PID en lazo cerrado es un procedimiento crítico orientado a la determinación de los valores óptimos de las ganancias Proporcional ($K_p$), Integral ($T_i$ o $K_i$) y Derivativa ($T_d$ o $K_d$). Existen diversas metodologías para este fin; entre las más reconocidas se encuentran el Método de Ziegler & Nichols y el Método del Relé.

### 2.1. Método de Ziegler & Nichols (Ciclo Último)

El método de Ziegler & Nichols, en su variante de "ciclo último", es una técnica empírica para la sintonización de controladores PID en lazo cerrado. Su aplicación es directa, aunque requiere la inducción de una oscilación sostenida en el sistema.

El procedimiento para la aplicación de este método se articula en los siguientes pasos:

1.  **Anulación de Ganancias Integrales y Derivativas:** Inicialmente, las ganancias del componente Integral ($K_i$ o $T_i$) y Derivativo ($K_d$ o $T_d$) del controlador se establecen a cero. En esta fase, el controlador opera exclusivamente en modo Proporcional.
2.  **Incremento de la Ganancia Proporcional ($K_p$):** La ganancia proporcional ($K_p$) del controlador se incrementa progresivamente. Este proceso se lleva a cabo con observación continua de la respuesta de la salida del sistema. El objetivo es identificar el valor de $K_p$ que induce una oscilación sostenida y marginalmente estable en la salida del sistema, caracterizada por una amplitud constante.
3.  **Medición del Periodo Último ($P_u$):** Una vez alcanzado el estado de oscilación marginalmente estable, se mide el periodo de esta oscilación, denominado "periodo último" ($P_u$).
4.  **Determinación de la Ganancia Última ($K_u$):** El valor de la ganancia proporcional ($K_p$) a la cual se establece la oscilación marginalmente estable se designa como "ganancia última" ($K_u$).

Con los valores de $P_u$ y $K_u$ obtenidos, se emplean tablas de sintonización predefinidas (Tabla 1) para determinar los parámetros finales del controlador P, PI o PID.

### 2.1.1. Solución Analítica (Ejemplo)

Para ejemplificar la aplicación de este método, consideremos un sistema con una función de transferencia de lazo abierto $G(s) = \frac{1}{s(s+1)(s+2)}$. El objetivo es sintonizar un controlador PID utilizando el método de Ziegler & Nichols (ciclo último).

La función de transferencia de la planta se reescribe como $G(s) = \frac{1}{s(s^2 + 3s + 2)} = \frac{1}{s^3 + 3s^2 + 2s}$.
La función de transferencia en lazo cerrado con un controlador proporcional $K_p$ es:

$$G_o(s) = \frac{K_p \cdot G(s)}{1 + K_p \cdot G(s)} = \frac{K_p}{s^3 + 3s^2 + 2s + K_p}$$

Para identificar la condición de oscilación marginalmente estable, se sustituye $s = j\omega$ en el polinomio característico:

$$(j\omega)^3 + 3(j\omega)^2 + 2(j\omega) + K_p = 0$$
$$-j\omega^3 - 3\omega^2 + j2\omega + K_p = 0$$

Agrupando los términos reales e imaginarios:

$$(K_p - 3\omega^2) + j(2\omega - \omega^3) = 0$$

Para que esta ecuación sea nula, ambas partes, real e imaginaria, deben ser cero.

**Parte Imaginaria:**
$$2\omega - \omega^3 = 0$$
$$\omega(2 - \omega^2) = 0$$Descartando la solución trivial $\omega = 0$, se obtiene:$$2 - \omega^2 = 0 \implies \omega^2 = 2 \implies \omega_u = \sqrt{2} \text{ rad/s}$$

Esta es la frecuencia última de oscilación ($\omega_u$).

**Parte Real:**
$$K_p - 3\omega^2 = 0$$Sustituyendo el valor de $\omega^2 = 2$:$$K_p - 3(2) = 0 \implies K_p - 6 = 0 \implies K_u = 6$$

Por consiguiente, la ganancia última es $K_u = 6$.
El periodo último ($P_u$) se calcula como:

$$P_u = \frac{2\pi}{\omega_u} = \frac{2\pi}{\sqrt{2}} = \pi\sqrt{2} \approx 4.44 \text{ segundos}$$

Finalmente, se aplican los valores de $K_u = 6$ y $P_u = 4.44$ segundos utilizando la Tabla 1 para un controlador PID:

| Tipo | $K_p$       | $T_i$           | $T_d$           |
|------|-------------|-----------------|-----------------|
| P    | $0.5K_u$    | ---             | ---             |
| PI   | $0.45K_u$   | $\frac{P_u}{1.2}$ | ---             |
| PID  | $0.6K_u$    | $\frac{P_u}{2}$   | $\frac{P_u}{8}$   |
Tabla 1. Coeficientes de sintonización de Ziegler & Nichols.

Aplicando los valores para un controlador PID:
* $K_p = 0.6 \times K_u = 0.6 \times 6 = 3.6$
* $T_i = \frac{P_u}{2} = \frac{4.44}{2} = 2.22$ segundos
* $T_d = \frac{P_u}{8} = \frac{4.44}{8} = 0.555$ segundos

Los parámetros determinados para el controlador PID son: $K_p = 3.6$, $T_i = 2.22$ s, $T_d = 0.555$ s.

---

### 2.2. Método del Relé

El Método del Relé representa una metodología de sintonización avanzada que mejora las capacidades del método de Ziegler & Nichols en lazo cerrado. Una ventaja significativa de esta técnica es la capacidad de inducir oscilaciones sostenidas sin requerir niveles excesivos de señal de control, lo cual puede ser beneficioso en sistemas con limitaciones de actuador. Adicionalmente, el método del relé permite una mayor flexibilidad en la manipulación de la respuesta obtenida durante la prueba, proporcionando así un mayor control sobre el proceso de sintonización.

#### 2.2.1. Metodología del Relé

La implementación del método del Relé comprende los siguientes pasos:

1.  **Medición del Tiempo Estacionario en Lazo Abierto:** Previo al cierre del lazo, es recomendable determinar el tiempo requerido para que el sistema alcance un estado estacionario bajo operación en lazo abierto. Esto establece una referencia del comportamiento intrínseco del sistema.
2.  **Cierre del Lazo con un Relé y Histéresis:** El lazo de control se cierra incorporando un relé con histéresis. Un relé es un dispositivo conmutador que alterna su salida entre dos valores discretos (ON/OFF) en función del cruce de umbrales por la señal de error. La histéresis se introduce para evitar conmutaciones rápidas e innecesarias cerca del punto de cruce.
3.  **Captura de la Oscilación Sostenida:** La aplicación del relé con histéresis resultará en una oscilación sostenida de la salida del sistema. Esta respuesta oscilatoria debe ser registrada.
4.  **Medición del Periodo Último ($P_u$) y Amplitud del Ciclo Último ($A_u$):** De la oscilación sostenida, se extraen dos parámetros fundamentales: el periodo último ($P_u$), que es la duración de un ciclo completo de oscilación, y la amplitud del ciclo último ($A_u$), definida como la mitad de la diferencia entre los valores máximo y mínimo de la oscilación.
5.  **Determinación de la Ganancia Crítica ($K_c$):** La ganancia crítica ($K_c$) se calcula a partir de la amplitud de la oscilación ($A_u$) y la amplitud de la señal de salida del relé ($d$), así como la histéresis ($\epsilon$). La expresión para $K_c$ es:

    $$K_c = \frac{4d}{\pi\sqrt{A_u^2 - \epsilon^2}}$$

    Donde $d$ representa la amplitud de la señal de salida del relé y $\epsilon$ es el valor de la histéresis. Es imperativo que exista un desfase de $180^\circ$ entre la señal del relé y la salida de la planta para la validez de esta ecuación.

6.  **Determinación de la Ganancia Estática:** Adicionalmente a la ganancia crítica, es relevante estimar la ganancia estática del sistema, la cual puede ser inferida a partir del comportamiento en lazo abierto o del ensayo con el relé.

La sintonización PI mediante el método del Relé es de uso común y se combina frecuentemente con ecuaciones derivadas de Ziegler & Nichols, adaptadas para este método. Estas ecuaciones buscan un sobreimpulso máximo inferior al 10%. Por ejemplo, para un controlador PI, se pueden utilizar las siguientes fórmulas:

| Controlador | $K_p$                                                        | $T_i$                                                        |
|-------------|--------------------------------------------------------------|--------------------------------------------------------------|
| PI          | $\frac{5K_c}{6}(\frac{12+KK_c}{15+14KK_c})$ | $\frac{P_u}{5}(1+\frac{4}{15}KK_c)$ |
Tabla 2. Ecuaciones para sintonización PI con método de Relé.

---

### 2.2.2. Diagrama de Bloques y Respuesta Típica del Método de Relé

Para una comprensión más profunda del funcionamiento del método del relé, es útil analizar su representación en diagrama de bloques y la respuesta temporal típica del sistema.

💡**Ejemplo 4:** El siguiente diagrama de bloques ilustra la implementación de un relé en un sistema de control.

![Diagrama de Bloques del Método de Relé](http://googleusercontent.com/ontology/media/images/c234b071_2c52_4f1e_a696_9f50f28a7e04)
Figura 2. Diagrama de bloques de un sistema con controlador de relé.

En este esquema, la señal de error ($e(t)$) es la entrada al relé, cuya salida ($u(t)$) constituye la señal de control aplicada al proceso. El relé, con su característica de histéresis, conmuta la señal de salida entre dos valores discretos, lo que induce una oscilación en la variable de salida del proceso.

La respuesta temporal característica del sistema a una prueba con relé se distingue por una oscilación sostenida en la salida de la planta (e.g., temperatura del líquido), mientras que la señal de control conmuta entre dos estados discretos.

💡**Ejemplo 5:** Se presentan a continuación las gráficas de la salida de temperatura del líquido y la salida del relé (apertura de válvula) obtenidas durante una prueba con el método de relé.

![Salida del Relé y Temperatura del Líquido](http://googleusercontent.com/ontology/media/images/223b9d62_0d44_40d4_b7b6_81a63c631e84)
Figura 3. Salida de la temperatura del líquido y salida del relé durante la prueba.

En la Figura 3, se observa que la temperatura del líquido (salida del sistema) exhibe una oscilación cuasi-sinusoidal inducida por la acción conmutada del relé. La gráfica superior permite identificar el periodo ($t$) y la amplitud ($a$) de la oscilación. La gráfica inferior muestra la señal de control generada por el relé, con sus dos niveles discretos, y la amplitud ($d$) de la señal de control. Este comportamiento es fundamental para la extracción de los parámetros $P_u$, $A_u$ y la ganancia crítica $K_c$.

---

## 3. Fenómeno *Wind-up* y Estrategias Anti Wind-up

En controladores que incorporan acción integral (controladores PI y PID), un problema común y de importancia crítica es el fenómeno conocido como *wind-up* o "acumulación integral". Este fenómeno se manifiesta cuando el actuador del sistema alcanza sus límites de saturación, es decir, su valor máximo o mínimo de operación.

>🔑 *Fenómeno Wind-up:* Es la acumulación excesiva del término integral en un controlador PID cuando el actuador del sistema opera en saturación (alcanza sus límites físicos). Esta situación provoca que, ante un cambio en la referencia o al salir de la saturación, el controlador requiera un tiempo prolongado para restablecer su operación normal, lo que puede inducir sobreimpulsos indeseables y una respuesta transitoria lenta.

Cuando el actuador se satura, la señal de control calculada por el controlador excede la capacidad física de dicho actuador. A pesar de la incapacidad del actuador para incrementar su salida, el término integral del controlador persiste en la integración del error positivo. Esto resulta en un incremento excesivo del valor interno del integrador del controlador.

Cuando la temperatura del horno eventualmente alcanza el punto de ajuste, o cuando el punto de ajuste es reducido, el término integral, al estar sobredimensionado, requiere un tiempo considerable para "descargarse" y alcanzar un valor apropiado antes de que el controlador pueda generar una acción de control efectiva. Esta "descarga" del integrador es la causa principal del retardo en la disminución de la temperatura, ya que el controlador mantiene una señal de control elevada (o una que no induce enfriamiento) debido a la acumulación integral previa.

💡**Ejemplo 6:** La siguiente figura ilustra el impacto del fenómeno *wind-up* en la respuesta de un sistema.

![Fenómeno Wind-up](http://googleusercontent.com/ontology/media/images/154c1a84_832d_494c_a62f_2b7ec992b861)
Figura 4. Comportamiento de un sistema afectado por el fenómeno wind-up.

En la Figura 4, la gráfica superior muestra la señal de referencia $y_{sp}$ y la salida del sistema $y$. Cuando la referencia aumenta rápidamente, el actuador se satura (gráfica central, señal $u$ en su límite). Mientras el actuador permanece saturado, el término integral (gráfica inferior, señal $I$) continúa incrementándose, acumulando un error integral considerable. Una vez que la salida del sistema se aproxima a la referencia, el actuador deja la saturación, pero el término integral sobreacumulado ocasiona que la salida oscile o requiera un tiempo prolongado para asentarse.

Para mitigar los efectos adversos del *wind-up*, se han desarrollado diversas estrategias "anti wind-up".

### 3.1. Anti Wind-up por Saturación de la Acción Integral

Una de las estrategias más directas para contrarrestar el *wind-up* es la saturación de la acción integral. Este método consiste en limitar la acumulación del término integral cuando la salida del actuador alcanza sus límites de operación.

💡**Ejemplo 7:** El diagrama de bloques para la estrategia anti *wind-up* por saturación de la acción integral se presenta a continuación:

![Anti Wind-up por Saturación](http://googleusercontent.com/ontology/media/images/ecfc3508_4c21_4250_b9ec_19446d32847a)
Figura 5. Diagrama de bloques de un controlador PID con anti wind-up por saturación de la acción integral.

En este esquema, se implementa una lógica que "recorta" la acción integral si la señal del actuador intenta exceder sus límites. Aunque la acción integral continuará acumulando, se previene que el actuador reciba una señal de control irrealmente grande, y se busca minimizar el impacto negativo en los tiempos de respuesta del sistema debido a una acumulación excesiva del término integral.

### 3.2. Anti Wind-up por Integración Condicional

La integración condicional es otra estrategia efectiva. En este método, la acción integral solo se activa (es decir, el término integral solo se acumula) cuando la señal de error se encuentra dentro de un rango predefinido o cuando el actuador no está operando en saturación.

💡**Ejemplo 8:** El diagrama de bloques para la estrategia anti *wind-up* por integración condicional se muestra a continuación:

![Anti Wind-up por Integración Condicional](http://googleusercontent.com/ontology/media/images/bf7e31d3_b713_4a50_b51b_1001a75094ef)
Figura 6. Diagrama de bloques de un controlador PID con anti wind-up por integración condicional.

Esta solución aborda el problema del tiempo de respuesta del sistema y previene la generación de pulsos no deseados en la respuesta que podrían resultar de una suspensión abrupta de la acción integral. Al controlar las condiciones bajo las cuales se integra el error, se evita la acumulación excesiva cuando el actuador está saturado, resultando en una respuesta del sistema más suave y predecible.

### 3.3. Anti Wind-up por Recálculo y Seguimiento

El método de recálculo y seguimiento es una estrategia anti *wind-up* más avanzada. Implica la estimación del modelo del actuador para suspender la acción integral de manera gradual a medida que la señal de control se aproxima a los límites de saturación.

💡**Ejemplo 9:** El diagrama de bloques para la estrategia anti *wind-up* por recálculo y seguimiento se muestra a continuación:

![Anti Wind-up por Recálculo y Seguimiento](http://googleusercontent.com/ontology/media/images/5f97d5a5_9436_4020_9185_f37f37dd2b44)
Figura 7. Diagrama de bloques de un controlador PID con anti wind-up por recálculo y seguimiento.

En este enfoque, la ganancia $T_t$ (tiempo de seguimiento) es un parámetro crítico, ya que determina la velocidad de respuesta de la estrategia anti *wind-up*. Un valor comúnmente empleado para $T_t$ es $T_t = \sqrt{T_i T_d}$. Este método facilita una transición más fluida cuando el actuador entra o sale de la saturación, minimizando los efectos adversos en la respuesta del sistema.

### 3.3.1. Efectos del Anti Wind-up

La implementación de estrategias anti *wind-up* produce un impacto positivo significativo en el rendimiento del sistema, particularmente en controladores PID con una acción integral pronunciada. Estas estrategias contribuyen a mantener la integridad del proceso incluso en presencia de saturación del actuador.

💡**Ejemplo 10:** Las siguientes gráficas demuestran los efectos de la implementación del anti *wind-up* en la respuesta del sistema, con una comparación de diferentes valores de $T_t$.

![Efectos del Anti Wind-up](http://googleusercontent.com/ontology/media/images/c04b4070_887e_41b1_80ed_43997ef057e9)
Figura 8. Comparación de los efectos del anti wind-up con diferentes tiempos de seguimiento ($T_t$).

Como se ilustra en la Figura 8, una sintonización adecuada de $T_t$ (e.g., $T_t = 0.1$ o $T_t = 1$) mejora considerablemente la respuesta del sistema, previniendo sobreimpulsos y reduciendo el tiempo de asentamiento en comparación con un controlador sin una estrategia anti *wind-up* o con un $T_t$ mal ajustado (e.g., $T_t = 3$ o $T_t = 2$). Esto subraya la importancia de seleccionar la estrategia anti *wind-up* apropiada y sintonizarla correctamente para el sistema en cuestión.

---

# Ejercicios

📚 1. **Ejercicio 1: Sintonización PID con Ziegler & Nichols**

Se dispone de un sistema cuya función de transferencia en lazo abierto es $G(s) = \frac{1}{s(s+1)(s+2)}$. Se requiere sintonizar un controlador PID utilizando el método de Ziegler & Nichols (ciclo último). Determine la ganancia última ($K_u$) y el periodo último ($P_u$), y subsiguientemente, calcule los parámetros ($K_p$, $T_i$, $T_d$) del controlador PID.

**Solución:**

La función de transferencia de la planta se expresa como $G(s) = \frac{1}{s(s+1)(s+2)} = \frac{1}{s(s^2 + 3s + 2)} = \frac{1}{s^3 + 3s^2 + 2s}$.
La función de transferencia en lazo cerrado con un controlador proporcional $K_p$ es:

$$G_o(s) = \frac{K_p \cdot G(s)}{1 + K_p \cdot G(s)} = \frac{K_p}{s^3 + 3s^2 + 2s + K_p}$$

Para identificar la condición de oscilación marginalmente estable, se sustituye $s = j\omega$ en el polinomio característico:

$$(j\omega)^3 + 3(j\omega)^2 + 2(j\omega) + K_p = 0$$
$$-j\omega^3 - 3\omega^2 + j2\omega + K_p = 0$$

Agrupando los términos reales e imaginarios:

$$(K_p - 3\omega^2) + j(2\omega - \omega^3) = 0$$

Para que esta ecuación sea nula, ambas partes, real e imaginaria, deben ser cero.

**Parte Imaginaria:**
$$2\omega - \omega^3 = 0$$
$$\omega(2 - \omega^2) = 0$$Descartando la solución trivial $\omega = 0$, se obtiene:$$2 - \omega^2 = 0 \implies \omega^2 = 2 \implies \omega_u = \sqrt{2} \text{ rad/s}$$

Esta es la frecuencia última de oscilación ($\omega_u$).

**Parte Real:**
$$K_p - 3\omega^2 = 0$$Sustituyendo el valor de $\omega^2 = 2$:$$K_p - 3(2) = 0 \implies K_p - 6 = 0 \implies K_u = 6$$

Por consiguiente, la ganancia última es $K_u = 6$.
El periodo último ($P_u$) se calcula como:

$$P_u = \frac{2\pi}{\omega_u} = \frac{2\pi}{\sqrt{2}} = \pi\sqrt{2} \approx 4.44 \text{ segundos}$$

Finalmente, se aplican los valores de $K_u = 6$ y $P_u = 4.44$ segundos utilizando la Tabla 1 para un controlador PID:

* $K_p = 0.6 \times K_u = 0.6 \times 6 = 3.6$
* $T_i = \frac{P_u}{2} = \frac{4.44}{2} = 2.22$ segundos
* $T_d = \frac{P_u}{8} = \frac{4.44}{8} = 0.555$ segundos

Los parámetros determinados para el controlador PID son: $K_p = 3.6$, $T_i = 2.22$ s, $T_d = 0.555$ s.

📚 2. **Ejercicio 2: Identificación de Fenómeno *Wind-up***

En un sistema de control de temperatura de un horno, se ha implementado un controlador PI. Durante la operación, se observa que la señal de salida del actuador (un calefactor) se mantiene constantemente en su valor máximo durante un intervalo prolongado, incluso después de que la temperatura del horno ha alcanzado el punto de ajuste deseado. Cuando el punto de ajuste se reduce, la temperatura del horno experimenta un retardo significativo en su disminución, a pesar de que el calefactor se encuentra en estado de apagado. Describa el fenómeno que se está manifestando, sus causas y proponga una estrategia para su mitigación.

**Solución:**

El fenómeno observado en el sistema de control de temperatura del horno es el **Fenómeno *Wind-up*** o acumulación integral.

**Causas del Fenómeno:**
Este fenómeno se produce debido a que el controlador PI, al incorporar una acción integral, continúa acumulando el error entre el punto de ajuste y la temperatura actual del horno, incluso cuando el calefactor ya ha alcanzado su límite de saturación (capacidad máxima de calentamiento). A pesar de que el actuador no puede incrementar más su salida de calor, el término integral del controlador persiste en la integración del error positivo. Esto resulta en un incremento excesivo del valor interno del integrador del controlador.

Cuando la temperatura del horno eventualmente alcanza el punto de ajuste, o cuando el punto de ajuste es reducido, el término integral, al estar sobredimensionado, requiere un tiempo considerable para "descargarse" y alcanzar un valor apropiado antes de que el controlador pueda generar una acción de control efectiva. Esta "descarga" del integrador es la causa principal del retardo en la disminución de la temperatura, ya que el controlador mantiene una señal de control elevada (o una que no induce enfriamiento) debido a la acumulación integral previa.

**Estrategia para Mitigación:**
Para mitigar el *wind-up* en este escenario, se recomienda la implementación de estrategias como la **Integración Condicional** o el **Anti Wind-up por Recálculo y Seguimiento**.

* **Integración Condicional:** Con esta estrategia, la acción integral del controlador se activa o permite la acumulación del error únicamente cuando el actuador no se encuentra en saturación y/o cuando la señal de error está dentro de un rango predefinido. Esto previene que el integrador acumule un valor excesivo mientras el calefactor opera a su máxima capacidad. Al alcanzar la saturación del actuador, la integración se pausa o se reduce, evitando la sobreacumulación.

* **Anti Wind-up por Recálculo y Seguimiento:** Esta estrategia es más avanzada. Implica la modificación del integrador para que su salida "siga" la salida real del actuador cuando este se satura. En otras palabras, si el actuador está en su límite máximo, el integrador se ajusta para que su contribución no intente forzar la salida del actuador más allá de dicho límite. Esto asegura que, al salir de la saturación, el integrador ya se encuentre en un valor adecuado, lo que permite una respuesta del sistema más rápida y suave. El diseño de esta estrategia implica la realimentación de la señal de saturación del actuador al integrador a través de una ganancia de seguimiento ($T_t$).

Ambas estrategias tienen como objetivo principal evitar la sobreacumulación del término integral, lo que se traduce en una respuesta más ágil y predecible del sistema de control de temperatura, minimizando los sobreimpulsos y los tiempos de asentamiento cuando el actuador opera en sus límites.

---

## 4. Conclusiones

La presente investigación sobre el diseño de controladores PID en lazo cerrado ha permitido establecer las siguientes conclusiones fundamentales para la ingeniería mecatrónica:

* Las metodologías de sintonización en lazo cerrado ofrecen una aproximación práctica y relevante para la industria, permitiendo la caracterización dinámica de un sistema bajo sus condiciones operativas normales. Esta capacidad es una ventaja significativa en entornos donde la interrupción del proceso es inviable.
* A pesar de su carácter empírico, el método de Ziegler & Nichols de lazo cerrado sigue siendo una herramienta considerablemente útil y ampliamente aplicada para obtener una sintonización inicial efectiva de los controladores PID. Su simplicidad lo posiciona como un punto de partida accesible para diversos sistemas.
* Se ha demostrado cómo diversas investigaciones han propuesto métodos de sintonización más avanzados, frecuentemente basados en los parámetros obtenidos mediante el método del Relé. El método del Relé, al facilitar la inducción controlada de oscilaciones, representa una mejora sustancial en comparación con Ziegler & Nichols, particularmente en sistemas donde se busca evitar una excitación excesiva.
* Finalmente, la implementación de controladores PI y PID en sistemas reales requiere una consideración crítica del fenómeno *wind-up*. Es imperativo integrar estrategias anti *wind-up* (tales como la saturación integral, integración condicional o recálculo y seguimiento) para asegurar que, incluso cuando los actuadores operan en sus límites de saturación, el rendimiento del sistema no se degrade y la respuesta se mantenga robusta y predecible. La omisión de estas consideraciones puede conducir a un comportamiento oscilatorio indeseado y a una respuesta lenta del sistema.

En síntesis, el diseño de controladores PID en lazo cerrado es una disciplina que integra principios teóricos con la experimentación práctica. La comprensión y dominio de estas metodologías, junto con la gestión de fenómenos como el *wind-up*, son esenciales para el desarrollo de sistemas de control eficientes y confiables en el campo de la ingeniería mecatrónica.

---

## 5. Referencias

* Cote Ballesteros, Jorge Eduardo. "Diseño de controladores PID lazo cerrado". Diapositivas de clase M7A Sistemas de Control I. Escuela Tecnológica Instituto Técnico Central, 2023.
* Aström, K.J. y T. Hägglund. "Benchmark Systems for PID Control". IFAC Workshop on Digital Control: Past, Present and Future of PID Control, Terrassa, España, Abril 5-7, 2000. [Aström, K.J. y T. Hägglund - "Benchmark Systems for PID Control"](http://googleusercontent.com/ontology/media/images/c04b4070_887e_41b1_80ed_43997ef057e9) (Referenciado para figuras y conceptos de anti *wind-up*).
* Morilla, F. "Controladores PID - Ajuste empírico". Departamento de Informática y Automática, UNED, 2006. [Morilla, F. "Controladores PID - Ajuste empírico"](http://googleusercontent.com/ontology/media/images/223b9d62_0d44_40d4_b7b6_81a63c631e84) (Referenciado para la Figura 2 y Figura 3 del Método de Relé).
