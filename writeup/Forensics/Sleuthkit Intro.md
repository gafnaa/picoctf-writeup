# Sleuthkit Intro

## Description

Download the disk image and use mmls on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag.
Note: if you are using the webshell, download and extract the disk image into /tmp not your home directory.
Download disk image
Access checker program: nc saturn.picoctf.net 64059

## Solution

First, decompress file using this command

```
$ gzip -d disk.img.gz
```

Then, use ```mmls``` on file to find the size of the linux partition

```bash
$ mmls disk.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000204799   0000202752   Linux (0x83)
```

Access checker program, then input the lenght size of Linux partition

```bash
$ nc saturn.picoctf.net 51732
What is the size of the Linux partition in the given disk image?
Length in sectors: 202752
202752
Great work!
picoCTF{mm15_f7w!}
```

## Flag
    picoCTF{mm15_f7w!}
