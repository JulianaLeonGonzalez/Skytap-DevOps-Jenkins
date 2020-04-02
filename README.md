# Skytap-DevOps-Jenkins
## Entorno de desarrollo :computer:
---
Se aprovisiona una máquina en skytap haciendo uso de la plantilla de _Jenkins v2.121.3 on Ubuntu 16.04.5 LTS Desktop-Firstboot_ la cual tiene instalada la versión _2.121.3_ de la herramienta de integración contínua _Jenkins_. 
## Entorno de producción :computer: 
---
Se aprovisiona una máquina en skytap haciendo uso de la plantilla cuyo sistema operativo es ubuntu. Para el despliegue de la aplicación se desarrolla el siguiente procedimiento:

### 1.Conexión ssh entorno producción - entorno desarrollo
Se debe crear una clave SSH con el propósito de facilitar los inicios de sesión automatizados y sin contraseña. Para generar la clave ssh utilice el sieguiente comando:
```sh
ssh-keygen
```
