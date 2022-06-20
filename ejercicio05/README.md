# Ejercicio 5

Investigar que hacen y para que se usan los siguientes comandos dentro de un Dockerfile:

* `HEALTHCHECK`
* `ONBUILD`
* `VOLUME`

Escribir la respuesta en el repositorio personal en ejercicio05/README.md, entregar el link director al archivo.

## Solución

Explicación de cada comando:


### HEALTHCHECK
Verifica que el contenedor esté en un determinado deseado después de iniciarlo.

### ONBUILD
Es una instrucción que se ejecuta en caso de que la imagen generada a partir del Dockerfile se utilice como base de otra, de forma tal que solamente generará capas en las imágenes hijas, y no en la que se genera sólo con ese Dockerfile.

### VOLUME
Esta instrucción va seguida de un directorio que se expondrá al Host. No modifica el comportamiento de la imágen, sólo agrega metadata.
