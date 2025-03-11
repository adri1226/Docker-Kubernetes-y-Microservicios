## Imágenes en Docker
`/var/lib/docker/image/ovwrlay2/imagedb/content` en ese path es donde estan las imágenes.

## Namespaces en imágenes
+ Root-like, son de los repositorios oficiales de las empresas.
+ User, hace referencia a una organización.
+ Sef-Hosted, hace referencia a un servidor propio que se tenga.

## Descargando imágenes
Al descargar una imágen con `pull` siempre va a buscar aquella en la que el tag sea latest.<br>
Podemos decirle descargar una imagen de un registry propio.

## Commit en un Container
`docker container commit - a "contacto <email@algo.com>" -m "Comentario del commit" conatiner container:tag` así genero una imagen a partir de un contenedor

## Exportar/Importar Imágenes
Lo aconsejable es exportar los contenedores como .tar.<br>
Cuando se importe un contenedor exportado, se importa como una imagen.
