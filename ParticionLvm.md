# PARTICIONAMIENTO LVM

* * *
Para particionar una maquina virtual con particion LVM seguimos los siguientes pasos.
1. /boot
2. swap
3. / (Sistema de fichero Raiz)
3. LVM
4. home
5. tmp

# 1.- /boot
* Seleccionamos el tipo de particion **Manual**.
* Seleccionamos el **disco duro Virtual**.
* Seleccionamos **Crear tabla de particion**.
* Seleccionamos el Espacio Libre del disco virtual.
* Elegimos **Nueva Particion** y le damos un tamano (256 MB) para el booteo.
* Marcamos como tipo **Primario**.
* Posicion **Principio**.
* Seleccionar la Opcion utilizar como..(Elegimos **Sistema de ficheros  ext2**).
* Punto de montaje **/boot**
* Elegir **Finalizar Particion.**
* * *
# 2.- Swap
* Seleccionamos **Espacio Libre**
* Elegimos **Nueva Particion**
* Le damos un espacio de 512MB
* Seleccionamos el tipo de particion como **Logica**
* Y lugar de la Particion **Principio**
* Seleccionamos la Opcion utiliza como... (Elegimos **Area de Intercambio**)
* Elegir **Finalizar Particion**
* * *
# 3.- / (SISTEMA DE FICHERO RAIZ)
* Seleccionamos **Espacio Libre**
* Elegimos **Nueva Particion**
* Le damos un espacio de 1GB o mas
* Tipo de particion **Logica**
* Lugar de la Pariticion **al Principio**
* Seleccionamos la Opcion utiliza como... (Elegimos **Sistema de ficheros ext4**)
* Punto de Montaje **/ Sistema de fichero Raiz**
* Elegir **Finalizar Particion**
* * *
# 4.- LVM
* Seleccionamos la Opcion Configurar el Gestor de Volumenes Logico LVM
* Guardar los cambios de la Particion anterior.
* Seleccionar la Opcion **Crear Grupo de Volumen**
* Colocamos un Nombre significativo y le damos aceptar
* Seleccionamos el espacio libre y le damos Aceptar
* Finalizamos la Particion
* * *
# 5.- home
* Seleccionamos la Opcion **Crear Volumen Logico**
* Seleccionamos el grupo de volumen que se creo anteriormente 
* Le damos un nombre al Volumen Logico 'home'
* Le damos un tamano de 500MB
* * *
# 6.- tmp
* Seleccionamos nuevamente **Crear Volumen Logico**
* Seleccionamos el grupo de volumen que se creo anteriormente.
* Le damos un nombre al Volumen Logico 'tmp'
* Le damos un tamano de 200MB
* Y finalmente seleccionamos la Opcion Terminar.
* * *

Ahora configuramos las opciones de Arranque de la particion Creada.
* Seleccionamos el home de LVM que se creo le damos enter.
* Le damos Utilizar como.. (ext4)
* Seleccionamos Punto de Montaje home
* Y seleccionamos se ha terminado de definir la particion

Ahora configuramos el tmp.
* Seleccionamos el tmp del LVM creado
* Seleccionamos Utilizar como.. (ext4)
* Seleccionamos Punto de Montaje (/tmp)
* Y seleccionamos se ha terminado de definir la Particion

### Y por ultimo seleccionamos Finalizar Particion para que comience con la instalacion del nuevo Sistema Operativo
