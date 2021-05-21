# Crear un túnel SSH
Sintaxis general:
```bash
ssh -L [ip_local:]puerto_local:host_remoto:puerto_remoto user@hostname
```
Donde:
* **ip_local**: se suele obviar. Ip de tu equipo
* **puerto_local**: puerto LOCAL que estará en tú extremo del túnel
* **host_remoto**: IP del servidor remoto. Otro extremo del túnel
* **puerto_remoto**: puerto al otro lado del túnel
* **usuario@hostremoto**: (host que hará de pasarela)

## Ejemplo 1
Me quierlo conectar a la web http://www.prueba.com usando como pasarela 192.168.1.129
```bash
ssh -L 8888:www.prueba.com:80 smr@192.168.1.129
``` 
He eligido mi puerto local prueba.com:80.
Si abro un navegador y me conecto a https://localhost:8888 me conecto a la web www.prueba.com.

## Ejemplo 2
Me quiero conectar a un mysql server de una máquina que no admite conexiones de fuera:
```ssh
ssh -L 3306:localhost:3306 root@servidorMySQL
```

Ojo que ese localhost no se refiere a tu máquina sino a servidorMySQL

### Fuente
https://www.sombreroblanco.es/2018/10/tunel-ssh-for-dummies-una-explicacion-sencilla/