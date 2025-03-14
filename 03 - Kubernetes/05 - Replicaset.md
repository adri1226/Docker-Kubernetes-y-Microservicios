## ReplicaSet
Es un objeto separado del pod, esta a un nivel mas alto, crea pod.<br>
Si un pod muere, el replicaset se dará cuenta, y creara un nuevo pod de esa replica, ya que se encarga de que hay aN replicas de un pod.

### ¿Como crea y mantiene los pods?
Los pods de un replicaset tiene que tener un label obligatoriamente.<br>
Porque levanta los pods dado un label, si un replicaset no encuentra un pod con dicho label lo creara.

El pod tendra un propietario, un owner reference.

Al borrar un replicaset se borraran todos los pods que controla.<br>
Los ultimos pods en nacer son los primeros en morir.

El no mira si ha cambiado algo del pod, si cambia no lo actualiza, el solo se encarga de mirar el numero de replicas que hay.<br>
Eno se de cuenta de los cambios, solo se dara cuenta cuando le vuelvan alanzar, ya sea con apply o create.<br>
Hay una carencia porque puede haber inconsistencias porque si se hace el apply el no creara de nuevo los que ya tenía, y habrá pods con dos versiones.<br>
Estas carencias solventan con Deployments.
