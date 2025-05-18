# Circuit Breaker
Spring Boot propricion una herramienta llamada Hystrix, la cual nos permite implementar un patron circuit-breaker.

La finalidad de esta herramienta es mejorar la fiabilidad del sistema, controlar la latencia y tener mejor tolerancia a fallo.

## Como funciona
Cuando un microservicio hace peticiones a otros microservicios, es decir depende de otros microservicios, y uno de ellos falla (por error o latencia), el microservicio que cliente puede implementar un fallback (un plan b) para dar una respuesta alternativa con la finiladidad de que se pueda completar el proceso

Un circuit braker permite definir umbrales (valores limite de fallo), cuando algun microservicio supera este error Hystrix "corta el circuito" y ya no permite que se realicen peticiones a el microservicio en error. 

## Como implimentarlo en un microservicio

para utilizar Hystrix en un microservicio se deben realizar los siguientes pasos:
1. Agregar dependencias `spring-cloud-starter-netflix-hystrix` y `spring-cloud-starter-netflix-hystrix-dashboard`
2. Tambien es necesario habilitar actuaror `spring-boot-starter-actuator`
3. En la clase principal del microservicio se debe anotar con `@EnableHystrix` y `@EnableHystrixDashboard`
4. Modificar properties en el config server, se deben agregar los campos 
```yaml
#Hystrix
feign:
  hystrix: 
    enable: true

#actuator    
management:
  endpoints:
    web:
      exposure:
        include: "*"  
```
5. Para implemenatr un fallback se debe crear una clase que implemente la interza de comunicacion con otros microservicios, e implementar los metodos de la interfaz. Debe anotarse como `@Component`
6. Quitar la anotacion `@RequestMapping()` de la interfaz que implementa el cliente con otro microservicio y agregar en `@FeignClient` el valor `fallback = classFallBack`

