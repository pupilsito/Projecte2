## Recuperar contraseña en Ubuntu (modo recuperación)

1. Cuando aparece el menú, seleccionamos la **segunda opción (modo recuperación)**.  
   *Ejemplo:*  
   `recovubuntu01`

2. En el menú de recuperación, elegimos la opción **root**  
   *(en versiones anteriores aparecía con el nombre de `netroot`)*.  
   *Ejemplo:*  
   `recovubuntu02`

3. Ya tenemos abierto un terminal en **modo root**, pero si intentamos cambiar la contraseña de un usuario con:

   ```bash
   passwd nombre_usuario

   
## Configurar autenticación en GRUB con contraseña cifrada

### 1. Generar el hash con PBKDF2

Ejecutamos el siguiente comando para generar un hash a partir de una contraseña, utilizando la función criptográfica PBKDF2:


```bash
grub-mkpasswd-pbkdf2

### Guardar el hash generado en un archivo

El problema es que necesitaremos añadir este hash a un archivo, y escribirlo manualmente no es una opción cómoda ni sencilla. Para facilitar este proceso, usaremos el comando `tee`, que permite redirigir la salida estándar hacia un archivo.

Por tanto, escribiremos lo siguiente:

```bash
grub-mkpasswd-pbkdf2 | tee salida.txt

grub-mkpasswd-pbkdf2 | tee salida.txt

