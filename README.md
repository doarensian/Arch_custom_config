# Arch Linux own custom configs

## Requires
1. Arch Linux base group packages
1. linux kernel(ex linux-lts....)
1. systemd
1. git

## Installation
```
$ cd ~/
$ git clone https://github.com/doarensian/Arch_custom_config.git
$ cd ~/Arch_custom_config
```

## Pacman mirrorlist update configs:
```
$ cd ~/Arch_custom_config/Pacman_mirrorlist_update
$ sudo cp reflector.service /etc/systemd/system/reflector.service
$ sudo systemctl daemon-reload
$ sudo systemctl start reflector.service
```
---
**Note: For the first time, reflector.service takes a long time.**
---
```
$ sudo systemctl enable reflector.service
$ sudo cp mirrorupgrade.hook /etc/pacman.d/hooks/mirrorupgrade.hook
$ sudo mkinitcpio -p linux (linux reads as a linux-lts,linux-hardend.)
$ sudo cp reflector.timer /etc/systemd/system/reflector.timer
$ sudo systemctl daemon-reload
$ sudo systemctl start reflector.timer
```

## References
> 1. [ArchWiki:Reflector#Automation](https://wiki.archlinux.org/index.php/Reflector#Automation)
