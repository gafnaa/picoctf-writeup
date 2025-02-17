# Verify

## Description

People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the SHA-256 hash and a decrypt script to help you know that my flags are legitimate.
Additional details will be available after launching your challenge instance.

```
ssh -p 54707 ctf-player@rhea.picoctf.net
Using the password 83dcefb7. Accept the fingerprint with yes, and ls once connected to begin. Remember, in a shell, passwords are hidden!
Checksum: 467a10447deb3d4e17634cacc2a68ba6c2bb62a6637dad9145ea673bf0be5e02
To decrypt the file once you've verified the hash, run ./decrypt.sh files/<file>.
```
## Solution

First, connect ssh according to the question description, then enter the password listed.

Once connected, we do the ```ls``` command as in the question description to check the existing files/folders. We get 2 files (checksum.txt, decrypt.sh) and 1 folder (files). 

After that, use the ```sha256sum``` command to check the checksums of the files in the files folder. 

```
sha256sum files/*
```
Because there are so many files, use the ```grep``` command to get the checksum that matches the one in the question description.

```
$ sha256sum files/* | grep "467a10447deb3d4e17634cacc2a68ba6c2bb62a6637dad9145ea673bf0be5e02"
467a10447deb3d4e17634cacc2a68ba6c2bb62a6637dad9145ea673bf0be5e02  files/c6c8b911

```
After getting the matching file, decrypt it using the given program to get the flag.

```
$ ./decrypt.sh files/c6c8b911
```


## Flag
    picoCTF{trust_but_verify_c6c8b911}