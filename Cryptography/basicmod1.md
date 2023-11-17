# basic mod1
---
## Description
We found this weird message being passed around on the servers, we think we have a working decryption scheme.\
Download the message here.\
Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.\
Wrap your decrypted message in the picoCTF flag format (i.e. picoCTF{decrypted_message})
---
downloaded message is 165 248 94 346 299 73 198 221 313 137 205 87 336 110 186 69 223 213 216 216 177 138 \
and I wrote the code according to the condition stating.
```python 
#include <stdio.h>

int main() {
    int array[] = {165, 248, 94, 346, 299, 73, 198, 221, 313, 137, 205, 87, 336, 110, 186, 69, 223, 213, 216, 216, 177, 138 };
    int size = sizeof(array) / sizeof(array[0]);
    char newCharArr[size]; // Array to store the new characters
    int i;

    for (i = 0; i < size; i++) {
        int modulus_result = array[i] % 37;

        if (modulus_result >= 0 && modulus_result <= 25) {
            // Replace with uppercase letters A to Z
            newCharArr[i] = 'A' + modulus_result;
        } else if (modulus_result >= 26 && modulus_result <= 35) {
            // Replace with numbers 0 to 9
            newCharArr[i] = '0' + (modulus_result - 26);
        } else if (modulus_result == 36) {
            // Replace with underscore
            newCharArr[i] = '_';
        } else {
            // Handle other cases if needed
            newCharArr[i] = '?'; // For example, you can use '?' for unhandled cases
        }
    }

    // Print the modified characters
    printf("Modified Characters: picoCTF{");
    for (i = 0; i < size; i++) {
        printf("%c", newCharArr[i]);
    }
    printf("}");
    printf("\n");

    return 0;
}
```
and after running it i got the flag
![image](https://github.com/Bg652/ctf/assets/144695497/f1666dfa-c14d-4f25-812d-086036f6a08f)

