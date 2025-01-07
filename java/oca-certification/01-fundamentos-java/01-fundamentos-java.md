# 1. Fundamentos de java
## 1.1 Principales características de Java
Desde su primera version, lanzada por Sun Microsystems en mayo de 1995, java incorporó una característica que hizo que tuviera una gran aceptación, se trata es la posibilidad de compilar una vez y ejecutar en cualquier parte.

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



