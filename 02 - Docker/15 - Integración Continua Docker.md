## Integración Continua Docker
Para hcerlo necesitamos de una herramienta entre medias del repo y el despliegue --> Jenkins.<br>

### Docker in docker
La ejecucución de docker dentro de docker te permite crear imagenes y lanzar contenedores dentro de un entorno ya en contenedores.

El modo priviledge le da al contenedor acceso completo al sistema. Hay que tener cuidado en como usarlo, pero es necesario para crear docker in docker.