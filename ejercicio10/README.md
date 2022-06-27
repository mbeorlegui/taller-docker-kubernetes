# Ejercicio 10

Desplegar en kubernetes un bot de telegram.

En primer lugar tienes que crear un bot a partir de:

1. Ir a https://web.telegram.org/#/im?p=@BotFather y seguir los pasos
2. Enviar el comando `/newbot`
3. Seguir los pasos y al final el BotFather responde con un token, tomar nota del token

Luego puedes utilizar esta imagen que ya tiene un bot listo con algunas funcionalidades básicas (`nicopaez/telegrambot:0.0.7`).
Para correr esa imagen necesitas darle una variable de ambiente TELEGRAM_TOKEN con el correspondiente valor del token que obtuviste previamente.

Primero asegurate de poner a correr el bot localmente con docker run y pasandole como variable de ambiente el `TELEGRAM_TOKEN`.
En telegram agrega el bot como contacto y chateale `/version`. Deberá contestar con la versión.


Una vez que esto corra, entonces escribe el correspondientes descriptor para desplegar el bot en minikube.
Pista: puedes definir la variable de ambiente del token como parte del deployment.yaml.

Finalmente, entrega el link a tu repositorio (ejercicio10) incluyendo:
- Un screenshot de un chat con el bot que muestre la versión
- El deployment.yml (no pongas el valor de token en el repo, simplemente deja "A COMPLETAR")
- Las instrucciones detalladas que seguiste

# Solución

1. Obtenet el Toker del bot de telegram con BotFather

2. Probar en el contenedor de Docker con la imagen dada:
```
docker run --env TELEGRAM_BOT=<token> nicopaez/telegrambot:0.0.7
```

3. Probar con `/start` y `/version` (primeros dos mensajes de la imagen adjuntada abajo)

4. Crear `deployment.yml` incluyendo el token.

5. Deployar:
```
kubectl apply -f deployment.yaml
```

6. Verificar pod:
```bash
[17:22:12] mbeorlegui@MatiasFierro:~/Escritorio/Matias/curso-docker-kube$ (master [ ? +- ]) kubectl get deployments
NAME          READY   UP-TO-DATE   AVAILABLE   AGE
telegrambot   0/1     1            0           67s
```

```bash
[17:23:31] mbeorlegui@MatiasFierro:~/Escritorio/Matias/curso-docker-kube$ (master [ ? +- ]) kubectl get pods
NAME                            READY   STATUS              RESTARTS       AGE
telegram-bot-56b4499454-qh6zb   0/1     ContainerCreating   0              2s
```

7. Probar envio de mensajes `/start` y `/version`:

![Botcito](Telegram-bot.png)