# Exp.No:31  
## IMPLEMENTATION OF STACK

---

### AIM  
To write a python program  to reverse substring between each pair of parenthesis.

---

### ALGORITHM

1. **Start the program.**
2.Initialize an empty stack to store characters.
3.Traverse the string character by character:
    If the character is not ‘)’,
      → Push it onto the stack.
   If the character is ‘)’:
      a. Pop characters from the stack until you find ‘(’.
       b. Store these popped characters (which form the substring inside parentheses).
      c. Reverse the collected substring.
      d. Push the reversed characters back onto the stack (without parentheses).
4.After scanning all characters:
   Pop all remaining characters from the stack and form the final result.
   Reverse it (since stack gives reversed order).
5.Return the resulting string without any parentheses.
6. **End the program.**

---

### PROGRAM

```
def reverseParentheses(strr):
    st = []
    lenn = len(strr)
    st = [i for i in strr]
    for i in range(lenn):

        if (strr[i] == '('):
            st.append(i)

        elif (strr[i] == ')'):
            temp = strr[st[-1]:i + 1]
            strr = strr[:st[-1]] + temp[::-1] +                    strr[i + 1:]
            del st[-1]
    res = ""
    for i in range(lenn):
        if (strr[i] != ')' and strr[i] != '('):
            res += (strr[i])
    return res
strr = input()
print(reverseParentheses(strr))

```
### OUTPUT
<img width="807" height="221" alt="image" src="https://github.com/user-attachments/assets/25df1e48-d215-4e3f-a352-80235edd8858" />

### RESULT
      Thus the program  to reverse substring between each pair of parenthesis is successfully verified.


