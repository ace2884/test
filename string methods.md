

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

     



