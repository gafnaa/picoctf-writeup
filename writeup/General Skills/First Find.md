# First Find

## Description
Unzip this archive and find the file named 'uber-secret.txt'
Download zip file

## Solution
unzip the file, then go to folder inside.

```
$ unzip files.zip
$ cd files
```

From description we have to find a file 'uber-secret.txt.Then, I using **find** command to help.

```
$ find -type f -name "uber-secret.txt"
./adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
```
After we found the file, then just open it and get the flag.

```
$ cat adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
picoCTF{f1nd_15_f457_ab443fd1}
```

## Flag
    picoCTF{f1nd_15_f457_ab443fd1}