# PRÁCTICA 2

## 1. Descarga la imagen 'httpd' y comprueba que está en tu equipo.

Para descargar la imagen se utiliza un **"pull"**:

    docker pull httpd

Para comprobar que se ha descargado se utilza **"images"**:

## 2. Crea un contenedor con el nombre 'asir_httpd'

Para dar nombre se utiliza **"--name"**:

    docker run -dit --name asir_httpd httpd

## 3. Mapea el puerto 80 del contenedor con el puerto 8000 de tu máquina.

Se utiliza **"-p"** para asignar el puerto:

     docker run -dit --name asir_httpd -p 8000:80 httpd
## 4. Utiliza bind mount para que el directorio del apache2 'htdocs' este montado un directorio que tu elijas. 

Para elegir un directorio específico primero se coloca la ruta destino seguido de: **":/usr/local/apache2/htdocs/"**

    docker run -dit --name asir_httpd -p 8000:80 -v /home/asir2/Documentos/SRI/PRACTICA2/Carpeta:/usr/local/apache2/htdocs/ httpd:2.4

## 5. Realiza un 'hola mundo' en html y comprueba que accedes desde el navegador.

Se crea un index.html en la carpeta que asignamos previamente al contenedor y dentro de este html se escribe **"Hola mundo"**

## 6. Crea un contenedor 'asir_web1' que use este mismo directorio para 'htdocs' y el puerto 8000

Se repite lo empleado anteriormente y se crea un nuevo contenedor llamado **"asir_web1"** y se le asigna la el mismo directorio

    docker run -dit --name asir_web1 -p 8000:80 -v /home/asir2/Documentos/SRI/PRACTICA2/htdocs:/usr/local/apache2/htdocs/ httpd:2.4