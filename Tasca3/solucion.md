## Recuperar contraseña en Ubuntu (modo recuperación)

Después del primer trabajo exitoso, os llega un encargo urgente que obliga a que os ponéis para darle solución.

Como fase previa recibiréis una formación sobre la seguridad lógica que os permitirá tener los conocimientos necesarios para afrontar la tarea.

Han llegado a la consultora un equipo proveniente de un cliente que pide que se los solucionemos el problema.

Tienen un portátil con Zorin HUESO (uno Linux con entorno gráfico) que usaba habitualmente un directivo. El problema es que ha olvidado la contraseña y es necesario poder recuperar el acceso porque hay documentación muy importante que hay que recuperar. Para evitar que una acción catastrófica pueda dañar el equipo original, nos han clonado el disco en un disco virtual porque trabajáis.

Por lo tanto, el primer paso será crear una máquina virtual al que conectaréis este disco. A continuación, hace falta que entráis a la máquina virtual, encontráis el nombre del usuario existente y asignadle una contraseña nueva.

Cuando el cliente es informado del sencillo que es acceder al equipo, pide si hay alguna manera de fortificar el sistema, puesto que tiene miedo que si alguien ropa el portátil pueda acceder a la información que contiene. Por lo tanto, ahora nos piden que busquemos soluciones para evitar que se pueda reiniciar la contraseña con el procedimiento anterior.

Investigáis el procedimiento para que el acceso al GRUB quede protegido por contraseña para evitar cambios de configuración.

1. Cuando aparece el menú, seleccionamos la **segunda opción (modo recuperación)**.  
   *Ejemplo:*  
   `recovubuntu01`

2. En el menú de recuperación, elegimos la opción **root**  
![Root](img/2foto.png)

3. Para identificar el root haremos el comando: "mount -rw -o remount /"
![Root](img/3foto.png)

4.Seguidaemnte como hemos verificado que somos root hacemos el comando "passwd miquel"
![contraseña](img/4foto.png)

## Configurar autenticación en GRUB con contraseña cifrada

### 1. Generar el hash con PBKDF2

Ejecutamos el siguiente comando para generar un hash a partir de una contraseña, utilizando la función criptográfica PBKDF2: "grub-mkpasswd-pbkdf2"

![encriptación](img/5foto.png)

### Guardar el hash generado en un archivo
El problema es que necesitaremos añadir este hash a un archivo, y escribirlo manualmente no es una opción cómoda ni sencilla. Para facilitar este proceso, usaremos el comando `tee`, que permite redirigir la salida estándar hacia un archivo.

![encriptación](img/6foto.png)

