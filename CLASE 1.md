# Sistemas Dinamicos
Los sistemas dinamicos son aquellos cuyos estados van variando en el tiempo en respuestas a entradas o perturvaciones externas sistemas dinamico.
El estudio de sistemas dinámicos es indispensable para el diseño y análisis de sistemas de control, para asi predecir su comportamiento ante diferentes condiciones,perturvaciones  y garantinzar su rendimiento de una manera mas optima.

El modelado matemático de un sistema dinámico consiste en describir su comportamiento mediante ecuaciones diferenciales, obtenidas a partir de leyes físicas fundamentales como:

🔹Leyes de Newton en sistemas mecánicos.

🔹Leyes de Kirchhoff en sistemas eléctricos.

🔹Principios de conservación de energía y masa en sistemas térmicos e hidráulicos.


# Sistemas Mecanicos 
Para modelar sistemas mecanicos necesitamos tener un conocimiento basico de la mecanica clasica y las ley Newton,tambien tener conocimiento sobre matematicas para poder resolver ecuaciones diferenciales para comprender el sistema.En los sistemas Mecanicos tendremos sistemas de describen la corelacion entre fuera, desplazamiento, friccion, velocidades y aceleracion. Tener estos conocimientos y poder hacer el modelamiento del sistema es muy util ya que nos permite poder evaluar el comportamiento y funcionamiento de un sistema antes de su implementacion fisica.
## 1. Masa Resorte Amortiguador
Este sistema es un modelo que usamos para estudiar el comportamiento de los sistemas mecanicos cuando estan expuestos a un movimiento.En sistemas de control es un modelo que representa un sistema dinamico de segundo orden, el cual nos sirve para enteder la estabilidad y el comportamiento fisico ante perturbaciones externas, en este sistemas en espesifico la masa representa la inercia, el resorte representa la elasticidad y el amortiguador introduce disipacion de la energia.
Este sistema se describe mediante una ecuacion diferencial lineal, que nos permite diseñar controladores que regulen su comportamiento y ayudar a prevenir las oscilaciones y tener un sistema mas estable que es lo que siempre se busca.

Las ecuaciones de un sistema masa-resorte-amortiguador son:

$$
F_R = k_2 \cdot x
$$

$$
F_F = k_1 \cdot v_m
$$

$$
F = m \cdot a
$$

Donde:  
- \( F_R \) es la fuerza del resorte.  
- \( F_F \) es la fuerza de fricción viscosa.  
- \( F \) es la fuerza neta aplicada.  
- \( k_2 \) es la constante del resorte.  
- \( k_1 \) es el coeficiente de amortiguamiento.  
- \( v_m \) es la velocidad de la masa.  
- \( m \) es la masa.  
- \( a \) es la aceleración.  

Como ya se habia mencionado anteriormente este sistema cueta con 3 principales componentes que se van a describir a continuacion.

### 🔑 1.1. Masa (m)
Es el objeto que se mueve, tiene inercia esto quiere decir que resiste cambios en su movimiento.

Almacena energia cinetica cuando esta en movimiento.

### 🔑 1.2. Resorte (k)
Es aquel que se estira o se comprime.

Sigue la Ley de Hooke en la cual k es la constante del resorte,x cuando se estira o se comprime 

### 🔑 1.3. Amortiguador (c)
Hace referencia a un piston que frena el movimiento.

La fuerza que hace depende de la velocidad.

Disipa energia en forma de calor.


## 3. Ejemplos
💡**Ejemplo 1:** # Modelo Matemático de la Suspensión de un Automóvil

![Diagrama de la suspensión](imagen_2025-03-10_092507139.png)

El sistema está compuesto por una masa \( m \) que representa el chasis del vehículo, un resorte con constante \( k_2 \), y un amortiguador con coeficiente \( k_1 \). También se considera una fuerza de entrada \( u(t) \).

## Ecuación de Movimiento

Aplicando la Segunda Ley de Newton:

$$
u(t) + F_w - F_R - F_F = m \cdot a
$$

Sustituyendo las expresiones para cada fuerza:

$$
- u(t) + mg - k_2 y(t) - k_1 y'(t) = m y''(t)
$$

Donde:
- \( u(t) \) es la entrada al sistema.
- \( mg \) es la fuerza gravitacional.
- \( k_2 y(t) \) es la fuerza restauradora del resorte.
- \( k_1 y'(t) \) es la fuerza de amortiguamiento.
- \( y''(t) \) es la aceleración del sistema.

---


## 4. Ecuaciones
Para la edición de ecuaciones debe utilizar la etiqueta '$$' al comienzo y final de la ecuación para que la ecuación quede centrada ocupando una línea. Si se quiere que la ecuación quede integrada en el texto debe utilizar la etiqueta '$' al comienzo y final de la ecuación. Las ecuaciones pueden ser editadas utilizando el código LATEX, en el siguiente enlace encuentran un editor de ecuaciones que les genera el código. http://www.alciro.org/tools/matematicas/editor-ecuaciones.jsp . Sin embargo hay muchas otras herramientas que pueden utilizar para esto.

💡**Ejemplo 1:** si se va a representar la ecuación de la ley de Ohm se puede mostrar así $R=\frac{V}{I}$ o también,

$$R=\frac{V}{I}$$

## 5. Figuras
Todas las figuras que incluya deben ser generadas por ustedes, **no utilizar las figuras de las presentaciones**. Para incluir figuras puede seguir los siguientes pasos:
* Primero escribimos ![]().
* Después escribimos, dentro de los corchetes, el texto alternativo. Este es opcional y solo entra en acción cuando no se puede cargar la imagen correctamente.
* Después escribimos, dentro de los paréntesis, la ubicación del archivo (ya sea una url o una ubicación dentro de algun folder local). Se recomienda poner las imágenes en una carpeta que se llame imágenes dentro del repositorio github para que no tengan problemas al cargar las imágenes.

💡**Ejemplo 2:**

![Figura de prueba](images/plantilla/Captura2.PNG)

Figura 1. Figura de prueba

Incluya la respectiva etiqueta a modo de descripción de la figura y mantenga numeración consecutiva para todas las figuras de la clase.


## 6. Ejercicios
Deben agregar 2 ejercicios con su respectiva solución, referentes a los temas tratados en cada una de las clases. Para agregar estos, utilice la etiqueta #, es decir como un nuevo título dentro de la clase con la palabra 'Ejercicios'. Cada uno de los ejercicios debe estar numerado y con su respectiva solución inmediatamente despues del enunciado. Antes del subtitulo de cada ejercicio incluya el emoji 📚


## 7. Conclusiones
Agregue unas breves conclusiones sobre los temas trabajados en cada clase, puede ser a modo de resumen de lo trabajado o a indicando lo aprendido en cada clase

## 8. Referencias
Agregue un subtítulo al final donde pueda poner todas las referencias consultadas incluyendo el origen o fuente de los ejercicios planteados. Tambien dentro del texto referencie los textos o artículos consultados y las figuras y tablas dentro de la explicación de las mismas.
