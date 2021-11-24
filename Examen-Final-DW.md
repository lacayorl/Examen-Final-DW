Examen Final DW
================
Roberto Lacayo
24/11/2021

## Instrucciones

-   Usted tiene el período de la clase para resolver el examen final.
-   La entrega del final, al igual que las tareas, es por medio de su
    cuenta de GitHub, adjuntando el link en el portal de MiU.
-   Pueden hacer uso del material del curso e internet (stack overflow,
    etc.). Sin embargo, si encontramos algún indicio de copia, se
    anulará el examen para los estudiantes involucrados.

## Serie Única: Conteste a las siguientes preguntas

## 1) ¿Qué es una expresión regular?

Una expresión regular es una cadena de texto que se crea con patrones
que ayudan a clasificar, encontrar, coincidir y controlar el texto al
que se le aplique y se utilizan normalente para localizar texto dentro
de algún archivo.

## 2) Enumere y explique brevemente cuatro aplicaciones prácticas en las cuales

las expresiones regulares son utilizadas.

1.  Busqueda de caracteres o secuencias: una aplicación de las regex es
    que podemos crear una expreción que facilite la busqueda de algun
    texto en especifico dento de un archivo, base de datos, etc.

2.  Modificación de texto: Las regex tienen un uso practico para
    localizar cierto patrón de un texto y seguir otro patrón para
    sustituir algún fragmento del mismo.

3.  Verificación de datos: Las regex también tienen la función de
    verificar si ciertos datos de un texto son los necesarios, por
    ejemplo verificar contraseñas o correos electronicos.

4.  Cuantificación de datos: También son muy utilies para realizar
    calculos numericos sencillos basados en el análisis de texto.

## 3) Explique brevemente las 3 condiciones que establecen que una tabla se

encuentra en formato tidy.

-   Cada variable es una columna: Esta condición significa que los datos
    que conforman una variable deben estar en la misma columna, es decir
    si existen variables categoricas por ejemplo, sus factores deben
    estar en la misma columna, no puede ser una columna por cada
    categoria de la variable.

-   Cada tabla se compone de una unidad observacional: Aquí hablamos de
    compara manzanas con manzanas, tenemos que asegurarnos de que cada
    operación que se haga en la data debe de concistenete con la
    información y el tipo de variables o datos que manejamos.

-   Cada observación forma una fila: las observaciones o entradas deben
    ser filas para un buen funcionamiento de la data, ya que no podemos
    tener variables y obervaciones en el mimso sentido, ya que pierde el
    valor de tidy.

## 4) Diagnostique y explique por qué la siguiente tabla no está en formato tidy.

Luego, explique cómo convertirla a formato tidy.

En la tabla del PDF podemos notar que no existe un formato tidy, ya que
las observaciones de fecha están en las columnas, cuando deberian ser
filas porque no son variables. Debería de tener una observación por cada
año en una sola columna que agrupe las fechas y por cada país y una sola
columna de valor que contenga los datos nuemricos que al final son la
misma información.

Esto se puede hacer mediante la función ´melt´ de la libreria
´reshape2´, definiendo como variables estaticas la de los países y
aplicandolo sobre las 3 columnas de años, para así conseguir una columna
de país, otra de año y una ultima de valores.

## 5) Diagnostique y explique por qué la siguiente tabla no está en formato tidy.

Luego, explique cómo convertirla a formato tidy.

Analizando la tabla del PDF podemos ver que no cumple con el formato
tidy, porque no sigue la condición de que cada tabla debe componerse de
una unidad observacional, aquí vemos que en la segunda variable o
columna tenemos 2 variables juntas, el jugador y su posición de juego.

Para arreglarlo al tratarse de texto podemos emplear ´regex´ de la
librearia ´stringr´ para crear una expresión que separe el nombre del
jugador de su posición y coloque la segunda en una nueva columna solo
para la variable de posición. Entregando una tabla de 3 columna (Equipo
- Jugador - Posición).

## 6) Diagnostique y explique por qué la siguiente tabla no está en formato tidy.

Luego, explique cómo convertirla a formato tidy.

Analizando la tabal en el PDF podemos ver que no cumple con el formato
tidy, porque existe más de una columna para una misma categoria de
variable, en el caso de la infraestructura deberia ser una sola columna
en la que las observaciones serán ´Urbano´ o ´Rural´ y en el caso de los
rangos de monto debería ser una sola columna de monto que contenga el
tipo de rango al que pertenece. Esto lo podemos solucionar de igual
forma con un ´melt´ a la tabla.

## 7) Sobre lubridate: Explique la diferencia entre las funciones period y las funciones duration.

Las funciones ´period´ miden el cambio de tiempo entre 2 instantes, esta
toma en cuenta la presencia de los segundos, años bisiestos y cualer
tipo de cambio horario. Por otro lado las funciones ´duration´ no toma
en cuenta estas ultimas variables y solo entrega el tiempo entre 2
instantes.

## 8) ¿En qué contexto utilizaría una función period y en cúal utilizaría una función duration?

Una función ´period´ sería empleada por ejemplo cuando queremos calcular
cuanto tiempo falta para algún evento historico, como un eclipse total,
ya que toma en cuenta los años bisiestos y el cambio en el tiempo. Y la
función de ´duraion´ la utilizaria para calcular el tiempo transcurrido
entre dos fechas en que unicametne necesite un dato general.

## 9) Explique el concepto de data Missing Completely at Random (MCAR).

El MCAR es cuendo el que los datos esten o no, no depende directametne
de las mediciones a las observaciones.

## 10) Si logramos verificar que la data faltante es MCAR, ¿cuál imputación recomendaría utilizar?

Se recomiensa utilizar una imputacion general, por medio de ´media´,
´moda´ y ´mediana´.

## 11) Si estamos realizando el análisis de una encuesta en la cual tenemos información sobre 150 individuos y tenemos valores faltantes en diferentes variables de nuestra tabla, ¿cúal de los siguientes métodos utilizaría y por qué?

-   Pairwise deletion

Se utiliza este metodo porque así se excluye del análisis los registros
completos si en dado caso falta algún valor.

## 12) 12.Usted se encuentra realizando un modelo sobre la capacidad necesaria que necesita para atender la demanda de transporte de un producto determinado. Se requiere que cumpla con el 90% de la demanda mensual. ¿Cúal de los siguientes métodos utilizaría para determinar con qué población de sus datos trabajar?

-   Min Max Scaling

Utilizariamos una normalización por una escala de minimos y maximos para
reescalar el rango de características para escalar el rango ´\[0,1\]´.

## 13)¿En qué contexto de Machine Learning se recomienda utilizar Min Max Scaling?

Es util cuando queremos normalizar datos que tengan un rango entre un
conjunto de valores arbitrarios, un ejemplo es el de rango de edades de
un grupo de personas.

## 14) Si encuentra que la distribución de sus datos tiene un comportamiento exponencial, ¿cúal técnica de normalización utilizaría para transformar los datos a una distribución normal?

Se puede utlizar una normalización por el valor z de la distribución.

## 15) Si se tiene una variable categórica con tres niveles, cúantas variables dummy necesita para poder pasar la data a un modelo econométrico o de machine learning?

-   Se necsitan 2 variables dummy

## 16) ¿En cuál contexto utilizamos one hot encoding?

Se utiliza para logica digital en circuitos o machine learning.

## 17) ¿Qué es un n-gram?

Un n-gram es una subsecuencia de cierta cantidad de elemtos que confoman
otra secuencia y se utiliza para seguir tendencias

## 18) Si quiero obtener como resultado las filas de la tabla A que no se encuentran en la tabla B, ¿cómo debería de completar la siguiente sentencia de SQL?

-   SELECT \* FROM A {} JOIN B ON A.KEY = B.KEY {}

respuesta:

-   SELECT \* FROM A LEFT JOIN B ON A.KEY = B.KEY WHERE A!=B
