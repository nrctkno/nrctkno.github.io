---
layout: post
title: Mover imágenes WSL a otro volumen
categories: [Tutoriales]
---

Hace unos días tomé finalmente la decisión de mover las imágenes VHDX de WSL a otro volumen. Quienes lo usamos sabemos que dichas imágenes de crean por defecto en el volumen primario (usualmente c:/). Estas imágenes suelen crecer a un ritmo vertiginoso y corremos el riesgo de quedamos sin espacio en nuestra partición primaria. En una publicación anterior y para salir del paso, intenté [reducir el tamaño de dichas imágenes](https://nicolascastrodev.blogspot.com/2021/10/reducir-tamano-de-un-disco-virtual-wsl.html). Esta, sin embargo, fue una medida paleativa.

<!--more-->

Disponer de nuestras imágenes de WSL en otro volumen trae como beneficio adicional una mayor tolerancia a problemas con nuestra unidad principal, permitiéndonos reinstalar el sistema operativo sin perder dichas imágenes y todo el trabajo que tengamos en ellas. Mejor aún, en el caso de que dicho volumen pertenezca a un disco físico diferente, tendremos ventajas adicionales como un menor número de cuellos de botella en la unidad principal e incluso la posibilidad de mover dicho disco a otra máquina y montar nuestras imágenes en ella.

El procedimiento resultó más simple de lo que creía.

## 1. Apagar docker desktop

Haz click derecho sobre el ícono de docker desktop en el área de notificaciones y elige la opción para cerrarlo.

## 2. Obtener el listado de imágenes

```shell
wsl --list --all
```

Obtendremos una salida similar a la siguiente:

```shell
  NAME                   STATE           VERSION
* Ubuntu-20.04           Running         2
  docker-desktop         Stopped         2
  docker-desktop-data    Stopped         2
```

## 3. Exportar cada imagen

Este proceso demorará desde unos segundos hasta varios minutos dependiendo del tamaño de cada imagen. Por comodidad, en primer lugar nos posicionamos en el volumen de destino, y en la carpeta en la cual queremos volcar las copias de seguridad.

```shell
d:
cd wsl/
wsl --export Ubuntu-20.04 ubuntu_20_04.tar
wsl --export docker-desktop docker-desktop.tar
wsl --export docker-desktop-data docker-desktop-data.tar
```

## 4. Eliminar las imágenes existentes

Este paso es necesario para evitar colisiones de nombre al momento de importarlas (en el siguiente paso). Sin embargo nada nos impediría importar/registrar las mismas imágenes bajo un nombre diferente. Para el caso de uso presentado en este artículo - liberar el espacio en mi unidad primaria y dejar todo tal cual estaba pero en un volumen diferente -, este paso es necesario.

```shell
wsl --unregister Ubuntu-20.04
    Eliminando del registro...
    
wsl --unregister docker-desktop
    Eliminando del registro...
    
wsl --unregister docker-desktop-data
    Eliminando del registro...

Verificamos que ya no existan registros:

wsl -l
    El subsistema de Windows para Linux no tiene distribuciones instaladas.
    Para instalar las distribuciones, se puede visitar Microsoft Store:
    https://aka.ms/wslstore
```

A este altura ya podremos notar que hemos liberado el espacio en nuestro volumen.

## 5. Importar/registrar las imágenes exportadas

Llegó el momento de importar las imágenes. En este caso los argumentos que indicamos son a. el nombre de la imagen, b. el directorio de destino y c. la copia de seguridad desde la cual realizaremos la importación. La carpeta de destino que he elegido es la misma en la que he volcado las copias de seguridad, pero bien podría ser cualquier otro.

```shell
wsl --import Ubuntu-20.04 D:\wsl\Ubuntu-20.04 ubuntu_20_04.tar
wsl --import docker-desktop D:\wsl\docker-desktop docker-desktop.tar
wsl --import docker-desktop-data D:\wsl\docker-desktop-data docker-desktop-data.tar
```

## 6. Configurar usuario por defecto en las instalaciones de Linux

Luego de montar una imagen de linux, la misma se iniciará por defecto con el usuario root. Si bien no es un gran problema, esto nos puede generar inconvenientes relacionados con permisos en un futuro. Por lo anterior y manteniendo la premisa de dejar todo tal y como estaba, ejecutamos desde Windows el comando específico para configurarlo dentro de dicha imagen:

```shell
ubuntu2004.exe config --default-user miusuariolinux
```

Si no recuerdas tu usuario, una forma fácil de obtenerlo es ejecutar `ls /home`.