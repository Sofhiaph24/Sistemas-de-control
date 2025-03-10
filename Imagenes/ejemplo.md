
# Modelamiento de Sistemas Dinámicos
Un modelo matemático de un sistema dinámico es básicamente un conjunto de ecuaciones que describen con bastante precisión, o al menos con una buena aproximación, cómo se comporta dinámicamente el sistema. Hay que tener en cuenta que un mismo sistema puede representarse de varias maneras diferentes, lo que quiere decir que no existe un único modelo matemático, sino que hay múltiples enfoques posibles dependiendo de cómo lo mires.
La dinámica de un montón de sistemas se expresa mediante ecuaciones diferenciales. Estas ecuaciones vienen de las leyes físicas que gobiernan cada sistema, como las leyes de Newton en sistemas mecánicos y las leyes de Kirchhoff en sistemas eléctricos. Conseguir un modelo matemático adecuado es una de las partes más importantes cuando analizas cualquier sistema.

## 1. Definiciones
> 🔑 *Sistema dinámico:* Un sistema cuyo estado cambia con el tiempo debido a la interacción de sus elementos internos o con el entorno.

> 🔑 *Modelo matemático:* Representación de un sistema físico mediante ecuaciones matemáticas que describen su comportamiento.

> 🔑 *Ecuación diferencial:* Ecuación que relaciona una función con sus derivadas y describe la dinámica de un sistema.

# Sistemas Mecánicos
Un sistema mecánico es un conjunto de componentes diseñados para transmitir, transformar o controlar el movimiento y la energía mecánica. entre los cuales podemos encontrar los siguientes tipos de sistemas 

## 1. Sistema Masa-Resorte-Amortiguador
Este sistema está compuesto por una masa unida a un resorte y un amortiguador. Se modela con la ecuación diferencial:
```math
m \ddot{y} + c \dot{y} + ky = F(t)
```
Donde:
- *m* es la masa,
- *c* es la constante de amortiguamiento,
- *k* es la constante del resorte,
- *y* es el desplazamiento,
- *F(t)* es la fuerza aplicada.

## 2. Péndulo Simple
Un péndulo simple consta de una masa suspendida de un hilo que oscila bajo la acción de la gravedad. Se modela mediante la ecuación:
```math
\ddot{\theta} + \frac{g}{L} \sin\theta = 0
```
Donde:
- *\theta* es el ángulo de oscilación,
- *g* es la aceleración debido a la gravedad,
- *L* es la longitud del péndulo.

## 3. Ecuaciones resultantes

| Sistema | Ecuación de Movimiento |
|---------|----------------------|
| Masa-Resorte-Amortiguador | \$m \ddot{x} + c \dot{x} + kx = F(t)$ |
| Péndulo Simple | $\ddot{\theta} + \frac{g}{L} \sin\theta = 0$ |

Tabla 1. Resumen de ecuaciones de sistemas mecánicos.


# Rotacionales 
En los sistemas rotacionales se ven involucradas las variables como son el torque, el desplazamiento angular y velocidad angulas. Son comunes en motores electricos, engranajes, volantes de inercia y sistemas de transmicion de potencia

## 1. variables del sistema
Es importante destacar que las magnitudes en un sistema rotacional se pueden definir mediante tres parametros

- angulo de giro * 1* es la posicion angular del sistema medida en radianes
- velocidad angular *2* la rapidez con la que gira
- aceleracion angular *3* es la variacion de la velocidad angular, medida en (rad/s^2)
## 2. Ecuaciones de movimiento en sistemas rotacionales
Utilizando la segunda Ley de Newton para estos sistemas se determina como:

- suma de los momentos de torsion
- momento de inercia rotacional
- aceleracion angular
  
## 3. Modelamiento matematico 
## 4. Ejemplos
### 4.1 Ejemplo 1
### 4.2 Ejemplo 2

# Conclusiones
- El modelamiento de sistemas dinámicos permite predecir el comportamiento de sistemas mecánicos mediante ecuaciones diferenciales. Comprender estas ecuaciones es fundamental para el análisis y diseño de sistemas en ingeniería.

- Una vez obtenido un modelo matemático, se pueden realizar simulaciones para prever la respuesta del sistema ante distintos escenarios. Esto es crucial en el diseño de sistemas de control, ya que permite implementar estrategias para mejorar la estabilidad, el rendimiento y la eficiencia.

# Referencias
- Ogata, K. (2010). *Ingeniería de Control Moderna*. Pearson.
- Dorf, R. C., & Bishop, R. H. (2017). *Sistemas de control moderno*. Pearson.

## 4. Ejercicios

📚 **Ejercicio 1**

- imagennnn


# Solución Paso a Paso

## Paso 1: Definir el Sistema y las Variables

- **M₁**: Masa del vehículo  
- **M₂**: Masa del remolque  
- **Kₕ**: Constante elástica del acoplamiento  
- **Bₕ**: Coeficiente de amortiguamiento del acoplamiento  
- **Bᵢ**: Coeficiente de fricción viscosa del remolque  
- **y₁(t)**: Desplazamiento del vehículo  
- **y₂(t)**: Desplazamiento del remolque  
- **f(t)**: Fuerza aplicada al vehículo  

---

## Paso 2: Establecer las Ecuaciones de Movimiento

Usando la segunda ley de Newton, se pueden escribir las ecuaciones de movimiento para el vehículo y el remolque.

### Para el vehículo (M₁):

```math
M_1 \ddot{y}_1 (t) = f(t) - K_h (y_1 (t) - y_2 (t)) - B_h (\dot{y}_1 (t) - \dot{y}_2 (t))
```

### Para el remolque (M₂):

```math
M_2 \ddot{y}_2 (t) = K_h (y_1 (t) - y_2 (t)) + B_h (\dot{y}_1 (t) - \dot{y}_2 (t)) - B_i \dot{y}_2 (t)
```

---

## Paso 3: Simplificar las Ecuaciones

Combinamos términos para simplificar las ecuaciones.

### Para el vehículo (M₁):

```math
M_1 \ddot{y}_1 (t) = f(t) - K_h y_1 (t) + K_h y_2 (t) - B_h \dot{y}_1 (t) + B_h \dot{y}_2 (t)
```

### Para el remolque (M₂):

```math
M_2 \ddot{y}_2 (t) = K_h y_1 (t) - K_h y_2 (t) + B_h \dot{y}_1 (t) - (B_h + B_i) \dot{y}_2 (t)
```

---

## Respuesta Final

El sistema de ecuaciones diferenciales que representa el movimiento del vehículo y el remolque es:

### Para el vehículo (M₁):

```math
M_1 \ddot{y}_1 (t) = f(t) - K_h y_1 (t) + K_h y_2 (t) - B_h \dot{y}_1 (t) + B_h \dot{y}_2 (t)
```

### Para el remolque (M₂):

```math
M_2 \ddot{y}_2 (t) = K_h y_1 (t) - K_h y_2 (t) + B_h \dot{y}_1 (t) - (B_h + B_i) \dot{y}_2 (t)
```
