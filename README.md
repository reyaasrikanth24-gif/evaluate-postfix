# evaluate-postfix
def evaluate_postfix(expression):
    stack = []
    
    for char in expression:
        if char.isdigit():  
            stack.append(int(char))
        
        else:  
            val2 = stack.pop()
            val1 = stack.pop()
            
            if char == '+':
                stack.append(val1 + val2)
            elif char == '-':
                stack.append(val1 - val2)
            elif char == '*':
                stack.append(val1 * val2)
            elif char == '/':
                stack.append(int(val1 / val2))  
            elif char == '^':
                stack.append(val1 ** val2)
    
    return stack.pop()

postfix_expr = input("Enter the psotfix expression:")
print("Postfix Expression: ", postfix_expr)
print("Evaluated Result: ", evaluate_postfix(postfix_expr))
