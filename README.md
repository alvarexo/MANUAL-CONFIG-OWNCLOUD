# MANUAL-CONFIG-OWNCLOUD

Para configurar owncloud, comenzaremos accediendo a la consola de mysql.
![Captura desde 2024-10-30 12-39-11](https://github.com/user-attachments/assets/83318904-9100-4e89-8f82-86c7b2a18a91)

Cuando ya estamos dentro de la consola, crearemos una base de datos con el nombre bbdd.
![Captura desde 2024-10-30 12-44-26](https://github.com/user-attachments/assets/cc1db9e5-c704-4bef-a0b6-648e8cbf3016)

Seguidamente, haremos la creación de un usuario para acceder a la base de datos.
CREATE USER 'usuario'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
![Captura desde 2024-10-30 12-47-36](https://github.com/user-attachments/assets/28a94ce1-9455-4c85-b944-caa21b5e9847)

Por último dentro de la base de datos le añadiremos unos permisos al usuario.
GRANT ALL ON bbdd.* to 'usuario'@'localhost';

Y ya después de este paso salimos de la base de datos con el "exit"

Lo que haremos ahora desde la terminal, probaremos y comprovaremos si un usuario sin permisos/privilegios se puede connectar introduciendo nuestra contraseña. 
mysql -u usuario -p
![Captura desde 2024-10-30 12-59-12](https://github.com/user-attachments/assets/3f1b3467-3f80-4710-bcc4-8bd159013a27)

### Seguimos con la descarga del archivo

sudo cp ~/Baixades/app-web.zip /var/www/html en mi caso cambiaria el nombre de archivo a owncloud.zip

Seguidamente, con este comando iremos al directorio, cd /var/www/html

El siguiente paso que haremos será descomprimir el archivo poniendo lo siguiente: sudo unzip owncloud.zip

sudo cp -R app-web/. /var/www/html, este comando lo haremos servir para copiar los archivos y modificarlos por el nombre del directorio

Y para acabar eliminamos la carpeta que hemos creado cuando hemos hecho el unzip: "sudo rm -rf app-web/"

Eliminamos el archivo del apache "sudo rm -rf /var/www/html/index.html"

### Permisos a nuestras aplicaciones

Una vez todo descomprimido, aplicamos estos permisos al directorio:

cd /var/www/html

sudo chmod -R 775 .

sudo chown -R usuario:www-data .

Y con esto ya acabariamos la configuración de OwnCloud.
