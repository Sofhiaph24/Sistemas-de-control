# Resumen clase 3 

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

## 2. Definiciones
Utilice el símbolo '>' para crear bloques de texto. En la presente plantilla estas cajas están reservadas para resaltar las definiciones, las cuales deben ser breves, y la palabra o frase que se está definiendo debe estar en letra itálica. El inicio del bloque de texto debe realizarse con el emoji 🔑 .
>🔑 *Definición:* descripción precisa y clara del significado de una palabra, término, concepto o fenómeno. Es una explicación que establece los límites y el alcance de aquello que se está definiendo, aclarando su naturaleza, características esenciales y, en algunos casos, su relación con otros conceptos.

## 3. Subsecciones
Las subsecciones pueden utilizarse para sub dividir ciertos temas que se tienen en clases, por ejemplo si se está trabajandolos conversores D/A, puede ser necesario subdividir este en circuito de resistencias ponderadas y circuito de escalera R2R. 
### 3.1. Título de subsecciones
Para la creación de estas subsecciones debe utilizar un tamaño de letra más pequeño, por lo tanto utilice la etiqueta '###' 
### 3.2. Numeración de subsecciones
Siga la numeración de la sección seguida de un punto y luego el número de la subsección.

## 4. Ejemplos
Si en algún caso pretende dar un ejemplo explicativo ya sea a través de texto o através de ecuaciones matemáticos, utilizar la palabra 'Ejemplo' seguido de una numeración consecutiva dentro de la clase. Utilice el emoji 💡 antecediendo la palabra.

## 5. Ecuaciones
Para la edición de ecuaciones debe utilizar la etiqueta '$$' al comienzo y final de la ecuación para que la ecuación quede centrada ocupando una línea. Si se quiere que la ecuación quede integrada en el texto debe utilizar la etiqueta '$' al comienzo y final de la ecuación. Las ecuaciones pueden ser editadas utilizando el código LATEX, en el siguiente enlace encuentran un editor de ecuaciones que les genera el código. http://www.alciro.org/tools/matematicas/editor-ecuaciones.jsp . Sin embargo hay muchas otras herramientas que pueden utilizar para esto.

💡**Ejemplo 1:** si se va a representar la ecuación de la ley de Ohm se puede mostrar así $R=\frac{V}{I}$ o también,

$$R=\frac{V}{I}$$

## 6. Figuras
Todas las figuras que incluya deben ser generadas por ustedes, **no utilizar las figuras de las presentaciones**. Para incluir figuras puede seguir los siguientes pasos:
* Primero escribimos ![]().
* Después escribimos, dentro de los corchetes, el texto alternativo. Este es opcional y solo entra en acción cuando no se puede cargar la imagen correctamente.
* Después escribimos, dentro de los paréntesis, la ubicación del archivo (ya sea una url o una ubicación dentro de algun folder local). Se recomienda poner las imágenes en una carpeta que se llame imágenes dentro del repositorio github para que no tengan problemas al cargar las imágenes.

💡**Ejemplo 2:**

![Figura de prueba](images/plantilla/Captura2.PNG)

Figura 1. Figura de prueba

Incluya la respectiva etiqueta a modo de descripción de la figura y mantenga numeración consecutiva para todas las figuras de la clase.

## 7. Tablas
En caso de necesitar la inclusión de tablas para organizar información se recomienda el uso de la herramienta del siguiente enlace https://www.tablesgenerator.com/markdown_tables , la cual permite organizar la información dentro de la tabla y genera el código markdown automáticamente:

💡**Ejemplo 3:** 

| **Resultado** | **x = número de intentos hasta primer éxito** |
|---------------|-----------------------------------------------|
|       S       |                       1                       |
|       FS      |                       2                       |
|      FFS      |                       3                       |
|      ...      |                      ...                      |
|    FFFFFFS    |                       7                       |
|      ...      |                      ...                      |

Tabla 1. Tabla de ejemplo

Cada tabla debe llevar la etiqueta que describa su contenido y numeración consecutiva para todas las tablas

## 8. Código
Teniendo en cuenta que el curso requiere del desarrollo de código matlab, c, c++ u otro. Si requiere incluir pequeños segmentos de código en los apuntes hágalos de la siguiente manera:

💡**Ejemplo 4:**
```
var sumar2 = function(numero) {
  return numero + 2;
}
```

## 9. Ejercicios
Deben agregar 2 ejercicios con su respectiva solución, referentes a los temas tratados en cada una de las clases. Para agregar estos, utilice la etiqueta #, es decir como un nuevo título dentro de la clase con la palabra 'Ejercicios'. Cada uno de los ejercicios debe estar numerado y con su respectiva solución inmediatamente despues del enunciado. Antes del subtitulo de cada ejercicio incluya el emoji 📚

## Rúbrica
| 0-1                                                                                   | 1-2                                                                                  | 2-3                                                                                                                                                                               | 3-4                                                                                                                                                                       | 4-5                                                                                                                                                                               |
|---------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Presenta menos del 10% de los temas o no presenta por  el medio y formato  solicitado | Presenta menos del 40% de los temas solicitados, y  cumple parcialmente la plantilla | Presenta menos del 60% de los temas solicitados (con descripciones, gráficos tablas, etc), y cumple  parcialmente la plantilla. No presenta la totalidad  de ejercicios resueltos | Presenta menos del 80% de los temas solicitados (con descripciones, gráficos, tablas, etc) y cumple con  la plantilla. No presenta  la totalidad de ejercicios  resueltos | Presenta el 100% de los temas vistos en clase (con descripciones, gráficos, tablas, etc), siguiendo totalmente la plantilla. presenta la  totalidad de los ejercicios solicitados |

## 10. Conclusiones
Agregue unas breves conclusiones sobre los temas trabajados en cada clase, puede ser a modo de resumen de lo trabajado o a indicando lo aprendido en cada clase

## 11. Referencias
Agregue un subtítulo al final donde pueda poner todas las referencias consultadas incluyendo el origen o fuente de los ejercicios planteados. Tambien dentro del texto referencie los textos o artículos consultados y las figuras y tablas dentro de la explicación de las mismas.
