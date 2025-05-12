# Kubernetes

## ¿Qué es Kubernetes?
Es una plataforma open-source de orquestación de contenedores.
Permite crear una capa de abstracción entre la infraestructura y las aplicaciones. Por ejemplo, teniendo multiples servidores, permite agruparlos en un **clúster** y manejarlo como una sola pieza, esto permite desplegar aplicaciones sobre todos los **nodos** del clúster de una forma transparente.

Al desarrollador le permite crear aplicaciones sin tener que preocuparse por la infraestructura. Mientras que al administrador de sistemas le permite dedicarse a mantener la infraestructura y los nodos del clúster sin preocuparse de las aplicaciones que se desplieguien en el.

## Ejemplo practico. 
En un entorno tradicional, un administrador de sistemas tendria que aporvisionar una maquina virtual con los requisitos especificos (paqueterias, configuracion de red, hardware, etc.) por cada aplicacion.


![Aprovisionamiento VM](imagenes/01-aprovisionamiento-vm.svg)
[Créditos: Imagen tomada de pabpereza.dev](https://pabpereza.dev/docs/cursos/kubernetes/Introduccion)

En un entorno de kubernestes, creado por 4 servidores (1 nodo maestro y 3 trabajadores), el administrador solo tendria que añadir y mantener los nodos del cluster. 
Cuando se requiera gregar una aplicacion nueva se pueden asignar una cantidad de los recursos del clúster.
La pincipal diferencia es que no se tendria que dar una "maquina" sino solo un número de recursos cuantificados de CPU y RAM del cluster.

![Entorno Kubernetes](imagenes/02-entorno-kubernetes.svg)
[Créditos: Imagen tomada de pabpereza.dev](https://pabpereza.dev/docs/cursos/kubernetes/Introduccion)

## Beneficios de Kubernetes.
Kubernetes ofrexe las siguientes ventajas:.

- **Escalabilidad:** permite escalar (vertical y/o horizantal) aplicaciones de forma automatica en funcion de la demanda.
- **Resilencia:** kubernetes es capaz de reubicar la aplicacion en caso de que falle un nodo o contenedor. Ademas, permite la replicacion de aplicaciones para garantizar la disponibilidad
- **Automatización:** permite automatizar tareas como el despliegue, la escalabilidad, auto-reparación, etc. 
- **Estandarizacion:** Al ser open-source se ha convertio en un estandar enla orquestacion de contenedores. La mayoria de servicios en la nube ofrecen soporte para Kubernetes, esto permite crear entornos interoperables entre si, permitiendo migrar de manera facil entre entornos, crear entornos hibridos o multi-cloud.
- **Ecosistema:** cuenta con un amplio ecosistema que permite extender su funcionalidad.