# TouchPad(LibInput)
### Why is LibInput?
#### I didn't install any desktop environment like KDE etc.So the touchpad is really hard to use.Some people may mention syntatics,but its `wiki page says that it will not be upgrade so much.`And it't recommanded to use libinput to configure touchpad so here we are.

### Install
```
sudo pacman -S xserver-xorg-input-libinput
```

### Configuration
#### First of all,you have to find the configuration file which locates at `/usr/share/X11/xorg.conf.d/xx-libinput.conf`.xx should be a number.for example,mine is 40.if you have a different number,don't worry about that.
#### Find the line that wites something like `Indentifier "libinput touchpad catchall"` and add those lines below.
```c
//take a one-finger-tapping as a left-click
Option "Tapping" "on"
//open natural scrolling like apple devices
Option "NaturalScrolling" "true"
//define the way to click by checking the numer of fingers instead of the eara at touchpad
Option "ClickMethod" "clickfinger"
//disable touchpad while typing
Option "DisableWhileTyping" "True"
```
#### When you have done all of these,you should want to reboot to make it hanppen.
