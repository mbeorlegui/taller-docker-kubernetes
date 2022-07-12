# Ejercicio 9

Escribir el descriptor yaml (deployment) para correr la aplicación [PasswordAPI](https://hub.docker.com/r/nicopaez/password-api) en Kubernetes (minikube) con 3 replicas.
Puedes tomar [este descriptor](https://gitlab.com/-/snippets/2088421/raw/master/deployment.yaml) de ejemplo como puntos de partida.

Una vez tengas escrito el descriptor puedes aplicarlo con `kubectl apply -f`.
En principio la aplicación no será accesible desde fuera del cluster, con lo cual para probarla puedes conectarte al pod (`kubectl exec -it podname --  bash`) y hacer un `curl localhost:3000/password`.

Una vez completo, compartir el link al repositorio (carpeta ejercicio09) con el correspondiente descriptor y las instrucciones que utilizaste para desplegar y verificar su funcionamiento.

## Solucion

Para deployar los cambios:
```
minikube start
kubectl apply -f deployment.yaml
```

Obtenemos los nombres de los pods con:
```
kubectl get pods
```

Ingresamos a un pod con:
```
kubectl exec -it password-api-6b7f67dbd6-5s6k5 --  bash
```

Salida en consola:
```bash
mbeorlegui@MatiasFierro:~/Escritorio/Matias/curso-docker-kube$ (master [ ? ]) kubectl exec -it password-api-6b7f67dbd6-5s6k5 --  bash
root@password-api-6b7f67dbd6-5s6k5:/usr/src/app# curl localhost:3000/password
{"password":"!440FfCcHh??"}
```

