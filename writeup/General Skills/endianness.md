# endianness

## Descrition

Know of little and big endian?
[Source](https://artifacts.picoctf.net/c_titan/119/flag.c)
nc titan.picoctf.net 53006

## Solution

In the given program, we are asked to enter input in the form of conversion from the given word to **Little Endian** and **Big Endian**. Then, to help convert it, I created a program by applying the reverse engineering method.

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

char *find_little_endian(const char *word)
{
    size_t word_len = strlen(word);
    char *little_endian = (char *)malloc((2 * word_len + 1) * sizeof(char));

    if (little_endian == NULL)
    {
        perror("Memory allocation failed");
        exit(EXIT_FAILURE);
    }

    for (size_t i = word_len; i-- > 0;)
    {
        snprintf(&little_endian[(word_len - 1 - i) * 2], 3, "%02X", (unsigned char)word[i]);
    }

    little_endian[2 * word_len] = '\0';
    return little_endian;
}

char *find_big_endian(const char *word)
{
    size_t length = strlen(word);
    char *big_endian = (char *)malloc((2 * length + 1) * sizeof(char));

    if (big_endian == NULL)
    {
        perror("Memory allocation failed");
        exit(EXIT_FAILURE);
    }

    for (size_t i = 0; i < length; i++)
    {
        snprintf(&big_endian[i * 2], 3, "%02X", (unsigned char)word[i]);
    }

    big_endian[2 * length] = '\0';
    return big_endian;
}

int main()
{
    int word_length = 5;
    char *word = (char *)malloc((word_length + 1) * sizeof(char));

    printf("Enter a word (max %d chars): ", word_length);
    scanf("%5s", word); 

    char *little_endian = find_little_endian(word);
    char *big_endian = find_big_endian(word);

    printf("Little Endian: %s\n", little_endian);
    printf("Big Endian: %s\n", big_endian);

    return 0;
}
```

After that, just do the netcat process in the terminal
```
$ nc titan.picoctf.net 53006
Welcome to the Endian CTF!
You need to find both the little endian and big endian representations of a word.
If you get both correct, you will receive the flag.
Word: zbvzo
Enter the Little Endian representation: 6F7A76627A
Correct Little Endian representation!
Enter the Big Endian representation: 7A62767A6F
Correct Big Endian representation!
Congratulations! You found both endian representations correctly!
Your Flag is: picoCTF{3ndi4n_sw4p_su33ess_28329f0a}
```

## Flag
    picoCTF{3ndi4n_sw4p_su33ess_28329f0a}