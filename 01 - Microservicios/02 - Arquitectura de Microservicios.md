## Arquitectura y Componentes
Los microservicios son mas pequeños, desacoplados y perfeccionados para realizar pequeñas tareas de manera eficiente.

![alt text](img/image.png)

![alt text](img/image-1.png)

## Componentes - Descubrimiento y Orquestación
Todo microservicio en un entonor clusterizado se registra.
<br>Se registra cada nueva instancia dejando consigna de los datos de ubicacion, puerto, Ip...
<br>Cada microservicio se registra para que otros puedan hacer uso de él.

Se descubre, discoverty, permite tener acceso a la información de registro.

![Hola Mundo de Microservicios](img/image-2.png)

Eureka pone en comunicación los dos microservicios.
<br>Greeting-servicies, es en http, y lo que hace es saludar.
<br>Cuando se lanza lo primero que hace es registrarse (su ip, puerto, protocolo, etc.). 
<br>Para dejar sus credenciales para que Client-greeting-service pueda usarlo.
<br>El cliente cuando se lance además de registrarse, va a pedir comunicación con el servidor.

Una herramienta de orquestación despliega todas las herrmientas que tengo dockerizadas, y las despliega en un entorno clusterizado.
<br>Da una alta ??

## Enrutamiento

## Balanceador de Carga
Balancea la peticion de diferentes microservicios.
<br>Consulta al servidor de registros, porque es quien tiene todo registrado.

## Monitorización y Logs
ELK, elasticsearch, quivana.
<br>Prometeus, la gestion perfecta, pero la parte gráfica mala, por eso se usa grafana.
<br>Esto lo que nos permite es monitorizar, porque Docker y Podman no puede monitorizar.

## Trazabilidad de Peticiones
Spring Sleuth y Zipkin.
<br>Spring Sleuth, es una librería que implementa una solución de trazado distribuido.
<br>Zipkin, se consigue un sistema completo de trazabilidad distribuida. Podemos ver la trazabilidad completa.

## Servicios de configuración
Da remotamente la configuración a cada servicio.
<br>Permite gestionar el ciclo de vida y versionado.

## Vida CI/CD
![Ciclo de Vida](img/image-3.png)

