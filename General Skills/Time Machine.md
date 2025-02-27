# Time Machine

## Description

What was I last working on? I remember writing a note to help me remember...
You can download the challenge files here:
[challenge.zip](https://artifacts.picoctf.net/c_titan/160/challenge.zip)

## Solution

after looking inside the zip, there is a file, namely **message.txt** which says

```
This is what I was working on, but I'd need to look at my commit history to know why...
```

from there we get information that we have to look for clues when the file was committed, namely by opening the ```.git/logs``` folder. In it there is a **HEAD** file and after the file is opened there is a flag

## Flag
    picoCTF{t1m3m@ch1n3_186cd7d7}