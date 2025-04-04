# endianness-v2

## Description

Here's a file that was recovered from a 32-bits system that organized the bytes a weird way. We're not even sure what type of file it is.
Download it here and see what you can get out of it

## Solution

After did `exiftool` I found this

```sh
$ exiftool challengefile
ExifTool Version Number         : 13.10
File Name                       : challengefile
Directory                       : .
File Size                       : 3.4 kB
File Modification Date/Time     : 2024:03:12 07:36:46+07:00
File Access Date/Time           : 2025:03:21 15:56:19+07:00
File Inode Change Date/Time     : 2025:03:21 15:56:16+07:00
File Permissions                : -rwxr-xr-x
Warning                         : Processing JPEG-like data after unknown 1-byte header
```

Then, i checked the hex code of the file and comparing it with the original jpg file.

![endian](picoCTF/assets/endian.PNG)

It is known that in the header of the file the hex code is swapped so that the file format becomes damaged. Then, we can fix it by swapping it manually but here I use `cyberchef` to help me.

![endian2](picoCTF/assets/endian2.PNG)

After that, you can save it to .jpg format, then open it to see the flag.

![flag](picoCTF/assets/flag.jpg)

## Flag
    picoCTF{cert!f1Ed_iNd!4n_sOrrY_3nDian_004850bf}