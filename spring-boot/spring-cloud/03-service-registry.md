# Service Registry
Spring Cloud porporciona una herramienta llamada Eureka Server la cual nos permite crear un Service Registry.

- Registro y localizacion de microservicios: Nos permite saber los microservicios que tenemos y en que lugar viven
- Conocer estado de los microservicios: los microservicios conectados (eureka-client) envian una señal (heartbeats) cada 30 segundos para informar su estado
- Copia en cache en microservicios: cada microservicio (eureka-client) tiene una copia en cache del registro de Eureka para conocer que microservicios estan activos
- Modo cluster: es un modo recomendable para cuando se quiera operar en produccion
- Modo selft-preservation: es un modo que se activa cuando los microservicios registrados no notifican su estado a Eureka Server

## Como utilizarlo

Para poder incluirlo en un proyecto de Java con Spring Boot se deben seguir los siguientes pasos:

### Dependencias
 agregar las siguientes dependencias:
- Eureka Server: permite configurar la aplicacion como un Server Registry
- Config client: permite conectar al Config Server

### Activar proyecto como server registry
Se debe inidicar que la aplicacion es un servidor de registro, para ello se debe anotar la clase principal con `@EnableEurekaServer`

### Configurar properties en config server
En la carpeta configurada en nuestros config server se debe agregar un nuevo properties "registry-service.yaml" y publicarlo en el repositorio.
Aqui se debe configurar lo siguiente:

```yaml
server:
  port: <puerto donde ejecutara>

eureka:
  instance:
    hostname: <host donde ejecutara>
  client:
    registerWithEureka: false
    fetchRegistry: false
    serviceUrl:
      defaultZone: http://${eureka.instance.hostanme}:${server.port}/eureka/
```

### Modificacion de properties por bootstrap
Se debe sustituir el archivo application.properties por un archivo llamado bootstrap.yml

En este archivo se debera configurr el nombre del servicio y la conexion con el confg server

## Como conectar microservicios al server registry
Para conectar un microservice con el config server se deben agregar las siguientes dependencias:

- spring-cloud-starter-netflix-eureka-client

Posteriormente, se deben agregar los siguientes campos al properties del microservicio.

```yaml
eureka:
  client:
    serviceUrl:
      defaultZone: <direccion de server registry>
```

por ultimo se debe anotar la clase principal con `@EnableEurekaClient`