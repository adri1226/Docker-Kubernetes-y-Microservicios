# Comandos kubectl

+ `kubectl get pod podName -o yaml` te da la configuración actual de ese objeto.
+ `kubectl logs podName -c containerName` me da los logs del pod.
+ `kubectl exec -ti podName -c conatinerName /bin/sh` accedo a un contenedor.
+ `kubectl rollout status deploy deployName` me dice como es el proceso del deploy al hacer un rolling update.
+ `kubectl rollout history status deploy deployName`me da un hitorial que dice que ha habido cambios, pero no me dice los cambios.
+ `kubectl rollout status deploy deployName --revision=N` y podría comprar con el anterior.<br>
Por eso cuando se hace un cambio se recomienda poner un `annotations:` para poder tener un registro mas controlado de los cambios que se van produciendo.