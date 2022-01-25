# FAIL2BAN
FAIL2BAN es una plaicación de Linux, que nos permite controlar y denegar conexiones de IPs no autorizadas a nuestro servidor.
Estas acciones las realiza al bloquear o banear a las IPs que realizan varios intentos fallidos de acceso a nuestro servidor (ataques de fuerza bruta).

Se distribuye bajo licencia GNU y funciona en sistemas POSIX.

Vamos a explicar la instalación y configuración de FAIL2BAN.
Pero antes instalaremos un servidor SSH en nuestro caso instalaremos OpenSSH.

## Instalación

Para instalar FAIL2BAN solo tendremos que poner en Ubuntu el comando: 
sudo apt install -y fail2ban

## Configuración

Una vez lo tengamos instalado deberemos ir al fichero de configuración para añadir nuestras reglas de conexión.

El fichero es: **/etc/fail2ban/jail.conf**, pero no es recomendable modificarlo por temas de actualizaciones.
Para poner nuestras propias reglas de conexión deberemos modificar el siguiente fichero: **/etc/fail2ban/jail.d/defaults-debian.conf**

También podemos crear el fichero ***jail.local*** en la ruta **/etc/fail2ban/jail.local** y añadir nuestras reglas, pero mi preferencia es usar el fichero que ya viene para ello.

### BIBLIOGRAFÍA
- https://programmerclick.com/article/3350758799/
- https://www.redeszone.net/tutoriales/servidores/servidor-openssh-linux-configuracion-maxima-seguridad/
- https://www.arsys.es/blog/instalar-fail2ban
