## accenture codes


```python
N,E,D = map(int,input().split())    #4 5 20
days = (D-(D//7))   # 18
required = D*E      # 100
maximum = days * N  # 72
res = 0
if required > maximum:
    return -1
else:
    if required%N == 0:
        res =  required//N
    else:
        res = (required//N)+1
    return res
```

```python
def rhymes(word, words, n):
    max_count = 0
    result = "No Word"

    for text in words:
        if word == text:
            continue

        i = len(text) - 1
        j = len(word) - 1
        count = 0

        # Check for matching characters from the end of the words
        while i >= 0 and j >= 0:
            if text[i] == word[j]:
                i -= 1
                j -= 1
                count += 1
            else:
                break

        # Update the result if a better match is found
        if count > max_count:
            max_count = count
            result = text

    return result

if __name__ == "__main__":
    word = input()
    n = int(input())
    words = [input() for _ in range(n)]

    res = rhymes(word, words, n)
    print(res)
```

```python
def oddeven(n,m):
    sum1=0
    sum2=0
    for i in range(1,m+1):
        if i%n==0: 
            sum1=sum1+i
            #print(sum1)
        else:
            sum2=sum2+i
            #print(sum2)
    return sum1-sum2 if sum1>sum2 else sum2-sum1   
        
#n,m=map(int,input().split())
print(oddeven(4,20))
```

Here are Python codes for each of the problems:

### 1. **Reverse a String**
```python
def reverse_string(s):
    return s[::-1]

# Example Usage
s = "hello"
print(reverse_string(s))  # Output: "olleh"
```

### 2. **Find the Maximum Element in an Array**
```python
def find_max(arr):
    return max(arr)

# Example Usage
arr = [3, 1, 4, 1, 5, 9]
print(find_max(arr))  # Output: 9
```

### 3. **Check if a String is a Palindrome**
```python
def is_palindrome(s):
    return s == s[::-1]

# Example Usage
s = "racecar"
print(is_palindrome(s))  # Output: True
```

### 4. **Find the Missing Number in an Array**
**Note:** The array contains numbers from 1 to n with one missing number.
```python
def find_missing_number(arr):
    n = len(arr) + 1
    total_sum = n * (n + 1) // 2
    return total_sum - sum(arr)

# Example Usage
arr = [1, 2, 4, 5, 6]
print(find_missing_number(arr))  # Output: 3
```

### 5. **Find the Intersection of Two Arrays**
```python
def array_intersection(arr1, arr2):
    return list(set(arr1) & set(arr2))

# Example Usage
arr1 = [1, 2, 2, 3]
arr2 = [2, 3, 4]
print(array_intersection(arr1, arr2))  # Output: [2, 3]
```

### 6. **Remove Duplicates from an Array**
```python
def remove_duplicates(arr):
    return list(set(arr))

# Example Usage
arr = [1, 2, 2, 3, 4, 4, 5]
print(remove_duplicates(arr))  # Output: [1, 2, 3, 4, 5]
```

### 7. **Count the Occurrence of Each Element in an Array**
```python
from collections import Counter

def count_occurrences(arr):
    return Counter(arr)

# Example Usage
arr = [1, 2, 2, 3, 4, 4, 5]
print(count_occurrences(arr))  # Output: Counter({2: 2, 4: 2, 1: 1, 3: 1, 5: 1})
```

### 8. **Find the Second Largest Element in an Array**
```python
def second_largest(arr):
    unique_arr = list(set(arr))
    unique_arr.sort()
    return unique_arr[-2] if len(unique_arr) >= 2 else None

# Example Usage
arr = [2, 3, 6, 6, 5]
print(second_largest(arr))  # Output: 5
```

### 9. **Merge Two Sorted Arrays**
```python
def merge_sorted_arrays(arr1, arr2):
    return sorted(arr1 + arr2)

# Example Usage
arr1 = [1, 3, 5]
arr2 = [2, 4, 6]
print(merge_sorted_arrays(arr1, arr2))  # Output: [1, 2, 3, 4, 5, 6]
```

### 10. **Find the Length of the Longest Substring Without Repeating Characters**
```python
def longest_unique_substring(s):
    char_set = set()
    left = 0
    max_len = 0

    for right in range(len(s)):
        while s[right] in char_set:
            char_set.remove(s[left])
            left += 1
        char_set.add(s[right])
        max_len = max(max_len, right - left + 1)
    
    return max_len

# Example Usage
s = "abcabcbb"
print(longest_unique_substring(s))  # Output: 3
```

### 11. **Reverse a Linked List**
```python
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

def reverse_linked_list(head):
    prev = None
    current = head
    while current:
        next_node = current.next
        current.next = prev
        prev = current
        current = next_node
    return prev

# Example Usage
# Creating a simple linked list 1 -> 2 -> 3 -> None
head = ListNode(1, ListNode(2, ListNode(3)))
reversed_head = reverse_linked_list(head)

# Output the reversed linked list
while reversed_head:
    print(reversed_head.val, end=" -> ")
    reversed_head = reversed_head.next  # Output: 3 -> 2 -> 1 -> 
```

### 12. **Implement a Stack Using an Array**
```python
class Stack:
    def __init__(self):
        self.stack = []

    def push(self, val):
        self.stack.append(val)

    def pop(self):
        if not self.is_empty():
            return self.stack.pop()

    def peek(self):
        if not self.is_empty():
            return self.stack[-1]

    def is_empty(self):
        return len(self.stack) == 0

# Example Usage
stack = Stack()
stack.push(1)
stack.push(2)
print(stack.pop())  # Output: 2
print(stack.peek())  # Output: 1
```

### 13. **Implement a Queue Using an Array**
```python
class Queue:
    def __init__(self):
        self.queue = []

    def enqueue(self, val):
        self.queue.append(val)

    def dequeue(self):
        if not self.is_empty():
            return self.queue.pop(0)

    def peek(self):
        if not self.is_empty():
            return self.queue[0]

    def is_empty(self):
        return len(self.queue) == 0

# Example Usage
queue = Queue()
queue.enqueue(1)
queue.enqueue(2)
print(queue.dequeue())  # Output: 1
print(queue.peek())  # Output: 2
```

### 14. **Find the Lowest Common Ancestor in a Binary Tree**
```python
class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

def lowest_common_ancestor(root, p, q):
    if not root or root == p or root == q:
        return root
    left = lowest_common_ancestor(root.left, p, q)
    right = lowest_common_ancestor(root.right, p, q)
    if left and right:
        return root
    return left if left else right

# Example Usage
# Building a simple tree: 
#     3
#    / \
#   5   1
root = TreeNode(3)
root.left = TreeNode(5)
root.right = TreeNode(1)
p = root.left
q = root.right

print(lowest_common_ancestor(root, p, q).val)  # Output: 3
```

### 15. **Check if a Binary Tree is a Binary Search Tree**
```python
class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

def is_valid_bst(root, left=float('-inf'), right=float('inf')):
    if not root:
        return True
    if not (left < root.val < right):
        return False
    return is_valid_bst(root.left, left, root.val) and is_valid_bst(root.right, root.val, right)

# Example Usage
# Building a simple valid BST:
#     2
#    / \
#   1   3
root = TreeNode(2)
root.left = TreeNode(1)
root.right = TreeNode(3)
print(is_valid_bst(root))  # Output: True
```

### 16. **Find the Level Order Traversal of a Binary Tree**
```python
from collections import deque

class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

def level_order_traversal(root):
    if not root:
        return []
    result = []
    queue = deque([root])
    while queue:
        level = []
        for i in range(len(queue)):
            node = queue.popleft()
            level.append(node.val)
            if node.left:
                queue.append(node.left)
            if node.right:
                queue.append(node.right)
        result.append(level)
    return result

# Example Usage
# Building a simple tree:
#     3
#    / \
#   9  20
#      / \
#     15  7
root = TreeNode(3)
root.left = TreeNode(9)
root.right = TreeNode(20)
root.right.left = TreeNode(15)
root.right.right = TreeNode(7)

print(level_order_traversal(root))  # Output: [[3], [9, 20], [15, 7]]
```

### 17. **Find the Kth Largest Element in an Array**
```python
import heapq

def find_kth_largest(arr, k):
    return heapq.nlargest(k, arr)[-1]

# Example Usage
arr = [3, 2, 1, 5, 6, 4]
k = 2
print(find_kth_largest(arr, k))  # Output: 5
```
