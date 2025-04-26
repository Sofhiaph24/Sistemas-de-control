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

Para hacer el análisis de estabilidad por el método del valor final tendremos que comparar la entrada con la salida de nuestra función, para determinar si están limitadas de la misma forma.

#### 3.1.1. Ejemplo 1

En el siguitente ejemplo tenemos una funcion de tipo escalon, que vamos a comprobar si es estable

$$U(S) = \frac{A}{S}$$

Para saber si es estable vamos a usar el metodo del teorema del valor final explicado anteriormete, usando las formulas del limite cuando tiende a cero. 

$$s\lim_{ s\to 0} * U(S)$$

Lo que toca hacer es reemplazar nuestra funcion U(s) en nuestra ecuacion. Despues de eso sinplificamos nuestra "s" del numerador con la que multiplica el limite, y nos da que el resultado del analisis es "A"

$$s\lim_{s \to 0 } * \frac{A}{S} = A$$

Por lo tanto de este sistema podemos entender que es estable, debido a que el valor "A" esta limitado por la entrada

#### 3.1.2. Ejemplo 2

Para el segundo ejemplo se desea saber si la siguiente funcion es estable ante una entrada escalon, usando el metodo del teorema del valor final 

$$G = \frac{8}{2s-1}$$

Lo primero que hacemos es aplicar la formula del teorema y reemplazar valores con los de la funcion que tenemos.

$$\lim_{s \to 0} * \frac{A}{S} * \frac{8}{2s-1}$$

Despues de eso simplificamos terminos y reemplazamos la "s" sobrante por cero como indica el limite, dejandonos lo siguiente:

$$frac{-8A}{1} = -8A$$

Por ultimo simplificamos la funcion y nos queda -8A. Esto significa que la funcion no es estable, esto debido a que el escalon es positivo, pero la respuesta que obtenemo es negativo; por lo que no estan limitados de la misma manera

### 3.2. Analisis por ubicacion de polos 

## 4. Criterio de Routh Hurwitz

## 5. Diseño controlador estable 

## 6. Conclusion

## 7. Referencias

- C. Chen, Analog and digital control system design, New York, Saunders College Publishing
- Introducción a los sistemas de control, R. Hernandez, Pearson, 2010
- Ogata, K. Ingeniería de Control Moderna. 5 edición. Prentice Hall
