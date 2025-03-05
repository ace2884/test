##  arrays (lists) using array/list methods and concepts. 

### 1. **Find the Maximum and Minimum in an Array**
```python
def find_max_min(arr):
    return max(arr), min(arr)

# Example usage
print(find_max_min([3, 5, 1, 9, 2]))  # Output: (9, 1)
```

### 2. **Reverse an Array**
```python
def reverse_array(arr):
    return arr[::-1]

# Example usage
print(reverse_array([1, 2, 3, 4, 5]))  # Output: [5, 4, 3, 2, 1]
```

### 3. **Find the Second Largest Element in an Array**
```python
def second_largest(arr):
    unique_arr = list(set(arr))  # Remove duplicates
    unique_arr.sort()
    return unique_arr[-2] if len(unique_arr) > 1 else None

# Example usage
print(second_largest([5, 3, 9, 1, 9]))  # Output: 5
```

### 4. **Check if an Array is Sorted**
```python
def is_sorted(arr):
    return arr == sorted(arr)

# Example usage
print(is_sorted([1, 2, 3, 4, 5]))  # Output: True
print(is_sorted([1, 3, 2, 5, 4]))  # Output: False
```

### 5. **Find the Sum of All Elements in an Array**
```python
def sum_array(arr):
    return sum(arr)

# Example usage
print(sum_array([1, 2, 3, 4]))  # Output: 10
```

### 6. **Find the Product of All Elements in an Array**
```python
from functools import reduce

def product_array(arr):
    return reduce(lambda x, y: x * y, arr)

# Example usage
print(product_array([1, 2, 3, 4]))  # Output: 24
```

### 7. **Find the Frequency of Each Element in an Array**
```python
from collections import Counter

def frequency_of_elements(arr):
    return dict(Counter(arr))

# Example usage
print(frequency_of_elements([1, 2, 2, 3, 3, 3]))  # Output: {1: 1, 2: 2, 3: 3}
```

### 8. **Rotate an Array to the Left by K Positions**
```python
def rotate_left(arr, k):
    k = k % len(arr)
    return arr[k:] + arr[:k]

# Example usage
print(rotate_left([1, 2, 3, 4, 5], 2))  # Output: [3, 4, 5, 1, 2]
```

### 9. **Rotate an Array to the Right by K Positions**
```python
def rotate_right(arr, k):
    k = k % len(arr)
    return arr[-k:] + arr[:-k]

# Example usage
print(rotate_right([1, 2, 3, 4, 5], 2))  # Output: [4, 5, 1, 2, 3]
```

### 10. **Find All Pairs in an Array Whose Sum is Equal to a Given Number**
```python
def find_pairs(arr, target):
    pairs = []
    seen = set()
    for num in arr:
        diff = target - num
        if diff in seen:
            pairs.append((diff, num))
        seen.add(num)
    return pairs

# Example usage
print(find_pairs([1, 2, 3, 4, 5], 6))  # Output: [(2, 4), (1, 5)]
```

### 11. **Remove Duplicates from an Array**
```python
def remove_duplicates(arr):
    return list(set(arr))

# Example usage
print(remove_duplicates([1, 2, 2, 3, 4, 4, 5]))  # Output: [1, 2, 3, 4, 5]
```

### 12. **Find the Intersection of Two Arrays**
```python
def intersection(arr1, arr2):
    return list(set(arr1) & set(arr2))

# Example usage
print(intersection([1, 2, 3, 4], [3, 4, 5, 6]))  # Output: [3, 4]
```

### 13. **Find the Union of Two Arrays**
```python
def union(arr1, arr2):
    return list(set(arr1) | set(arr2))

# Example usage
print(union([1, 2, 3], [3, 4, 5]))  # Output: [1, 2, 3, 4, 5]
```

### 14. **Move All Zeros to the End of an Array**
```python
def move_zeros(arr):
    return [num for num in arr if num != 0] + [0] * arr.count(0)

# Example usage
print(move_zeros([0, 1, 0, 3, 12]))  # Output: [1, 3, 12, 0, 0]
```

### 15. **Find the Missing Number in a Consecutive Sequence**
```python
def find_missing_number(arr):
    n = len(arr) + 1
    total_sum = n * (n + 1) // 2
    return total_sum - sum(arr)

# Example usage
print(find_missing_number([1, 2, 4, 5, 6]))  # Output: 3
```

### 16. **Find the Duplicates in an Array**
```python
def find_duplicates(arr):
    return [item for item in set(arr) if arr.count(item) > 1]

# Example usage
print(find_duplicates([1, 2, 3, 4, 4, 5, 5, 6]))  # Output: [4, 5]
```

### 17. **Merge Two Sorted Arrays**
```python
def merge_sorted_arrays(arr1, arr2):
    return sorted(arr1 + arr2)

# Example usage
print(merge_sorted_arrays([1, 3, 5], [2, 4, 6]))  # Output: [1, 2, 3, 4, 5, 6]
```

### 18. **Check if an Array is a Subset of Another Array**
```python
def is_subset(arr1, arr2):
    return set(arr1).issubset(set(arr2))

# Example usage
print(is_subset([1, 2], [1, 2, 3, 4]))  # Output: True
print(is_subset([1, 5], [1, 2, 3, 4]))  # Output: False
```

### 19. **Find the Maximum Product of Two Integers in an Array**
```python
def max_product(arr):
    arr.sort()
    return max(arr[0] * arr[1], arr[-1] * arr[-2])

# Example usage
print(max_product([1, 10, -5, 1, -100]))  # Output: 500
```

### 20. **Find the Length of the Longest Subarray with a Given Sum**
```python
def longest_subarray(arr, target_sum):
    prefix_sum = 0
    sum_map = {}
    max_len = 0

    for i in range(len(arr)):
        prefix_sum += arr[i]

        if prefix_sum == target_sum:
            max_len = i + 1

        if prefix_sum - target_sum in sum_map:
            max_len = max(max_len, i - sum_map[prefix_sum - target_sum])

        if prefix_sum not in sum_map:
            sum_map[prefix_sum] = i

    return max_len

# Example usage
print(longest_subarray([1, -1, 5, -2, 3], 3))  # Output: 4
```
