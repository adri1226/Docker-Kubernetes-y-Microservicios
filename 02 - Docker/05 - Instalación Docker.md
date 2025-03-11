## Versiones
Docker Community Edition (CE).
Docker Desktop, para so que no son linux.


+ dockerd,
+ docker-containerd,
+ docker-runc, contenedor simple.
+ docker, es el cliente.

## ¿Cómo instalar docker?
```bash
yum install -y docker-ce
systemctl enable --now docker
systemctl status docker
```
Con `systemctl` lo que hacemos es iniciar el docker service.

`var/lib/docker` es donde se guarda todo lo de docker.<br>
Para docker lo ideal es sacarlo del path de arriba y crearle su propia particion en linux.<br>
`fsadm -l resice /dev/vg0/var 5G` así damos mas espacio a la particion que tenemos en el labo para docker.

`usermod -G docker guru` añado a guru al grupo de docker, proque se crea un grupo de docker cuando se instala, y sino me pide ser super usuario.

## ¿Cómo configuro un servidor de confianza?
`docker info` apartado registry me dice el servidor de registro.<br>
`/etc/docker` cada vez que arranca el servicio de docker mira este el fichero daemon.json, que es el fichero de parametrización de docker.<br>
Para crearlo: `nano daemon.json`

Valores:
```json
{
    "insecure-registries":["10.100.0.0/24"],
    "registry-mirrors":["https://server1:5001"]
}
```

En toda esa red puede meter toda un servidor de registros.<br>
Al usar insecure-registries le decimos que no tiene un cifrado tls.<br>
`registry-mirrors`, dentro del abanico de posibles servidor le digo que servidor es y el puerto en el que esta.

Despues de crearlo tengo que relanzar el servidor de docker: `systemctl restart docker`, y debería salirme el servidor de registro.

