Para instalar Batcat iremos a su GitHub y entraremos en Releases para descargarnos el `bat_0.25.0_amd64.deb` y hacemos lo mismo con el Lsd

Ahora debemos ir al directorio de descargas y como usuario root
`dpkg -i bat_0.25.0_amd64.deb`
`dpkg -i lsd_1.1.5_amd64.deb`

Para quitar las **negritas** del Lsd podemos usar el siguiente comando:
`echo $LS_COLORS | sed 's/=01;/=/g'`

```
export LS_COLORS="rs=0:di=34:ln=36:mh=00:pi=40;33:so=35:do=35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=00:tw=30;42:ow=34;42:st=37;44:ex=32:*.7z=31:*.ace=31:*.alz=31:*.apk=31:*.arc=31:*.arj=31:*.bz=31:*.bz2=31:*.cab=31:*.cpio=31:*.crate=31:*.deb=31:*.drpm=31:*.dwm=31:*.dz=31:*.ear=31:*.egg=31:*.esd=31:*.gz=31:*.jar=31:*.lha=31:*.lrz=31:*.lz=31:*.lz4=31:*.lzh=31:*.lzma=31:*.lzo=31:*.pyz=31:*.rar=31:*.rpm=31:*.rz=31:*.sar=31:*.swm=31:*.t7z=31:*.tar=31:*.taz=31:*.tbz=31:*.tbz2=31:*.tgz=31:*.tlz=31:*.txz=31:*.tz=31:*.tzo=31:*.tzst=31:*.udeb=31:*.war=31:*.whl=31:*.wim=31:*.xz=31:*.z=31:*.zip=31:*.zoo=31:*.zst=31:*.avif=35:*.jpg=35:*.jpeg=35:*.mjpg=35:*.mjpeg=35:*.gif=35:*.bmp=35:*.pbm=35:*.pgm=35:*.ppm=35:*.tga=35:*.xbm=35:*.xpm=35:*.tif=35:*.tiff=35:*.png=35:*.svg=35:*.svgz=35:*.mng=35:*.pcx=35:*.mov=35:*.mpg=35:*.mpeg=35:*.m2v=35:*.mkv=35:*.webm=35:*.webp=35:*.ogm=35:*.mp4=35:*.m4v=35:*.mp4v=35:*.vob=35:*.qt=35:*.nuv=35:*.wmv=35:*.asf=35:*.rm=35:*.rmvb=35:*.flc=35:*.avi=35:*.fli=35:*.flv=35:*.gl=35:*.dl=35:*.xcf=35:*.xwd=35:*.yuv=35:*.cgm=35:*.emf=35:*.ogv=35:*.ogx=35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:*~=00;90:*#=00;90:*.bak=00;90:*.crdownload=00;90:*.dpkg-dist=00;90:*.dpkg-new=00;90:*.dpkg-old=00;90:*.dpkg-tmp=00;90:*.old=00;90:*.orig=00;90:*.part=00;90:*.rej=00;90:*.rpmnew=00;90:*.rpmorig=00;90:*.rpmsave=00;90:*.swp=00;90:*.tmp=00;90:*.ucf-dist=00;90:*.ucf-new=00;90:*.ucf-old=00;90:"
```

Lo agregamos al final del `.zshrc`
También debemos añadir el PATH del usuario normal haciendo:
`echo PATH` copiar lo que nos devuelve y pegarlo en el archivo `.zshrc` debajo de lo anterior:
`export PATH=/opt/kitty/bin:/home/kk/.local/bin:/usr/local/sbin:/usr/sbin:/sbin:/usr/local/bin:/usr/bin:/bin:/usr/local>`

Para añadir los alias para que ``bat sea cat`` y ``ls sea lsd`` añadiremos el contenido del siguiente recurso al archivo de configuración `.zshrc`
[[Custom Aliases ZSH]]

>Arreglar problema de `burpsuite`
>https://medium.com/@neat_mahogany_porcupine_191/burpsuite-no-longer-launches-after-parrot-upgrade-d1c6b17cb70d

Para arreglar el tamaño en el archivo `.zshrc` 
agregamos estas líneas:

```
# Fix th java Problem
export _JAVA_AWT_WM_NONREPARENTING=1
```

En el `bspwmrc` agregamos hasta el final: `wmname LG3D &`
Con esto quedaría arreglado cunado se lanza desde la consola pero para arreglarlo cuando se lanza desde Rofi debemos hacer lo siguiente:

Nos dirigimos a `/usr/bin` hacemos `echo $PATH` copiamos el contenido que no da, creamos el archivo `burpsuite-launcher`
le damos permisos de ejecución `chmod +x burpsuite-launcher` lo abrimos y escribimos lo siguiente:

```
#!/bin/bash

export _JAVA_AWT_WM_NONREPARENTING=1
wmname LG3D &

/usr/bin/burpsuite

```
