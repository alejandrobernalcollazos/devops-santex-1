# Actividad en clase

## Requierimientos

- Una terminal para conectarse por ssh

## 1. Crear una llave de ssh

## 2. Conectarse a una maquina remota

```
ssh -i <path a la llave privada> root@<ip de la maquina>
```

## 3. Actualizar los paquetes del sistema operativo

```
apt-get update
```

## 4. Instalar NodeJS

### 4.1 Instalar curl

```
apt-get install curl

```

### 4.2 Configurar el repositorio

```
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
```

### 4.3 Instalar node

```
apt-get install nodejs
```

## 5. Crear el usuario "desarrollo" e impersonarme con el usuario desarrollo

```
adduser desarrollo
```
Impersonarme como el usuario desarrollo
```
sudo su desarrollo
```

## 6. Ir al home del usuario desarrollo

```
cd ~
```

## 7. Crear el archivo script.sh con el siguiente contenido

```
#!/bin/bash

echo "Buuueeeenasssss"
```

## 8. Verificar los permisos del archivo

```
ll script.sh
``` 

## 9. Dar permisos de ejecución al archivo solo para el usuario dueño del mismo

```
chmod u+x script.sh
```

## 10. Ejecutar el archivo script.sh

```
./script.sh
```

## 11. Crear un archivo server.js con el siguiente contenido

```
var http = require('http');
http.createServer(function (req, res) {
  res.writeHead(200, {'Content-Type': 'text/plain'});
  res.end('Hello World\n');
}).listen(3000);
console.log('Server running at 3000');
``` 

## 12. Volverse root

Ejecuta el siguiente comando para salir del usuario desarrollo

```
exit
```

## 13. Instalar Docker

### 13.1 Instalar dependencias

```
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```

### 13.2 Instalar las llaves de GPG

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

### 13.3 Agregar el repositorio de Docker en los repositorios de APT

```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
```

### 13.4 Actualizar los repositorios 

```
sudo apt update
```

### 13.5 Limpiar la cache de repositorios

```
apt-cache policy docker-ce
```

### 13.6 Instalar docker 

```
sudo apt install docker-ce
```

### 13.7 Validar que docker este corriendo

```
sudo systemctl status docker
```

### 13.8 Correr el hello world de docker

```
docker run hello-world
```

### 13.9 Correr un nginx con docker

```
docker run nginx
```

### 13.10 Correr un nginx con docker haciendo un bind al puerto 80 local con el puerto 80 del contenedor

```
docker run -p 80:80 nginx
```
