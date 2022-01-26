# FAIL2BAN
FAIL2BAN es una plaicación de Linux, que nos permite controlar y denegar conexiones de IPs no autorizadas a nuestro servidor.
Estas acciones las realiza al bloquear o banear a las IPs que realizan varios intentos fallidos de acceso a nuestro servidor (ataques de fuerza bruta).

Se distribuye bajo licencia GNU y funciona en sistemas POSIX.

Vamos a explicar la instalación y configuración de FAIL2BAN.
Pero antes instalaremos un servidor SSH en nuestro caso instalaremos OpenSSH.

## Instalación

Para instalar FAIL2BAN solo tendremos que poner en Ubuntu el comando: 
**sudo apt install -y fail2ban**

## Configuración

Una vez lo tengamos instalado deberemos ir al fichero de configuración para añadir nuestras reglas de conexión.

El fichero es: **/etc/fail2ban/jail.conf**, pero no es recomendable modificarlo por temas de actualizaciones.
Para poner nuestras propias reglas de conexión deberemos modificar el siguiente fichero: **/etc/fail2ban/jail.d/defaults-debian.conf**

También podemos crear el fichero ***jail.local*** en la ruta **/etc/fail2ban/jail.local** y añadir nuestras reglas, pero mi preferencia es usar el fichero que ya viene para ello.

## EJEMPLOS
### Ejemplo 1
En el primer ejemplo vamos ignorar nuestra propia IP y por mucho que nos equivoquemos no bloqueará la IP.

Tras poner que ignore la IP proparemos la conexión, primero fallando los tres intentos para ver que no nos bloquea y por último nos conectaremos con nuestra propia IP.

### Ejemplo 2
El segundo ejemplo será un poco más realista.
Ignoraremos una IP del rango del servidor.

Haremos como en el primer ejemplo, primero nos equivocaremos en el tercer intento y luego nos conectaremos viendo que no nos ha bloqueado.

### Ejemplo 3

El último ejemplo lo realizaremos con un vídeo ya que haremos una atque de fuerza bruta con una IP, a la que no hemos especificado que sea ignorada y la cual al fallar tres veces nos bloqueará la IP durante 24 horas hasta poder intentarlo de nuevo.

También veremos los log de FAIL2BAN para comprobar lo que ha ido sucediendo con el ataque de fuerza bruta.

## ENLACE AL VÍDEO


### BIBLIOGRAFÍA
- https://programmerclick.com/article/3350758799/
- https://www.arsys.es/blog/instalar-fail2ban
- https://www.youtube.com/watch?v=5sE2Mici96o
