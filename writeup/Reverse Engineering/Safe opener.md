# Safe opener

## Description
Can you open this safe?
I forgot the key to my safe but this program is supposed to help me with retrieving the lost key. Can you help me unlock my safe?
Put the password you recover into the picoCTF flag format like:
picoCTF{password}

## Solution
After downloading the file, we can check the content of the file. There is password that've been encrypted using **base64**. We can decrypt those and run the program.

```
echo "cGwzYXMzX2wzdF9tM18xbnQwX3RoM19zYWYz" | base64 --decode
```

Because the file format that given is a java, we can run the file using this command

```
java SafeOpener.java
```

## Flag

    picoCTF{pl3as3_l3t_m3_1nt0_th3_saf3}
