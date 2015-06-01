#COMANDOS BASICOS Y GENERALES

***Listar archivos por fecha de modificacion***
```
ls -lahts
```
***Crear Directorio***
```
mkdir nombre_carpeta
```
***Crear Subcarpetas***
```
mkdir -p /***nombre_carpeta***/***nombre_subcarpeta***
```
***Crear varias carpetas en uno***
```
mkdir /tmp/xxx/aaa/eee/{c1,c2,c3,c4,c5}
```
***Identificacion del Directorio Actual***
```
.  (Punto)
```
***Crear un archivo vacio de texto plano***
```
Touch ***nombre_archivo***
```
***Edicion de archivos***
```
	*nano*
	*vi*
	*vim*
	*etc*
```
***Concatenacion de archivos***
```
ls -l >> nombre de archivo
```
***Busqueda de archivos***
```
grep nombre_archivo_buscar
find ~name /* |a \ * 
```
***Busqueda de CARPETA***
```
rm -r ***nombre de archivo***
```
***Crear carpeta en Directorios sin permiso***
```
sudo mkdir /opt/aaa
```
***Ingreso a carpetas***
```
cd Documentos
```
***salir***
```
cd ..
cd ~  //salir de home//
```
***Instalar paquetes***
```
apt-get install  ***nombre paquete***
aptitude install ***nombre paquete***
```
###CONFIGURACION DE LA RED

***Informacion de la tarjeta de red***
```
 lspci 
 lspci |grep -i network 
 lspci |grep -i ethernet
```
***Informacion de la red wifi***
```
 lspci |grep -i wireles
```
***Configuracion de red***
```
gnome-control-center network
```
###REPOSITORIOS
***Ingreso a repositorio***
```
nano /etc/apt/sources.list
```
***Instalacion de sudo***
```
apt-get install sudo
add user **usuario** sudo
```
***Instalacion de drives***
```
aptitude search ~dBCM4313
apt-get install firmware-brcm80211
non-free
```
*** Instalacion de drives por puertos DVD***
```
sudo mkdri /mnt/dvd/2
sudo mkdir /mnt/dvd3
sudo mount /mnt/hd/iso/wheezy/debian-7.4.0 - amd 64 - DVD -1.ISO  /mnt/dvd!
```