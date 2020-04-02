# Skytap-DevOps-Jenkins
## Entorno de integración :computer:
---
Se aprovisiona una máquina en skytap haciendo uso de la plantilla de _Jenkins v2.121.3 on Ubuntu 16.04.5 LTS Desktop-Firstboot_ la cual tiene instalada la versión _2.121.3_ de la herramienta de integración contínua _Jenkins_. 

### 1.Conexión ssh entorno producción - entorno integración
Se debe crear una clave SSH con el propósito de facilitar los inicios de sesión automatizados y sin contraseña. Para generar la clave ssh utilice el sieguiente comando:
```sh
ssh-keygen
```
_id_rsa_ es la clave privada, la que permanecerá en la máquina local, _id_rsa.pub_ es la clave pública, la que se tiene que copiar al servidor remoto al que se quiere acceder. Una vez generado el par de claves en la máquina de integración hay que copiar la clave pública a la máquina de producción:
```sh
 scp ~/.ssh/id_rsa.pub deploy@ip_produccion:/home/user/uploaded_key.pub
```

## Entorno de producción :computer: 
---
Se aprovisiona una máquina en skytap haciendo uso de la plantilla cuyo sistema operativo es ubuntu. Para el despliegue de la aplicación se desarrolla el siguiente procedimiento:



