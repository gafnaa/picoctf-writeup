# Glitch Cat

## Description
Our flag printing service has started glitching!
$ nc saturn.picoctf.net 55000

## Solution
Run the command, and you will get the flag, but some part has been encoded to hexadecimal. So, just decode it to ASCII and you will get the real flag.

```
$ nc saturn.picoctf.net 64764
'picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}'
```

## Flag
    picoCTF{gl17ch_m3_n07_a4392d2e}