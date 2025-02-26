# Bbbbloat

## Description
Can you get the flag?
Reverse engineer this binary.

## Solution
First, check the format file, it known that the format is ELF file. Then, after running the file, it's ask to enter a number, then I eneter a random number but that's not a correct answer.

So, try to open the file using IDA, then generate Pseudocode of main function by press F5 or View > Open Subviews > Generate Pseudocode.

Then, we have this code
```c
__int64 __fastcall main(int a1, char **a2, char **a3)
{
  int v4; // [rsp+10h] [rbp-40h] BYREF
  int v5; // [rsp+14h] [rbp-3Ch]
  char *s; // [rsp+18h] [rbp-38h]
  char v7[40]; // [rsp+20h] [rbp-30h] BYREF
  unsigned __int64 v8; // [rsp+48h] [rbp-8h]

  v8 = __readfsqword(0x28u);
  strcpy(v7, "A:4@r%uL4Ff0f9b03=_cf0be55b`e2N");
  printf("What's my favorite number? ");
  v5 = 863305;
  __isoc99_scanf("%d", &v4);
  v5 = 863305;
  if ( v4 == 549255 )
  {
    v5 = 863305;
    s = (char *)sub_1249(0LL, v7);
    fputs(s, stdout);
    putchar(10);
    free(s);
  }
  else
  {
    puts("Sorry, that's not it!");
  }
  return 0LL;
}
```
After, we get correct input for the program, then run the program again to get the flag.

```
 ./bbbbloat
What's my favorite number? 549255
picoCTF{cu7_7h3_bl047_36dd316a}
```
## Flag
    picoCTF{cu7_7h3_bl047_36dd316a}