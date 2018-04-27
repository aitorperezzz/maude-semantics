# Especificación de semánticas en Maude
En este repositorio hay carpetas para cada uno de los programas, que se detallan a continuación:

### **IMP**
Se trata de un lenguaje sencillo de alto nivel. Tiene las siguientes características:

  * _Variables_: cargando el módulo predeterminado de Maude QID tenemos disponibles los conjuntos de letras 
para representar variables. Cada variable está asociada a un número; esto se consigue con el módulo de la memoria
que asocia a cada nombre de una variable un número. Tenemos operaciones para acceder a los elementos de la memoria
y para añadir nuevos elementos.  
  * _Números naturales_: como un paquete predeterminado de Maude. No hay números reales.  
  * _Expresiones aritméticas_: Los casos base son los números y las variables. Existe una función que a cada variable
le puede extraer el número que representa en la memoria. Además, podemos construir nuevas expresiones aritméticas con
los símbolos para la suma y el producto.  No hay más operaciones porque solo disponemos de los números naturales.  
  * _Expresiones Booleanas_: dos valores true y false, y expresiones para el AND lógico, el OR lógico y el NOT
lógico. También podemos comparar expresiones aritméticas para obtener valores Booleanos. En concreto, podemos
comparar expresiones con un símbolo para el menor o igual, y con otro para la igualdad.  

En cuanto al funcionamiento de la semántica, la idea es "evaluar" un Programa en cierto estado de la memoria para obtener una de tres cosas:

* Bien una expresión aritmética, es decir, que la ejecución del programa sirve para devolver cierto valor para cierta
variable de la memoria.
* Bien una expresión Booleana, es decir, el programa puede devolver true o false a un programa de tipo expresión 
booleana.
* Bien un `skip`, que es un símbolo que indica que el programa ha terminado. Lo útil sería mirar en la memoria los valores
que nos interesan, ya que la utilidad del programa ha sido cambiar los mismos.

Dicha evaluación tiene la sintaxis `< Programa, Estado de la memoria >`.

### **Assembly**
Esto es un sencillo lenguaje ensamblador. La máquina a la que hacemos referencia tiene una memoria y tiene ocho registros
a nuestra disposición. Existen comandos para sumar los números guardados en dos registros y almacenar el resultado en un 
tercer registro, y acciones del estilo. Tenemos una memoria en la que podemos guardar datos también. Un programa escrito 
en este ensamblador consta de una serie de _líneas_ de la forma `{ Número de la instrucción ; Instrucción }`. Con un contador
de programa, se puede saber cuál es la instrucción que debe ejecutarse a continuación. Como funcionamiento normal, el contador de
programa va incrementando de uno en uno según se ejecutan programas. Este comportamiento se puede alterar con ciertas operaciones.
Las instrucciones pueden ser de varios tipos:

* Operaciones aritméticas. De suma y resta de números. Estos números pueden estar almacenados en registros, o bien como inmediatos
(es decir, datos que se pasan dentro de la misma instrucción). No hay límite en el tamaño de un número.
* Operaciones de intercambio de datos entre registros y memoria. `LOAD` permite cargar datos desde la memoria hacia un registro,
para poder usar un operación aritmética sobre él. `STORE` permite guardar un dato procedente de un registro, en una posición de la
memoria.
* Condiciones de salto. Si se cumplen ciertas condiciones, es posible alterar el sentido natural del contador de programa, y pasar a determinada línea de instrucción.
        
