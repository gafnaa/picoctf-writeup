# interencdec

## Description

Can you get the real meaning from this file.
Download the file [here](https://artifacts.picoctf.net/c_titan/108/enc_flag).

## Solution

After the file is downloaded, it will contain the following contents: 
``` 
YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgyZzBOMm8yYXpZNWZRPT0nCg==
```

If you look closely, it seems like the flag has been encrypted using base64. Then, we try to decode it. 
```
echo "YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgyZzBOMm8yYXpZNWZRPT0nCg==" | base64 --decode
```
And we got this result:
```
b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2g0N2o2azY5fQ=='
```
It seems to be encrypted again using base64, we decode it again, but remove the characters that are not found.
```
echo "d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2g0N2o2azY5fQ==" | base64 --decode
```
And we got this result:
```
wpjvJAM{jhlzhy_k3jy9wa3k_h47j6k69}
```
Judging from the encryption format pattern, it seems like the flag is encrypted using ROT, here I use a web [multidecoder](https://www.cachesleuth.com/multidecoder/) to help decode it.

[![interencdec-1.png](https://i.postimg.cc/KvcqY2fC/interencdec-1.png)](https://postimg.cc/WtK69xQ7)

## Flag

    picoCTF{caesar_d3cr9pt3d_a47c6d69}
