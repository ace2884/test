# accenture codes


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

## string manipulation using built-in string methods:

### 1. **Check if a String is a Palindrome**

A palindrome is a string that reads the same forward and backward.

```python
def is_palindrome(s):
    # Converting the string to lowercase and removing non-alphanumeric characters
    cleaned_str = ''.join(filter(str.isalnum, s.lower()))
    return cleaned_str == cleaned_str[::-1]

# Example usage
print(is_palindrome("Madam"))          # Output: True
print(is_palindrome("Hello"))          # Output: False
```

### 2. **Count the Number of Vowels and Consonants**
This program counts the number of vowels and consonants in a given string.

```python
def count_vowels_consonants(s):
    vowels = "aeiouAEIOU"
    s = s.replace(" ", "")  # Ignore spaces
    vowel_count = sum(1 for char in s if char in vowels)
    consonant_count = len([char for char in s if char.isalpha() and char not in vowels])
    return vowel_count, consonant_count

# Example usage
vowels, consonants = count_vowels_consonants("Hello World")
print(f"Vowels: {vowels}, Consonants: {consonants}")
# Output: Vowels: 3, Consonants: 7
```

### 3. **Check if Two Strings are Anagrams**
Two strings are anagrams if they have the same characters with the same frequency.

```python
def are_anagrams(str1, str2):
    return sorted(str1.lower()) == sorted(str2.lower())

# Example usage
print(are_anagrams("Listen", "Silent"))  # Output: True
print(are_anagrams("Hello", "World"))    # Output: False
```

### 4. **Find the Longest Word in a Sentence**
This program finds the longest word in a given sentence.

```python
def longest_word(sentence):
    words = sentence.split()
    longest = max(words, key=len)
    return longest

# Example usage
print(longest_word("Find the longest word in this sentence"))  # Output: "sentence"
```

### 5. **Capitalize the First Letter of Each Word**
This program capitalizes the first letter of each word in a string.

```python
def capitalize_words(s):
    return s.title()

# Example usage
print(capitalize_words("hello world, welcome to python!"))  # Output: "Hello World, Welcome To Python!"
```

### 6. **Count the Frequency of Each Character in a String**
This program counts how often each character appears in a string.

```python
from collections import Counter

def char_frequency(s):
    return dict(Counter(s))

# Example usage
print(char_frequency("helloworld"))
# Output: {'h': 1, 'e': 1, 'l': 3, 'o': 2, 'w': 1, 'r': 1, 'd': 1}
```

### 7. **Replace All Occurrences of a Substring**
This program replaces all occurrences of a substring with another substring.

```python
def replace_substring(s, old, new):
    return s.replace(old, new)

# Example usage
print(replace_substring("Hello World", "World", "Python"))  # Output: "Hello Python"
```

### 8. **Reverse Each Word in a Sentence**
This program reverses each word in a given sentence while keeping the word order intact.

```python
def reverse_each_word(s):
    return ' '.join(word[::-1] for word in s.split())

# Example usage
print(reverse_each_word("Hello World"))  # Output: "olleH dlroW"
```

### 9. **Check if a String is a Substring of Another String**
This program checks if one string is a substring of another.

```python
def is_substring(sub, full):
    return sub in full

# Example usage
print(is_substring("World", "Hello World"))  # Output: True
print(is_substring("Python", "Hello World"))  # Output: False
```





### 1. **Reverse a String**
```python
def reverse_string(s):
    return s[::-1]

print(reverse_string("Hello World"))  # Output: dlroW olleH
```

### 2. **Check if a String is a Palindrome**
```python
def is_palindrome(s):
    return s == s[::-1]

print(is_palindrome("radar"))  # Output: True
print(is_palindrome("hello"))  # Output: False
```

### 3. **Count Vowels and Consonants in a String**
```python
def count_vowels_consonants(s):
    vowels = "aeiouAEIOU"
    v_count = sum(1 for char in s if char in vowels)
    c_count = sum(1 for char in s if char.isalpha() and char not in vowels)
    return v_count, c_count

print(count_vowels_consonants("Hello World"))  # Output: (3, 7)
```

### 4. **Check if Two Strings are Anagrams**
```python
def are_anagrams(s1, s2):
    return sorted(s1) == sorted(s2)

print(are_anagrams("listen", "silent"))  # Output: True
print(are_anagrams("hello", "world"))   # Output: False
```

### 5. **Remove Duplicates from a String**
```python
def remove_duplicates(s):
    return "".join(sorted(set(s), key=s.index))

print(remove_duplicates("programming"))  # Output: progamin
```

### 6. **Find the Longest Word in a Sentence**
```python
def longest_word(sentence):
    words = sentence.split()
    return max(words, key=len)

print(longest_word("Find the longest word in this sentence"))  # Output: sentence
```

### 7. **Count the Frequency of Each Character**
```python
from collections import Counter

def char_frequency(s):
    return dict(Counter(s))

print(char_frequency("mississippi"))  # Output: {'m': 1, 'i': 4, 's': 4, 'p': 2}
```

### 8. **Convert a String to Title Case**
```python
def to_title_case(s):
    return s.title()

print(to_title_case("hello world"))  # Output: Hello World
```

### 9. **Check if a String Contains Only Digits**
```python
def is_digit_only(s):
    return s.isdigit()

print(is_digit_only("12345"))  # Output: True
print(is_digit_only("12abc"))  # Output: False
```

### 10. **Find All Substrings of a String**
```python
def all_substrings(s):
    return [s[i:j] for i in range(len(s)) for j in range(i + 1, len(s) + 1)]

print(all_substrings("abc"))  # Output: ['a', 'ab', 'abc', 'b', 'bc', 'c']
```

### 11. **Check if a String is a Valid Email Address**
```python
import re

def is_valid_email(email):
    pattern = r'^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$'
    return re.match(pattern, email) is not None

print(is_valid_email("test@example.com"))  # Output: True
print(is_valid_email("test.com"))         # Output: False
```

### 12. **Count Words in a Sentence**
```python
def word_count(sentence):
    return len(sentence.split())

print(word_count("Count the number of words"))  # Output: 5
```

### 13. **Replace All Spaces with Hyphens**
```python
def replace_spaces(s):
    return s.replace(" ", "-")

print(replace_spaces("hello world"))  # Output: hello-world
```

### 14. **Find the First Non-Repeating Character**
```python
def first_non_repeating(s):
    for char in s:
        if s.count(char) == 1:
            return char
    return None

print(first_non_repeating("swiss"))  # Output: w
```

### 15. **Check if a String is a Substring of Another String**
```python
def is_substring(s1, s2):
    return s1 in s2

print(is_substring("abc", "abcdef"))  # Output: True
print(is_substring("xyz", "abcdef"))  # Output: False
```

### 16. **Check if a String is Alphanumeric**
```python
def is_alphanumeric(s):
    return s.isalnum()

print(is_alphanumeric("abc123"))  # Output: True
print(is_alphanumeric("abc 123"))  # Output: False
```

### 17. **Reverse Each Word in a Sentence**
```python
def reverse_each_word(sentence):
    return " ".join(word[::-1] for word in sentence.split())

print(reverse_each_word("hello world"))  # Output: olleh dlrow
```

### 18. **Check if a String Has Balanced Parentheses**
```python
def is_balanced(s):
    stack = []
    for char in s:
        if char in "({[":
            stack.append(char)
        elif char in ")}]":
            if not stack or stack[-1] + char not in ["()", "{}", "[]"]:
                return False
            stack.pop()
    return not stack

print(is_balanced("{[()]}"))  # Output: True
print(is_balanced("{[(])}"))  # Output: False
```

### 19. **Convert a String to a List of Characters**
```python
def string_to_list(s):
    return list(s)

print(string_to_list("hello"))  # Output: ['h', 'e', 'l', 'l', 'o']
```

### 20. **Find the Most Frequent Character in a String**
```python
def most_frequent_char(s):
    return max(s, key=s.count)

print(most_frequent_char("aabbbccde"))  # Output: b
```

These programs cover a range of essential string operations, each showcasing important string methods and concepts commonly used in Python coding interviews.

# string methods

Here is a list of 20 common string problems that are frequently asked in interviews, along with the string methods and functions you can practice in Python:

### 1. **Reverse a String**
   - Problem: Reverse the input string.
   - Example: `"hello" -> "olleh"`
   - Methods: `.join()`, slicing `[::-1]`

### 2. **Check if a String is a Palindrome**
   - Problem: Determine if a string reads the same forward and backward.
   - Example: `"racecar" -> True`
   - Methods: Slicing `[::-1]`

### 3. **Count the Number of Vowels and Consonants in a String**
   - Problem: Count the vowels and consonants in a given string.
   - Example: `"hello" -> 2 vowels, 3 consonants`
   - Methods: `for`, `in`, `lower()`

### 4. **Find the First Non-Repeating Character in a String**
   - Problem: Find the first character in a string that doesn’t repeat.
   - Example: `"swiss" -> "w"`
   - Methods: `collections.Counter`, loops

### 5. **Check if Two Strings are Anagrams**
   - Problem: Check if two strings are anagrams of each other.
   - Example: `"listen", "silent" -> True`
   - Methods: `sorted()`, `collections.Counter`

### 6. **Longest Common Prefix Among a List of Strings**
   - Problem: Find the longest common prefix among a group of strings.
   - Example: `["flower", "flow", "flight"] -> "fl"`
   - Methods: `min()`, `max()`, slicing

### 7. **Remove Duplicates from a String**
   - Problem: Remove duplicate characters in a string.
   - Example: `"programming" -> "progamin"`
   - Methods: `set()`, `join()`

### 8. **Check if a String is a Substring of Another**
   - Problem: Determine if one string is a substring of another.
   - Example: `"hello", "ell" -> True`
   - Methods: `in`, `find()`

### 9. **Replace Spaces with %20 (URL Encoding)**
   - Problem: Replace spaces in a string with `%20`.
   - Example: `"Mr John Smith" -> "Mr%20John%20Smith"`
   - Methods: `replace()`

### 10. **Find the Most Frequent Character in a String**
   - Problem: Find the character that appears the most in the string.
   - Example: `"mississippi" -> "i"`
   - Methods: `collections.Counter`

### 11. **Convert a String to Title Case**
   - Problem: Capitalize the first letter of every word in a string.
   - Example: `"hello world" -> "Hello World"`
   - Methods: `title()`, `split()`, `join()`

### 12. **Find All Permutations of a String**
   - Problem: Generate all possible permutations of a string.
   - Example: `"abc" -> ["abc", "acb", "bac", "bca", "cab", "cba"]`
   - Methods: `itertools.permutations`

### 13. **Check if a String Contains Only Digits**
   - Problem: Verify if a string consists only of digits.
   - Example: `"12345" -> True`, `"123a45" -> False`
   - Methods: `isdigit()`

### 14. **Find the Longest Palindromic Substring**
   - Problem: Find the longest substring in a string that is a palindrome.
   - Example: `"babad" -> "bab" or "aba"`
   - Methods: `expand around center`, dynamic programming

### 15. **Find the Length of the Longest Substring Without Repeating Characters**
   - Problem: Find the longest substring without repeating characters.
   - Example: `"abcabcbb" -> 3 (substring "abc")`
   - Methods: `sliding window`, `set()`

### 16. **Check if Two Strings are Rotations of Each Other**
   - Problem: Check if one string is a rotation of another string.
   - Example: `"abcde", "cdeab" -> True`
   - Methods: `in`, string concatenation

### 17. **Remove All Occurrences of a Character in a String**
   - Problem: Remove a specified character from the string.
   - Example: `"hello", "l" -> "heo"`
   - Methods: `replace()`, `filter()`

### 18. **Find the Length of the Last Word in a Sentence**
   - Problem: Return the length of the last word in a string.
   - Example: `"Hello World" -> 5`
   - Methods: `split()`, `strip()`

### 19. **Check if a String is a Valid Parentheses Sequence**
   - Problem: Determine if the string has valid parentheses.
   - Example: `"()[]{}" -> True`, `"(]" -> False`
   - Methods: Stack, `dict`, loops

### 20. **Remove All Non-Alphanumeric Characters from a String**
   - Problem: Clean up a string by removing non-alphanumeric characters.
   - Example: `"a@b#c$d!" -> "abcd"`
   - Methods: `isalnum()`, `filter()`, `re.sub()`

     
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



