# Sleuthkit Apprentice

## Description


## Solution

I'm too lazy to explain, the point is these are the steps to solve it

```
$ gzip -d disk.flag.img.gz

┌──(gafnaa㉿WIN-VQ99FOIVV68)-[/tmp/sleuthkit-appr]
└─$ ls
disk.flag.img

┌──(gafnaa㉿WIN-VQ99FOIVV68)-[/tmp/sleuthkit-appr]
└─$ mmls disk.flag.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000360447   0000153600   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000360448   0000614399   0000253952   Linux (0x83)

┌──(gafnaa㉿WIN-VQ99FOIVV68)-[/tmp/sleuthkit-appr]
└─$ fls -o 2048 disk.flag.img
d/d 11: lost+found
r/r 12: ldlinux.sys
r/r 13: ldlinux.c32
r/r 15: config-virt
r/r 16: vmlinuz-virt
r/r 17: initramfs-virt
l/l 18: boot
r/r 20: libutil.c32
r/r 19: extlinux.conf
r/r 21: libcom32.c32
r/r 22: mboot.c32
r/r 23: menu.c32
r/r 14: System.map-virt
r/r 24: vesamenu.c32
V/V 25585:      $OrphanFiles

┌──(gafnaa㉿WIN-VQ99FOIVV68)-[/tmp/sleuthkit-appr]
└─$ mmls -o 360448 disk.flag.img

┌──(gafnaa㉿WIN-VQ99FOIVV68)-[/tmp/sleuthkit-appr]
└─$ fls -o 360448 disk.flag.img
d/d 451:        home
d/d 11: lost+found
d/d 12: boot
d/d 1985:       etc
d/d 1986:       proc
d/d 1987:       dev
d/d 1988:       tmp
d/d 1989:       lib
d/d 1990:       var
d/d 3969:       usr
d/d 3970:       bin
d/d 1991:       sbin
d/d 1992:       media
d/d 1993:       mnt
d/d 1994:       opt
d/d 1995:       root
d/d 1996:       run
d/d 1997:       srv
d/d 1998:       sys
d/d 2358:       swap
V/V 31745:      $OrphanFiles

┌──(gafnaa㉿WIN-VQ99FOIVV68)-[/tmp/sleuthkit-appr]
└─$ fls -o 360448 disk.flag.img 1995
r/r 2363:       .ash_history
d/d 3981:       my_folder

┌──(gafnaa㉿WIN-VQ99FOIVV68)-[/tmp/sleuthkit-appr]
└─$ fls -o 360448 disk.flag.img 3981
r/r * 2082(realloc):    flag.txt
r/r 2371:       flag.uni.txt

┌──(gafnaa㉿WIN-VQ99FOIVV68)-[/tmp/sleuthkit-appr]
└─$ icat disk.flag.img -o 360448 2371 > flag.uni.txt

┌──(gafnaa㉿WIN-VQ99FOIVV68)-[/tmp/sleuthkit-appr]
└─$ ls
disk.flag.img  flag.uni.txt

┌──(gafnaa㉿WIN-VQ99FOIVV68)-[/tmp/sleuthkit-appr]
└─$ cat flag.uni.txt
picoCTF{by73_5urf3r_3497ae6b}
```

## Flag
    picoCTF{by73_5urf3r_3497ae6b}