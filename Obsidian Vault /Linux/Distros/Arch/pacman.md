# PACMAN
###### Make pacman great Again

### update Arch

```
sudo pacman -Syyu
```


### install packages
```
sudo pacman -S pacman-contrib reflector
```


### rank mirrors and update them to mirror list
```
reflector -a 10 -c in -f 5 --sort rate --save /etc/pacman.d/mirrorlist
```


### install rsync if you get errors related to rsync
```
sudo pacman -S rsync
```
