Primeramente actualizamos el sistema con:
`sudo apt update`
`sudo apt upgrade`
Posteriormente ejecutaremos los siguientes comandos:
```
apt install build-essential git vim xcb libxcb-util0-dev libxcb-ewmh-dev libxcb-randr0-dev libxcb-icccm4-dev libxcb-keysyms1-dev libxcb-xinerama0-dev libasound2-dev libxcb-xtest0-dev libxcb-shape0-dev
```
>En mi caso cuando copie y pegue el comando en Kali me decía `Error: No se ha podido localizar el paquete xcb` así que simplemente borre esa parte del comando y seguí. 

Acto seguido, nos dirigimos a la carpeta de descargas y descargamos los proyectos **bswpm** y **sxhkd** con los siguientes comandos:
```
git clone https://github.com/baskerville/bspwm.git
git clone https://github.com/baskerville/sxhkd.git
```

Para instalarlos debemos meter ambos en directorios separados y ejecutar los comandos `make` y `sudo make install`

Ahora creamos sus dos directorios en `/.config` con el siguiente comando:
`mkdir ~/.config/{bspwm,sxhkd}`

Podemos copiar los archivos de ejemplo de la ruta `~/Descargas/bspwm/examples` a los directorios que creamos antes en `/.config` con los comandos:
```
cp bspwmrc ~/.config/bspwm/
cp sxhkdrc ~/.config/sxhkd/
```

Ahora continuamos a personalizar nuestro archivo `sxhkdrc`:
[[sxhkdrc]]

Creamos el siguiente directorio:
`mkdir scripts ~/.config/bspwm/`
y dentro del directorio creamos el siguiente archivo:
`touch bspwm_resize`
le damos permisos de ejecución:
`chmod +x bspwm_resize`
y dentro colocamos el siguiente contenido:
[[bspwm_resize]]
