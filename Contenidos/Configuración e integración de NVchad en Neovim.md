Primero ejecutamos este comando
`git clone https://github.com/NvChad/starter ~/.config/nvim`

Descargamos Neovim desde su repositorio de GitHub en Releases.

vamos a la ruta ``/opt`` como usuario root y creamos un directorio con nombre `nvim` 

Dentro del directorio que acabamos de crear ejecutamos el siguiente comando para mover lo que descargamos al directorio actual
`mv /home/kk/Descargas/nvim-linux-x86_64.tar.gz .`

Descomprimimos con `tar -xf nvim-linux-x86_64.tar.gz`

Ahora para que nvim este contemplado en el PATH simplemente lo agregamos en el archivo `.zshrc`

En la ruta `~/.config/nvim` en el archivo `init.lua`
agregamos la siguiente instrucción:
`vim.opt.listchars = "tab:»·,trail:·"`

### Implementar un tema en Rofi

Lo que haremos es ir al directorio `.config` y creamos una carpeta `rofi` y otro `themes` 

En otra terminal vamos a la rota `/opt` y clonamos el siguiente repositorio: 
`a`

en la siguiente ruta `/opt/rofi-themes-collection/themes` copiamos los temas a la carpeta que creamos en `.config` con el siguiente comando: `cp * /home/kk/.config/rofi/themes` 
ahora para poder seleccionar el tema de preferencia podemos hacer: `rofi-theme-selector`

### Instalar i3lock
podemos instalar i3lock con `sudo apt install i3lock`

Ahora en el directorio `/opt` nos clonamos el repositorio de i3lock-fancy: `git clone https://github.com/meskarune/i3lock-fancy.git` 
Dentro de la carpeta que nos crea hacemos un `sudo make install` 

Por ultimo para añadir un atajo de teclado lo hacemos en:
`.config/sxhkd/sxhkdrc`
Añadiendo al final del archivo lo siguiente:
```
#
# i3lock-fancy
#
super + shift + x
        /usr/bin/i3lock-fancy
```
