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
+ `ctrl+p ctrl+q` manda a detached el contenedor.