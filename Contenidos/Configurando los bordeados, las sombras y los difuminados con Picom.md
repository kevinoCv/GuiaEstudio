Comenzamos creando el directorio de Picom en `~/.config/` con `mkdir` 

Ya dentro de la nueva carpeta de Picom creamos un archivo llamado `picom.conf` y dentro pegamos todo el contenido de este recurso:
[[picom.conf]] 

Para que Picom comience a ejecutarse debemos añadirlo en el archivo de `bspwmrc` y posteriormente recargar bspwm con:

	super + shift + r

>en mi caso al recargar bspwm me apareció un mensaje de alerta de Picom y para solucionarlo tuve que cerrar sesión y entrar con otro WM para modificar el archivo de configuración de Picom.
>la lineal que modifique para arreglar fue la siguiente:
>antes: `backend = "glx";`
>después: `backend = "xrender"`
>y también tuve que comentar esta lineal: `refresh-rate = 0`

Para ajustar o personalizar el Picom se hace desde `picom.conf` ya eso depende del gusto del usuario solo para quitar el borde que hay en las ventanas se debe de hacer desde el archivo ``bspwmrc`` con la siguiente lineal de código:
`bspc config border_width 0`
