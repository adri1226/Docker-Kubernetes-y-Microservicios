## Docker Compose & Swarm
### Docker Compose
Docker Compose nos ayuda a no tener que levantar de manera manual los contenedores de manera automatica.<br>

`docker-compose up`, inicia y levanta los contenedores definidos en el fichero de configuración. Compila directamente cuando levanta los contenedores.
`docker-compose ps` mira los recusos que estan levantados.
`docker-compose down`, termina el servicio.

Docker compose usa como fichero de configuración un yaml (no usa tabulaciones sino 3 espacios).

Ejecuta y administra aplicaciones multiprocedurales.

## Docker Swarm
Es el cluster de Docker (es como kubernetes).<br>
Esta compuesto por nodos, que pueden ser fisicos o virtuales.

Los nodos pueden ser de dos tipos:
+ Manager, que es quien gestiona los recursos del cluster, como por ejemplo el DNS, IP, cantidad de contenedores corriendo, etc.
+ Worker, que es donde se van a gestionar los contenedores (que son servicios).

Al final lo que se va a hacer con swarp es gestionar servicios.

