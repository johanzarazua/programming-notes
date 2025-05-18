Cuando se trabaja con microservicios es comun que se deben comunicar entre ellos. Puede ser para enviar informacion que debe ser procesada o unicamente para consultar datos.
Spring provee una herramienta que nos permite realizar esta comunicacion de forma sencilla

# Feign
Es una libreria para generar clientes de servicios Rest de manera declarativa sin la necesidad de utilizar RestTemplate
Permite integracion con Eureka para descubrimiento de microservicios, con Hystrix para definir un fallback a nivel de clientes y con Ribbon para balaceo de carga.

## Cuando utilizarlo
Es combeniente utilizar Feign cuando un microservicio requiere consumir o invocar apis de otro microservicio.

## Como utilizarlo
Suponiendo la existencia de 3 microservicios A, B y C. En los cuales el microservicio A necesita invocar apis de los microservicios B y C, los pasos a seguir serian los siguientes:

1. Agregar clases en el microservices A como modelos de las peticiones en los otros dos microservicios
2. Agregar la dependencia "spring-cloud-starter-openfeign" en microservicio A
3. crear un paquete client, para alamcenar interfaces de los clientes a los otros microservicios
4. crear una interfaz, haciendo referencia al servicio a consumir, la cual se anotara con `@RequestMapping(<path>)` y ` @FeignClient(<microservices name>)` que debe ser tomado del microservicio a consumir y se deben definir los methodos del microservices a conumir con su respectiva anotacion p.e: `@GetMapping(<path>)`
5. Injectar estas interfaces donde se deseen utilizar, utilizando los metodos para hacer la peticiones y obtener la respuesta. 
6. Anotar la clase principal con `@EnableFeignClients` y `@EnableDiscoveryClients`