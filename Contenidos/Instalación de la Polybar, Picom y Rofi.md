### Instalar Polybar
`sudo apt install polybar`

### Instalar Picom desde los repositorios de GitHub
Primero instalamos las dependencias: 
`sudo apt install libconfig-dev libdbus-1-dev libegl-dev libev-dev libgl-dev libepoxy-dev libpcre2-dev libpixman-1-dev libx11-xcb-dev libxcb1-dev libxcb-composite0-dev libxcb-damage0-dev libxcb-glx0-dev libxcb-image0-dev libxcb-present-dev libxcb-randr0-dev libxcb-render0-dev libxcb-render-util0-dev libxcb-shape0-dev libxcb-util-dev libxcb-xfixes0-dev meson ninja-build uthash-dev`

Ahora vamos al directorio de Descargas y nos clonamos el repositorio d Picom:
`git clone https://github.com/yshui/picom`

Dentro del directorio que nos clonamos hacemos lo siguiente:
`meson setup --buildtype=release build`
>si al ejecutar el comando anterior aparece este error: 
>`ERROR: Unable to find CMake` simplemente es porque no tenemos instalado cmake así que lo instalamos con apt y listo.

`ninja -C build`

Para por fin instalarlo solo escribimos el siguiente comando:
`ninja -C build install`

### Instalar Rofi
`sudo apt install rofi`

Procedemos a reiniciar la Pc para entrar en bspwm

>en Kali Linux al reiniciar no me aparecía la opción de bspwm
>Para solucionarlo solo instale bspwm con `sudo apt install bspwm`
