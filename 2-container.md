# Contenedores

### Crear un contenedor
Para crear un nuevo contenedor Docker a partir de una imagen específica, pero sin iniciarlo automáticamente. 

```
docker create --name <nombre contenedor> <nombre imagen>:<tag>

docker create --name srv-web nginx:alpine
```

![alt text](image-5.png)

Crear el contenedor  **srv-web** usando la imagen nginx version alpine

Si creas un contenedor en Docker sin asignarle un nombre específico utilizando la opción --name, Docker asignará automáticamente un nombre aleatorio al contenedor. Este nombre suele consistir en una combinación de palabras y números.  

Crear el contenedor usando la imagen hello-world

![alt text](image-6.png)


### Listar los contenedores ejecutándose o no

```
docker ps -a
```
![alt text](image-7.png)

### Para iniciar un contenedor

```
docker start <nombre contenedor o identificador>
docker start srv-web
```
Iniciar el contenedor srv-web 
![alt text](image-8.png)

### Listar los contenedores ejecutándose
```
docker ps 
docker ps | grep <nombre contenedor>
```
![alt text](image-9.png)

### Para detener un contenedor

```
docker stop <nombre contenedor>
docker stop srv-web
```
![alt text](image-10.png)

### Para crear un contenedor y ejecutarlo inmediatamente

```
docker run --name <nombre contenedor> <nombre imagen>:<tag>

```
![Ecosistema de Docker](dockerRun.PNG)

Crear y ejecutar inmediatamente el contenedor **srv-web2** usando la imagen nginx:alpine
```
docker run --name srv-web2 nginx:alpine

```
![alt text](image-19.png)

**¿Qué sucede luego de la ejecución del comando?**

La ejecución del contenedor se da en primer plano, se logra capturar la entrada estándar de la terminal.

Cuando ejecutas un contenedor en primer plano sin la opción -d (modo detach), el contenedor captura la entrada estándar (stdin) del terminal, lo que significa que el terminal queda "atrapado" y no puedes introducir más comandos hasta que detengas el contenedor.

### Para crear un contenedor y ejecutarlo inmediatamente sin estar vinculados al mismo
-d: Es la opción que indica a Docker que ejecute el contenedor en segundo plano (en modo "detach").
Cuando un contenedor se ejecuta en segundo plano, Docker devuelve el control al terminal inmediatamente después de iniciar el contenedor, lo que permite al usuario seguir ejecutando otros comandos en el mismo terminal sin que el contenedor detenga la interacción.

```
docker run -d --name <nombre contenedor> <nombre imagen>:tag
```
Crear y ejecutar inmediatamente el contenedor **srv-web3** en modo detach usando la imagen nginx:alpine

```
docker run -d --name srv-web3 nginx:alpine
```
![alt text](image-11.png)

### Para eliminar un contenedor

```
docker rm <nombre contenedor>
```

Eliminar el contenedor que se creó a partir de la imagen hello-world 
```
docker rm epic_swanson
```
![alt text](image-12.png)


Verificar que el contenedor que se eliminó

![alt text](image-13.png)

### Para eliminar un contenedor que esté ejecutándose

```
docker rm -f <nombre contenedor>

docker rm -f srv-web3
```
Eliminar el contenedor **srv-web3** 

![alt text](image-14.png)

Verificar que el contenedor que se eliminó
![alt text](image-15.png)

### Para inspecionar un contenedor 

Inspeccionar el contenedor **srv-web** 
![alt text](image-16.png)