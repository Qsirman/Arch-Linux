# URXVT(unicode ouR eXterned Virtual Terminal)

## Warnnings
#### I've been using gnome-terminal for like a life and always use `CTRL+SHIFT+C` to copy and use `CTRL+SHIFT+V` to paste.
#### However,in rxvt-unicode,we paste with `SHIFT+INSERT` 

## Display Configurations
#### We configure rxvt's display by modifying `.Xresources` file,which commonly was palced under the user's home directory.
#### So open the configuration file and add the following lines like I do.Of course,if you don't have that file,don't be panic.Just create a new file.
```c
! urxvt color set
URxvt.background:black
URxvt.foreground:green
URxvt.colorBD:yellow
URxvt.colorUL:Green
URxvt.color0: #000000
URxvt.color1: #CC0000
URxvt.color2: #4E9A06
URxvt.color3: #C4A000
URxvt.color4: #3465A4
URxvt.color5: #75507B
URxvt.color6: #06989A
URxvt.color7: #D3D7CF
URxvt.color8: #555753
URxvt.color9: #EF2929
URxvt.color10: #8AE234
URxvt.color11: #FCE94F
URxvt.color12: #729FCF
URxvt.color13: #AD7FA8
URxvt.color14: #34E2E2
URxvt.color15: #EEEEEC
URxvt.scrollBar:false
URxvt.saveLines:5000
URxvt.font:xft:Liberation Mono:pixelsize=16:antialias=false,xft:Microsoft Yahei:pixelsize=16
URxvt.boldFont:xft:Liberation Mono:pixelsize=16:antialias=false:Bold,xft:Microsoft Yahei:pixelsize=16:Bold
URxvt.geometry: 80x30
URxvt.title:Rxvt-Unicode
!make background into transparent
URxvt.inheritPixmap:true
```
