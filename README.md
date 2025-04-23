# Ex-1 IMPLEMENTATION-OF-SYMBOL-TABLE
# Date: 19-03-2025
# AIM :
## To write a C program to implement a symbol table.
# ALGORITHM
1.	Start the program.
2.	Get the input from the user with the terminating symbol ‘$’.
3.	Allocate memory for the variable by dynamic memory allocation function.
4.	If the next character of the symbol is an operator then only the memory is allocated.
5.	While reading, the input symbol is inserted into symbol table along with its memory address.
6.	The steps are repeated till ‘$’ is reached.
7.	To reach a variable, enter the variable to be searched and symbol table has been checked for corresponding variable, the variable along with its address is displayed as result.
8.	Stop the program. 
# PROGRAM
```c
#include<stdio.h>
#include<ctype.h>
#include<string.h>
#include<stdlib.h>
#define MAX_EXPRESSION_SIZE 100
int main() 
{
    int i = 0, j = 0, x = 0, n, flag = 0;
    void *add[5]; // Array to store addresses
    char b[MAX_EXPRESSION_SIZE], d[5], c, srch;
    printf("Enter the Expression terminated by $: ");
    while ((c = getchar()) != '$' && i < MAX_EXPRESSION_SIZE - 1) {
        b[i++] = c;
    }
    b[i] = '\0'; 
    n = i; 
    printf("Given Expression: %s\n", b);
    printf("\nSymbol Table\n");
    printf("Symbol\taddr\ttype\n");
    for (j = 0; j < n; j++) {
        c = b[j];
        if (isalpha((unsigned char)c)) { 
            if (j == n - 1 || !isalpha(b[j + 1])) { 
                void *p = malloc(sizeof(char));
                add[x] = p; 
                d[x] = c; 
                printf("%c\t%p\tidentifier\n", c, p);
                x++;
            }
        }
    }
    getchar();
    printf("\nThe symbol to be searched: ");
    srch = getchar();
    for (i = 0; i < x; i++) {
        if (srch == d[i]) {
            printf("Symbol Found\n");
            printf("%c@address %p\n", srch, add[i]);
            flag = 1;
            break;
        }
    }
    if (flag == 0) {
        printf("Symbol Not Found\n");
    }
    for (i = 0; i < x; i++) {
        free(add[i]);
    }
    return 0;
}
```
# OUTPUT
# SYMBOL FOUND
![Screenshot 2025-04-23 152132](https://github.com/user-attachments/assets/cf705fb1-6e36-4658-88f8-d481e124d380)

# SYMBOL NOT FOUND
![Screenshot 2025-04-23 152201](https://github.com/user-attachments/assets/c26e9a78-c3c3-42ca-baf7-a6efe1084f81)


# RESULT
### The program to implement a symbol table is executed and the output is verified.
