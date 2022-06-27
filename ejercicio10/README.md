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