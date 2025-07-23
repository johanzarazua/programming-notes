# 1. Fundamentos de java

<!-- TODO: Agregar historia de Java -->

## 1.1 Principales características de Java
Las principales características de Java son:

- **Orientado a objetos.** El codigo es escrito en clases, las cuales contienen atributos (caracteristicas de la clase) y metodos que pueden ser inovcados por instancias de la clase.
Los lenguajes orientados a objetos tienen una serie de caracteristicas como herencia, sobrecarga, sobreescritura, polimorfismo y encapsilacion, que los dotan de un gran potencia.

- **Portabilidad.** Java nos brinda la posibilidad de poder compilar una vez y ejecutar en cualquier parte, esto es gracias a un elemento clave del lenguaje llamado Java Virtual Machine (JVM). Esto quiere decir que el resultado de la compilacion es independiente a la plataforma y puede ejecutarse en cualquier sistema que cuenta con una JVM.
Esta es quizas la caracteristica principal del lenguaje. 

* **Encapsulación.** Consiste en la protección de atributos de la clase para que no sean accesibles desde el exterior, permitiendo el acceso a ellos mediante metodos.

* **Robusto.** La JVM gestiona de manera automática la memoria, de tal forma que no se permite el acceso a ella desde código y evita problemas de violación de acceso.

* **Seguro.** El código Java es ejecutado en un entorno controlado por la JVM lo que impide que se realicen operaciones dañinas sobre el equipo

### 1.1.1 Compilación de un programa Java
Los programas en Java se escriben en archivos .java (código fuente), al compilar estos archivos se generan archivos .class conocidos como bytecodes, estos son independientes de la plataforma y se pueden ejecutar en cualquier sistema que cuente con una JVM.

### 1.1.2 Java Virtual Machine (JVM)
La JVM es un software que se encarga de traducir en tiempo de ejecución los bytecodes a código máquina.
![java-compilation](..%2Fimgs%2Fjava-compilation.png)

La JVM incluye difernetes componentes, entre los cuales se encuentran:
- Gestor multitareas
- Garbage Collector
- Class Loader
- JIT Compiler
<!-- TODO: agregar descripcion de cada componente -->

Existen versionde de la JVM para cada sistema operativo lo que permite que un programa compilado (archivos .class) pueda ser ejecutado en cualquier S.O.

## 1.2 Programas en Java
### 1.2.1 Clases
Todos los programas en Java se escirben dentro de clases, el objetivo de una clase es definir el comportamiento de los objetos creados a partir de ella.  

El comportamiento de una clase se define mediante atributos y metodos.
- atributos: definen caracteristicas de los objetos
- metodos: definen las operaciones que puede realizar un objeto

Podemos entender/pensar en una clase como si un molde y los objetos las entidades "fisicas" creadas mediante el molde

### 1.2.2 Estructura de una clase
Una clase se define utilizando la palabra reservada `class`, seguida del nombre de la clase y entre llaves se definen el contenido de la clase.
Un ejemplo de una clase sería el siguiente:

```java
class ClassName{
  int a; //atributo
  public ClassName(){ //constructor
    
  }
  public void metodo1(){ //método
    
  }
}
```

Un archivo .java puede contener 1 o más clases, pero solo una debe tener la palabra reserveda public (y debe coinicidir con el nombre del archivo .java)

Suponiendo que tenemos un archivo con el nombre CLase1.java, un ejemplo del contenido del archivo puede ser el siguiente
```java
public class Clase1{
  public void metodo1(){
    
  }
}

class Clase2{
  public void metodo2(){

  }
}

```

> [!CAUTION]
> Si dos clases dentro de un archivo contienen la palbra `public` se generara un error de compilacion. Este error tambien puede ser producido si la clase publica no coincide con el nombre del archivo


### 1.2.3 Paquetes (Packages)
Las clases se organizan en paquetes (directorios), un paquete puede contener varios archivos .java e incluso subpaquetes

Dentro del archivo .java el paquete se indica utilizando la palabra **package** y debe colocarse al inicio, de modo que todas las clases contenidas en este archivo sé encontrar en el mismo paquete.
Ejemplo
```java
package mypackage;

public class Clase1{
  public void metodo1(){
    
  }
}

class Clase2{
  public void metodo2(){

  }
}
```

> [!IMPORTANT]
> la sentencia `package` debe ser la primera en el archivo .java

### 1.2.4 Metodo main
El metodo `main()` representa el punto de entrada/inicio de un programa Java. Este metodo es utilizado por la JVM para ejecutar una clase.
Es comun que los programas en Java cuenten con muchas clases, entre todas ellas una debera contener el metodo main.

El metodo main puede tener dos formatos validos.
La diferencia entre ellos es la forma de definir los argumentos de entrada, estos pueden ser con un arreglo de String (formato 1) o indicando un numero de variable de argumentos (formato 2)

```java
//formato 1
public class ClaseA{
  public static void main (String[] args){

  }
}

//formato 2
public class ClaseA{
  public static void main (String ... args){

  }
}
```

Algunos ejemplos incorretos de la declaracion del metodo main son los siguientes
```java

static void main(String[] args) //falta public

public void main(String[] args) //falta static

public static int main(String[] args) //tipo de retorno incorrecto

public static void Main(String[] args) //nombre incorrecto

```


> [!CAUTION]
> Los ejemplos anteriores no provocan un error de compilacion ya que sintacticamente son correctos, sin embargo se generaria un error ejecucion ya que la JVM no encontraria el metodo main

## 1.3 Compilacion y Ejecucion

### 1.3.1 Herramientas JDK

El JDK (Java Development Kit) cuenta con un conjunto de herramientas basicas que nos permiten compilar y ejecutar progrmas java, asi como con las clases que forman el Java Standard Edition (Java SE)

El comando para compilar un archivo .java tiene el nombre de `javac`, mientras que el comando para ejecutar una clase se llama `java`. Ambos comandos se enccuentran dentro del directorio de instalacion del JDK, en la subcarpeta bin.

### 1.3.2 Compilacion 

Para compilar un archivo .java, debemos situarnos desde terminal en la ruta donde se encuentre nuestro archivo y lanzaremos el comando

```shell
javac Archivo.java
```

Si las clases se encuentran definidad en un paquete y queremos generar la estructura de carpetas correspondiente debemos usar el comando

```shell
javac -d . Archivo.java
```

En caso de existir errores de compilacion se mostraran en la salida del comaando, de lo contrario se generaran los arhivos .class correspondientes.

### 1.3.3 Ejecucion

Para ejecutar un programa java deberemos colocarnos desde terminal en la ruta donde se realizo la compilacion y ejecutaremos el siguiente comando utilizando la clase que contiene el metodo main.

```shell
java Archivo
```

si la clase se ecuentra dentro de algun paquete, se debe indicar el nombre cualificado de la clase.

```shell
java paquete.Archivo
```

> [!NOTE]
> Al ejecutar una clase se indica el nombre de la misma, no el nombre del archivo .class
