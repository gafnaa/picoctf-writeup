# WPA-ing Out

## Description
I thought that my password was super-secret, but it turns out that passwords passed over the AIR can be CRACKED, especially if I used the same wireless network password as one in the rockyou.txt credential dump.
Use this 'pcap file' and the rockyou wordlist. The flag should be entered in the picoCTF{XXXXXX} format.

## Solution

I use **aircrack-ng** to solve it.

```
$ aircrack-ng wpa-ing_out.pcap -w /usr/share/wordlists/rockyou.txt
```

![wpa-ing](https://i.imgur.com/R5fN7tz.jpeg)

## Flag

    picoCTF{mickeymouse}