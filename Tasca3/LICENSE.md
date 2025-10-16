El primer paso será ejecutar el comando grub-mkpasswd-pbkdf2. Este comando sirve para generar un hash a partir de una contraseña, utilizando la función criptográfica PBKDF2. El resultado que se obtiene es un hash como el siguiente:

grub.pbkdf2.sha512.10000.E32CE9ABBEBCD4501E5A1341CAEBDBBD82FD10D4CB8

7B2A881938E1B825216C75F139AF3AC7677FBCF9753AC5E8B012FEBFA2832CCCB

31D0775B7BA55F017402.CE01C7AD62FC93CCF8BEF6223643C9DCB728B0C574A6

7867389D5D172D41C87629979559BF79F3AF77CAD3F11352C5397AC51BFFCB3159

E514D8412A740D3043

El problema, es que necesitaremos añadir este hash a un archivo y escribirlo no es una opción cómoda ni sencilla. Usaremos el comando tee que nos va a permitir redirigir la salida estandard hacia un archivo. Por tanto, escribiremos lo siguiente:

grub-mkpasswd-pbkdf2 | tee salida.txt

El siguiente paso será editar el archivo /etc/grub.d/40\_conf para añadir la autenticación. Será en ese archivo donde necesitaremos añadir el hash calculado anteriormente. Por este motivo, abriremos el editor nano pero habilitando la opción multibuffer que permite copiar texto de un archivo a otro.

sudo nano -F /etc/grub.d/40\_custom

Una vez abierto el editor, hacemos CTRL+r y nos aparecerá una diálogo para introducir el fichero origen, aquí pondremos el archivo creado anteriormente salida.txt. Ahora vemos como en pantalla lo que se nos muestra es este archivo.

El siguiente paso es copiar el bloque del texto correspondiente al hash, para ello, nos situamos al inicio de la línea en cuestión y pulsamos simultáneamente ALT+a. Nos vamos al final de la línea (con el cursor o con CTRL-e), con ello hemos seleccionado el texto que queremos copiar. Con ALT+6 copiamos el texto en el buffer y podemos cerrar el archivo con CTRL+x.

De nuevo estamos en el archivo /etc/grub.d/40\_custom y añadiremos estas dos líneas al final del archivo:

set superusers="nombre\_login"

password\_pbkdf2 nombre\_login

Donde nombre\_login será el identificador de usuario para autentificarse en el GRUB. Este identificador no tiene porqué coincidir con un usuario del sistema, el proceso de validación se realiza antes de iniciar el sistema y por tanto, no se accede al archivo de usuarios registrados del sistema.

En la segunda línea, a continuación del nombre usado para el login, pegaremos el contenido del buffer, que corresponde al hash. Para ello, simplemente haremos CTRL+u y una vez hecho esto, solo resta guardar y salir de nano.

Finalmente, aplicamos los cambios a la configuración de GRUB

sudo grub-mkconfig -o /boot/grub/grub.cfg
