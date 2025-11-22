# Exp.No:32  
## CONVERSION OF INFIX TO POSTFIX

---

### AIM  
To Write a Python program to convert user given Infix expression to Postfix expression in stack, also by following the precedence and associative rule. The infix expression contains two operators viz., Addition and Subtraction.

---

### ALGORITHM

1. **Start the program.**
2. Initialize an empty stack for operators.
3.Initialize an empty output string for the postfix expression.
4.Scan the infix expression from left to right:
   If the character is an operand(+ or -);
   → Append it directly to the postfix output.
   If the character is an operator (+ or -):
      a. While the stack is not empty and the top of the stack has
      operator of higher or equal precedence,
      → Pop it and add to postfix.
      b. Push the current operator onto the stack.
5.After scanning the entire infix expression:
   → Pop all remaining operators from the stack and append to postfix.
6. **Return the final postfix expression.**
7. **Print the result.**
8. **End the program.**

---

### PROGRAM

```
Operators = set(['+', '-','*','/','(', ')','^'])  
Priority = {'+':1, '-':1, '*':2, '/':2, '^':3} 
 
 
def infixToPostfix(expression): 

    stack = [] 
    output = '' 
    for character in expression:
        if character not in Operators:
            output+=character
        elif character=='(':
            stack.append('(')
        elif character==')':
            while stack and stack[-1]!= '(':
                output+=stack.pop()
            stack.pop()
        else:
            while stack and stack[-1]!='(' and Priority[character]<=Priority[stack[-1]]:
                output+=stack.pop()
            stack.append(character)
    while stack:
        output+=stack.pop()
         
      
    return output
    
expression = input() 
print('Infix notation: ',expression)
print('Postfix notation: ',infixToPostfix(expression))

```

### OUTPUT
<img width="816" height="198" alt="image" src="https://github.com/user-attachments/assets/daf86fab-d07a-4ca0-bfc5-3645dafb6aaf" />



### RESULT
The Python program successfully converts the user-entered infix expression containing the addition and subtraction operators into its correct postfix form by using a stack and applying both precedence and associativity rules.

