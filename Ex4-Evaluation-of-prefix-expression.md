# Ex1(d) Evaluation of prefix expression
## DATE: 24/02/2025
## AIM:
To write a C function to evaluate the given prefix expression using stack and print the output of the given prefix expression from the stack inside the function . 

## Algorithm
1. Start the program.  
2. Initialize an empty stack with a variable `top` to manage the index.  
3. Define a `push()` function to insert an element onto the stack.  
4. Define a `pop()` function to remove and return the top element from the stack.  
5. Traverse the prefix expression from right to left.  
6. If the character is an operator, pop two elements from the stack, perform the operation, and push the result; if it's a digit, convert it to an integer and push it.  
7. After completing the traversal, pop and print the final result from the stack.
8. End

## Program:
```
/*
Program to evaluate the given prefix expression
Developed by: VIGNESH R
RegisterNumber: 212223240177
*/

#include<stdio.h> 
#include<string.h> 
#include<ctype.h>
int s[50]; 
int top=0;
void push(int ch)
{
top++; 
s[top]=ch;
}
int pop()
{
int ch; 
ch=s[top]; 
top=top-1; 
return(ch);
}
void evalprefix(char p[50])
{
int a,b,c,i;
for(i=strlen(p)-1;i>=0;i--)
{
if(p[i]=='+')
{
a=pop();
b=pop(); 
c=a+b; 
push(c);
}
else if(p[i]=='*')
{
a=pop();
b=pop(); 
c=a*b; 
push(c);
}
else
{
push(p[i]-48);
}
}
printf("%d",pop());
}
```

## Output:
![image](https://github.com/user-attachments/assets/b9714ad5-757e-4882-af46-f77c6d7dc559)


## Result:
Thus, the C program to evaluate the prefix expression using stack and print the output of the given prefix expression from the stack inside the function is implemented successfully.
