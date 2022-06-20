# Ejercicio 6

Crear un contenedor para la aplicaci�n PasswordApi (del ejercicio 4) que est� basada en la imagen `redhat-openjdk-18/openjdk18-openshift`
disponible [en la registry de Red Hat](https://catalog.redhat.com/software/containers/redhat-openjdk-18/openjdk18-openshift/58ada5701fbe981673cd6b10).


1. Escribe el dockerfile
2. Genera la imagen (docker build)
3. Publica la imagen en tu cuenta de Dockerhub


Pon el dockerfile en un repositorio Github en una carpeta ejercicio06. Agregar tambi�n en esa carpeta un archivo readme con el link a la imagen generada en dockerhub.
Entrega el link a la carpeta en el repositorio Github.

## Soluci�n

A partir del Dockerfile del directorio actual construyo la imagen. Parado en la carpeta madre del repositorio:
```bash
docker build -t passwordapi2 ejercicio06/
```
Esto crea la imagen con el nombre `passwordapi2`, la cual se puede consultar con el comando `docker ps -a`.

Luego, levanto el contenedor en modo iteractivo para chequear mejor que se encuentre andando, todo esto a partir de la imagen que creamos antes, llamada `passwordapi2`:
```bash
docker run -it --name password-api2 -p 8080:8080 passwordapi2
```

Se puede chequear que se encuentra correctamente levantado en el puerto deseado haciendo `docker ps`, y tambien verificando la p�gina web http://localhost:8080/

Una vez realizadas las comprobaciones, subimos la imagen a nuestro dockerhub:
```bash
docker container commit password-api2 matibeor/passwordapi2:0.0.1
docker push matibeor/passwordapi2:0.0.1
```

Finalmente, la im�gen qued� publicada [aqu�](https://hub.docker.com/r/matibeor/passwordapi2)