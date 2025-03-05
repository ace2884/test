
# **Number System Conversions**

### Convert Binary to Decimal
```python
def binary_to_decimal(binary):
    return int(binary, 2)

print(binary_to_decimal("1010"))
```

### Convert Binary to Octal
```python
def binary_to_octal(binary):
    return oct(int(binary, 2))[2:]

print(binary_to_octal("1010"))
```

### Convert Decimal to Binary
```python
def decimal_to_binary(decimal):
    return bin(decimal)[2:]

print(decimal_to_binary(10))
```

### Convert Decimal to Octal
```python
def decimal_to_octal(decimal):
    return oct(decimal)[2:]

print(decimal_to_octal(10))
```

### Convert Octal to Binary
```python
def octal_to_binary(octal):
    return bin(int(octal, 8))[2:]

print(octal_to_binary("12"))
```

### Convert Octal to Decimal
```python
def octal_to_decimal(octal):
    return int(octal, 8)

print(octal_to_decimal("12"))
```

### Convert Digits/Numbers to Words
```python
def number_to_words(n):
    from num2words import num2words
    return num2words(n)

print(number_to_words(123))
```


