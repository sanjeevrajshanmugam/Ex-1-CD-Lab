# Ex-1 IMPLEMENTATION-OF-SYMBOL-TABLE
# Register Number : 212223220096
# Date : 19/03/2025
# AIM :
## To write a C program to implement a symbol table.
# ALGORITHM
1.	Start the program.
2.	Get the input from the user with the terminating symbol ‘$’.
3.	Allocate memory for the variable by dynamic memory allocation function.
4.	If the next character of the symbol is an operator then only the memory is allocated.
5.	While reading, the input symbol and memory address are inserted into the symbol table.
6.	The steps are repeated till ‘$’ is reached.
7.	To reach a variable, enter the variable to be searched and the symbol table has been checked for the corresponding variable, the variable along with its address is displayed as a result.
8.	Stop the program. 
# PROGRAM

```
%{
#include <stdio.h>
%}

%%

[0-9]+       {printf("NUMBER: %s\n", yytext); }
[A-Za-z][A-Za-z0-9]*    { printf("IDENTIFIER: %s\n", yytext); }
[+\-*/=]       {printf("OPERATOR: %s\n", yytext); }
[ \t\n]      { /* Ignore whitespace */ }
.           { printf("UNKNOWN: %s\n", yytext); }

%%

int yywrap() { return 1; }

int main() {
    printf("Enter your input: ");
    yylex();
    return 0;
}
```
# OUTPUT
![Screenshot 2025-03-19 152445](https://github.com/user-attachments/assets/15e4dbeb-83d7-47da-97fe-9d517ed17b54)


# RESULT
### The program to implement a symbol table is executed and the output is verified.
