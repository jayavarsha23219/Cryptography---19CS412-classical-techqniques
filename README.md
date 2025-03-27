# Cryptography---19CS412-classical-techqniques
## Hill Cipher
Hill Cipher using with different key values

## AIM:

To develop a simple C program to implement Hill Cipher.

## DESIGN STEPS:

### Step 1:

Design of Hill Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:
1. Convert each letter of the message to a number (A = 0, B = 1, ..., Z = 25) and dividethe message into blocks of size n.
2. Select an invertible n × n matrix as the cipher key (modulo 26 for the English alphabet).
3. Multiply each block of n letters by the cipher key matrix (modulo 26) to get theencrypted numbers.
4. Convert the encrypted numbers back into letters using the reverse of step 1.
5. Multiply the encrypted blocks by the inverse of the cipher key matrix (modulo 26) torecover the original message.
6. Ensure the key matrix is invertible (mod 26) for decryption to be possible.

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
    printf("Enter plain text (3 letters):");
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

![image](https://github.com/user-attachments/assets/840455f5-eda5-4e0e-99d7-55b341318a73)


## RESULT:
The program is executed successfully
