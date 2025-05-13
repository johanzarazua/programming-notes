# Config Server

Es un servidor de configuracion centralizado, este nos permite:
- Almacenar configuraciones de multiples microservicios
- Centralizar configuraciones de multiples entonos (dev, pre, pro)
- Controlar version mediante herramientas como GIYHUB, GITLAB u otros
- Permite utilizar hot-reloading de las propiedades

## Como utilizarlo

Para poder incluirlo en un proyecto de Java con Spring Boot se deben seguir los siguientes pasos:

### Dependencias
 agregar las siguientes dependencias:
- Config Server: permite configurar el servidor centralizado
- Spring Security: permite proteger el servidor centralizado

### Activar proyecto como servidor de configuracion
Se debe inidicar que la aplicacion es un servidor de configuracion, para ello se debe agregar la clase principal debe anotarse con `@EnableConfigServer`

### Modificacion de properties
Se debe sustituir el archivo application.properties por un archivo llamado bootstrap.yml

Aqui se podra configurar el puerto donde correra el config server, asi como la ruta donde se encontraran los properties de cada servicio.

```yaml
server:
  port: 8081

spring:
  cloud:
    config:
      server:
        git:
          uri: <repo>
          searchPath: <carpeta-properties>
          username: ${GIT_USER}
          password: ${GIT_PASSWORD}
  
  security:
    user:
      name: root
      password: secret
```

El ejemplo anterior es una muestra de configuracion cuando nuestros properties se encuentran en un repositorio git. Dentro de este repo debe existir una carpeta donde se encontraran los propeties de todos lo microservicios.

---

Con los pasos anteriores podemos levnatra una aplicacion, la cual sera nuestro config server.
Esta aplicacion admite peticiones rest en las que nos devuleve el properties solicitado.

Nuestros microservicios deberan comunicarse con esta aplicacion para obtener sus properties.

## Como conectar microservice

Para conectar un microservice con el config server se deben agregar las siguientes dependencias:

- spring-cloud-starter-config

Posteriormente, se debe renombrar el application.properties por bootstrap.yml. Este archivo se debe configurar de la siguiente manera.

```yaml
spring:
  application:
    name: <microservice-name>
  cloud: 
    uri: <direccion config server>
    username: <user config server>
    password: <password user config server>
```

