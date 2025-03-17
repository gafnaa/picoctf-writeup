# repetitions

## Description

Can you make sense of this file?
Download the file here.

## Solution

Do **cat** to view the content of file. It seems the flag has been encode using base64. Then, decode it

```
$ cat enc_flag
YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgyZzBOMm8yYXpZNWZRPT0nCg==

$ cat enc_flag | base64 --decode
b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2g0N2o2azY5fQ=='

$ echo "d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2g0N2o2azY5fQ==" | base64 --decode
wpjvJAM{jhlzhy_k3jy9wa3k_h47j6k69}
```
We get the flag, but again it's already encoded using some ROT method. So, I use website to help me solve it.
https://www.cachesleuth.com/multidecoder/

## Flag
    picoCTF{caesar_d3cr9pt3d_a47c6d69}