# REDIMENCIONAR o AUMENTAR DISCO
Para redimencionar o aumentar un disco seguiremos los siguientes pasos.
* Nos posicionamos en el directorio donde se encuentra nuestro disco duro virtual don las siguietes lineas de codigo.\
```
lvextend -L+100M /dev/mapper/Sistemas -lvs
```
* Desmontamos la Particion
```
umount  /tmp/dev/mapper/Sistemas-tmp
```
* Le damos el tipo de formato
```
e2fsck -f /dev/mapper/Sistemas-tm
```
* Redimencionamos el Disco
```
resize2fs /dev/mapper/Sistemas-tmp
```
* Montamos nuevamente la Particion redimencionada
```
mount /tmp
```
