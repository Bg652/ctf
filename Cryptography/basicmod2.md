# basic mod1
---
## Description
A new modular challenge!
Download the message here.
Take each number mod 41 and find the modular inverse for the result. Then map to the following character set: 1-26 are the alphabet, 27-36 are the decimal digits, and 37 is an underscore.
Wrap your decrypted message in the picoCTF flag format (i.e. picoCTF{decrypted_message})
---
message is 268 413 438 313 426 337 272 188 392 338 77 332 139 113 92 239 247 120 419 72 295 190 131
after getting the code according to the condition
```python 
#include <stdio.h>

int modInverse(int a, int m) {
    int m0 = m;
    int x0 = 0, x1 = 1;

    if (m == 1)
        return 0;

    while (a > 1) {
        int q = a / m;
        //printf("%d\t",q);
        int t = m;

        m = a % m;
        //printf("%d\t",m);
        a = t;
        //printf("%d\t",a);
        t = x0;
        //printf("%d\t",t);
        x0 = x1 - q * x0;
        //printf("%d\t",x0);
        x1 = t;
        //printf("%d\t",x1);
        //printf("\n");
    }

    if (x1 < 0)
        x1 += m0;

    return x1;
}

int main() {
    int array[] = {268, 413, 438, 313, 426, 337, 272, 188, 392, 338, 77, 332, 139, 113, 92, 239, 247, 120, 419, 72, 295, 190, 131};
    int size = sizeof(array) / sizeof(array[0]);
    char newCharArr[size];
    int i;

    for (i = 0; i < size; i++) {
        int modulus_result = array[i] % 41;
        //printf("%d\t",modulus_result);
        int inverse = modInverse(modulus_result, 41);
        //printf("%d\t",inverse);
        printf("\n");

        if (inverse >= 1 && inverse <= 26) {
            newCharArr[i] = 'A' + inverse - 1;
        } else if (inverse >= 27 && inverse <= 36) {
            newCharArr[i] = '0' + inverse - 27;
        } else if (inverse == 37) {
            newCharArr[i] = '_';
        } else {
            // Handle other cases if needed
            newCharArr[i] = '?';
        }
    }

    // Print the modified characters
    printf("Modified Characters: picoCTF{");
    for (i = 0; i < size; i++) {
        printf("%c", newCharArr[i]);
    }
    printf("}");
    //printf("\n");

    return 0;
}
```
and on running it I got the flag\
![image](https://github.com/Bg652/ctf/assets/144695497/6d2ee7a0-d559-474a-8c36-e07f2c64cfa7)
