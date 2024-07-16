# Born2beroot

Crear la maquina irtual
Evaluar la maquina virtual

Seguir la guía de <a href="https://github.com/gemartin99/Born2beroot-Tutorial">Gerard Martinez</a>

La unica cosa a tener en cuenta es en el paso:

**4-6 Conectarse vía SSH**

Tienes que seguir esta miniguia que te dejo debajo.

Y despues conectarte con **ssh tuUsuario@192.168.56.1 -p 4242**

## **Comprobrar que tenemos la tarjeta de red de VirtualBox configurada:**

![image](https://github.com/user-attachments/assets/e8e3ff50-f3ec-4b8b-b123-8910b0af8dec)

Seleccionamos red

![image](https://github.com/user-attachments/assets/dd3986c5-670f-4bdc-9f21-62efb6d97e73)

En caso contrario

![image](https://github.com/user-attachments/assets/a5036f80-223b-4b14-aba9-4c05c7a22194)

## **Comprobrar que la tarjeta de red de VirtualBox esta "despierta", que tiene IP asignada**

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

## La configuración tiene que quedar asi:

![image](https://github.com/user-attachments/assets/4e5392cb-ca5d-4709-acb0-d940c06cc5bc)

![image](https://github.com/user-attachments/assets/fdf28646-f228-4508-90a8-02c24d517783)

![image](https://github.com/user-attachments/assets/f257c878-4531-4ebf-96a8-e29b889530d7)



Evaluar la maquina virtual
