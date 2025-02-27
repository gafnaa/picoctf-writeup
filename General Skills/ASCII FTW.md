# ASCII FTW

## Description
This program has constructed the flag using hex ascii values. Identify the flag text by disassembling the program.
You can download the file from here.

## Solution
I use IDA to help me find the flag.

```
; __unwind {
endbr64
push    rbp
mov     rbp, rsp
sub     rsp, 30h
mov     rax, fs:28h
mov     [rbp+var_8], rax
xor     eax, eax
mov     [rbp+var_30], 70h ; 'p'
mov     [rbp+var_2F], 69h ; 'i'
mov     [rbp+var_2E], 63h ; 'c'
mov     [rbp+var_2D], 6Fh ; 'o'
mov     [rbp+var_2C], 43h ; 'C'
mov     [rbp+var_2B], 54h ; 'T'
mov     [rbp+var_2A], 46h ; 'F'
mov     [rbp+var_29], 7Bh ; '{'
mov     [rbp+var_28], 41h ; 'A'
mov     [rbp+var_27], 53h ; 'S'
mov     [rbp+var_26], 43h ; 'C'
mov     [rbp+var_25], 49h ; 'I'
mov     [rbp+var_24], 49h ; 'I'
mov     [rbp+var_23], 5Fh ; '_'
mov     [rbp+var_22], 49h ; 'I'
mov     [rbp+var_21], 53h ; 'S'
mov     [rbp+var_20], 5Fh ; '_'
mov     [rbp+var_1F], 45h ; 'E'
mov     [rbp+var_1E], 41h ; 'A'
mov     [rbp+var_1D], 53h ; 'S'
mov     [rbp+var_1C], 59h ; 'Y'
mov     [rbp+var_1B], 5Fh ; '_'
mov     [rbp+var_1A], 37h ; '7'
mov     [rbp+var_19], 42h ; 'B'
mov     [rbp+var_18], 43h ; 'C'
mov     [rbp+var_17], 44h ; 'D'
mov     [rbp+var_16], 39h ; '9'
mov     [rbp+var_15], 37h ; '7'
mov     [rbp+var_14], 31h ; '1'
mov     [rbp+var_13], 44h ; 'D'
mov     [rbp+var_12], 7Dh ; '}'
movzx   eax, [rbp+var_30]
movsx   eax, al
mov     esi, eax
lea     rdi, format     ; "The flag starts with %x\n"
mov     eax, 0
call    _printf
nop
mov     rax, [rbp+var_8]
xor     rax, fs:28h
jz      short locret_122F
```


## Flag
    picoCTF{ASCII_IS_EASY_7BCD971D}