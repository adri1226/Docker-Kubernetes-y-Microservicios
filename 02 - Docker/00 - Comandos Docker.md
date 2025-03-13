# Comandos Docker

+ `docker ps` me dice los docker que estan corriendo.<br>
**CONTAINER ID** y **NAMES** es único para cada contenedor que esta corriendo.
    + `[-s]` me dice el tamaño que ocupa el contenedor.<br>
XB (virtual XXMB) lo de fuera del parentesis es lo que realmente ocupa en disco el contenedor.
    + `[-l]` muestra información sobre el último contenedor que fue creado o ejecutado.
    + `[-q]` muestra los IDs de todos los contenedores en ejecución.
+ `docker/overlay2` es la capa de escritura lectura que monta docker
+ `docker exec [contenedor]` se ejecutan comandos dentro del contenedor.
+ `docker logs [container]` me muestra los logs que han salido por consola.
+ `docker stop [container]` le hace una parada ordenada al docker, sisgterm.
+ `docker rm -f [container]` lo mata a la fuerza.
+ `docker inspect [container]` me permite ver toda la configuración en tiempo real del contenedor.
    + `-f {{opciones}}` filtramos la salida para ver diferentes opciones.
    + `-f '{{.HostConfig.RestartPolicy}}` miramos que politica de restart tiene dicho contenedor.
    + `-f '{{.RestartCount}}'` miramos las veces que el contenedor se ha reinciado.
+ `docker container prune` borra todos los contenedores parados.
+ `docker stats` me da consumos de recursos del sistema de los contenedores.<br>
Hay un limite (LIMIT) que es el limite de memoria de mi sistema.
+ `docker top [container]` permite ver los procesos lanzados dentro del contenedor.
+ `docker attach [container]` permite volver a conectarte a un contenedor que tiene una terminal ya corriendo.
+ `docker container rename [container] [newName]` cambia el nombre del contenedor.
+ `docker image history` me dice las capas de lo que esta compuesto mi imagen.
+ `docker search nombre` busca en los repositorios configurados el nombre dado.
+ `docker system prune -a` borra todos los elementos no asignados en ese momento.
+ `docker image build -t nombreImagen:tagImagen` para compilar una imagen.
    + `[-f]`, nos permite darle otro nombre al Dockerfile u otro path.
+ `docker run`
    + `[-P]` si la imagen tiene un puerto descuberto, esta diciendo que en nuestro hst habra un puerto y lo redireccione a nuestro host.
    + `[-v path/host:path/container | path/host]` nos permite compartir del SO con el contenedor.
    + `[-v nombreVol:path/que/quiera]` me crea un contenedor con con acceso a dicho volumen.
    + `[--volumes-from container]` usa el mismo volumen creado por dicho contenedor.
    + `[-p puertoHost:puertoContenedor]` lo que hace es redireccionar al puertoHost con el puertoContenedor. El puertoHost tiene que estar libre. Si no se pone el puertoHost se deja que se redireccione al puerto que el SO decida.
    + `[-p ipQueQuiera::puertoContenedor]` le digo que coja esa IP fija del puerto del contenedor, pero el puerto del host será random.
    + `[-p ipQueQuiera:puertoHost:puertoContenedor]` le digo que coja esa IP y tambien le digo el puerto que quiero exportar del contedor al host.
    + `[-P]` redirecciona cualquier puerto expuerto en el contenedor con cualquier puerto del host.
    + `[--net=nameNetwork]` nos permite crear un nuevo contenedor con la network especificada.
    + `[-h]` establece el hostname del contenedor, es decir, el nombre que tendrá dentro de la red del contenedor.
+ `docker volume create --name nombre` crea un volumen con ese nombre.
+ `docker volume ls` me dice los volumenes que hay creados.
+ `docker volume inspect volumenName` me dice mas datos sobre ese volumen
+ `docker volume rm volName` borra el volumen siempre y cuando no este asociado a ningun contenedor.
+ `docker network ls` me dice que los tipos de red que hay en los contenedores.
+ `docker network inspect bridge` es el docker0.
+ `docker network create --driver bridge nameNetwork` nos permite crear una network.
+ `docker network connect netName containerName` conectamos el contenedor a la ntework una vez ya se ha lanzado el contenedor.
+ `docker container port nameContainer` me dice que puertos estan expuestos en el contenedor.
+ `ctrl+p ctrl+q` manda a detached el contenedor.