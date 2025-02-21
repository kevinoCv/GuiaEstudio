Utilizaremos los dotfiles del usuario ``VaughnValle`` clonando su repositorio de GitHub
Estando en el directorio de Descargas:
`git clone https://github.com/VaughnValle/blue-sky.git`
Nos dirigimos al directorio de Polybar dentro del proyecto que nos acabamos de clonar y copiamos todo su contenido al directorio Polybar pero que se encuentra en nuestro `.config` con el siguiente comando: `cp -r * ~/.config/polybar`

Para que la Polybar siempre se inicie con bspwm y no tenerlo que iniciar manualmente podemos implementar el siguiente comando:
``echo '~/.config/polybar/./launch.sh &' >> ~/.config/bspwm/bspwmrc``
>en mi caso como tengo los archivos `bspwmrc` y `sxhkdrc` finales no es necesario hacer este ultimo paso.

Por ultimo para que la Polybar funcione correctamente debemos copiar las fonts del proyecto que nos clonamos en el directorio fonts nuestro así que como usuario root lo hacemos con el siguiente comando:
`cp fonts/* /usr/share/fonts/truetype`
`fc-cache -v`
