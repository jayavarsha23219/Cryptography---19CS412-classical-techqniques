# Cryptography---19CS412-classical-techqniques
## DATE : 18.03.2025
## NAME : JAYAVARSHA T
## REG NO : 212223040075
## Caeser Cipher
Caeser Cipher using with different key values

## AIM:

To encrypt and decrypt the given message by using Ceaser Cipher encryption algorithm.


## DESIGN STEPS:

### Step 1:

Design of Caeser Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

1.	In Ceaser Cipher each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet.
2.	For example, with a left shift of 3, D would be replaced by A, E would become B, and so on.
3.	The encryption can also be represented using modular arithmetic by first transforming the letters into numbers, according to the   
    scheme, A = 0, B = 1, Z = 25.
4.	Encryption of a letter x by a shift n can be described mathematically as,
                       En(x) = (x + n) mod26
5.	Decryption is performed similarly,
                       Dn (x)=(x - n) mod26


## PROGRAM:
```
PROGRAM 01;
#include <stdio.h>
#include <string.h>
#include <ctype.h>
int main() 
{
	char plain[100], cipher[100];
	int key, i, length;
	printf("Enter the plain text: ");
	scanf("%s", plain);
	printf("Enter the key value: ");
	scanf("%d", &key);
	printf("\nPLAIN TEXT: %s", plain);
	printf("\nENCRYPTED TEXT: ");
	length = strlen(plain);
	for (i = 0; i < length; i++) {
	cipher[i] = plain[i] + key;
	
	// Handling uppercase letters
	if (isupper(plain[i]) && cipher[i] > 'Z')
	{
	cipher[i] = cipher[i] - 26;
	}
	
	// Handling lowercase letters
	if (islower(plain[i]) && cipher[i] > 'z') {
	cipher[i] = cipher[i] - 26;
        }
        printf("%c", cipher[i]);
	}
	cipher[length] = '\0'; // Null-terminate the cipher text string
	printf("\nDECRYPTED TEXT: ");
	for (i = 0; i < length; i++) {
	plain[i] = cipher[i] - key;
	// Handling uppercase letters
	if (isupper(cipher[i]) && plain[i] < 'A') {
	plain[i] = plain[i] + 26;
	}
	// Handling lowercase letters
	if (islower(cipher[i]) && plain[i] < 'a') {
	plain[i] = plain[i] + 26;
	}
	printf("%c", plain[i]);
	}
	plain[length] = '\0'; // Null-terminate the plain text string
	return 0;
}
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/512c5aac-efa8-4bba-b3c8-921a8c2c1958)



## RESULT:
The program is executed successfully

-------------------------------------------------
## PlayFair Cipher
Playfair Cipher using with different key values

## AIM:

To implement a program to encrypt a plain text and decrypt a cipher text using play fair Cipher substitution technique.

 
## DESIGN STEPS:

### Step 1:

Design of PlayFair Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

Testing algorithm with different key values. 

### ALGORITHM DESCRIPTION:

The Playfair cipher uses a 5 by 5 table containing a key word or phrase. To generate the key table, first fill the spaces in the table with the letters of the keyword, then fill the remaining spaces with the rest of the letters of the alphabet in order (usually omitting "Q" to reduce the alphabet to fit; other versions put both "I" and "J" in the same space). The key can be written in the top rows of the table, from left to right, or in some other pattern, such as a spiral beginning in the upper-left-hand corner and ending in the centre.
The keyword together with the conventions for filling in the 5 by 5 table constitutes the cipher key. To encrypt a message, one would break the message into digrams (groups of 2 letters) such that, for example, "HelloWorld" becomes "HE LL OW OR LD", and map them out on the key table. Then apply the following 4 rules, to each pair of letters in the plaintext:
1.	If both letters are the same (or only one letter is left), add an "X" after the first letter. Encrypt the new pair and continue. Some   
   variants of Playfair use "Q" instead of "X", but any letter, itself uncommon as a repeated pair, will do.
2.	If the letters appear on the same row of your table, replace them with the letters to their immediate right respectively (wrapping 
   around to the left side of the row if a letter in the original pair was on the right side of the row).
3.	If the letters appear on the same column of your table, replace them with the letters immediately below respectively (wrapping around 
   to the top side of the column if a letter in the original pair was on the bottom side of the column).
4.	If the letters are not on the same row or column, replace them with the letters on the same row respectively but at the other pair of 
   corners of the rectangle defined by the original pair. The order is important – the first letter of the encrypted pair is the one that 
    lies on the same row as the first letter of the plaintext pair.
To decrypt, use the INVERSE (opposite) of the last 3 rules, and the 1st as-is (dropping any extra "X"s, or "Q"s that do not make sense in the final message when finished).


## PROGRAM:
```
#include<stdio.h>
#include<conio.h>
#include<string.h>
int main()
{
    unsigned int a[3][3]={{6,24,1},{13,16,10},{20,17,15}};
    unsigned int b[3][3]={{8,5,10},{21,8,21},{21,12,8}};
    int i,j, t=0;
    unsigned int c[20],d[20];
    char msg[20];
    printf("Enter plain text : ");
    scanf("%s",msg);
    for(i=0;i<strlen(msg);i++)
    {
        c[i]=msg[i]-65;
        printf("%d ",c[i]);
    }
    for(i=0;i<3;i++)
    {
        t=0;
        for(j=0;j<3;j++)
        {
            t=t+(a[i][j]*c[j]);
        }
        d[i]=t%26;
    }
    printf("\nEncrypted Cipher Text :");
    for(i=0;i<3;i++)
    printf(" %c",d[i]+65);
    for(i=0;i<3;i++)
    {
        t=0;
        for(j=0;j<3;j++)
        {
            t=t+(b[i][j]*d[j]);
        }
        c[i]=t%26;
    }
    printf("\nDecrypted Cipher Text :");
    for(i=0;i<3;i++)
    printf(" %c",c[i]+65);
    getch();
    return 0;
}
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/0ff6568f-c581-4b51-9c2f-d98092f69a4d)


## RESULT:
The program is executed successfully
