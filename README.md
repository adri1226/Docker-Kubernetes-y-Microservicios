# Docker-Kubernetes-y-Microservicios
Curso de Docker, Kubernetes y Microservicios

## Tabla de contenido
**01 - Microservicios**
+ [01 - Microservicios](01%20-%20Microservicios/01%20-%20Microservicios.md)
+ [02 - Arquitectura de Microservicios](01%20-%20Microservicios/02%20-%20Arquitectura%20de%20Microservicios.md)
<br><br>

**02 - Docker**
+ [00 - Comandos Docker](02%20-%20Docker/00%20-%20Comandos%20Docker.md)
+ [03 - Introducción a la Tecnología de Contenedores](02%20-%20Docker/03%20-%20Introducción%20a%20la%20Tecnología%20de%20Contenedores.md)
+ [04 - Gestión de servicios en Contenedores](02%20-%20Docker/04%20-%20Gestión%20de%20servicios%20en%20Contenedores.md)
+ [05 - Instalación Docker](02%20-%20Docker/05%20-%20Instalación%20Docker.md)
+ [06 - Gestión de contenedores](02%20-%20Docker/06%20-%20Gestión%20de%20contenedores.md)
+ [07 - Gestión de Imagenes en Contenedores](02%20-%20Docker/07%20-%20Gestión%20de%20Imagenes%20en%20Contenedores.md)
+ [08 - Construccion de Imagenes con Dockerfile](02%20-%20Docker/08%20-%20Construccion%20de%20Imagenes%20con%20Dockerfile.md)
+ [08.1 - Construcciones normales de Docker](02%20-%20Docker/08.1%20-%20Contrucciones%20normales%20de%20Docker.md)
+ [09 - Almacenamiento Docker](02%20-%20Docker/09%20-%20Almacenamiento%20Docker.md)
+ [10 - Gestión de Redes en Docker](02%20-%20Docker/10%20-%20Gestión%20de%20Redes%20en%20Docker.md)
+ [11 - Docker Compose & Swarm](02%20-%20Docker/11%20-%20Docker%20Compose%20&%20Swarm.md)
+ [13 - Docker Registry](02%20-%20Docker/13%20-%20Docker%20Registry.md)
+ [15 - Integración Continua Docker](02%20-%20Docker/15%20-%20Integración%20Continua%20Docker.md)
<br><br>

**03 - Kubernetes**
+ [01 - Introducción a Kubernetes](03%20-%20Kubernetes/01%20-%20Introducción%20a%20Kubernetes.md)
+ [03 - Instalacion de Kubernetes](03%20-%20Kubernetes/03%20-%20Instalacion%20de%20Kubernetes.md)

## Introdución
Se da la introducción a microservicios para dar una introducción a lo que es docker y kubernetes.

Docker y Podman son herramientas para implementar microservicios.
Estas herramientas en un entorno productivo se van a quedar pequeñas.
¿Docker es capaz de levantar un servidor caido? No, docker solo gestiona imagenes y contenedores. Esto lo hace una herramienta de terceros.

Contenedores, ¿qué es?¿que hacen?
No van a sustituir las Maquinas Viruales, van a convivir con ellas.
Aunque la solución que vamos a implementar es en sustitución de maquinas virtuales, por costes de recursos.

Lo que lleva una imagen es mi aplicacion.
Una imagen sin contenedor no es nadie, y viceversa.
Quien ejecuta mi aplicación es el contenedor.

Docker compose hace despliegues automáticos.
Vaqmos a hacer una integración continua con docker y jenkins automatica.

Docker registry, es para guardar las imagenes.

Kubernetes, vamos a ver 3 objetos:
+ Pods, 
+ Replicasent, 
+ Deployment,
Hay que aprender a leer un manifest (fichero de despliegue).