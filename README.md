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

## 7. Utiliza Code para hacer un hola mundo en html

Ya que se ha anexado la misma carpeta a este contenedor que al de **"asir_httpd"** ya hay un documento html que tiene escrito **"Hola Mundo"**, por ende al abrir el navedor nos mostrará dicho mensaje

## 8. Crea otro contenedor 'asir_web2' con el mismo directorio y a otro puerto, por ejemplo 9080.

Se repite el uso de comandos anteriores, en este caso para crear un contenedor con nombre **"asir_web2"** y con el puerto **9080**

    docker run -dit --name asir_web2 -p 9080:80 -v /home/asir2/Documentos/SRI/PRACTICA2/htdocs:/usr/local/apache2/htdocs/ httpd:2.4