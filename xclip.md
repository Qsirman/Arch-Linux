# XCLIP

## What & Why xclip
#### I've been used to use vim for editing and viewing like everything.However,the buffer eara of vim is seperated with OS's.So it's troublesome to copy the whole contains to other places.Usually we use `cp` command to copy and paste the whole file.And we can use xclip tool as a command to copy and paste the file's contains.

## Install
```
sudo pacman -S xclip
```

## Usage
### Just copy a file's contains into terminal 
```
> xclip -i $(THE PATH OF YOUR FILE)
```
#### Then you just use `CTRL+SHIFT+V` or `SHIFT+INSERT` etc. keys to paste what you have copied.
#### ***WARNNING*** PLEASE WRITE THE WRITE PATH.IF THE FILE IS UNDER THE CURRENT PATH,PLEASE ADD `./` BEFORE IT.FOR EXAMPLE `xclip -i ./hello.c`
#### If you want,you can configure it as a conbined keys.


### Copy the file's contains into browser or other windows.
```
xclip -sel clip < file
```
