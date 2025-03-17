# Packer

## Description
Reverse this linux executable? [Binary](https://artifacts.picoctf.net/c_titan/21/out)
Hint : What can we do to reduce the size of a binary after compiling it.


## Solution

First, download the available file, and check the original extension of the file. Then, do the command "strings" to check if there are any instructions in it. It turns out that the information was found. 

![packer1](https://i.imgur.com/ShZ7gnC.png)
![packer2](https://i.imgur.com/ozzzRMt.png)

It is known that the file is packed using a program called UPX. Then, from that information we try to unpack using that program too.

After that, run the “file” command again to see if there are any changes to the file extension information. Then, run the “strings” and “grep” commands again to get information related to the flag.

![packer3](https://i.imgur.com/t7wczou.png)

From this information, it seems that the flag has been encrypted, so we have to decrypt it to get the original flag. Here, I use the following website to do this process: https://www.cachesleuth.com/multidecoder/

## Flag

    picoCTF{U9X_UnP4ck1N6_B1n4Ri3S_371aa9ff}