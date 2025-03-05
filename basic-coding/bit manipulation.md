## bit manipulation techniques:

### 1. **Check if a Number is Even or Odd**
```python
def is_even(n):
    return (n & 1) == 0

# Example
print(is_even(4))  # Output: True
print(is_even(7))  # Output: False
```

### 2. **Get the ith Bit of a Number**
```python
def get_ith_bit(n, i):
    return (n >> i) & 1

# Example
print(get_ith_bit(5, 0))  # Output: 1 (binary: 101)
print(get_ith_bit(5, 1))  # Output: 0
```

### 3. **Set the ith Bit of a Number**
```python
def set_ith_bit(n, i):
    return n | (1 << i)

# Example
print(set_ith_bit(5, 1))  # Output: 7 (binary: 111)
```

### 4. **Clear the ith Bit of a Number**
```python
def clear_ith_bit(n, i):
    return n & ~(1 << i)

# Example
print(clear_ith_bit(5, 2))  # Output: 1 (binary: 001)
```

### 5. **Toggle the ith Bit of a Number**
```python
def toggle_ith_bit(n, i):
    return n ^ (1 << i)

# Example
print(toggle_ith_bit(5, 0))  # Output: 4 (binary: 100)
```

### 6. **Count the Number of Set Bits (Hamming Weight)**
```python
def count_set_bits(n):
    count = 0
    while n:
        count += n & 1
        n >>= 1
    return count

# Example
print(count_set_bits(5))  # Output: 2 (binary: 101)
```

### 7. **Check if a Number is a Power of Two**
```python
def is_power_of_two(n):
    return n > 0 and (n & (n - 1)) == 0

# Example
print(is_power_of_two(8))  # Output: True
print(is_power_of_two(10)) # Output: False
```

### 8. **Find the Only Non-Repeating Element in an Array (XOR)**
```python
def find_single_element(arr):
    result = 0
    for num in arr:
        result ^= num
    return result

# Example
print(find_single_element([2, 3, 2, 4, 3]))  # Output: 4
```

### 9. **Swap Two Numbers without Using a Temporary Variable**
```python
def swap(a, b):
    a = a ^ b
    b = a ^ b
    a = a ^ b
    return a, b

# Example
a, b = 3, 5
a, b = swap(a, b)
print(a, b)  # Output: 5 3
```

### 10. **Find the Rightmost Set Bit**
```python
def rightmost_set_bit(n):
    return n & -n

# Example
print(rightmost_set_bit(18))  # Output: 2 (binary: 10)
```

### 11. **Clear All Bits from LSB to ith Bit**
```python
def clear_bits_up_to_i(n, i):
    mask = ~((1 << (i + 1)) - 1)
    return n & mask

# Example
print(clear_bits_up_to_i(29, 2))  # Output: 24 (binary: 11000)
```

### 12. **Clear All Bits from MSB to ith Bit**
```python
def clear_bits_from_msb_to_i(n, i):
    mask = (1 << (i + 1)) - 1
    return n & mask

# Example
print(clear_bits_from_msb_to_i(29, 2))  # Output: 5 (binary: 101)
```

### 13. **Check if a Number is Odd Using Bitwise AND**
```python
def is_odd(n):
    return n & 1 == 1

# Example
print(is_odd(5))  # Output: True
print(is_odd(8))  # Output: False
```

### 14. **Turn Off the Rightmost 1-Bit**
```python
def turn_off_rightmost_bit(n):
    return n & (n - 1)

# Example
print(turn_off_rightmost_bit(10))  # Output: 8 (binary: 1000)
```

### 15. **Find XOR of All Numbers from 1 to n**
```python
def xor_upto_n(n):
    if n % 4 == 0:
        return n
    elif n % 4 == 1:
        return 1
    elif n % 4 == 2:
        return n + 1
    else:
        return 0

# Example
print(xor_upto_n(7))  # Output: 0
```

### 16. **Check if Two Numbers Have Opposite Signs**
```python
def have_opposite_signs(a, b):
    return (a ^ b) < 0

# Example
print(have_opposite_signs(4, -2))  # Output: True
print(have_opposite_signs(4, 2))   # Output: False
```

### 17. **Determine the Sign of a Number**
```python
def sign(n):
    return 1 if n > 0 else -1 if n < 0 else 0

# Example
print(sign(5))   # Output: 1
print(sign(-3))  # Output: -1
print(sign(0))   # Output: 0
```

### 18. **Multiply a Number by 2 Using Bitwise Shift**
```python
def multiply_by_two(n):
    return n << 1

# Example
print(multiply_by_two(7))  # Output: 14
```

### 19. **Divide a Number by 2 Using Bitwise Shift**
```python
def divide_by_two(n):
    return n >> 1

# Example
print(divide_by_two(7))  # Output: 3
```

### 20. **Reverse Bits of an Integer**
```python
def reverse_bits(n):
    result = 0
    for i in range(32):
        result = (result << 1) | (n & 1)
        n >>= 1
    return result

# Example
print(reverse_bits(43261596))  # Output: 964176192
```
