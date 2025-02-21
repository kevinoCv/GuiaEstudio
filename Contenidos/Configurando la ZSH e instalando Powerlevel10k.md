En mi caso al estar usando Kali Linux esta distribución ya viene incluida la zsh y varios plugin que se instalan manualmente en la guía original pero dejo el comando de instalación:

```
sudo apt install zsh-autocomplete zsh-autosuggestions zsh-syntax-highlighting
```

ejecutamos el siguiente comando para clonarnos el repositorio de Powerlevel10k:

```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/powerlevel10k
echo 'source ~/powerlevel10k/powerlevel10k.zsh-theme' >>~/.zshrc
```

y posteriormente para configurar el tema:

```
cd
zsh
```

Todo lo anterior lo hicimos para el usuario normal pero para también tener la Powerlevel10k como root debemos hacer todos los pasos exactamente igual pero como usuario root

Podemos personalizar lo que se muestra en el archivo de Powerlevel10k
- Para el usuario normal: en la guía original comenta todo el contenido que aparezca a la derecha en el archivo `.p10k.zsh`
- Para el usuario root: en `/root` podemos configurar `.p10k.zsh` de la misma forma que el usuario normal

>Al volverme usuario root `sudo su` me aparecía el mensaje: `[WARNING]: Console output during zsh initialization detected.`
>para solucionarlo seguí el consejo de este usuario:

```
También me aparecía el mismo error, en la consola escribe echo $POWERLEVEL9K_INSTANT_PROMPT si te da como resultado la palabra verbose debes ingresar al archivo de configuración .p10k.zsh y al final añadir typeset -g POWERLEVEL9K_INSTANT_PROMPT=quiet guardas y reinicias la consola. Para probar que quedo correcto vuelve a ejecutar echo $POWERLEVEL9K_INSTANT_PROMPT te debe dar como resultado la palabra quiet.
```

---

Ahora haremos que tanto el usuario normal y el root utilicen la misma configuración de zsh.

Como root creamos un link simbólico al ``.zshrc`` del usuario normal

```
ln -s -f /home/kk/.zshrc .zshrc
```

Este comando es para reasignar permisos: `chown root:root /usr/local/share/zsh/site-functions/_bspc`

Este comando es para que en la consola se muestre un autocompletado: `source /usr/share/zsh-autosuggestions/zsh-autosuggestions.zsh`

Para no tener que hacerlo manualmente siempre es mejor modificar el `.zshrc` agregando las siguientes líneas:

```
# ZSH AutoSuggestions Plugin
if [ -f /usr/share/zsh-autosuggestions/zsh-autosuggestions.zsh ]; then
        source /usr/share/zsh-autosuggestions/zsh-autosuggestions.zsh
fi
```

```
# ZSH Syntax Highlighting
if [ -f /usr/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh ]; then
        source /usr/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
fi
```

```
# ZSH Sudo Plugin
if [ -f /usr/share/zsh-sudo/sudo.plugin.zsh ]; then
        source /usr/share/zsh-sudo/sudo.plugin.zsh
fi
```

>En resumen para instalar cualquier plugin en zsh se usa la misma estructura. 

Para tener un historial de comandos en la zsh añadiremos estas líneas justo debajo de los plugin anteriores:

```
# History
HISTFILE=~/.zsh_history
HISTSIZE=10000
SAVEHIST=10000
setopt histignorealldups sharehistory
```

Por ultimo podemos copiar y pegar todo este sistema de autocompletado inteligente que autocompleta el comando en caso de que falte una letra:
[[Modern Completion System]]
