# Api Gateway
Un api gateway nos permite tener una unica puerta de entrada a todos los microservicios, asi los clientes no accederan directamente a los microservicios.

Nos ayuda con un enrutamiento dinamico, monitorizacion y seguridad. Ademas de que nos permite generar filtros en caliente.

## Como implemntarlo
Se debe crear un proyecto que utilice las dependencias:
- Gateway
- Config client
- Eureka Discovery Client

una vez creado el proyecto, se debe cambiar el application.properties por un bootstrap.yml en el cual colocaremos los siguientes parametros:

```yaml
spring:
  application:
    name: name
  cloud:
    config:
      uri:
      username:
      password:
```

Tambien es necesario crear su archivo de configuracion en el config server. Este debe ser similar al siguiente ejemplo:
```yaml
server:
  port: 8080

eureka:
  client:
    serviceUrl:
      defaultZone: <path eureka>

spring:
  cloud:
    gateway:
      discovery:
        locator:
          enabled: true
      routes:
        - id: <microservice-name>
          uri: lb://<microservice-name>
          predicate:
            - Path=<path microservice>
```

En la clase principal de este proyecto se debe anotar con ``@EurekaClient` para que se registre en eureka