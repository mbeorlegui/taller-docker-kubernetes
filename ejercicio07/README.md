# Ejercicio 7
Para este ejercicio necesitas docker-compose, si estas usando Docker Desktop ya lo tienes instalados, sino deberás instalarlo aparte. 

Crea un archivo llamado `docker-compose-jobvacancy.yml` y pon dentro el contenido de este link: https://gitlab.com/-/snippets/2088421/raw/master/docker-compose-jobvacancy.yml.

A continuación ejecuta este comando en una terminal: `docker-compose -f docker-compose-jobvacancy.yml up`
Espera unos minutos hasta que dejen de aparecer mensaje en la terminal. Luego navega `localhost:3000` para verificar que la aplicación levantó correctamente.

Finalmente contesta:

- ¿Cuántos contenedores se están ejecutando? (pueden verlo en el archivo `docker-compose-jobvacancy.yml` y también ejecutando docker ps)
- ¿Cuales son las imágenes en las que están basados los mencionados contenedores?
- ¿Puedes leer el `docker-compose-jobvacancy.yml` y describir lo que hace cada una de sus lineas?
- Dado que cada contenedor corre en forma aislada ¿Cómo es posible que esos contenedores se vean entre sí?


Escribe tus respuestas ejercicio07/README.md en tu repositorio github y entrega el link directo al archivo.

## Solución

- Con `docker ps` vemos que se iniciaron un contenedor basado en la imagen de `postgres`, y otro basado en la imagen de `nicopaez/jobvacancy-ruby:1.3.0`, lo cual coincide con el `yml` que nombra a las mismas dos imagenes como servicios, uno para `web` y otro para `db`

- Desglose del docker-compose:
  - Empieza indicando que la versión de docker-compose a utilizar es la 2.
  - Continua describiendo los servicios (contenedores que se generan luego de hacer un `up`), en este caso uno para la web, y otro para la base de datos.
  - Para la base de datos, indica que el contenedor está basado en la imágen de postgres, y que tiene como variable de entorno un `POSTGRES_PASSWORD`, el cual es definido.
  - Para la web, indica que el contenedor está basado en la imágen `nicopaez/jobvacancy-ruby:1.3.0`, que ocupa el puerto 3000, que está linkeado al contenedor `db`, y que depende del mismo. Además, tiene definidas otras variables de entorno, como el puerto (mismo que antes mencionado), un env, y una URL desde la que se accede a la base de datos.