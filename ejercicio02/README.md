# Ejercicio 2

1. Descarga la imagen `nicopaez/pingapp:3.0.0`
2. Crear un repositorio en dockerhub
3. Sube la imagen descargada al repositorio creado
4. Crea una carpeta "ejercicio02" en tu repositorio y pon dentro de la misma un archivo README.md con el detalle de instrucción que utilizaste para completar la tarea. 
5. Asegurate que la imagen queda publicada como pública
6. Incluye al final de las instrucciones la sentencia docker pull exacta para descargar tu imagen.

Pista: utilizar comandos tag, login y push

## Solución

Descargo la imágen con `docker run`:
```
docker run nicopaez/pingapp:3.0.0
```

Hacer login de dockerhub. Como en mi caso ya tenia logueado el de la empresa, debo salir de la sesión actual:
```bash
docker logout
mv ~/.docker/config.json ~/.docker/config_old.json
docker login -u matibeor -p <password>
```

Commit y push de la imagen:
```bash
docker container commit <id_contenedor> matibeor/pingapp:0.0.1
docker push matibeor/pingapp:0.0.1
```

Para descargar desde otro lugar:
```bash
docker pull matibeor/pingapp:0.0.1
```

La imágen quedó publicada [aquí](https://hub.docker.com/u/matibeor).