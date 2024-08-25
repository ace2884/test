accenture codes
```
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

```
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

```
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

