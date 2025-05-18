# Actuator
Actuator es una libreria que nos propercia una amplia coleccion de funcionalidades para monitorear y administrar aplicaciones desarrolladas con Spring Boot, esto lo podemos hacer mediante endpoints y/o JMX Bean.

endpoint: http://<server>:<port>/actuator

## Como habilitarlo
Para habilitarlo debemos seguir los siguientes pasos.

1. Agregar la dependencia `spring-boot-starter-actuator`
2. Agregar la configuracion 
```yaml
#actuator    
management:
  endpoints:
    web:
      exposure:
        include: "*"
```


# Admin Server
Se encargar de administrar todas las metricas de los microservcios en un solo punto, es posible configurarlo para que tome las metricas devueltas por actuator.

## Como utilizarlo.
Para crear un admin server se debe crear un proyecto nuevo y seguir los siguientes paso:

1. Agregar las dependencias `Admin Server`
2. Habilitar el admin server decorando la clase principal del proyecto con `@EnableAdminServir`
3. Agregar configuraciones al application.properties 
```properties
spring.application.name=<name>
server.port=<port>
```
4. Agregar dependencia en microservices para que se conecten al admin server `spring-boot.admin-starter-client` y agregar en bootstarp.yaml la configuracion de conexion al admin server 
```yaml
spring:
  boot:
    admin:
      client:
        uri: <path admin server>
```