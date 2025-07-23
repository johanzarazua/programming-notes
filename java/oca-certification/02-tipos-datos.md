# 2. Tipos de datos

En java los datos son manejados a traves de variables. Una variable es un espacio en memoria a la cual se le accina un identificador y se almacenan los datos que se manejaran en el programa.

## 2.1 Declaracion de variables 

En java es necesario declarar la variable antes de utilizarla, la declaracion de una variable consiste en indicar al compilador el tipo de e indentificador de la variable. Esto se consigue siguiendo la estructura `<tipo> <identificador>;` por ejemplo `int edad;`

una vez declarara podemos asignarle un valor, esto se hace con la estructura `<identificador> = <valor>;`, siguiendo el ejmplo anteriro, la asigancion de valor seria de la siguiente manera `edad = 25;`

Es posible declarar e inicializar una variable en una sola linea: `int edad = 25;`, incluso tambien es permitido declarar e inicializar multiples variables en una linea: `int a = 3, b = 5, c;`

## 2.2 Identificadores

Al momento de declarar una variable es necesario colocar un identificar, el identificador debe de cumplir con las siguientes reglas:
- Se pueden utilizar cualquier combinacion de letras, numeros y los simbolos $ y _
- No se pueden utilizar palabras reservadas
- No puede comenzar con por un caracter numerico

>[!CAUTION]
>Si una de las reglas mencionadas no se cumple se genera in error de compilacion

```java
int _1 = 10 //valido
char break; //error, break es palabra reservada
int 3a; //error, no puede iniciar con numeros
float car.t; //error, simbolo . no permitido
```

## 2.3 Ambito de una variable

El ambito de una variable se refiere a la visibilidad de la misma, la cual esta determinada por la zona en la que sea declarada.
Existen dos ambitos:
- variable atributo: declarada a nivel de la clase, es visible por todos los metodos de la clase
- variable local: declarada dentro de un metodo, solo es visible para el metoddo que la declara

```java
public class Car{
    private String model; // varible atributo

    public void method1(){
        int b; //variable local
        a = "ABX-009"; //acceso a variable atributo
    }

    public void method2(){
        b = b+2; //error, varible no definida
    }
}
```

Java permite que una variable local tenga el mismo nombre que una variable atributo. En este caso para acceder a la variable atributo se debe usar this

```java
public class Car{
    private String model; // varible atributo

    public void method1(){
        String model; //variable local
        model = "ABX-009"; //acceso a variable local
        this.model = "ABC-008"; //acceso a variable atributo
    }
}
```

>[!NOTE]
>Las variables que se declaren dentro de bloques como if, for, while, etc. Solo son visibles dentro de ese bloque

