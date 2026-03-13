class Node:
    def __init__(self,data):
        self.data=data
        self.left=None
        self.right=None

def build_balanced(arr):
    if not arr:
        return None
    mid=len(arr)//2
    root=Node(arr[mid])
    root.left=build_balanced(arr[:mid])
    root.right=build_balanced(arr[mid+1:])
    return root

def inorder(root):
    if root:
        inorder(root.left)
        print(root.data,end=" ")
        inorder(root.right)

# Driver
arr=[10,20,30,40,50,60,70]
root=build_balanced(arr)

print("Balanced Search Tree Inorder:")
inorder(root)# Data-structure-practical-program-24
