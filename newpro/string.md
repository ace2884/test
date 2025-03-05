# **String Problems Solutions**

## **Basic String Operations**

### Check if a given string is palindrome or not
```python
def is_palindrome(s):
    return s == s[::-1]

print(is_palindrome("racecar"))
```

### Count number of vowels, consonants, spaces in a String
```python
def count_vowels_consonants_spaces(s):
    vowels = "aeiouAEIOU"
    v_count = sum(1 for c in s if c in vowels)
    c_count = sum(1 for c in s if c.isalpha() and c not in vowels)
    spaces = s.count(' ')
    return v_count, c_count, spaces

print(count_vowels_consonants_spaces("Hello World"))
```

### Find the ASCII value of a character
```python
def ascii_value(c):
    return ord(c)

print(ascii_value('A'))
```

### Remove all vowels from the string
```python
def remove_vowels(s):
    return ''.join(c for c in s if c.lower() not in "aeiou")

print(remove_vowels("Hello World"))
```

### Remove spaces from a string
```python
def remove_spaces(s):
    return s.replace(" ", "")

print(remove_spaces("Hello World"))
```

### Remove characters from a string except alphabets
```python
def remove_non_alphabets(s):
    return ''.join(c for c in s if c.isalpha())

print(remove_non_alphabets("Hello123@ World!"))
```

### Reverse a String
```python
def reverse_string(s):
    return s[::-1]

print(reverse_string("Hello"))
```

### Remove brackets from an algebraic expression
```python
def remove_brackets(expression):
    return expression.replace("(", "").replace(")", "")

print(remove_brackets("(a+b)*(c-d)"))
```

### Sum of the numbers in a String
```python
def sum_of_numbers(s):
    import re
    return sum(map(int, re.findall(r'\d+', s)))

print(sum_of_numbers("abc123xyz45"))
```

### Capitalize first and last character of each word
```python
def capitalize_first_last(s):
    words = s.split()
    return ' '.join(w[0].upper() + w[1:-1] + w[-1].upper() if len(w) > 1 else w.upper() for w in words)

print(capitalize_first_last("hello world"))
```

### Calculate frequency of characters in a string
```python
def char_frequency(s):
    from collections import Counter
    return dict(Counter(s))

print(char_frequency("hello"))
```

### Find Non-repeating characters of a String
```python
def non_repeating_chars(s):
    return [c for c in s if s.count(c) == 1]

print(non_repeating_chars("hello"))
```

### Check if two strings are anagram of each other
```python
def are_anagrams(s1, s2):
    return sorted(s1) == sorted(s2)

print(are_anagrams("listen", "silent"))
```

### Count common sub-sequence in two strings
```python
def common_subsequence_count(s1, s2):
    return sum(1 for c in s1 if c in s2)

print(common_subsequence_count("abc", "bcd"))
```

### Check if two strings match where one string contains wildcard characters
```python
def wildcard_match(s, pattern):
    import fnmatch
    return fnmatch.fnmatch(s, pattern)

print(wildcard_match("hello", "h*o"))
```

### Return maximum occurring character in the input string
```python
def max_occuring_char(s):
    from collections import Counter
    return max(Counter(s), key=Counter(s).get)

print(max_occuring_char("hello world"))
```

### Remove all duplicates from the input string
```python
def remove_duplicates(s):
    return "".join(dict.fromkeys(s))

print(remove_duplicates("banana"))
```

### Print all the duplicates in the input string
```python
def find_duplicates(s):
    from collections import Counter
    return [char for char, count in Counter(s).items() if count > 1]

print(find_duplicates("hello"))
```

### Remove characters from first string present in the second string
```python
def remove_chars(s1, s2):
    return ''.join(c for c in s1 if c not in s2)

print(remove_chars("hello world", "aeiou"))
```

### Change every letter with the next lexicographic alphabet in the given string
```python
def next_letter(s):
    return ''.join(chr(ord(c) + 1) if c.isalpha() else c for c in s)

print(next_letter("hello"))
```

### Find the largest word in a given string
```python
def largest_word(s):
    return max(s.split(), key=len)

print(largest_word("hello beautiful world"))
```

### Sort characters in a string
```python
def sort_characters(s):
    return ''.join(sorted(s))

print(sort_characters("hello"))
```

### Count number of words in a given string
```python
def word_count(s):
    return len(s.split())

print(word_count("hello world"))
```

### Find a word in a given string with the highest number of repeated letters
```python
def word_with_max_repeated_chars(s):
    words = s.split()
    return max(words, key=lambda word: max(word.count(c) for c in word))

print(word_with_max_repeated_chars("hello banana apple"))
```

### Change case of each character in a string
```python
def toggle_case(s):
    return s.swapcase()

print(toggle_case("Hello World"))
```

### Concatenate one string to another
```python
def concatenate_strings(s1, s2):
    return s1 + s2

print(concatenate_strings("Hello ", "World"))
```

### Find a substring within a string and display its starting position
```python
def find_substring(s, sub):
    return s.find(sub)

print(find_substring("hello world", "world"))
```

### Reverse words in a string
```python
def reverse_words(s):
    return ' '.join(s.split()[::-1])

print(reverse_words("hello world"))
```

This document now contains complete Python solutions for **String Problems**. Let me know if you need further modifications! 🚀

