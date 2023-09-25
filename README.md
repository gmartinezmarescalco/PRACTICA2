# PRÁCTICA 2

## 1. Descarga la imagen 'httpd' y comprueba que está en tu equipo.

Para descargar la imagen se utiliza un **"pull"**:

    docker pull httpd

Para comprobar que se ha descargado se utilza **"images"**:

## 2. Crea un contenedor con el nombre 'asir_httpd'

Para dar nombre se utiliza **"--name"**:

    docker run -dit --name asir_httpd httpd
