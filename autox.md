# AUTOX 

## WHY 
#### I don't want to use the heavy desktop environment so I want to only use `xorg` service and a WM(window manager),which I choose [awesome](https://github.com/Qsirman/Arch-Linux/blob/master/awesome.md),to manager my windows.

## PROBLEMS
* How to auto-start xorg after I log in in a command line instead of humanly type `startx`?
* How to auto-start the WM after I start my xorg service?
* When I change my default shell,the reginal configuration doesn't work any more?!

## TUTORIAL
### LOG-IN AUTO-START
#### If you want to auto-start some service or software in bash,you just need to modify the file `.bash_profile` like below. 

```
# ~/.bash_profile
[[ -f ~/.bashrc ]] && . ~/.bashrc && exec startx 
if[ -z "$DISPLAY" ] && [ -n "$XDG_VTNR" ] && [ "$XDG_VTNR" -eq 1] then
# YOU CAN ADD ANY SERVICE YOU WANT!
# LIKE NOW I'M GOING TO ADD THE STARTX HERE
exec startx
fi
```
#### However,if you are not using the bash as your default shell,you have got to modify the another file.Take `ZSH` as an example,You have to modify the file named `zprofile`,whose address is  `/etc/zsh/zprofile`.And the modifying way is similar.

### STARTX AUTO-START
#### Since we have set to auto-start startx,then we just auto-start our WM,awesome,while the xorg service is beginning.
#### We also need to modify a file named `.xinitrc`,which locates under your user's home directory.
```
vim ~/.xinitrc
```
#### And you just add a line writes `exec awesome` then BINGO!
```
#!/bin/zsh

userresources=$HOME/.Xresources
usermodmap=$HOME/.Xmodmap
sysresources=/etc/X11/xinit/.Xresources
sysmodmap=/etc/X11/xinit/.Xmodmap

# merge in defaults and keymaps

if [ -f $sysresources ]; then
    xrdb -merge $sysresources
fi

if [ -f $sysmodmap ]; then
    xmodmap $sysmodmap
fi

if [ -f "$userresources" ]; then
    xrdb -merge "$userresources"
fi

if [ -f "$usermodmap" ]; then
    xmodmap "$usermodmap"
fi

# start some nice programs

if [ -d /etc/X11/xinit/xinitrc.d ] ; then
 for f in /etc/X11/xinit/xinitrc.d/?*.sh ; do
  [ -x "$f" ] && . "$f"
 done
 unset f
fi
# JUST ADD WAHT YOU WANT TO AUTO-START
exec awesome
```
