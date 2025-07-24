# Kubernetes

## ¿Qué es Kubernetes?
Es una plataforma open-source de orquestación de contenedores.
Nos ayuda a automatizar la implementacion, escalado y operacion de aplicaciones en contenedores.
Crear una capa de abstracción entre la infraestructura y las aplicaciones.
Nos permite agrupar multiples servidores en un **cluster**, asi podemos manejarlos como una sola pieza. Esto nos ayuda a desplegar aplicaciones sobre todos los **nodos** del cluster de forma transparente

De esta forma el desarrollador puede centrarse en crear aplicaciones sin preocuparse de la infraestructura, y el administrador de sistemas puede dedicarse a mantener los nodos (servidores) sin preocuparse de las aplicaciones que se desplieguen en el.

Ejemplo. 
En un entorno tradicional, un administrador de sistemas tendria que aporvisionar una maquina virtual con los requisitos especificos (paqueterias, configuracion de red, hardware, etc.) por cada aplicacion.


![Aprovisionamiento VM](imagenes/01-aprovisionamiento-vm.svg)
[Créditos: Imagen tomada de pabpereza.dev](https://pabpereza.dev/docs/cursos/kubernetes/introduccion_a_kubernetes_guia_completa_para_principiantes)

En un entorno de kubernestes, creado por 4 servidores (1 nodo maestro y 3 trabajadores), el administrador solo tendria que añadir y mantener los nodos del cluster. 
La pincipal diferencia es que al solicitar una nueva aplicacion, se puede asignar una cantidad de recursos del cluster (RAM y CPU) y no se tendria que dar una "maquina" configurada con los requerimientos de la applicacion.

![Entorno Kubernetes](imagenes/02-entorno-kubernetes.svg)
[Créditos: Imagen tomada de pabpereza.dev](https://pabpereza.dev/docs/cursos/kubernetes/introduccion_a_kubernetes_guia_completa_para_principiantes)

## Beneficios de Kubernetes.
Kubernetes ofrece las siguientes ventajas:

- **Escalabilidad:** permite escalar (vertical y/o horizantal) aplicaciones de forma automatica en funcion de la demanda.
- **Resilencia:** kubernetes es capaz de reubicar la aplicacion en caso de que falle un nodo o contenedor. Ademas, permite la replicacion de aplicaciones para garantizar la disponibilidad
- **Automatización:** permite automatizar tareas de administracion como el despliegue, la escalabilidad, auto-reparación, etc. 
- **Estandarizacion:** Al ser open-source se ha convertio en un estandar enla orquestacion de contenedores. La mayoria de servicios en la nube ofrecen soporte para Kubernetes, esto permite crear entornos interoperables entre si, permitiendo migrar de manera facil entre entornos, crear entornos hibridos o multi-cloud.
- **Ecosistema:** cuenta con un amplio ecosistema que permite extender su funcionalidad.