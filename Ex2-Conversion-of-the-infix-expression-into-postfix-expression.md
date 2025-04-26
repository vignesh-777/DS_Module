# Ex1(b) Conversion of the infix expression into postfix expression
## DATE: 24/02/2025
## AIM:
To write a C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule.

## Algorithm
1. Start the program.  
2. Initialize an empty stack and set the top index to -1.  
3. Define the push and pop functions for stack operations.  
4. Define a function to assign priority to each operator.  
5. Traverse the infix expression character by character and process operands, operators, and parentheses accordingly.  
6. After the traversal, pop and print all remaining operators from the stack.  
7. End the program.

## Program:
```
/*
Program to convert the infix expression into postfix expression
Developed by: VIGNESH R
RegisterNumber: 212223240177
*/

#include<stdio.h> 
#include<ctype.h>
char stack[100]; 
int top = -1;
void push(char x)
{
stack[++top]=x;
}
char pop()
{
if(top==-1) 
return 0;
else
return stack[top--];
}
int priority(char x)
{
if(x=='(')
{
return 0;
}
if(x=='&'||x=='|')
{
return 1;
}
if(x=='+'||x=='-')
{
return 2;
}
if(x=='*'||x=='/'||x=='%')
{
return 3;
}
if(x=='^')
{
return 4;
}
return 0;
}
char IntoPost(char *exp)
{
char *e,x; 
e=exp; 
while(*e!='\0')
{
if(isalnum(*e))
{
printf("%c ",*e);
}
else if(*e=='(')
{
push(*e);
}
else if(*e==')')
{
while((x=pop())!='(') 
printf("%c ",x);
}
else
{
while(priority(stack[top])>=priority(*e)) 
printf("%c ",pop());
push(*e);
}
e++;
}
while(top != -1)
{
printf("%c ",pop());
}return 0;
}
int main()
{
char exp[100]="3%2+4*(A&B)"; 
IntoPost(exp);
return 1;
}
```

## Output:
![image](https://github.com/user-attachments/assets/706066db-884c-4c25-84f8-c06b3a66e781)




## Result:
Thus, the C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule is implemented successfully.
