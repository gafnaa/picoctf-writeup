# Reverse

## Description
Try reversing this file? Can ya?
I forgot the password to this file. Please find it for me?

## Solution
After downloading the file, and checking the file format, it is known that the file format is **ELF**. We can try ```strings``` and ```grep``` command to obtaining information.

```
strings ret | grep "pico"
picoCTF{H
Password correct, please see flag: picoCTF{3lf_r3v3r5ing_succe55ful_d7b14d43}
```


## Flag
    picoCTF{3lf_r3v3r5ing_succe55ful_d7b14d43}