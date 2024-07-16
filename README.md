# Born2beroot

> Module 00
>
> - :bookmark_tabs: [Crear la maquina virtual](#crear-la-maquina-virtual)  
>
> - :white_check_mark: [Evaluar](#evaluar-la-maquina-virtual)






Seguir la guía de <a href="https://github.com/gemartin99/Born2beroot-Tutorial">Gerard Martinez</a>

La unica cosa a tener en cuenta es en el paso:

**4-6 Conectarse vía SSH**

Tienes que seguir esta miniguia que te dejo debajo.

Y despues conectarte con **ssh tuUsuario@192.168.56.1 -p 4242**



### **Comprobrar que tenemos la tarjeta de red de VirtualBox configurada:**

![image](https://github.com/user-attachments/assets/e8e3ff50-f3ec-4b8b-b123-8910b0af8dec)

Seleccionamos red

![image](https://github.com/user-attachments/assets/dd3986c5-670f-4bdc-9f21-62efb6d97e73)

En caso contrario

![image](https://github.com/user-attachments/assets/a5036f80-223b-4b14-aba9-4c05c7a22194)



### **Comprobrar que la tarjeta de red de VirtualBox esta "despierta", que tiene IP asignada**

En un terminal Ejecutamos **ip address show**

![image](https://github.com/user-attachments/assets/cc359fd1-d5cc-4431-90ad-07a97762eac4)

Si como se ve en la imagen, vboxnet0 no tiene asignada ninguna IP, tenemos que "despertar" latarjeta de red:

![image](https://github.com/user-attachments/assets/b8974215-7675-4b14-b0ed-249f13fe0bbe)

Habilitamos el Adaptador 2

![image](https://github.com/user-attachments/assets/974c3eec-1545-40bc-bd6d-b1143d7e6c52)

Conectado a Adaptador sólo anfitrión

![image](https://github.com/user-attachments/assets/ebe76581-ef8c-4568-9c7b-ddf0bb8cc3f2)

Arrancamos la maquina y nos da error

![image](https://github.com/user-attachments/assets/d7b43166-c435-44e2-b8a8-e640699a7ff9)

Volvemos a comprobrar en el terminal la IP con **ip address show**

![image](https://github.com/user-attachments/assets/d9348668-eea0-46fb-8212-45eab286fc99)

Volvemos a deshabilitar el Adaptador 2

![image](https://github.com/user-attachments/assets/056e4896-0a47-41f2-a3d0-20136efbc4ae)

Ahora ya podemos continuar.



### La configuración tiene que quedar asi:

![image](https://github.com/user-attachments/assets/4e5392cb-ca5d-4709-acb0-d940c06cc5bc)

![image](https://github.com/user-attachments/assets/fdf28646-f228-4508-90a8-02c24d517783)

![image](https://github.com/user-attachments/assets/f257c878-4531-4ebf-96a8-e29b889530d7)




## Evaluar la maquina virtual

> **Cómo funciona una máquina virtual.**	
>
> - Es un programa que simula una maquina a la que se le instala un SO, con la ventaja de que se puede exportar, duplicar, eliminar....																								


> **Elección del sistema operativo.**
>
> - Debian esta enfocado a un entorno más basico y Rocky a uno profesional																								


> **Diferencias básicas entre Rocky y Debian.**
>
> - Debian una distribución independiente con mayor flexibilidad, libertad de elección y una comunidad grande y activa.
>
> - Rocky es una distribución comercial y estable, compatible con RHEL (Red Hat Enterprise Linux) y con soporte empresarial


> **El propósito de las máquinas virtuales.**
>
> - Ejecutar para hacer pruebas o para producción diferentes maquinas y SO y asi por ejemplo correr Linux en una maquina tiene Windows


> **Si el estudiante evaluado eligió Rocky: qué son SELinux y DNF.**

> **Si el estudiante evaluado eligió Debian: la diferencia entre aptitude y apt, y qué es APPArmor.**
>
> - Aptitude es una versión mejorada de apt.
>
> - apt es un administrador de paquetes de nivel inferior.
>
> - aptitude es un administrador de paquetes de alto nivel.
>
> - APPArmor es un módulo de seguridad del kernel Linux que permite al administrador del sistema restringir las capacidades de un programa.


> **LVM**
>
> - Es un gestor de volúmenes lógicos.
>
> - Proporciona un método para asignar espacio en dispositivos de almacenamiento masivo, que es más flexible que los esquemas de particionado convencionales para almacenar volúmenes		


> **Durante la defensa, un script debe mostrar información cada 10 minutos.**


> **Asegúrate de que la máquina no tenga un entorno gráfico al inicio**
>
> ls /usr/bin/*session


> **Se solicitará una contraseña antes de intentar conectarse a esta máquina**


> **Conéctate con un usuario con la ayuda del estudiante evaluado. Este usuario no debe ser root.**
>
> getent group root
>
> id tuUsuario		


> **Comprueba que el servicio UFW esté iniciado con la ayuda del evaluador.**
>
> sudo ufw status
>
> To        Action   From
> 4242      ALLOW    Anywhere
> 4242 (v6) ALLOW    Anywhere (v6)	


> **Comprueba que el servicio SSH esté iniciado con la ayuda del evaluador.**
>
> sudo service ssh status

> active (running)
> Server listening on 0.0.0.0 port 4242
> Server listening on :: port 4242


> **Comprueba que el sistema operativo elegido sea Debian o Rocky con la ayuda del evaluador**
>
> uname -v
>
> #1 SMP PREEMPT_DYNAMIC Debian 6.1.90-1 (2024-05-03)			


> **Exista el usuario con el login evaluado**


> **Comprueba que se haya agregado y que pertenezca a los grupos "sudo" y "user42".**
>
> getent group sudo
> getent group user42
>
> id tuUsuario


> **crea un nuevo usuario**
> sudo adduser noroot	


> **Asígnale una contraseña de tu elección, respetando las reglas del subject**
>
> - minlen=10 ➤ La cantidad mínima de caracteres que debe contener la contraseña.
>
> - ucredit=-1 ➤ Como mínimo debe contener una letra mayúscula. Ponemos el - ya que debe contener como mínimo un carácter, si ponemos + nos referimos a como máximo esos caracteres.
>
> - dcredit=-1 ➤ Como mínimo debe contener un dígito.
>
> - lcredit=-1 ➤ Como mínimo debe contener una letra minúscula.
>
> - maxrepeat=3 ➤ No puede tener más de 3 veces seguidas el mismo carácter.
>
> - reject_username ➤ No puede contener el nombre del usuario.
>
> - difok=7 ➤ Debe tener al menos 7 caracteres que no sean parte de la antigua contraseña.
>
> - enforce_for_root ➤ Implementaremos esta política para el usuario root.


> **Cómo ha configurado las reglas solicitadas en el subject en su máquina virtual**
>
> nano /etc/pam.d/common-password				


> **El estudiante evaluado crea un grupo llamado "evaluating" frente a ti y asígnalo a este usuario**
>
> sudo addgroup evaluating
>
> sudo adduser name_user evaluating		


> **Ventajas de esta política de contraseñas, así como las ventajas y desventajas de su implementación**
>
> - Ventajas: Mayor seguridad
>
> - Desventajas: Mayor dificultad al tener que recodar y modificar


> **Comprueba que el nombre de host de la máquina esté formateado correctamente de la siguiente manera: login42 (login del estudiante evaluado)**
>
> hostname		


> **Modifica este nombre de host reemplazando el login por el tuyo y reinicia la maquina**
>
> sudo nano /etc/hostname


> **Si al reiniciar, el nombre de host no se ha actualizado, la evaluación se detiene aquí.**


> **Restaurar la máquina al nombre de host original.**
>
> sudo nano /etc/hostname


> **Ver las particiones de esta máquina virtual.**
>
> lsblk	


> **Compara la salida con el ejemplo proporcionado en el subject**


> **breve explicación de cómo funciona LVM y de qué se trata.**


> **Comprueba que el programa "sudo" esté instalado**
>
> dpkg -s sudo	


> **mostrar cómo asignar tu nuevo usuario al grupo "sudo"**
>
> sudo adduser noroot sudo	


> **explicar el valor y el funcionamiento de sudo usando ejemplos de su elección**
>
> - Sudo (Super-User Do) es un programa que permite a los usuarios ejecutar comandos con los privilegios de otro usuario, generalmente el usuario root.
>
> - Esto significa que los usuarios normales pueden realizar tareas administrativas sin tener que saber la contraseña de root.


> **mostrarte la implementación de las reglas impuestas por el subject**
>
> nano /etc/sudoers.d/sudo_config


> **Verifica que la carpeta "/var/log/sudo/" exista y tenga al menos un archivo**
>
> con permisos de "su"
>
> cd /var/log/sudo
>
> nano sudo_config
>
> cat sudo_config


> **Comprueba el contenido de los archivos de esta carpeta. Deberías ver un historial de los comandos utilizados con sudo**
>
> - Ver listado de comandos sudo	


> **intenta ejecutar un comando a través de sudo**
>
> sudo nano sudo_config


> **Observa si el(los) archivo(s) en "/var/log/sudo/" se han actualizado**


> **Comprueba que el programa "UFW" esté instalado correctamente en la máquina virtual.**
>
> dpkg -s ufw


> **Enumera las reglas activas en UFW (o Firewalld). Debe existir una regla para el puerto 4242.**
>
> sudo service ufw status
>
> sudo ufw status numbered


> **Agrega una nueva regla para abrir el puerto 8080. Comprueba que se haya agregado esta regla enumerando las reglas activas.**
>
> sudo ufw allow 8080
>
> sudo ufw status numbered


> **elimina esta nueva regla con la ayuda del estudiante evaluado**
>
> sudo ufw delete num_rule		


> **Comprueba que el servicio SSH esté instalado correctamente en la máquina virtual.**
>
> sudo service ssh status	


> **Comprueba que esté funcionando correctamente.**
>
> sudo service ssh status	


> **explicarte básicamente qué es SSH y el valor de usarlo**
>
> - SSH (Secure Shell) es un protocolo de red que permite una comunicación segura entre dos computadoras a través de una red no segura.
>
> - Se utiliza comúnmente para la administración remota de servidores, transferencias de archivos seguras y túneles de datos cifrados.


> **Verifica que el servicio SSH solo use el puerto 4242.**
>
> ssh tuUsuario@192.168.56.1 -p 8080


> **usar SSH para iniciar sesión con el usuario recién creado**
>
> ssh noroot@192.168.56.1 -p 4242	


> **debes asegurarte de que no se pueda usar SSH con el usuario "root" como se indica en el subject**
>
> ssh root@192.168.56.1 -p 4242


> **Cómo funciona su script mostrándote el código.**
>
> - desde la raiz
>
> ls
>
> nano monitoring.sh	


> **Qué es "cron".**
>
> - Cron en Linux es un demonio (proceso en segundo plano) que se ejecuta automáticamente en un sistema operativo Linux y permite programar la ejecución de tareas o scripts en intervalos específicos de tiempo. Estas tareas pueden ser simples comandos del sistema operativo, scripts más complejos o incluso aplicaciones completas.


> **Cómo el estudiante evaluado configuró su script para que se ejecute cada 10 minutos desde el inicio del servidor.**
>
> sudo crontab -u root -e


> **el estudiante evaluado debe asegurarse de que este script se ejecute cada minuto**
>
> */1 * * * * sh /home/ilastra-/monitoring.sh


> **el estudiante evaluado debe hacer que el script deje de ejecutarse cuando el servidor se haya iniciado, pero sin modificar el script en sí.**
>
> sudo /etc/init.d/cron stop


> **Para comprobar este punto, tendrás que reiniciar el servidor una última vez**


> **Al iniciar, será necesario verificar que el script sigue existiendo en el mismo lugar, que sus permisos no han cambiado y que no ha sido modificado.**
>
> sudo crontab -u root -e

