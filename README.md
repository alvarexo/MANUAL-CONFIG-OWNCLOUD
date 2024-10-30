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
