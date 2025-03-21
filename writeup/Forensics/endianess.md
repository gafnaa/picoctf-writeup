# endianness

## Description

Know of little and big endian?
Source
nc titan.picoctf.net 58542

## Solution

I just do reverse engineering for this chall.

From the source code we get this funtion
```c
int main()
{
    char *challenge_word = generate_random_word();
    printf("Word: %s\n", challenge_word);
    fflush(stdout);

    char *little_endian = find_little_endian(challenge_word);
    size_t user_little_endian_size = strlen(little_endian);
    char user_little_endian[user_little_endian_size + 1];
    bool correct_flag = false;
    while (!correct_flag)
    {
        printf("Enter the Little Endian representation: ");
        fflush(stdout);
        scanf("%10s", user_little_endian);
        for (size_t i = 0; i < strlen(user_little_endian); i++)
        {
            user_little_endian[i] = toupper(user_little_endian[i]);
        }

        if (strncmp(user_little_endian, little_endian, user_little_endian_size) == 0)
        {
            printf("Correct Little Endian representation!\n");
            fflush(stdout);
            correct_flag = true;
        }
```

Just add `printf` function to see the correct answer :D, and do it for `big endian function` too

```c
//Little Endian
char *little_endian = find_little_endian(challenge_word);
    size_t user_little_endian_size = strlen(little_endian);
    char user_little_endian[user_little_endian_size + 1];
    bool correct_flag = false;
    printf("Little Endian: %s\n", little_endian);
    while (!correct_flag)

//Big Endian
char *big_endian = find_big_endian(challenge_word);
    size_t user_big_endian_size = strlen(big_endian);
    char user_big_endian[user_big_endian_size + 1];
    
    bool final_flag = false;
    printf("Big Endian: %s\n", big_endian);
    while (!final_flag)
```
You can see the full source code of the file on [here](/files/endianv1/solve.c)

Then, just do netcat and solve it!
```sh
$ nc titan.picoctf.net 56938
Welcome to the Endian CTF!
You need to find both the little endian and big endian representations of a word.
If you get both correct, you will receive the flag.
Word: oleao
Enter the Little Endian representation: 6F61656C6F
Correct Little Endian representation!
Enter the Big Endian representation: 6F6C65616F
Correct Big Endian representation!
Congratulations! You found both endian representations correctly!
Your Flag is: picoCTF{3ndi4n_sw4p_su33ess_28329f0a}
```
## Flag
    picoCTF{3ndi4n_sw4p_su33ess_28329f0a}