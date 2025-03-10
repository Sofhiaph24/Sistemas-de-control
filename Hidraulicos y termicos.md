# Sistemas hidraulicos y termicos

## 1 Sistemas hidraulicos 
### 1.1 Introduccion

Los sistemas hidraulicos operan una tecnolofia que utiliza los liquidos para generar movimiento o fuerza. Se rige con el principio de la ley de Pascal, la cual dice que la presion que se aplica sobre un fluido confinado se transmite uniformemente en todas las direcciones. Gracias a eso lo sistemas pueden incrementar la fuerza y manejar un control mas preciso de las maquinas.

### 1.2 Sistema

Este sistema funciona mediante el principio de Pascal, en el cual es fundamental que mantengan un nivel de flujo constante, donde:
  - $q_{i}, q_{o}$; son los flujos de entrada y salida del liquido 
  - R, Es la resistencia al flujo
  - A, Area transversal del tanque
  - h, Nivel de liquido en el tanque  

### 1.3 Modelamiento tanques

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
 
#### 1.3.1 Ejemplo con dos tanques

$q_{i} = A_{1}\frac{dh_{1}}{dt} + q_{1}$

$q_{i} = A_{1}\frac{dh_{1}}{dt} + \frac{h_{1}}{R_{1}}$

$\frac{h_{1}}{R_{1}} = q_{i} - A_{1}\frac{dh_{1}}{dt}$

$\frac{h_{1}}{R_{1}} - q_{2} = A_{2}\frac{dh_{2}}{dt}$

$\frac{h_{1}}{R_{1}} = A_{2}\frac{dh_{2}}{dt} + q_{2}$

$q_{i} - A_{}\frac{dh_{1}}{dt} = A_{2}\frac{dh_{2}}{dt} + q_{2}$

#### 1.3.2 Ejemplo tanques interconectados

$q_{1} = \frac{h_{1} - h_{2}}{R_{1}}$

$A_{1}\frac{dh_{1}}{dt} = (q_{i} - q_{1})$

$q_{2} = \frac{h_{2}}{R_{2}}$

$A_{2}\frac{dh_{2}}{dt} = (q_{1} - q_{2})$

$R_{2}A_{2}\frac{dq_{2}}{dt} = (q_{1} - q_{2})$

$R_{2}A_{2}\frac{dq_{2}}{dt} + q_{2} = q_{1}$

$A_{1}\frac{dh_{1}}{dt} = (q_{i} - R_{2}A_{2}\frac{dq_{2}}{dt} + q_{2})$

$R_{1}q_{1} + h_{2} = h_{1}$

$R_{1}(R_{2}A_{2}\frac{dq_{2}}{dt} + q_{2}) + R_{2}q_{2} = h_{1}$

$A_{1}d\frac{(R_{1}(R_{2}A_{2}\frac{dq_{2}}{dt} + R_{2}q_{2}))}{dt} = q_{i} - R_{2}A_{2}\frac{dq_{2}}{dt} + q_{2}$

$A_{1}R_{1}R_{2}A_{2}\frac{d^{2}q_{2}}{dt^{2}} + (A_{1}R_{1} + A_{1}R_{2} + R_{2}A_{2})\frac{dq_{2}}{dt} - q_{2} = q_{i}$ 



### 1.6 Ejercicio
### 1.7 Conclusion

## 2 Sistemas termicos
### 2.1 Introduccion 
### 2.2 Sistema
### 2.3 Modelamiento
### 2.4 Conclusion 
 





## 4. Definiciones
Utilice el símbolo '>' para crear bloques de texto. En la presente plantilla estas cajas están reservadas para resaltar las definiciones, las cuales deben ser breves, y la palabra o frase que se está definiendo debe estar en letra itálica. El inicio del bloque de texto debe realizarse con el emoji 🔑 .
>🔑 *Definición:* descripción precisa y clara del significado de una palabra, término, concepto o fenómeno. Es una explicación que establece los límites y el alcance de aquello que se está definiendo, aclarando su naturaleza, características esenciales y, en algunos casos, su relación con otros conceptos.



## 9. Ejercicios
Deben agregar 2 ejercicios con su respectiva solución, referentes a los temas tratados en cada una de las clases. Para agregar estos, utilice la etiqueta #, es decir como un nuevo título dentro de la clase con la palabra 'Ejercicios'. Cada uno de los ejercicios debe estar numerado y con su respectiva solución inmediatamente despues del enunciado. Antes del subtitulo de cada ejercicio incluya el emoji 📚


## 5. Referencias
Agregue un subtítulo al final donde pueda poner todas las referencias consultadas incluyendo el origen o fuente de los ejercicios planteados. Tambien dentro del texto referencie los textos o artículos consultados y las figuras y tablas dentro de la explicación de las mismas.
