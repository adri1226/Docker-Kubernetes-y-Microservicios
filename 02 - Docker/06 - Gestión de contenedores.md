## Docker Run
`docker [opciones] [imagen] [comando] [argumentos]`<br>
Si le pasamos una imagen que no tiene en local la descarga.<br>
busybox es una imagen pequeña de linux.<br>

El orden de los registry es primero el por defecto y luego el que se ha creado, pero esto se pueden configurar.

## Detached y Foreground
+ Foreground, significa que mi shell se queda dependiendo con la del docker.<br>
+ Detached `[-d]`, significa que mi shell se queda en segundo plano.<br>

## Docker run interactivo
`[-t]` abre una terminal dentro del contenedor.<br>
`[-i]` te mete dentro del sistema al contenedor.<br>

Con eso se conecta a la consola, que se usa para reenviar eventos de la aplicación. Hay que tener cuidado con que la consola sea lectura/escritura o solo lectura.

## Copiar un fichero in/out a Containers


## Comandos varios de Docker
+ `docker ps` me dice los docker que estan corriendo.<br>
**CONTAINER ID** y **NAMES** es único para cada contenedor que esta corriendo.
+ `docker/overlay2` es la capa de escritura lectura que monta docker
+ `docker ps -s` me dice el tamaño que ocupa el contenedor.<br>
XB (virtual XXMB) lo de fuera del parentesis es lo que realmente ocupa en disco el contenedor.
+ `docker exec [contenedor]` se ejecutan comandos dentro del contenedor.
+ `docker logs [container]` me muestra los logs que han salido por consola.
+ `docker stop [container]` le hace una parada ordenada al docker, sisgterm.
+ `docker rm -f [container]` lo mata a la fuerza.
+ `docker inspect [container]` me permite ver toda la configuración en tiempo real del contenedor.