`victim_to_hack.sh`

```
#!/bin/bash

ip_address=$(/bin/cat /home/s4vitar/.config/bin/target | awk '{print $1}')
machine_name=$(/bin/cat /home/s4vitar/.config/bin/target | awk '{print $2}')

if [ $ip_address ] && [ $machine_name ]; then
    echo "%{F#e51d0b}ICONO %{F#ffffff}$ip_address%{u-} - $machine_name"
else
    echo "%{F#e51d0b}ICONO %{u-}%{F#ffffff} No target"
fi
```

funciones que van dentro del `.zshrc`

```
# Custom functions
function settarget(){
    ip_address=$1
    machine_name=$2
    echo "$ip_address $machine_name" > /home/s4vitar/.config/bin/target
}

function cleartarget(){
    echo '' > /home/s4vitar/.config/bin/target
}
```

---

Instalar `fzf`
Vamos a su repositorio de GitHub https://github.com/junegunn/fzf
ejecutamos el siguiente comando  tanto en el usuario normal como el usuario root:
```
cd

git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf
~/.fzf/install
```
