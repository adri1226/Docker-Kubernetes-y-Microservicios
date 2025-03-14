## Arquitectura de Kubernetes

Esta compuesto por nodos worker y master.

### Componentes Master Node
El conjunto de uno o mas de un master se llama control play.<br>
Y tiene una serie de componentes, que nos permiten gestionar el cluster y los despliegues.

El cliente que habla con Kubernetes es QFTL.

![alt text](img/image-10.png)

+ kube-api-server, me permite comunicar kubernetes, este componente es el que acepta las peticiones.<br>
Son peticiones a nivelk cluster, despliegue de aplicación, no a nivel de servicio de la aplicación.<br>
Le pasa las peticiones a kube-scheduler.
+ kube-scheduler, decide en que workers se hacen los despliegues.<br>
+ kubelet, que esta instalado en los workers. Tiene una continua comunicación con los master para pasarle info a nivel contenedor/nodo.<br>
Recepciona las peticiones del kube-scheduler, y se encarga de gestionar la creación de los contenedores.<br>
Los workers tendrán que tener instalado un CRI y será con el que se creen los contenedores.