# Arquitectura de kubernetes

Un cluster consta de dos piezas fundamentales:
- Control plane (nodo maestro): es el responsable de gestionar el clsuter. Se limita a gestionar los recursos del cluster e interactuar con los workers.
  
- Workers (nodo de trabajo): aloja los pods (contenedores) y maneja cargas de trabajo. Se encargan de ejecutar las aplicaciones y servicios que se despliegan en el cluster.

Esta division de funciones permite que los nodos maestros sean muy fiables, y una mayor flexibilidad para escalar nodos de trabajo.
Todos los nodos ejecutan el software de kubernetes y se comunican entre sí a través de la red, repartiéndose las tareas y garantizando la disponibilidad de las aplicaciones.

![Arquitectura general kubernetes](imagenes/03-arquitectura-general.svg)
[Créditos: Imagen tomada de pabpereza.dev](https://pabpereza.dev/docs/cursos/kubernetes/arquitectura_de_kubernetes_control_plane_y_workers_explicados)


## Componentes de los nodos
Todos los nodos cuentan con los siguientes componentes:

- **Cointainer runtime:** software para ejecutar contenedores (docker, conteinerd, CRI-O, etc.)
  
- **Kubelet:** encargado de gestionar los contenedores y de garantizar que esten en un estado deseado. Tiene comunicacion con el API Server para recibir instrucciones y pasarlas al container runtime
  
- **Kube-proxy:** encargado de gestionar el tráfico de red en el nodo, enruta las peticiones a los servicios, balancea la carga entre pods y expone los servicios al exterior.
 

## Componentes del nodo maestro
El nodo maestro es el mas complejo y cuenta con los siguientes componentes:

- **Kube-apiserver:** punto de entrada al cluster, tiene diferentes tareas entre las cuales se encuentran: gestionar peticiones (de usuarios y de los nodos de trabajo) para transformarlas en acciones y almacenar estado del cluster. Es el único que se comunica directamente con la base de datos de kubernetes (etcd).

- **Kube-scheduler:** encargado de decidir en qué nodo se ejecuta un pod. Decide de acuerdo a las necesidades de los pods y en las capacidades de los nodos

- **Etcd:** base de datos de kubernetes. Almacena el estado del cluster

- **Kube-controller-manager:** encargado de gestionar los controladores de kubernetes

- **Cloud-controller-manager:** similar a Kube-controller-manager pero par entornos en la nube.

>[!NOTE]
>Los controladores son procesos que se encargan de mantener el estado del cluster, estos suelen ejecutarse continuamente.

En conjunto, estos componentes garantian que los kubelets de los nodos de trabajo ejecuten los pods, y tambien se aseguran de mantenerlos en un estado deseado.