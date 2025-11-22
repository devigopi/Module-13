# Exp.No:34  
## PREFIX EVALUATION

---

### AIM  
To write a Python program to evaluate a user-given Prefix expression using a stack. The expression must contain operators such as Multiplication, Addition, and Subtraction.

---

### ALGORITHM

1. **Start the program.**
2. Define a set of valid operators: `*, -, +, %, /, **`.
3. Initialize an empty stack.
4. Traverse the prefix expression from **right to left**:
   - If the character is a **digit**, convert it to an integer and push it onto the stack.
   - If the character is an **operator**, pop two elements from the stack.
     - Apply the operator on the two popped operands.
     - Push the result back onto the stack.
   - If an invalid character is encountered, raise an error.
5. After traversal, the stack should contain only **one element**.
6. Return the **single element** as the evaluation result.
7. **End the program.**

---

### PROGRAM

```
OPERATORS=set(['*','-','+','%','/','**']) 

def evaluate(expression):
    stack=[]
    for i in expression[::-1]:
        if i not in OPERATORS:
            stack.append(int(i))
        else:
            o1=stack.pop()
            o2=stack.pop()
            if i=="+":
                stack.append(o1+o2)
            elif i=="-":
                stack.append(o1-o2)
            elif i=="*":
                stack.append(o1*o2)
            elif i=="/":
                stack.append(o1/o2)
    return stack.pop()
    
expression=input()
print("Prefix Expression :",expression)
print("Evaluation result :",evaluate(expression))


```


### OUTPUT
<img width="818" height="267" alt="image" src="https://github.com/user-attachments/assets/b6106035-4dc4-4f4b-a615-e140bd8d1e57" />

### RESULT
   Thus the program to evaluate the user given Prefix expression using stack. The infix expression must contain operators viz., Multiplication, Addition and Subtraction is verified successfully.



