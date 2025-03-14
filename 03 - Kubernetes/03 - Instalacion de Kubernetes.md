## Instalación de Kubernetes

Vamos a ver soluciones xx, pero nos vamos a centrar en Minikube.

## Distros de Kubernetes
#### Minikub
Es una solución all in one, permite tener un entorno de Kubernetes en una sola maquina.<br>
Genera una maquina virtual el solo.<br>
Es un linux con un kubernetes que hace de maste sy hace de slave.<br>

Minikube tiene una imagen en dockerhub, podría tener un contenedor con un sistema de kubernetes integrado.
Hay que hacer 2 cosas esenciales:
+ Descargar el software de minikube, 
+ Instalar el Software de Kubectl.<br>
Cuando se instala se habre un tunel de comunicación entre este y el minikube instalado.

Hay que levanatar el servicio de minikube: `minikube start --driver=docker`.<br>
Para descargar minikube es aconsejable limpiar el entorno, porque la descarga ocupa bastante.<br>
Como instalar minikube para [wsl](https://gist.github.com/wholroyd/748e09ca0b78897750791172b2abb051).

`minikube stop` esto me para el cluster.

#### MicroK8s
Es otra solucion all in one, en una solucion snap.<br>
Usa contenedores para aislarse, en vez de una maquina virtual como minikube.<br>

#### K3S
Es una solución all in one. Esta empaquetada en un solo binario.<br>
Adminite un lanzamiento como servidor y cliente.<br>
Se puede tener un solo binario en diferentes maquinas y tener un master y worker.<br>
Esta certificada por rancher labs.

#### Kubeadm
Es propio de kubernetes.<br>
Lo tienen los nodos master y workers.

Cuando se inicializa un cluster se crea un token, que dura 24h, `token` es para actualizar dicho token.

Si se quiere implementar Kubernetes no se puede tener la memoria swap activada.

#### Kubespray
Sirve para implementar y lanzar un cluster, y se centra mas en el proceso de configuración de las maquinas a nivel de sistema operativo.

#### KOPS - Kubernetes Operations
Permite hacer kubernetes en la nube.

¿Como limpiar docker? docker system prune -a, elimina **todo** lo que no este en marcha.