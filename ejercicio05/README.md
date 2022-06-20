# Ejercicio 5

Investigar que hacen y para que se usan los siguientes comandos dentro de un Dockerfile:

* `HEALTHCHECK`
* `ONBUILD`
* `VOLUME`

Escribir la respuesta en el repositorio personal en ejercicio05/README.md, entregar el link director al archivo.

## Soluci�n

Explicaci�n de cada comando:


### HEALTHCHECK
Verifica que el contenedor est� en un determinado deseado despu�s de iniciarlo.

### ONBUILD
Es una instrucci�n que se ejecuta en caso de que la imagen generada a partir del Dockerfile se utilice como base de otra, de forma tal que solamente generar� capas en las im�genes hijas, y no en la que se genera s�lo con ese Dockerfile.

### VOLUME
Esta instrucci�n va seguida de un directorio que se expondr� al Host. No modifica el comportamiento de la im�gen, s�lo agrega metadata.
