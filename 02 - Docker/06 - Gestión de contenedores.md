## Docker Run
`docker [opciones] [imagen] [comando] [argumentos]`<br>
Si le pasamos una imagen que no tiene en local la descarga.<br>
busybox es una imagen pequeña de linux.<br>

El orden de los registry es primero el por defecto y luego el que se ha creado, pero esto se pueden configurar.

## Detached y Foreground
+ Foreground, significa que mi shell se queda dependiendo con la del docker.<br>
+ Detached `[-d]`, significa que mi shell se queda en segundo plano.<br>

## Docker run opciones
`[-t]` abre una terminal dentro del contenedor.<br>
`[-i]` te mete dentro del sistema al contenedor.<br>
`[--memory XXM]` estoy diciendole al group que le doy como máximo XXM de RAM.
`[--restart=always]` le dice a docker que si ese contenedor se cae lo tiene que levantar.

Con eso se conecta a la consola, que se usa para reenviar eventos de la aplicación. Hay que tener cuidado con que la consola sea lectura/escritura o solo lectura.

## Copiar un fichero in/out a Containers
(Esta en las diapositivas).

## Docker Privilegios
Un usuario que no es root no puede enviar peticiones a docker.<br>
Cuando se instala docker se crea un nuevo fichero en el grupo de usuarios (/etc/group) y habrá que incluirlo para que pueda realizar peticiones a docker.

## Lanzar container como servicio gestionado por el sistema
Tenemos que crear un servicio en `/etc/systemd/system` (`nano ubuntu-cont.service`):
```
[Unit]
Description=Container Ubuntu
Requires=docker.service
After=docker.service

[Service]
ExecStartPre=-/bin/docker container run --name cj -dti ubuntu:18.04
ExecStart/bin/docker container start -a cj
ExecStop=/bin/docker container stop cj

[Install]
WantedBy=multi-user.target
```
Requires que necesito para ejecutar el servicio que estoy creando.<br>
ExecStartPre Antes de comenzar el start hacer algo.<br>
el - es condicional, osea que si el contenedor no esta creado lo crea y si esta creado pasa a la siguiente linea (ExecStart).<br>
ExecStart En el start arrancamos el contenedor.<br>
WantedBy le estoy diciendo para que usuario quiero que se ejecute.

Para lanzar el nuevo servicio tendría que: `systemctl --now ubuntu-cont.service`.<br>
Cuando lo levanta crea un link en un directorio.
Para saber el estado del servicio: `systemctl stus ubuntu-cont.service`.<br>
Para parar el servicio: `systemctl stop ubuntu-cont.service`.<br>

Esto se hace en el laboratorio 3.
