# Commitment Issues

## Description

I accidentally wrote the flag down. Good thing I deleted it!
You download the challenge files here:
[challenge.zip](https://artifacts.picoctf.net/c_titan/137/challenge.zip)

## Solution
Because the name of the file is "Commit.." so it will be linked with some **Git** stuffs. So, I do this commands to find the previous file before the flag has been down.


```
$ git logs
commit ef0b7cc6b98367fa168573c931e0f7098ef59182 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:20 2024 +0000

    remove sensitive info

commit ea859bf3b5d94ee74ce5ee1afa3edd7d4d6b35f0
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:20 2024 +0000

    create flag
```
we get the email info, username info, and information that user been removed something on commit "ef0b7cc6b98367fa168573c931e0f7098ef59182"

after that, do **git commit**

```
git config --global user.email "ops@picoctf.com"
git config --global user.name "picoCTF"
```

Finally, do **git checkout** to see the previous content of the file.

```
git checkout ea859bf3b5d94ee74ce5ee1afa3edd7d4d6b35f0 -- message.txt
cat message.txt
```

## Flag
    picoCTF{s@n1t1z3_cf09a485}