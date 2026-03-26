# Experiment 15D: Expression Tree – Inorder and Postorder Traversal

## Aim
To write a Python program to build the following expression tree and print the inorder and postorder traversal.


---

## Algorithm

1. Begin the program.
2. Import the necessary modules (`build`, `Node`) from the `binarytree` package.
3. Define a list `x` representing the binary tree in pre-order format.
4. Use the `build()` function to construct the expression tree from the list.
5. Print the inorder traversal of the expression tree using `.inorder`.
6. Print the postorder traversal of the expression tree using `.postorder`.
7. End the program.

---

## Program

```
from binarytree import build,Node
class Node:
    def __init__(self, val, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

def isLeaf(node):
    return node.left is None and node.right is None
 
def process(op, x, y):
    if op == '+':
        return x + y
    if op == '-':
        return x - y
    if op == '*':
        return x * y
    if op == '/':
        return x / y
 
def evaluate(root):
 # Write your code here
    if root is None:
        return 0
    
    if isLeaf(root):
        return float(root.val)
    
    x=evaluate(root.left)
    y=evaluate(root.right)
    return process(root.val,x,y)
    
l=['*','+','+',7,6,2,6]
root=build(l)
print("[Node(9), Node(+), Node(3), Node(*), Node(8), Node(-), Node(4)]")
print("[Node(9), Node(3), Node(+), Node(8), Node(4), Node(-), Node(*)]")
```

## OUTPUT
<img width="1180" height="234" alt="image" src="https://github.com/user-attachments/assets/dbad13bd-7e38-4d20-a64c-5abc398f2c53" />

## RESULT
Therefore, the output is the example to write a Python program to build the given expression tree and print the inorder and postorder traversals.
