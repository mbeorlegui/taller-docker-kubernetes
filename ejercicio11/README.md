# Ejercicio 11

Desplegar nicopaez/pingapp:2.1.0 en Kubernetes definiendo:

1. Un configmap1 con las variables de ambiente
`CONFIG_LOCATION=/mydata/config.json`
SECRETS_LOCATION=/mysecrets/secret.json

2. Definir un segundo configmap2:
`config.json = { "key1": "value1"}`

3. Definir un secret secret1:
`secret.json = { "mypass":"password!"}`

4. Definir un deployment.yaml que:
* Despliegue 3 replicas de `nicopaez/pingapp:2.1.0`
* Monte confimap1 como variables de ambiente
* Monte configmap2 y secret1 como volumenes

5. Definir un servicio de tipo NodePort que exponga el deployment

6. Una vez completo el deploy verificar que las variables de ambiente se leen correctamente y que al hacer un request a la ruta /config se ve el contenido de config.json y que la ruta `/secret` se ve el contenido de `secret.json`

Escribe todos los descriptores en una carpeta ejercicio11en tu repositorio personal y entrega el link correspondiente.

## Solucion
```bash
$ echo -n '{"mypass":"password!"}' | openssl base64
eyJteXBhc3MiOiJwYXNzd29yZCEifQ==
```

Deploy:
```
kubectl apply -f ejercicio11/deployment.yaml
```

```
appuser@pingapp-d8c68c957-ftrln:/apps/pingapp$ curl 10.103.123.4:4567
{"version":"2.1.0","ping":"2022-07-12T22:53:41+00:00","config_location":"/mydata/config.json","secrets_location":"/mysecrets/secret.json","host":"pingapp-d8c68c957-zzbrv"}

appuser@pingapp-d8c68c957-ftrln:/apps/pingapp$ curl 10.103.123.4:4567/config
{'key1':'value1'}

appuser@pingapp-d8c68c957-ftrln:/apps/pingapp$ curl 10.103.123.4:4567/secrets
{"mypass":"password!"}
```