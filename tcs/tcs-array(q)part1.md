
# **1. Array Problems**

## **Basic Operations**

- **Find the smallest number in an array**
```python
def find_smallest(arr):
    return min(arr)
```

- **Find the largest number in an array**
```python
def find_largest(arr):
    return max(arr)
```

- **Second Smallest and Second Largest element in an array**
```python
def second_smallest_largest(arr):
    unique_sorted = sorted(set(arr))
    if len(unique_sorted) < 2:
        return None, None
    return unique_sorted[1], unique_sorted[-2]
```

- **Reverse a given array**
```python
def reverse_array(arr):
    return arr[::-1]
```

- **Count frequency of each element in an array**
```python
from collections import Counter

def count_frequency(arr):
    return dict(Counter(arr))
```

- **Rearrange array in increasing-decreasing order**
```python
def rearrange_inc_dec(arr):
    arr.sort()
    return arr[:len(arr)//2] + arr[len(arr)//2:][::-1]
```

- **Calculate sum of the elements of the array**
```python
def sum_of_elements(arr):
    return sum(arr)
```

- **Rotate array by K elements – Block Swap Algorithm**
```python
def rotate_array(arr, k):
    k = k % len(arr)
    return arr[k:] + arr[:k]
```

- **Average of all elements in an array**
```python
def average_array(arr):
    return sum(arr) / len(arr)
```

- **Find the median of the given array**
```python
def median_array(arr):
    arr.sort()
    mid = len(arr) // 2
    return (arr[mid] + arr[mid - 1]) / 2 if len(arr) % 2 == 0 else arr[mid]
```

- **Remove duplicates from a sorted array**
```python
def remove_duplicates_sorted(arr):
    return list(dict.fromkeys(arr))
```

- **Remove duplicates from an unsorted array**
```python
def remove_duplicates_unsorted(arr):
    return list(set(arr))
```

- **Adding Element in an array**
```python
def add_element(arr, element):
    arr.append(element)
    return arr
```

## **Advanced Operations**

- **Find all repeating elements in an array**
```python
def find_repeating(arr):
    freq = Counter(arr)
    return [key for key, value in freq.items() if value > 1]
```

- **Find all non-repeating elements in an array**
```python
def find_non_repeating(arr):
    freq = Counter(arr)
    return [key for key, value in freq.items() if value == 1]
```

- **Find all symmetric pairs in an array**
```python
def find_symmetric_pairs(pairs):
    seen = set()
    symmetric = []
    for x, y in pairs:
        if (y, x) in seen:
            symmetric.append((x, y))
        seen.add((x, y))
    return symmetric
```

- **Maximum product subarray in an array**
```python
from functools import reduce

def max_product_subarray(arr):
    max_product = float('-inf')
    for i in range(len(arr)):
        for j in range(i, len(arr)):
            product = reduce(lambda x, y: x * y, arr[i:j+1], 1)
            max_product = max(max_product, product)
    return max_product
```

- **Replace each element of the array by its rank in the array**
```python
def replace_by_rank(arr):
    rank = {val: idx + 1 for idx, val in enumerate(sorted(set(arr)))}
    return [rank[num] for num in arr]
```

- **Sorting elements of an array by frequency**
```python
def sort_by_frequency(arr):
    freq = Counter(arr)
    return sorted(arr, key=lambda x: (-freq[x], x))
```

- **Rotation of elements of array - left and right**
```python
def left_rotate(arr, k):
    k %= len(arr)
    return arr[k:] + arr[:k]

def right_rotate(arr, k):
    k %= len(arr)
    return arr[-k:] + arr[:-k]
```

- **Finding equilibrium index of an array**
```python
def find_equilibrium(arr):
    total_sum = sum(arr)
    left_sum = 0
    for i, num in enumerate(arr):
        if left_sum == (total_sum - left_sum - num):
            return i
        left_sum += num
    return -1
```

- **Finding Circular rotation of an array by K positions**
```python
def circular_rotate(arr, k):
    k %= len(arr)
    return arr[-k:] + arr[:-k]
```

- **Sort an array according to the order defined by another array**
```python
def sort_by_other(arr1, arr2):
    order = {val: idx for idx, val in enumerate(arr2)}
    return sorted(arr1, key=lambda x: order.get(x, float('inf')))
```

- **Search an element in an array**
```python
def search_element(arr, target):
    return arr.index(target) if target in arr else -1
```

- **Check if an Array is a subset of another array or not**
```python
def is_subset(arr1, arr2):
    return set(arr2).issubset(set(arr1))
```





