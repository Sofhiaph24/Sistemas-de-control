# RESUMEN CLASE 4 

## 1. Circuitos con amplificadores operacionales 

### 1.1 Introduccion 
Un amplificador es un dispositivo electronico que sirve para aumentar la amplitud de una señal electrica sin cambiar en gran medida sus caracteristicas principales. Los que tienden a ser mas usados son los amplificadores operacionales, esto debido a que tienen una buena estabilidad y versatilidad; ademas son muy utiles para procesar señales. Para utilizar los amplificadores operacionales tenemos varios tipos de configuraciones que pueden ser utilizadas, las que usaremos en el curso son el amplificador inversor y el no inversor; cada uno se puede usar para diferentes tareas, y dependiendo de la señal que necesitemos podremos usar uno u otro.

### 1.2 Amplificador no inversor
El amplificador no inversor es una connfiguracion del amplificador operacional, donde la señal de entrada se aplica a la entrada no inversora (La parte positiva del operacional +) y la terminal inversora se conecta a una red de realimentacion resistiva, donde se regula la ganacia del amplificador. Algunas de las caracteristicas de esta configuracion son que tension entre las dos entradas del amplificador son iguales (V+ = V-); y que las corrientes que pasan por las entradas es igual a cero. Para poder modelarlo utilizaremos las leyes de kirchoff, y el modelo simplificado de los amplificadores operacionales.

### 1.3 Ejemplo 

![](Imagenes/Amplificadores1.PNG).

Figura 1. Ejemplo amplificadores 

Como ejemplo utilizaremos el de la imagen, en donde observamos que el circuito tiene dos resistencias, donde nuestra variables de interes sera $e_{o}$. la primer resistencia va entre la salida del amplificador y la entrada del terminal negativo, y la segunda va desde la salida, hasta tierra. 
Lo primero que hacemos es usar la ley de nodos, la cual nos dice que la suma de las corrientes que pasan por las resistencias es igual a cero

$i_{1} - i_{2} = 0$

Luego reemplazamos las corrientes para dejarlo todo en termino del voltaje utilizando la ley de ohm, como la primer resistencia esta siendo afectada por los voltajes de entrada y salida el valor la corriente en ese punto sera la diferencia entre los voltajes de entrada y salida sobre el valor de la resistencia; y como la segunda resistencia esta entre la salida y tierra el valor de la corriente sera el voltaje de salida sobre la corriente

$\frac{e_{o}-e_{i}}{R_{2}} - \frac{e_{i}}{R_{1}} = 0$

Por ultimo lo que hacemos es separar variables y despejar la ecuacion para que nos quede el modelo de la salida del amplificador $(e_{o})$

$\frac{e_{o}}{R_{2}} = e_{i}(\frac{1}{R_{2}} + \frac{1}{R_{1}})$

$e_{o} = e_{i}(1 + \frac{R_{2}}{R_{1}})$

### 1.4 Ejercicio
### 1.5 Conclusion 

## 2 Sistemas hidraulicos 
### 2.1 Introduccion

Los sistemas hidraulicos operan una tecnolofia que utiliza los liquidos para generar movimiento o fuerza. Se rige con el principio de la ley de Pascal, la cual dice que la presion que se aplica sobre un fluido confinado se transmite uniformemente en todas las direcciones. Gracias a eso lo sistemas pueden incrementar la fuerza y manejar un control mas preciso de las maquinas.

### 2.2 Sistemas

Estos sistemas funcionan mediante el principio de Pascal, y es fundamental que mantengan un nivel de flujo constante, donde:
  - $q_{i}, q_{o}$; son los flujos de entrada y salida del liquido 
  - R, Es la resistencia al flujo
  - A, Area transversal del tanque
  - h, Nivel de liquido en el tanque  

### 2.3 Modelamiento tanques

Flujo de salida del tanque:

 - $q_{1} = \frac{h_{1}}{R_{1}}$

Intercambio de masa:

 - $A_{1}\frac{dh_{1}}{dt} = q_{i} - q_{1}$

Modelo entrada $q_{i}$ y $h_{1}$ como altura 

- $q_{1} = \frac{d_{1}}{R1}$
- $A_{1}\frac{dh_{1}}{dt} = q_{i} - q_{1}$
- $A_{1}\frac{dh_{1}}{dt} = q_{i} - \frac{h_{1}}{R_{1}}$

Modelo entrada $q_{i}$ y $q_{1}$ como salida

- $q_{1} = \frac{h_{1}}{R1}$
- $A_{1}\frac{dh_{1}}{dt} = q_{i} - q_{1}$
- $h_{1} = q_{1}*R1$
- $R1A_{1}\frac{dh_{1}}{dt} = q_{i} - q_{1}$ 
 
#### 2.3.1 Ejemplo con dos tanques
#### 2.3.2 Ejemplo tanques interconectados

### 2.6 Ejercicio
### 2.7 Conclusion

## 3 Sistemas termicos
### 3.1 Introduccion 
### 3.2 Sistema
### 3.3 Modelamiento
### 3.4 Conclusion 
 





## 4. Definiciones
Utilice el símbolo '>' para crear bloques de texto. En la presente plantilla estas cajas están reservadas para resaltar las definiciones, las cuales deben ser breves, y la palabra o frase que se está definiendo debe estar en letra itálica. El inicio del bloque de texto debe realizarse con el emoji 🔑 .
>🔑 *Definición:* descripción precisa y clara del significado de una palabra, término, concepto o fenómeno. Es una explicación que establece los límites y el alcance de aquello que se está definiendo, aclarando su naturaleza, características esenciales y, en algunos casos, su relación con otros conceptos.



## 9. Ejercicios
Deben agregar 2 ejercicios con su respectiva solución, referentes a los temas tratados en cada una de las clases. Para agregar estos, utilice la etiqueta #, es decir como un nuevo título dentro de la clase con la palabra 'Ejercicios'. Cada uno de los ejercicios debe estar numerado y con su respectiva solución inmediatamente despues del enunciado. Antes del subtitulo de cada ejercicio incluya el emoji 📚


## 5. Referencias
Agregue un subtítulo al final donde pueda poner todas las referencias consultadas incluyendo el origen o fuente de los ejercicios planteados. Tambien dentro del texto referencie los textos o artículos consultados y las figuras y tablas dentro de la explicación de las mismas.
