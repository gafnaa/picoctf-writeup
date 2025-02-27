# Super SSH

## Description
Using a Secure Shell (SSH) is going to be pretty important.
Can you ssh as ctf-player to titan.picoctf.net at port 58166 to get the flag?
You'll also need the password 1ad5be0d. If asked, accept the fingerprint with yes.

If your device doesn't have a shell, you can use: https://webshell.picoctf.org
If you're not sure what a shell is, check out our Primer: https://primer.picoctf.com/#_the_shell

## Solution

Just, open terminal the type this command
```
ssh titan.picoctf.net -p 58166 -l ctf-player
```

input the password, then you will get the flag.

## Flag

    picoCTF{s3cur3_c0nn3ct10n_8306c99d}