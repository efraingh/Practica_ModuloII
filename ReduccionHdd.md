## REDUCIR EL TAMAÑO DE LA PARTICION

### Desmonstamos la particion de / tmp

```
umount /dev/mapper/sistemas-tmp
df -h
```

### Reducimos el tamaño de la particion

```
e2fsck -f /dev/mapper/sistemas-tmp 100M
resize2fs /dev/mapper/sistemas-tmp 100M 
```

### ahora montamos la particion de /tmp

```
mount /tmp
```

### Reducimos la informacion

```
lvreduce -L 100M /dev/sistemas-tmp
lvs
```

## Agregar nuevo hardware de almacenamiento a nuestra virtual.

### adicionamos el disco HD nuevo.
### Verificamos el tamaño de las extenciones.
```
df -h
fdisk -l
```

### Vemos el tamaño de las particiones para poder crear un nuevo volumen.

```
cfdisk /dev/vdb
``` 

### Verificamos con:

```
vgdisplay

pvdisplay   //verifica los grupos a los que pertenece
```

### Ahora cramos la nueva particion.

```
cfdisk /dev/vdb
```

### nos mostrara en consola algunas opciones en donde le daremos:
### New - Primario - tamaño: 1024M - Beging - Write - y Quit

### Teniendo ya la particion, creamos la particion física del HD

```
fdisk -l /dev/vdb1

pvcreate /dev/vdb1     //Nos mostrara un mensaje de Sercifull
```

### Creamos el nuevo nuevo grupo del Volumen lógico

```
vgcreate grupoA /dev/vdb1
```

### Verificamos si se a unido al grupo

```
pvdisplay
lvs
```

### Ahora crearemos el Volumen Logico dentro del grupoA

```
lvcreate -L 500M -n volumen01 greupoA
lvs
```

### Le damos el formato a la nueva particion

```
mkfs.ext3 -m 0 /dev/mapper/greupoA-Volumen01
```

### Ahora montamos la particion

```
mkdir /mnt/volumen01
mounnt /dev/mapper/grupoA-volumen01 /mnt/volumen-01
```

### Para poder montar automaticamente en cada reinicio modificamos, y adicionamos la direccion del montaje del nuevo volumen

```
nano /etc/fstab
```

## Ampliar tamaño del HD

### Ingresamos hasta la hubicacion de las unidades virtuales, una ves dentro la carpata donde se encuentran nuestras virtuales le damos el siguiente comando:

```
qemu-img resize nombre_maquina_virtual +10G
```

### Verificamos el Espacio adicionado con:

```
cfdisk /dev/vda
```

### Ahora cambiamos el Tamaño de la particion reiniciando con el "Git-parted", cambiando de tamaño del Extend y del LVM.

## Configuracion de redes en Linux.

### Ver las conexiones de las redes-

```
nm-connection-editor
```

### El Archivo para ver la configuracion de la Red es en la direccion.

```
/etc/network/interfaces
```

### Donde la interfas de red es: eth0
### donde el loop bak : lo

## Configuracion Dinamica

### al ingresar a la configuracion de la red, se encontrara en "dhcp"

## Configuracion Estatica

### Ingresamos a la configuracion de la red.

```
/etc/networking/interfaces
```

### Cambiar la configuracion estatica de la red.

```
iface eth0 inet static
address numero_ip
netmask mascara_red
gateway ip_gateway
```

### Reiniciamos los servicios de red, de dos formas.

```
service networking restart
/etc/init.d/networking restart
```

### Verificamos la ip

```
ip addr show eth0
```

### Adicionamos las DNS al equipo.

```
nano /etc/resolv.conf
```

## Servicio SSH

### Instalamos el Servicio ssh

```
apt-get install ssh
```

### Configuramos el Servicio SSH

```
nano -c /etc/ssh/sshd_config
```

### En la linea 31 colocamos "no" en PubKeyAutentication no

### Reiniciamos el Servicio SSH

```
service ssh restart
```

### Ingresamos desde otra maquina.

```
ssh usuario@ip_server_ssh
```

### Crear documento y lo subimos por ssh a la carpeta /tmp

```
echo "hola mundo" > hola.txt

scp hola.txt usuario@ip_server_ssh:/tmp
```

### Para poder copiar varias carpeta por SSH se usa lo siguiente:

```
scp -r /tmp/datos_carpeta/ usuario@ip_server_ssh:/srv
```

### Desabilitar el usuario root de SSH, en la linea 27 de la configuracion de SSH

```
en : PermitRootLogin  no
```

### Para poder ver los usuarios conectados por ssh

```
who
```

## Crear llaves para SSH

### Creamos la llave del usuario con el siguiente comando

```
ssh-keygen -t rsa -b 2048
```

### Copiamos la llave al Servidor SSH

```
ssh-copy-id -i /usuario/.ssh/id_rsa.pub usuario@ip_server_ssh
```

### Verificamos la copia de las llaves publicas

```
head ~/.ssh/id_rsa.pub
```
### Otorgar permisos a carpetas

```
chmod o+w prueba/
```

### Quitar permisos

```
chmod o-w prueba/
```

### Permisos solo de lectura

```
chmod 437 prueba/
```

### Cambiar usuarios de carpetas

```
chown root:usuario prueba/
```

### Adicionar usuarios en Linux

```
sudo useradd usuario1
```

### Adicionar Password de usuario

```
sudo passwd usuario1
```

### Listar usuarios del equipos

```
getent passwd
```

### Ingresar como otro usuario

```
sudo su - usuario1
```

### Crear usuario

```
sudo adduser usuario2
```
