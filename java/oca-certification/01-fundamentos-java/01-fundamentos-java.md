# 1. Fundamentos de java
## 1.1 Principales características de Java
Las principales características de Java son:

* **Lenguaje orientado a objetos.** En los lenguajes orientados a objetos el código es escrito en clases, y se organiza en metodos (funciones) que se invocan mediante instancias de la clase (objetos). Este tipo de lenguajes tienen una serie de características como herencia, sobrecarga y sobrescritura, polimorfismo y encapsulación, que les dan una gran potencia.

* **Portabilidad.** Desde su primera version, lanzada por Sun Microsystems en mayo de 1995, java incorporó una característica muy importante, quizá la principal característica del lenguaje, se trata de la posibilidad de compilar una vez y ejecutar en cualquier parte. Esto quiere decir que el resultado de la compilación es independiente de la plataforma y puede ejecutarse en cualquier sistema operativo. Esto es gracias a un elemento clave de java conocido como Java Virtual Machine (JVM).

* **Encapsulación.** Consiste en la protección de atributos de la clase para que no sean accesibles desde el exterior, permitiendo el acceso a ellos mediante metodos.

* **Robusto.** La JVM gestiona de manera automática la memoria, de tal forma que no se permite el acceso a ella desde código y evita problemas de violación de acceso.

* **Seguro.** El código Java es ejecutado en un entorno controlado por la JVM lo que impide que se realicen operaciones dañinas sobre el equipo

### 1.1.1 Compilación de un programa Java
Los programas en Java se escriben en archivos .java (código fuente), al compilar estos archivos se generan archivos .class conocidos como bytecodes, estos son independientes de la plataforma y se pueden ejecutar en cualquier sistema que cuente con una JVM.

### 1.1.2 Java Virtual Machine (JVM)
La JVM es un software que se encarga de traducir en tiempo de ejecución los bytecodes a código máquina.
![java-compilation](..%2Fimgs%2Fjava-compilation.png)

La JVM incluye un interprete y otros componentes como el Gestor multitarea, el Recolector de basura (Garbage Collector), el Cargador de clases (Class loader) y el Compilador JIT.
El compilador JIT es un componente que se encarga de compilar algunas partes de código que tiene que interpretar para no tener que repetir el proceso de interpretación al ejecutar esos bloques de código

## 1.2 Programas en Java
### 1.2.1 Clases
Todos los programas en Java se organizan mediante clases. Esto nos ayuda a definir el comportamiento de los objetos creados con una clase.

Las clases cuentan con atributos, los cuales nos ayudan a indicar las características de los objetos, constructores, funciones que nos permiten crear instancias de la clase, y métodos, que definen las acciones que pueden realizar los objetos. Una vez que se define una clase se pueden crear instancias (objetos) de la misma para hacer uso de los atributos y metodos definidos.

Podemos entender una clase como un molde de galletas y a las instancias como las galletas.

### 1.2.2 Estructura de una clase
Una clase se define utilizando la palabra reservada class, seguida del nombre de la clase y entre llaves se definen el contenido de la clase.
Un ejemplo de una clase sería el siguiente 
```java
class ClassName{
  int a; //atributo
  public ClassName(){ //constructor
    
  }
  public void metodo1(){ //método
    
  }
}
```
Un archivo .java puede contener 1 o más clases, pero solo una debe tener la palabra reserveda public y el nombre de esta clase debe coincidir con el nombre del archivo .java
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
Si en un archivo .java aparecen dos clases que utilicen la palabra public, generaría un error de compilación, este error también puede generarse si el nombre de la clase que utiliza public no coincide con el nombre del archivo .java

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