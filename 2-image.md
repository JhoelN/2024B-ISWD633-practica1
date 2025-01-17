# Imagen
Es un archivo único que contiene todos los programas, librerías, dependencias y configuraciones necesarias para instalar y/o ejecutar una aplicación o un conjunto de aplicaciones.
![Imagen](img/imagen.PNG)


## ¿Cuál es la relación entre una imagen y un contenedor? 

Imagen
Una imagen es una plantilla de solo lectura que contiene todo lo necesario para ejecutar una aplicación: código, dependencias, bibliotecas, configuraciones, etc.

Contenedor
Un contenedor es una instancia en ejecución de una imagen. Cuando ejecutas una imagen, Docker crea un contenedor a partir de esa imagen, lo cual incluye copiar el sistema de archivos de la imagen y crear un entorno aislado donde se ejecuta.


# COMPLETAR 

![Imagen y contenedores](img/imagenContenedores.JPG)
## Comandos para imágenes

### Descargar imagen
Descarga la última versión de la imagen disponible en el registro de Docker.

```
docker pull <nombre imagen> 
```

Descarga una versión específica de la imagen, cada imagen tiene etiquetas (tags) para diferentes versiones.
Una imagen puede tener la etiqueta latest para representar la última versión, si no se especifica una etiqueta se hará referencia a la versión latest.

```
docker pull <nombre imagen>:<tag>
```

Descargar la imagen **hello-world**

![Imagen y contenedores](img/Descargarimagenhello-world.png)

# COMPLETAR

**¿Qué es nginx**


Nginx, pronunciado como “engine-ex”, es un servidor web de código abierto que, desde su éxito inicial como servidor web, ahora también es usado como proxy inverso, cache de HTTP, y balanceador de carga.


# COMPLETAR 

Descargar la imagen  **nginx** en la versión **alpine**

![Imagen y contenedores](img/Descagarlaimagenalpine.png)

# COMPLETAR

### Listar imágenes

```
docker images
```

# COLOCAR UNA CAPTURA DE PANTALLA DEL RESULTADO 

![Imagen y contenedores](img/Listarimagenes.png)


**Identificadores**

En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran. 

### Inspeccionar una imagen
El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red.  Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>
docker inspect <nombre imagen>:<tag>
```

Inspeccionar la imagen hello-world 

![Imagen y contenedores](img/Inspeccionarhelloworld.png)


# COMPLETAR
**¿Con qué algoritmo se está generando el ID de la imagen**

Docker está utilizando el algoritmo de hash SHA-256 para identificar de manera única la imagen y sus capas.

# COMPLETAR

### Filtrar imágenes

```
docker images | grep <termino a buscar>

```
![Imagen y contenedores](img/Filtrarimagenes2.png)
![Imagen y contenedores](img/Filtrarimagenes1.png)

### Para eliminar una imagen
Eliminar permanentemente la imagen de tu sistema Docker.

```
docker rmi <nombre imagen>:<tag>
```

Eliminar la imagen hello-world 

![Imagen y contenedores](img/Eliminarpermanentementelaimagenhelloworld.png)

# COMPLETAR

-f: Es la opción para forzar la eliminación de la imagen incluso si hay contenedores en ejecución que utilizan esa imagen.
Cuando eliminas una imagen Docker, Docker no elimina automáticamente los contenedores que se han creado a partir de esa imagen. Esto significa que, aunque hayas eliminado la imagen, el contenedor seguirá ejecutándose normalmente.  
**Considerar**
Eliminar una imagen no afecta a los contenedores que se han creado a partir de esa imagen, a menos que esos contenedores dependan de archivos o configuraciones específicas de la imagen eliminada. En ese caso, es posible que los contenedores se comporten de manera inesperada después de eliminar la imagen.
Es una buena práctica detener y eliminar todos los contenedores que dependan de una imagen antes de eliminar la imagen en sí.

```
docker rmi -f <nombre imagen>:<tag>
```

