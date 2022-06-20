# Ejercicio 4

Adjunto hay un archivo .jar que tiene la aplicación PasswordApi.
Esa aplicación es una aplicación Java que se ejecuta con el comando: `java -jar passwordapi.jar`. Eso levanta una webapi en el puerto 8080 (ver captura de pantalla).

Lo que se pide es generar una imagen Docker que corra esa aplicación. Más concretamente lo que hay que hacer es:
1. Escribir un dockerfile
2. Generar la imagen a partir del dockerfile ejecutando un docker build
3. Publicar la imagen en Dockerhub

Resolver el ejercicio en un directorio "ejercicio04" del repositorio personal.
Mencionar en el readme el link a la imagen publicada en dockerhub
Entregar el link a la carpeta del repositorio github.

## Solución

A partir del Dockerfile del directorio actual construyo la imagen. Parado en la carpeta madre del repositorio:
```bash
docker build -t passwordapi ejercicio04/
```
Esto crea la imagen con el nombre `passwordapi`, la cual se puede consultar con el comando `docker ps -a`.

Luego, levanto el contenedor en modo iteractivo para chequear mejor que se encuentre andando, todo esto a partir de la imagen que creamos antes, llamada `passwordapi`:
```bash
docker run -it --name password-api -p 8080:8080 passwordapi
```

Se puede chequear que se encuentra correctamente levantado en el puerto deseado haciendo `docker ps`, y tambien verificando la página web http://localhost:8080/

Una vez realizadas las comprobaciones, subimos la imagen a nuestro dockerhub:
```bash
docker container commit password-api matibeor/passwordapi:0.0.1
docker push matibeor/passwordapi:0.0.1
```

Finalmente, la imágen quedó publicada [aquí](https://hub.docker.com/r/matibeor/passwordapi)