## Construccion de Imagenes con Dockerfile

Un Dockerfiles es un fichero que contiene directivas para poder crear una imagen de Docker.

Cuando se crea una imagen se suele exigir 2 cosas:
+ Pese poco,
+ Haya pocas capas, porque cuantas más capas, más tiempo de compilación, más tiempo de arranque y más ocupa en cache.

## Directivas de un Dockerfile
Cada directiva en un Dockerfile es una nueva capa de mi imagen.

+ `FROM <image>:<tag>` especificamos la imagen base de la imagen que vamos a crear.
+ `LABEL nombre=valor`
+ `RUN comando` ejecuta comandos durante el tiempo de creación de la imagen.
+ `CMD` comando que siempre se ejecuta cuando se inicia el contenedor. Especifica los argumentos que seran alimentados al Entrypoint.
+ `ENTRYPOINT` define un comando vase y sus parámetros para el contenedor. Es único, solo puede haber uno por imagen.
+ `ENV` establezco variables de entorno.
+ `WORKDIR` establezco un directorio de trabajo.
+ `ADD` permite que el origen sea una url.
+ `COPY` cuando sea copiar un fichero de host al contenedor.
+ `USER <user>:<group>` para especificar un usuario no root como usuario predeterminado del contenedor.
+ `VOLUME` para crear volumenes en el directorio de docker. Para conservar los datos y compartirlos entre contenedores.
+ `HEALTHCHECK` es un controlador de estado, se usa para comprobar si la aplicación se ejecuta correctamente.
+ `ONBUILD` para crear imagenes de docker reutilizables, para usarlas como base para crear nuestras propias aplicaciones.

Cada vez que arranque hare un ping a localhost.
```Dockerfile
FROM debian:wheezy
ENTRYPOINT ["/bin/ping"]
CMD["localhos"]
```

## Imagen Scratch
Docker proporciona una imagen base especia que indica que desea verificar el nivel supeior del sistema de archivos.<br>
Si quiero generar una imagen desde 0, le pondre FROM scratch al Dockerfile.<br>
La imagen scratch es una imagen "normal" de docker, pero no es realmente una imagen, sino solo el nivel de archivos minimo para una imagen de docker.

**¿Cuando usar scratch?** Depende de la aplicación, pero es ideal para alojar binarios estaticos de una aplicación cuando es necesario una ejecución rápida.<br>
Si tengo dependencias con algo probablemente no debería usar scratch.