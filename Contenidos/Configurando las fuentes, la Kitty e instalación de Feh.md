Descargamos las Hack Nerd Font (o las de preferencia) de la pagina nerdfonts.com
![[Pasted image 20250127011142.png]]

Estando en la ruta `/usr/local/share/fonts` usamos el siguiente comando para mover el comprimido que descargamos a la ruta actual:
`mv /home/kk/Descargas/Hack.zip .`
Descomprimimos: `7z x Hack.zip ` y borramos los archivos residuales: `rm Hack.zip LICENSE.md README.md`

Instalamos zsh: `sudo apt install zsh`
>en Kali ya viene instalada por defecto

### Actualizar Kitty
Si no la teníamos instalada previamente: `sudo apt install kitty`

Vamos al repositorio GitHub de Kitty damos clic en `Releases` y descargamos: `Linux amd64 binary bundle`

Nos dirigimos a la ruta `/opt` como root y removemos la Kitty con el comando: `apt remove kitty` para posteriormente mover el comprimido que previamente habíamos descargado:
`mv /home/kk/Descargas/kitty-0.39.0-x86_64.txz .`

Descomprimimos con: `7z x kitty-0.39.0-x86_64.txz` y borramos el comprimido: `rm kitty-0.39.0-x86_64.txz `

creamos un nuevo directorio `mkdir kitty` y movemos el comprimido al directorio que acabamos de crear: `mv kitty-0.39.0-x86_64.tar kitty`
 ahora dentro del directorio kitty `tar -xf kitty-0.39.0-x86_64.tar` y borramos el comprimido 
 Para finalizar con la parte de actualización comprobamos que la versión de kitty sea la ultima con:
 `./kitty --version`

### Personalizar kitty
Copiamos el contendió del siguiente recurso: 
[[kitty.conf]] 
Creamos el archivo `kitty.conf` en la ruta `~/.config/kitty` y pegamos.

Hacemos lo mismo para este recurso: 
[[color.ini]]
Creamos el archivo `color.ini` en la ruta `~/.config/kitty` y pegamos.

Como root ir a la ruta: `/root/.config/kitty` y copiar todas las configuraciones del usuario normal al root con el siguiente comando:
`cp /home/kk/.config/kitty/* .`

### Instalar feh
`sudo apt install feh`
[Wallpapers de Lain](https://wallpaperaccess.com/serial-experiments-lain)
