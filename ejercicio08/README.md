# Ejercicio 8

Utilizando docker compose generar una configuraci�n para correr dos instancias de passwordapi (`nicopaez/password-api`) balanceadas por Nginx.
La aplicaci�n tiene un endpoint `/health` que indica la ip/host de la instancia que atendi� el pedido, se puede usar esto para verificar el correcto balanceo.

Poner la soluci�n en un carpeta ejercicio08, incluyendo:
- La configuraci�n de compose
- El README.md con la forma correrlo y cualquier explicaci�n que consideres relevante.

## Solución

1. Levanto el servicio de Docker:
```
docker-compose up -d
```
2. Ingresar a http://localhost:8083/
3. Ingresar a http://localhost:8083/health

