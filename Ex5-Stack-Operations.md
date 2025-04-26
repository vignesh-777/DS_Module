# Ex1(e) Stack Operations
## DATE:
## AIM:
To write a C function to perform push and pop operation of the stack in the infix to postfix conversion.

## Algorithm
1. Start the program by initializing the stack as a character array and set `top = -1`.  
2. To insert (push) an element, increment `top` and store the character at `stack[top]`.  
3. To remove (pop) an element, check if the stack is empty (`top == -1`); if so, return -1.  
4. If the stack is not empty, return the character at `stack[top]` and decrement `top`.  

## Program:
```
/*
Program to find and display the priority of the operator in the given Postfix expression
Developed by: VIGNESH R
RegisterNumber: 212223240177
*/

char stack[100];
int top = -1;
void push(char x)
{
 stack[++top] = x;
}
char pop()
{
 if(top == -1)
 return -1;
 else
 return stack[top--];
}
```

## Output:
![image](https://github.com/user-attachments/assets/03a3b896-4546-4c01-94bd-21348b492edf)


## Result:
Thus the C program to perform push and pop operation of the stack in the infix to postfix conversion is implemented successfully.
