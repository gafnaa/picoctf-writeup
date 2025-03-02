# Secret of the Polyglot

## Description

The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?
Download the suspicious file here.

## Solution

Open the pdf first, and we will get the flag section. 

```
1n_pn9_&_pdf_1f991f77}
```

After that, try to check the original format of the file.

```
$ file flag2of2-final.pdf
flag2of2-final.pdf: PNG image data, 50 x 50, 8-bit/color RGBA, non-interlaced
```

We know the original format, so we just need to change the format.
```
$ mv flag2of2-final.pdf flag2of2.png
```

We got the png file that contain other part of flag. Now, just merge both of it.

## Flag
    picoCTF{f1u3n71n_pn9_&_pdf_1f991f77}


