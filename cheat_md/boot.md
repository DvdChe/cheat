# Boot configuration ( for encrypted partition w/ bootctl )

## Bootctl configuration 

```
# /boot/loader/entries
title Arch Linux
linux /vmlinuz-linux
initrd /initramfs-linux.img
options cryptdevice=UUID=<BLKID OF DEVICE PARTITION>:rootdevice root=/dev/mapper/< VOLUME NAME > rw

```

## Kernel arguments

In `/etc/mkinitcpio.conf`, locate the `HOOKS` variable assignement and add `encrypt` and  `lvm2` arguments. It should looks like this : 
```
HOOKS=(base udev autodetect modconf block filesystems keyboard fsck encrypt lvm2)
```
