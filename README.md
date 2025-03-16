# Vigenere Cipher
Vigenere Cipher using with different key values

# AIM:

To develop a simple C program to implement Vigenere Cipher.

## DESIGN STEPS:

### Step 1:

Design of Vigenere Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

Testing algorithm with different key values. 
ALGORITHM DESCRIPTION:
The Vigenere cipher is a method of encrypting alphabetic text by using a series of different Caesar ciphers based on the letters of a keyword. It is a simple form of polyalphabetic substitution.To encrypt, a table of alphabets can be used, termed a Vigenere square, or Vigenere table. It consists of the alphabet written out 26 times in different rows, each alphabet shifted cyclically to the left compared to the previous alphabet, corresponding to the 26 possible Caesar ciphers. At different points in the encryption process, the cipher uses a different alphabet from one of the rows used. The alphabet at each point depends on a repeating keyword.



## PROGRAM:
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

void encrypt(char text[], char key[], char cipher[]) {
    int textLen = strlen(text);
    int keyLen = strlen(key);
    
    for (int i = 0, j = 0; i < textLen; i++) {
        if (isalpha(text[i])) {
            char base = isupper(text[i]) ? 'A' : 'a';
            cipher[i] = ((text[i] - base + (toupper(key[j]) - 'A')) % 26) + base;
            j = (j + 1) % keyLen;
        } else {
            cipher[i] = text[i];
        }
    }
    cipher[textLen] = '\0';
}

void decrypt(char cipher[], char key[], char decrypted[]) {
    int textLen = strlen(cipher);
    int keyLen = strlen(key);

    for (int i = 0, j = 0; i < textLen; i++) {
        if (isalpha(cipher[i])) {
            char base = isupper(cipher[i]) ? 'A' : 'a';
            decrypted[i] = ((cipher[i] - base - (toupper(key[j]) - 'A') + 26) % 26) + base;
            j = (j + 1) % keyLen;
        } else {
            decrypted[i] = cipher[i];
        }
    }
    decrypted[textLen] = '\0';
}

int main() {
    char text[100], key[100], cipher[100], decrypted[100];

    printf("Enter the plaintext: ");
    scanf("%[^\n]%*c", text); ]

    printf("Enter the key: ");
    scanf("%s", key);

    encrypt(text, key, cipher);
    printf("Encrypted Text: %s\n", cipher);

    decrypt(cipher, key, decrypted);
    printf("Decrypted Text: %s\n", decrypted);

    return 0;
}
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/7c1ee287-03a7-45fc-ba92-94124c372b63)

## RESULT:
The program is executed successfully
