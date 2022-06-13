# Ejercicio 1

1. Crea una página html que tenga tu nombre
  
2. Ejecuta una imagen [nginx](https://hub.docker.com/_/nginx) para que sirva tu página. Para esto tendrás que utilizar el comando docker run y deberás investigar la documentación de la imagen nginx para descubrir cómo especificarle el contenido que el servidor debe servir.

Ten presente que no hay una única forma de resolver este ejercicio.

Pista: puede que tengas que utilizar `docker run` con la opción `-v`

Pongo los archivos que resuelven el ejercicio y las correspondientes instrucciones en una carpeta "ejercicio01" de tu repositorio Github y entrega en el classroom el link directo a la misma.

## Solución


```bash
$ docker container run -p 80:80 -v "$(pwd)"/ejercicio01:/usr/share/nginx/html nginx
```

Comprobamos que anda con el siguiente comando:
```bash
[15:34:04] mbeorlegui@MatiasFierro:~/Escritorio/Matias/curso-docker-kube$ (master [ ? ]) curl localhost:80/pagina.html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mi pagina en Docker</title>
</head>
<body>
  <h1>Hola me llamo Matias Beorlegui</h1>
</body>
```

También podemos entrar a http://localhost/pagina.html