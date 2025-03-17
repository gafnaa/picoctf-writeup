# Big Zip

## Description
Unzip this archive and find the flag.
Download zip file

## Solution
unzip the file, then go to folder inside.

```
$ unzip big-zip-files.zip
$ cd big-zip-files
```

Because there are many files and folders inside, we can use **grep** to help find the flag.

```
$ grep -r "pico"
folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}
```

## Flag
    picoCTF{gr3p_15_m4g1c_ef8790dc}