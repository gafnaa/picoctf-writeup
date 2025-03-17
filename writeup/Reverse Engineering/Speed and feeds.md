# Speed and feeds

## Description

There is something on my shop network running at nc mercury.picoctf.net 16524, but I can't tell what it is. Can you?

Hint : What language does a CNC machine use?

## Solution

After running program, I got this

```
$ nc mercury.picoctf.net 16524
G17 G21 G40 G90 G64 P0.003 F50
G0Z0.1
G0Z0.1
G0X0.8276Y3.8621
G1Z0.1
G1X0.8276Y-1.9310
G0Z0.1
G0X1.1034Y3.8621
G1Z0.1
G1X1.1034Y-1.9310
G0Z0.1
G0X1.1034Y3.0345
G1Z0.1
G1X1.6552Y3.5862
G1X2.2069Y3.8621
G1X2.7586Y3.8621
G1X3.5862Y3.5862
G1X4.1379Y3.0345
G1X4.4138Y2.2069
G1X4.4138Y1.6552
G1X4.1379Y0.8276
G1X3.5862Y0.2759
G1X2.7586Y0.0000
G1X2.2069Y0.0000
G1X1.6552Y0.2759
G1X1.1034Y0.8276
G0Z0.1
G0X2.7586Y3.8621
G1Z0.1
G1X3.3103Y3.5862
G1X3.8621Y3.0345
G1X4.1379Y2.2069
G1X4.1379Y1.6552
G1X3.8621Y0.8276
G1X3.3103Y0.2759
G1X2.7586Y0.0000
...
```

If you look at the hint given, it seems like the output is a g-code. Then, decode it to get the hint, here I use the web to help.
https://ncviewer.com/

And it turns out that it immediately succeeded in getting the flag

![spped-feeds](https://i.imgur.com/C4kKTV0.png)

## Flag

    picoCTF{num3r1cal_c0ntr0l_1395ffad}