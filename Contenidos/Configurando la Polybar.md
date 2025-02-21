En el archivo `~/.config/polybar/.launch.sh` podemos definir que barras queremos que se muestren y si queremos quitar algunas que ya vienen preestablecidas simplemente las comentamos

En el archivo `~/.config/polybar/current.ini` podemos personalizar los módulos de la Polybar 

[[Módulos de la Polybar]]

En la ruta `.config/bspwm/scripts` creamos el archivo `ethernet_status.sh` con `touch` y le damos permisos de ejecución

dentro colocamos este script:

```
#!/bin/sh

echo "%{F#2495e7}ICONO %{F#ffffff}$(/usr/sbin/ifconfig ens33 | grep "inet " | awk '{print $2}')%{u-}"
```

Y podemos hacer los mismos pasos para el modulo de `vpn_status.sh` pero con el siguiente script:

```
#!/bin/sh

IFACE=$(/usr/sbin/ifconfig | grep tun0 | awk '{print $1}' | tr -d ':')

if [ "$IFACE" = "tun0" ]; then
    echo "%{F#1bbf3e}ICONO %{F#ffffff}$(/usr/sbin/ifconfig tun0 | grep "inet " | awk '{print $2}')%{u-}"
else
    echo "%{F#1bbf3e}ICONO %{u-} Disconnected"
fi
```
