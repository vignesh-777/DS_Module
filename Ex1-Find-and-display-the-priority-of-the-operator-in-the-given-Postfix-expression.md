# EX 1 Display operator precedence in the infix expression.
## DATE:
## AIM:
To write a C program to find and display the priority of the operator in the given Postfix expression

## Algorithm
1. Start the program.  
2. Include the required libraries.  
3. Define a function to return the priority of a given operator.  
4. Initialize the postfix expression.  
5. Loop through each character of the expression.  
6. If the character is an operator, find its priority using the function.  
7. Print the operator along with its corresponding priority level (Highest, Second Highest, etc.).  
8. End the program.
## Program:
```
/*
Program to find and display the priority of the operator in the given Postfix expression
Developed by: VIGNESH R
RegisterNumber: 212223240177
*/

#include <stdio.h>
#include<string.h>

    int priority(char x)
{
   if(x=='^')
   return 1;
   if(x=='*'||x=='%'||x=='/')
   return 2;
   if(x=='+'||x=='-')
   return 3;
   if(x=='&')
   return 4;
   else
   return 0;
}
int main()
{
   int i,j;
   char x;
   char ch[100]="(A*B)^C+(D%H)/F&G";
   for(i=0;i<strlen(ch);i++)
   {
       for(j=0;j<strlen(ch);j++)
       {
           if(ch[i]=='^'||ch[i]=='*'||ch[i]=='%'||ch[i]=='/'||ch[i]=='+'||ch[i]=='-'||ch[i]=='&')
       {
           x=ch[i];
           if(priority(x)==1)
           {
               printf("%c  ----> Highest Priority\n",x);
               break;
           }
           if(priority(x)==2)
           {
               printf("%c  ----> Second Highest Priority\n",x);
               break;
           }
           if(priority(x)==3)
           {
              printf("%c  ----> Second Lowest Priority\n",x);
              break;
           }
           if(priority(x)==4)
           {
             printf("%c  ----> Lowest Priority\n",x);
             break;
           }
       } 
       }
   }
    return 0;
}
   
```

## Output:
![image](https://github.com/user-attachments/assets/b8c2942a-16f1-4867-b629-f4bfc75dadd6)



## Result:
Thus the C program to find and display the priority of the operator in the given Postfix expression is implemented successfully
