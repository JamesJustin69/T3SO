<div style="background-color: #ffb7c5; padding: 20px;">
  
# Tarea 3 - Sistemas operativos (Simón Onofri - Cristobal Zaror Puga)
Para esta actividad se pide implementar un sistemas de archivos (FS) simple, que cumpla con distintas funcionalidades de un FS, junto con i-nodos con su respectiva información. 

## Tecnologías Utilizadas
* VSCode
* debian: Debian GNU/Linux 12 (bookworm)

## ¿Como ejecutar el codigo?

* Paso 1; Descargar el archivo con el codigo, en el siguiente link de [drive](https://drive.google.com/drive/u/1/folders/18grUGS2Y3177hujlr6n08IVmBQg-kNcC)
* Paso 2; Ejecutar con los siguientes comandos: - Compilar: **gcc SimonOnofri_CristobalZaror.c -o tarea3** y **ejecutar: ./tarea3**
* Paso 3; para entender el funcionamiento del código, se tiene el video que se encuentra en el dirve junto al codigo.

## Funcionalidades

+ Mantenerse en todo momento en el directorio actual
+ create_file / create_directory : Crear archivos y directorios
+ rename_inode : Renombrar archivos y directorios
+ remove_inode(name) : eliminar archivos y directorio
+ set_permissions : Gestionar permisos
+ list_directory : Listar archivos de la ruta actual, de manera recursiva
+ find_inode_by_name(name) : Busqueda para encontrar archivos y directorios por nombre
+ print_history : Historial de comandos ejectuados
+ Archivos y directorio creados de manera persistente

A continuación se muestra y explica lo realiza con cada funcionalidad.

## create_file / create_directory
Código para crear archivos y directorios en el codigo:

![image](https://github.com/JamesJustin69/T3SO/assets/89882424/75133672-f087-4910-8339-ff88b8673bc2)

Explicación: Crea un archivo real en el directorio para poder trabajarlo segun sus permisos, y crea una referencia a este archivo como un nodo del arbol de inodos

## rename_inode

Para renombrar los archivos y directorios ya creados, es necesario implementar:

![image](https://github.com/JamesJustin69/T3SO/assets/89882424/d3d4b27a-d818-40f6-95e7-486303a87bd6)

Explicación: Se usa **strcpy(node->name, new_name);** para cambiar el nombre y el segundo argumento cambia el nombre del node 

## remove_inode(name)
Para eliminar un archivo o directorio ya creado:

![image](https://github.com/JamesJustin69/T3SO/assets/89882424/b1e04ba0-86d5-4032-a899-d75d98ab17cf)

Explicación: La eliminación ocurre en dos niveles, uno a nivel de FS y el otro ocurre en el arbol de referencias del FS

## set_permissions
Dar permisos de lectura, escritura y ejecución(chmod):

![image](https://github.com/JamesJustin69/T3SO/assets/89882424/b6734ebd-93d6-4a6b-ad33-72273e825a10)

Explicación: Para los permisos se genera un arreglo de tamaño 3(estricto), contiene un identifcador para los permisos, luego si se quiere editar se verifica el identificador para ver si es posible el cambio

## find_inode_by_name(name)
Buscar un archivo, directrio en particular:

![image](https://github.com/JamesJustin69/T3SO/assets/89882424/354566a6-0a37-4cdb-bfaf-a7d13ee73fd0)

Explicación: Se recorre el arbol y se hay un "match", este match recorre el arbol y si lo hay retorna el nodo con el nombre solictado, en caso de no haber match retorna nulo

## print_history
Historial de los comandos utilizados:

![image](https://github.com/JamesJustin69/T3SO/assets/89882424/0ffb57e4-8592-4426-9fd8-bd8a1e49cf13)

Explicación: Funciona en conjunto con **add_to_hisotry**, se genera un arreglo de **chars**, se va actualizando cada vez que se ejecuta un comando, y luego el **print** lo muestra en terminal 

</div>
