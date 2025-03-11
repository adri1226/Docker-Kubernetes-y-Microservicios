# Docker-Kubernetes-y-Microservicios
Curso de Docker, Kubernetes y Microservicios

## Introduccion
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