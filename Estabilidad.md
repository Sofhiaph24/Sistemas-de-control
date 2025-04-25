# ESTABILIDAD

## 1.  Introduccion 

La estabilidad es una pieza fundamental a la hora de analisar y diseñar sistemas, debido a que este afecta el compotamiento que se tiene a lo largo del tiempo de funcionamiento. Los sistemas son considerados estables cuando ante una perturbacion que me afecta el sistema, puede mantenerse controlado, y regresar a un estado donde funcione correctamente.  

En este trabajo se resumira lo visto en la clase, donde se explicaran los distintos metodos para determinar si un sistema es estable, los criterios que se tienen en cuenta, y como diseñar un controlador que nos ayude a estabilizar el sistema, todo esto con ejemplos y ejercicios para comprender mejor el tema

## 2. Teorema del valor final 

Lo primero que se vio en clase fue el teorema del valor final, el cual nos permite determinar el valor aproximado de una funcion en el tiempo, todo en terminos del dominio de Laplace. Este teorema dice:

$$f\lim_{ t\to \infty } (t) = sF\lim_{ s\to 0 } (s)$$

### 2.1. Ejemplo 

Para este ejemplo tenemos la siguiente funcion de transferencia
$$G(s) = \frac{Y(s)}{U(s)} = \frac{4}{5s + 1}$$

Lo primero que haremos para probar el teorema del valor final sera despejar la salida del sistema

$$Y(s) = \frac{4*U(s)}{5s+1}$$

Para este ejercicio decidimos trabajar con una entrada escalon, por lo tanto se reemplaza mi entrada por $${\frac{1}{s}}$$

$$Y(s) = \frac{\frac{4}{s}}{5s+1}$$

Para determinar el valor final de Y(s) utilizamos el teorema del valor final  

$$sY\lim_{ s\to 0 } = s\lim_{ s\to 0 }* \frac{\frac{4}{s}}{5s+1}$$

Simplificamos la s, y nos queda una fraccion. Una vez reemplazada la s que multiplica el 5 nos da el valor final de nuestra salida, el cual es 4.

$$\lim_{ s\to 0 } \frac{4}{5s+1} = 4$$

## 3.   Analisas de estabilidad



### 3.1. Analisis por teorema del valor final 
### 3.2. Analisis por ubicacion de polos 

## 4. Criterio de Routh Hurwitz

## 5. Diseño controlador estable 

## 6. Conclusion

## 7. Referencias

- C. Chen, Analog and digital control system design, New York, Saunders College Publishing
- Introducción a los sistemas de control, R. Hernandez, Pearson, 2010
- Ogata, K. Ingeniería de Control Moderna. 5 edición. Prentice Hall
