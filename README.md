# Skytap-DevOps-Jenkins
## Entorno de integración :computer:
---
Se aprovisiona una máquina en skytap haciendo uso de la plantilla de _Jenkins v2.121.3 on Ubuntu 16.04.5 LTS Desktop-Firstboot_ la cual tiene instalada la versión _2.121.3_ de la herramienta de integración contínua _Jenkins_. 

### 1.Creación del proyecto
Ingrese a la interfaz de jenkins mediante la IP o el DNS de la máquina por el puerto 8080, las credenciales las encontrará en skytap, en la sección VM settings -> credentials.
Un vez ingrese sus credenciales seleccione _crear nueva tarea_ para crear un _proyecto libre_. Es importante que configure el origen del código fuente, para esto, seleccionamos _git_ y en el campo _Repository URL_ ingresamos la [dirección de nuestro repositorio](https://github.com/mayi29/js-jenkis).

### 3.Plugin de SSH

### 4.Conexión SSH con la máquina de producción
Se debe crear una clave SSH con el propósito de facilitar los inicios de sesión automatizados y sin contraseña entre ambas máquinas. Para generar la clave ssh utilice el sieguiente comando:
```sh
ssh-keygen
```
_id_rsa_ es la clave privada, _id_rsa.pub_ es la clave pública. Una vez generado el par de claves hay que copiar la clave pública a la máquina de producción:
```sh
 scp ~/.ssh/id_rsa.pub deploy@ip_produccion:/home/user/uploaded_key.pub
```
En la máquina de producción, si la carpeta .ssh no existe, se debe crear junto con el archivo authorized_keys, usando los siguientes comandos:
```sh
mkdir .ssh
chmod 700 .ssh
touch .ssh/authorized_keys
chmod 600 .ssh/authorized_keys
```
Por último, en la máquina de producción copiamos la clave enviada por la máquina de integración y borramos el archivo copiado:
```sh
echo `cat ~/uploaded_key.pub` >> ~/.ssh/authorized_keys
rm /home/user/uploaded_key.pub
```
## Entorno de producción :computer: 
---
Se aprovisiona una máquina en skytap haciendo uso de la plantilla cuyo sistema operativo es ubuntu. Para el despliegue de la aplicación se desarrolla el siguiente procedimiento:

