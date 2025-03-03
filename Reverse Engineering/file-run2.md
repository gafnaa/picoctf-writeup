# file-run2

## Description
Another program, but this time, it seems to want some input. What happens if you try to run it on the command line with input "Hello!"?
Download the program here.

## Solution
fter downloading the file, check the format of the file. Use this command

```bash
file run
run: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=106bb01c6a4466da1f636e31c9167e8a3d18c89a, for GNU/Linux 3.2.0, not stripped
```

so after known the format is, we can try run the program. Before that, change permission of the file first using this command

```bash
chmod +x ./run
```

after that, just run the program

    ./run Hello!

## Flag
    picoCTF{F1r57_4rgum3n7_f65ed63e}