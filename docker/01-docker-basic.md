- [Docker](#docker)
- [Componentes de Docker](#componentes-de-docker)
  - [Dockerfile](#dockerfile)
    - [Formato](#formato)
  - [Persistencia de datos.](#persistencia-de-datos)
    - [Volumen](#volumen)

# Docker 
Docker es una plataforma open-source que simplifica el proceso de creacíon, 
empaquetado e implementación de aplicacion aislandolas en contenedores ligeros y portatiles. 

# Componentes de Docker
Existen tres componentes claves en el ecosistema de Docker:

## Dockerfile
Un Dockerfile es un documento de texto que contiene las instrucciones (comandos) para crear una imagen de Docker. Este documento puede contener todos los comandos que un usuario puede ejecutar en una línea de comandos para ensamblar una imagen.
El Dockerfile admite los siguientes comandos:

| Comando     | Descripcion                                                                     |
|:------------|:--------------------------------------------------------------------------------|
| ADD         | Agregar archivos y directorios locales o remotos.                               |
| ARG	        | Utilice variables de tiempo de compilación.                                     |
| CMD	        | Especificar comandos predeterminados.                                           |
| COPY	      | Copiar archivos y directorios.                                                  |
| ENTRYPOINT  | Especifique el ejecutable predeterminado.                                       |
| ENV	        | Establecer variables de entorno.                                                |
| EXPOSE	    | Describe en qué puertos está escuchando tu aplicación.                          |
| FROM	      | Crear una nueva etapa de compilación a partir de una imagen base.               |
| HEALTHCHECK	| Comprobar el estado de un contenedor al iniciarse.                              |
| LABEL	      | Añadir metadatos a una imagen.                                                  |
| MAINTAINER	| Especifique el autor de una imagen.                                             |
| ONBUILD	    | Especifique instrucciones para cuándo se utiliza la imagen en una compilación.  |
| RUN	        | Ejecutar comandos de compilación.                                               |
| SHELL	      | Establecer el shell predeterminado de una imagen.                               |
| STOPSIGNAL	| Especifique la señal de llamada del sistema para salir de un contenedor.        |
| USER	      | Establecer ID de usuario y grupo.                                               |
| VOLUME	    | Crear montajes de volumen.                                                      |
| WORKDIR	    | Cambiar directorio de trabajo.                                                  |

### Formato
El formato para indicar comandos dentro de un dockerfile es el siguiente:
```Dockerfile 
COMANDO argumentos
```
Los comandos no distinguen entre mayúsculas y minúsculas. Sin embargo, la convención es escribirlas en MAYÚSCULAS para distinguirlas más fácilmente de los argumentos.

  
- **Imagen Docker:** es un archivo ejecutable e independiente que se utiliza para crear un contenedor, las imagenes son creadas mediante un Dockerfile por lo que todo lo que se configure en este archivo estara incluido en la imagen.
Las imagenes de Docker son portables se pueden compartir o descargar de repositorios (Docker Hub) y ejecutar la misma imagen en diferentes ubicaciones a la vez.

- **Contenedor Docker:**  es un entorno de ejecucion que contiene todo los componentes necesarios para ejecutar una aplicacion sin utilizar dependencias de la maquina host.


## Persistencia de datos.
Por defecto los contenedores son efimeros, esto significa que cualquier dato almacenado dentro de ellos se perdera al finalizar su ejecucion. Para solucionar este problema existen los volumenes.

### Volumen
Los volumenes son mecanismos de alamcenamiento que perminten conservar los datos mas alla del ciclo de vida de un contenedor. Es como proporcionar un acceso directo o un enlace simbolico desde el interiro del contendor hacia el exteriro.





