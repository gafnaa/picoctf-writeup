# Collaborative Development

## Description
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?
You can download the challenge files here:
challenge.zip

## Solution

Because the name of the file is "Commit.." so it will be linked with some **Git** stuffs. So, I do this commands to find the previous file before the flag has been down.

```
$ git log
commit 5e4b2dae1868abb644627483c78a683286dfe67c (HEAD -> main)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:57 2024 +0000

    init flag printer
```

Since there is only a little information available, I tried to look at the contents of the **logs/HEAD**.

```
$ cd .git
$ cd logs
$ cat HEAD

0000000000000000000000000000000000000000 5e4b2dae1868abb644627483c78a683286dfe67c picoCTF <ops@picoctf.com> 1710202077 +0000    commit (initial): init flag printer
5e4b2dae1868abb644627483c78a683286dfe67c 5e4b2dae1868abb644627483c78a683286dfe67c picoCTF <ops@picoctf.com> 1710202077 +0000    checkout: moving from main to feature/part-1
5e4b2dae1868abb644627483c78a683286dfe67c 300cff1bf1f64637dd9ff603d90176e8e8bdeb01 picoCTF <ops@picoctf.com> 1710202077 +0000    commit: add part 1
300cff1bf1f64637dd9ff603d90176e8e8bdeb01 5e4b2dae1868abb644627483c78a683286dfe67c picoCTF <ops@picoctf.com> 1710202077 +0000    checkout: moving from feature/part-1 to main
5e4b2dae1868abb644627483c78a683286dfe67c 5e4b2dae1868abb644627483c78a683286dfe67c picoCTF <ops@picoctf.com> 1710202077 +0000    checkout: moving from main to feature/part-2
5e4b2dae1868abb644627483c78a683286dfe67c 74989a4f650d024929388b6788d2b4c214a07e49 picoCTF <ops@picoctf.com> 1710202077 +0000    commit: add part 2
74989a4f650d024929388b6788d2b4c214a07e49 5e4b2dae1868abb644627483c78a683286dfe67c picoCTF <ops@picoctf.com> 1710202077 +0000    checkout: moving from feature/part-2 to main
5e4b2dae1868abb644627483c78a683286dfe67c 5e4b2dae1868abb644627483c78a683286dfe67c picoCTF <ops@picoctf.com> 1710202077 +0000    checkout: moving from main to feature/part-3
5e4b2dae1868abb644627483c78a683286dfe67c 12c2ae89d8035b7a5aa7cd169dc9e93cc68201be picoCTF <ops@picoctf.com> 1710202077 +0000    commit: add part 3
12c2ae89d8035b7a5aa7cd169dc9e93cc68201be 5e4b2dae1868abb644627483c78a683286dfe67c picoCTF <ops@picoctf.com> 1710202077 +0000    checkout: moving from feature/part-3 to main
```

After getting complete information from the log, we can do **git checkout** to see the files before editing.

```
$ git checkout 300cff1bf1f64637dd9ff603d90176e8e8bdeb01 -- flag.py

$ cat flag.py
print("Printing the flag...")
print("picoCTF{t3@mw0rk_", end='')

$ git checkout 74989a4f650d024929388b6788d2b4c214a07e49 -- flag.py

$ cat flag.py
print("Printing the flag...")

print("m@k3s_th3_dr3@m_", end='')

$ git checkout 12c2ae89d8035b7a5aa7cd169dc9e93cc68201be -- flag.py

$ cat flag.py
print("Printing the flag...")
print("w0rk_798f9981}")
```

## Flag
    picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_798f9981}

