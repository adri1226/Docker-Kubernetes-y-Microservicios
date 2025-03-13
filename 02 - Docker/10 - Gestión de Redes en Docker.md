## Gestión de Redes en Docker

+ Bridge, 
    El Docker Host tiene un fichero que es el docker0 (IP 172.17.0.1).<br>
    Cuando creamos un conteendor lo que hace es darle una IP que sera la siguiente libre (172.17.0.2, 172.17.0.3, ...).<br>
    Si queremos que un contendor salga hacia afuera, lo lanza usando docker0 quien hace una petición a IPTABLES (software de firewall de linux) y sale por un NAT (camufla una IP interna con un externa) hacia afuera.<br>
    Cuando paras o borras un contenedor su IP desaparece, y cuando se levante no se asegura que se vuelva a la IP anterior.
+ Host, los contenedores tienen acceso directo a la pila de puertos de la maquina host, los puertos que esten expuestos en la maquina estaran expuestos en el contenedor.
+ None, no tendrán conectividad hacia el exterior. No tienen acceso a otros recursos de la red.
+ Macvlan, se usa en escenarios donde el contenedor requiere una dirección MAC y conectividad de red directa a la red subyacente. Asigna un MAC al contenedor. Permite que nuestro contenedor aparezca como un host físico. Pero muchos servicios en la nube no son compatiblen con esto.
+ Overlay, VPN, se suele usar cuando se montan cluster de swat, cluster de docker.

+ `brctl show`, permite ver los dispositivos bridge que tengo.
+ `docker network ls` me dice que los tipos de red que hay en los contenedores.
+ `docker network inspect bridge` es el docker0.
+ `docker network create --driver bridge nameNetwork` nos permite crear una network.
+ `docker run --net=nameNetwork` nos permite crear un nuevo contenedor con la network especificada.
+ connect así muevo un contenedor de redes.

Cuando **exponemos** puertos en un contenedor se exponen de forma interna, no se va a la red.<br>
Cuando **publicamos** puertos en un contenedor se hace para que desde fuera se pueda acceder a mi contenedor. Se redireccionara Docker con las tablas de IPTABLE.<br>
No se pueden publicar puertos que mi contenedor no exponga.<br>
Los puetos que se exponen de forma automática por el host no se mantien cuando un contenedor se borra o se para. (Mirarlo)

+ `docker run -p puertoHost:puertoContenedor` lo que hace es redireccionar al puertoHost con el puertoContenedor. El puertoHost tiene que estar libre.
+ `docker run -P` redirecciona cualquier puerto expuerto en el contenedor con cualquier puerto del host.
+ `docker container port nameContainer` me dice que puertos estan expuestos en el contenedor.

