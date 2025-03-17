# morse code

## Description
Morse code is well known. Can you decrypt this?
Download the file here.
Wrap your answer with picoCTF{}, put underscores in place of pauses, and use all lowercase.

## Solution
Because file is on .wav format, we can use some audio software, but here I use web audio morse code decoder.
https://morsecode.world/international/decoder/audio-decoder-adaptive.html

After decode, we got this string
```
WH47 H47H 90D W20U9H7
```

but, we have to put underscores in place of pauses, and use all lowercase. So, I make python program to fix it

```python
user_input = input("Enter a word: ")
user_input = user_input.lower().replace(" ", "_")
print("picoCTF{",user_input,"}",sep="")
```

## Flag
    picoCTF{wh47_h47h_90d_w20u9h7}