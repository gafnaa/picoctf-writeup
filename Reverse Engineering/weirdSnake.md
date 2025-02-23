# weirdSnake

## Description
I have a friend that enjoys coding and he hasn't stopped talking about a snake recently He left this file on my computer and dares me to uncover a secret phrase from it. Can you assist

## Solution
Open the available file, then get information if there is some kind of code that has been encrypted. Then separate the code.

![weirdsnake1](https://i.imgur.com/JWBQvnY.png)

Do the decryption process. Here I use cyberchef
![weirdsnake2](https://i.imgur.com/abkGjHz.png)

From this information we can do bruteforce to get the correct XOR key.
![weirdsnake3](https://i.imgur.com/BEFVoZt.png)

Get an output like this. So it can be ascertained that the correct key arrangement is ```t_Jo3```
![weirdsnake4](https://i.imgur.com/Ry6tB7I.png)
![weirdsnake5](https://i.imgur.com/WLBilwP.png)
## Flag

    picoCTF{N0t_sO_coNfus1ng_sn@ke_d6931de2}