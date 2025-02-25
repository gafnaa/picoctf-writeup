# file-run1

## Description

A program has been provided to you, what happens if you try to run it on the command line?
Download the program here.


## Solution
After downloading the file, check the format of the file. Use this command

```
file run
run: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=6e8c618e35e1676dcfc1528b849d349e82f127f1, for GNU/Linux 3.2.0, not stripped
```

so after known the format is, we can try run the program. Before that, change permission of the file first using this command

```
chmod +x ./run
```

after that, just run the program

    ./run

## Flag
    picoCTF{U51N6_Y0Ur_F1r57_F113_9bc52b6b}