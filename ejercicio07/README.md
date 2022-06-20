# Ejercicio 7
Para este ejercicio necesitas docker-compose, si estas usando Docker Desktop ya lo tienes instalados, sino deber�s instalarlo aparte. 

Crea un archivo llamado `docker-compose-jobvacancy.yml` y pon dentro el contenido de este link: https://gitlab.com/-/snippets/2088421/raw/master/docker-compose-jobvacancy.yml.

A continuaci�n ejecuta este comando en una terminal: `docker-compose -f docker-compose-jobvacancy.yml up`
Espera unos minutos hasta que dejen de aparecer mensaje en la terminal. Luego navega `localhost:3000` para verificar que la aplicaci�n levant� correctamente.

Finalmente contesta:

- �Cu�ntos contenedores se est�n ejecutando? (pueden verlo en el archivo `docker-compose-jobvacancy.yml` y tambi�n ejecutando docker ps)
- �Cuales son las im�genes en las que est�n basados los mencionados contenedores?
- �Puedes leer el `docker-compose-jobvacancy.yml` y describir lo que hace cada una de sus lineas?
- Dado que cada contenedor corre en forma aislada �C�mo es posible que esos contenedores se vean entre s�?


Escribe tus respuestas ejercicio07/README.md en tu repositorio github y entrega el link directo al archivo.

## Soluci�n

- Con `docker ps` vemos que se iniciaron un contenedor basado en la imagen de `postgres`, y otro basado en la imagen de `nicopaez/jobvacancy-ruby:1.3.0`, lo cual coincide con el `yml` que nombra a las mismas dos imagenes como servicios, uno para `web` y otro para `db`

- Desglose del docker-compose:
  - Empieza indicando que la versi�n de docker-compose a utilizar es la 2.
  - Continua describiendo los servicios (contenedores que se generan luego de hacer un `up`), en este caso uno para la web, y otro para la base de datos.
  - Para la base de datos, indica que el contenedor est� basado en la im�gen de postgres, y que tiene como variable de entorno un `POSTGRES_PASSWORD`, el cual es definido.
  - Para la web, indica que el contenedor est� basado en la im�gen `nicopaez/jobvacancy-ruby:1.3.0`, que ocupa el puerto 3000, que est� linkeado al contenedor `db`, y que depende del mismo. Adem�s, tiene definidas otras variables de entorno, como el puerto (mismo que antes mencionado), un env, y una URL desde la que se accede a la base de datos.