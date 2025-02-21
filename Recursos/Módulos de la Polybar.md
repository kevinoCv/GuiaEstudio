`.launch.sh`
```
#!/usr/bin/env sh

## Add this to your wm startup file.

# Terminate already running bar instances
killall -q polybar

## Wait until the processes have been shut down
while pgrep -u $UID -x polybar >/dev/null; do sleep 1; done

## Launch

## Left bar
polybar log -c ~/.config/polybar/current.ini &
polybar ethernet_bar -c ~/.config/polybar/current.ini &
polybar vpn_bar -c ~/.config/polybar/current.ini &

## Right bar
# polybar top -c ~/.config/polybar/current.ini &
polybar target_to_hack -c ~/.config/polybar/current.ini &
polybar primary -c ~/.config/polybar/current.ini &

## Center bar
polybar primary -c ~/.config/polybar/workspace.ini &
```

---

Módulos agregados en `current.ini`
```
##########################

[bar/ethernet_bar]
inherit = bar/main
width = 10%
height = 40
offset-x = 3.8%
offset-y = 15  
background = ${color.bg}
foreground = ${color.white}
bottom = false
padding = 1
;padding-top = 2
module-margin-left = 0
module-margin-right = 0
;modules-left = date sep mpd
modules-center = ethernet_status
wm-restack = bspwm

[bar/vpn_bar]
inherit = bar/main
width = 10%
height = 40
offset-x = 14.1%
offset-y = 15
background = ${color.bg} 
foreground = ${color.white}
bottom = false
padding = 1  
;padding-top = 2
module-margin-left = 0
module-margin-right = 0
;modules-left = date sep mpd
modules-center = vpn_status
wm-restack = bspwm

[bar/target_to_hack]
inherit = bar/main
width = 15%
height = 40
offset-x = 81.5%
offset-y = 15  
background = ${color.bg}
foreground = ${color.white}
bottom = false
padding = 1
;padding-top = 2
module-margin-left = 0
module-margin-right = 0
;modules-left = date sep mpd
modules-center = victim_to_hack
wm-restack = bspwm

##########################
##########################

[module/ethernet_status]
type = custom/script
interval = 2
exec = ~/.config/bspwm/scripts/ethernet_status.sh

[module/vpn_status]
type = custom/script
interval = 2 
exec = ~/.config/bspwm/scripts/vpn_status.sh

[module/victim_to_hack]
type = custom/script
interval = 2
exec = ~/.config/bspwm/scripts/victim_to_hack.sh

##########################
```
