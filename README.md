# Cryptography---19CS412-classical-techqniques


# Caeser Cipher
Caeser Cipher using with different key values

# AIM:

To develop a simple C program to implement Caeser Cipher.

## DESIGN STEPS:

### Step 1:

Design of Caeser Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

Testing algorithm with different key values. 

## PROGRAM:
```
#include<stdio.h>
#include <string.h>

#include <ctype.h>
int main()
{
char plain[10], cipher[10];
int key,i,length;
int result;
printf("\n Enter the plain text:");
scanf("%s", plain);
printf("\n Enter the key value:");
scanf("%d", &key);
printf("\n \n \t PLAIN TEXt: %s",plain);
printf("\n \n \t ENCRYPTED TEXT: ");
for(i = 0, length = strlen(plain); i < length; i++)
{
cipher[i]=plain[i] + key;
if (isupper(plain[i]) && (cipher[i] > 'Z'))
cipher[i] = cipher[i] - 26;
if (islower(plain[i]) && (cipher[i] > 'z'))
cipher[i] = cipher[i] - 26;
printf("%c", cipher[i]);
}
printf("\n \n \t AFTER DECRYPTION : ");
for(i=0;i<length;i++)
{
plain[i]=cipher[i]-key;
if(isupper(cipher[i])&&(plain[i]<'A'))
plain[i]=plain[i]+26;
if(islower(cipher[i])&&(plain[i]<'a'))
plain[i]=plain[i]+26;
printf("%c",plain[i]);
}
return 0;
}
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/d9dc6944-06ba-4223-bdcd-719749e63f85)

## RESULT:
The program is executed successfully

---------------------------------

# PlayFair Cipher
Playfair Cipher using with different key values

# AIM:

To develop a simple C program to implement PlayFair Cipher.

## DESIGN STEPS:

### Step 1:

Design of PlayFair Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

Testing algorithm with different key values. 

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
    printf("Enter plain text");
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
![image](https://github.com/user-attachments/assets/86f16052-5eaa-4677-bbbe-3ae5ad348fcc)


## RESULT:
The program is executed successfully


---------------------------

# Hill Cipher
Hill Cipher using with different key values

# AIM:

To develop a simple C program to implement Hill Cipher.

## DESIGN STEPS:

### Step 1:

Design of Hill Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

Testing algorithm with different key values. 

## PROGRAM:
```
#include <stdio.h>
#include<conio.h>
#include <ctype.h>
#include <string.h>
void encipher();
void decipher();
void main()
{
    int choice;
    while(1)
{
    printf("\n1. Encrypt Text");
    printf("\t2. Decrypt Text");
    printf("\t3. Exit");
    printf("\n\nEnter Your Choice : ");
    scanf("%d",&choice);
    if(choice == 3)
    exit(0);
    else if(choice == 1)
    encipher();
    else if(choice == 2)
    decipher();
    else
    printf("Please Enter Valid Option.");
}
}
void encipher()
{
    unsigned int i,j;
    char input[50],key[10];
    printf("\n\nEnter Plain Text: ");
    scanf("%s",input);
    printf("\nEnter Key Value: ");
    scanf("%s",key);
    printf("\nResultant Cipher Text: ");
    for(i=0,j=0;i<strlen(input);i++,j++)
    {
        if(j>=strlen(key))
        {
            j=0;
        }
        printf("%c",65+(((toupper(input[i])-65)+(toupper(key[j])-65))%26));
    }
    
}
void decipher()
{
    unsigned int i,j;
    char input[50],key[10];
    int value;
    printf("\n\nEnter Cipher Text: ");
    scanf("%s",input);
    printf("\n\nEnter the key value: ");
    scanf("%s",key);
    for(i=0,j=0;i<strlen(input);i++,j++)
    {
        if(j>=strlen(key))
        { 
            j=0;
            
        }
        value = (toupper(input[i])-64)-(toupper(key[j])-64);
        if( value < 0)
        {
            value = value * -1;
        }
        printf("%c",65 + (value % 26));
        
    }
}
```
## OUTPUT:
![Screenshot 2024-10-14 091214](https://github.com/user-attachments/assets/27db5c40-a222-40b3-ae99-759ed66e225f)



## RESULT:
The program is executed successfully

-------------------------------------------------

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

## PROGRAM:
```
#include <stdio.h>
#include <ctype.h>
#include <string.h>
void encipher();
void decipher();
int main()
{
int choice;
while(1)
{
printf("\n1. Encrypt Text");
printf("\n2. Decrypt Text");
printf("\n3. Exit");
printf("\n\nEnter Your Choice : ");
scanf("%d",&choice);
if(choice == 3)
exit(0);
else if(choice == 1)
encipher();
else if(choice == 2)
decipher();
else
printf("Please Enter Valid Option.");
}
}
void encipher()
{
unsigned int i,j;
char input[50],key[10];
printf("\n\nEnter Plain Text: ");
scanf("%s",input);
printf("\nEnter Key Value: ");
scanf("%s",key);
printf("\nResultant Cipher Text: ");
for(i=0,j=0;i<strlen(input);i++,j++)
{
if(j>=strlen(key))
{ j=0;
}
printf("%c",65+(((toupper(input[i])-65)+(toupper(key[j])-
65))%26));
}}
void decipher()
{
unsigned int i,j;
char input[50],key[10];
int value;
printf("\n\nEnter Cipher Text: ");
scanf("%s",input);
printf("\n\nEnter the key value: ");
scanf("%s",key);
for(i=0,j=0;i<strlen(input);i++,j++)
{
if(j>=strlen(key))
{ j=0; }
value = (toupper(input[i])-64)-(toupper(key[j])-64);
if( value < 0)
{ value = value * -1;
}
printf("%c",65 + (value % 26));
}
return 0;
}
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/f976e6d4-f774-4277-a351-d01ba4911e69)


## RESULT:
The program is executed successfully

-----------------------------------------------------------------------

# Rail Fence Cipher
Rail Fence Cipher using with different key values

# AIM:

To develop a simple C program to implement Rail Fence Cipher.

## DESIGN STEPS:

### Step 1:

Design of Rail Fence Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

Testing algorithm with different key values. 

## PROGRAM:
```
#include<stdio.h>
#include<conio.h>
#include<string.h>
int main()
{
int i,j,k,l;
char a[20],c[20],d[20];
printf("\n\t\t RAIL FENCE TECHNIQUE");
printf("\n\nEnter the input string : ");
gets(a);
l=strlen(a);
for(i=0,j=0;i<l;i++)
{
if(i%2==0)
c[j++]=a[i];
}
for(i=0;i<l;i++)
{
if(i%2==1)
c[j++]=a[i];
}
c[j]='\0';
printf("\nCipher text after applying rail fence :");
printf("\n%s",c);
if(l%2==0)
k=l/2;
else
k=(l/2)+1;
for(i=0,j=0;i<k;i++)
{
d[j]=c[i];
j=j+2;
}
for(i=k,j=1;i<l;i++)
{
d[j]=c[i];
j=j+2;
}
d[l]='\0';
printf("\nText after decryption : ");
printf("%s",d);
return 0;
}
```
## OUTPUT:
![WhatsApp Image 2024-10-14 at 09 28 22_b17c55a5](https://github.com/user-attachments/assets/fc34fb5c-ffbb-4ae6-9719-c44ce9b41423)


## RESULT:
The program is executed successfully
