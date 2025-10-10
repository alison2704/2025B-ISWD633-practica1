Esta práctica me ayudó a comprender la diferencia entre un contenedor y una máquina virtual. 

## CONTENEDOR

Los contenedores son instancias de una imagen,  permiten aislar y ejecutar aplicaciones con sus dependencias y configuraciones que necesite un proyecto, sin necesidad de instalar todas las herramientas en el sistema operativo host. De esta manera, facilitando la portabilidad del entorno; cuando una persona del equipo de desarrollo necesite ejecutar el sistema no tenga problemas de versiones o configuraciones.

Una ventaja es que utiliza los recursos de nuestro sistema operativo, por lo que son más livianos y rápidos que las VM.

## MÁQUINA VIRTUAL

Mientras que la VM es una emulación de un sistema operativo dentro de otro (host), esto la hace más pesado y lenta al arrancar.

## IMÁGENES

Las imágenes son archivos únicos e inmutables que contienen todas las dependencias, programas, librerías que requiere una aplicación para ejecutarla. 

## DockerHub

Existe un repositorio de imágenes llamado DockerHub, el cual almacena imágenes.

## Docker

Docker es una plataforma que permite crear, ejecutar y administrar contenedores.

Se compone de:

* Docker Engine: el motor que ejecuta los contenedores.

* Docker CLI: la línea de comandos.

* Docker Hub: repositorio de imágenes.

### COMANDOS QUE RECUERDO:

Descargar imagen
```
docker pull nombre-imagen
```

Crear contenedor, mapear puertos, especificar la  imagen, ejecutarlo en 2do plano

## MAPEO DE PUERTOS

Este permite conectar un puerto del contenedor con un puerto del host.

-d sirve para ejecutar el contenedor en 2do plano.

```
docker run -d --name nombre-contenedor -p puertoHost:puertoContenedor nombre-imagen:tag
```

Eliminar contenedor
```
docker rm nombre-contenedor
```

Eliminar imagen
```
docker rmi nombre-imagen
```

Ver contenedores en ejecución
```
docker ps
```

Ver todos los contVenedores creados
```
docker ps -a
```

Iniciar un contenedor
```
docker start nombre-contenedor
```

Pausar un contenedor
```
docker stop nombre-contenedor
```

Ver los puertos mapeados
```
docker port nombre-contenedor
```

Ver logs de un contenedor
```
docker logs nombre-contenedor
```

Ver la configuración del contendor

```
docker inspect nombre-contenedor
```

## DIFERENCIA ENTRE LOG Y INSPECT

docker logs → ver lo que imprime el contenedor.

docker inspect → ver la configuración completa y su estado interno. 

## OPERACIONES CON CONTENEDORES

Ejecutar un comando en un contenedor en ejecución

```
docker exec nombre-contenedor comando argumentos
```

Abrir un shell interactivo en un contenedor
```
docker exec -i nombre-contenedor sh
```

Abrir un shell interactivo bidireccional
```
docker exec -it nombre-contenedor sh
```

## DIFERENCIA ENTRE exec -i y exec -it
exec -i → se puede enviar comandos al contenedor desde la terminal, pero al no tener una terminal de salida completa la respuesta del comando puede no mostrarse.

exec -it → el argumento t asigna una terminal al contenedor, lo que permite una interacción completa entre la terminal y la salida de forma inmediata.