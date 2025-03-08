# **Number Problems Solutions**

## **Basic Number Checks**

### Check if a number is palindrome or not
```python
def is_palindrome(n):
    return str(n) == str(n)[::-1]

num = 121
print(is_palindrome(num))
```

### Find all Palindrome numbers in a given range
```python
def palindromes_in_range(start, end):
    return [num for num in range(start, end+1) if str(num) == str(num)[::-1]]

print(palindromes_in_range(10, 200))
```

### Check if a number is prime or not
```python
def is_prime(n):
    if n < 2:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True

print(is_prime(17))
```

### Find prime numbers in a given range
```python
def prime_numbers_in_range(start, end):
    return [num for num in range(start, end+1) if is_prime(num)]

print(prime_numbers_in_range(10, 50))
```

### Check if a number is an Armstrong number
```python
def is_armstrong(n):
    return sum(int(digit) ** len(str(n)) for digit in str(n)) == n

print(is_armstrong(153))
```

### Check if a number is a perfect number
```python
def is_perfect(n):
    return sum(i for i in range(1, n) if n % i == 0) == n

print(is_perfect(28))
```

### Check if a number is even or odd
```python
num = 7
print("Even" if num % 2 == 0 else "Odd")
```

### Check whether a given number is positive or negative
```python
num = -5
print("Positive" if num > 0 else "Negative")
```

### Sum of first N natural numbers
```python
def sum_natural(n):
    return n * (n + 1) // 2

print(sum_natural(10))
```

### Find Sum of AP Series
```python
def sum_ap(a, d, n):
    return (n / 2) * (2 * a + (n - 1) * d)

print(sum_ap(1, 2, 5))
```

### Find Sum of GP Series
```python
def sum_gp(a, r, n):
    return a * (1 - r ** n) // (1 - r) if r != 1 else a * n

print(sum_gp(2, 3, 4))
```

### Greatest of two numbers
```python
def greatest_of_two(a, b):
    return max(a, b)

print(greatest_of_two(10, 20))
```

### Greatest of three numbers
```python
def greatest_of_three(a, b, c):
    return max(a, b, c)

print(greatest_of_three(10, 20, 15))
```

### Leap Year or not
```python
def is_leap_year(year):
    return year % 4 == 0 and (year % 100 != 0 or year % 400 == 0)

print(is_leap_year(2024))
```

### Reverse digits of a number
```python
def reverse_number(n):
    return int(str(n)[::-1])

print(reverse_number(12345))
```

### Maximum and Minimum digit in a number
```python
def max_min_digit(n):
    digits = [int(d) for d in str(n)]
    return max(digits), min(digits)

print(max_min_digit(42968))
```

### Print Fibonacci up to Nth term
```python
def fibonacci(n):
    a, b = 0, 1
    for _ in range(n):
        print(a, end=" ")
        a, b = b, a + b

fibonacci(10)
```

### Factorial of a number
```python
def factorial(n):
    return 1 if n == 0 else n * factorial(n - 1)

print(factorial(5))
```

### Power of a number
```python
def power(x, y):
    return x ** y

print(power(2, 3))
```

### Factors of a given number
```python
def factors(n):
    return [i for i in range(1, n + 1) if n % i == 0]

print(factors(12))
```

### Print all prime factors of the given number
```python
def prime_factors(n):
    i = 2
    factors = []
    while i * i <= n:
        if n % i:
            i += 1
        else:
            n //= i
            factors.append(i)
    if n > 1:
        factors.append(n)
    return factors

print(prime_factors(56))
```

### Check if a number is a strong number or not
```python
def is_strong(n):
    return sum(factorial(int(digit)) for digit in str(n)) == n

print(is_strong(145))
```

### Check if a number is Automorphic
```python
def is_automorphic(n):
    return str(n**2).endswith(str(n))

print(is_automorphic(25))
```

### GCD of two numbers
```python
import math
print(math.gcd(48, 18))
```

### LCM of two numbers
```python
def lcm(a, b):
    return abs(a * b) // math.gcd(a, b)

print(lcm(12, 18))
```

### Check if a number is Harshad number
```python
def is_harshad(n):
    return n % sum(int(digit) for digit in str(n)) == 0

print(is_harshad(18))
```

### Check if the number is abundant number
```python
def is_abundant(n):
    return sum(i for i in range(1, n) if n % i == 0) > n

print(is_abundant(12))
```

### Sum of digits of a number
```python
def sum_of_digits(n):
    return sum(int(digit) for digit in str(n))

print(sum_of_digits(1234))
```

### Sum of numbers in the given range
```python
def sum_range(start, end):
    return sum(range(start, end + 1))

print(sum_range(1, 10))
```

### Find permutations where N people occupy R seats
```python
def permutations(n, r):
    from math import factorial
    return factorial(n) // factorial(n - r)

print(permutations(5, 3))
```

### Add two fractions
```python
def add_fractions(n1, d1, n2, d2):
    from math import gcd
    num = n1 * d2 + n2 * d1
    den = d1 * d2
    common = gcd(num, den)
    return num // common, den // common

print(add_fractions(1, 2, 1, 3))
```

### Replace all 0s with 1s in a given integer
```python
def replace_zeros(n):
    return int(str(n).replace('0', '1'))

print(replace_zeros(102030))
```

### Check if a number can be expressed as a sum of two prime numbers
```python
def is_prime(n):
    if n < 2:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True

def can_be_sum_of_two_primes(n):
    for i in range(2, n):
        if is_prime(i) and is_prime(n - i):
            return True
    return False

print(can_be_sum_of_two_primes(34))
```

### Calculate the area of a circle
```python
def circle_area(radius):
    from math import pi
    return pi * radius * radius

print(circle_area(5))
```

### Find roots of a Quadratic Equation
```python
def quadratic_roots(a, b, c):
    from math import sqrt
    d = b**2 - 4*a*c
    if d < 0:
        return "No Real Roots"
    elif d == 0:
        return -b / (2*a)
    else:
        root1 = (-b + sqrt(d)) / (2*a)
        root2 = (-b - sqrt(d)) / (2*a)
        return root1, root2

print(quadratic_roots(1, -3, 2))
```



