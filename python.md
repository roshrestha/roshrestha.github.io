---
layout: page
title: Python
---
**In this program I will create a function that takes a list of non-negative integers and strings and returns a new list with the strings filtered out**


```python
def filter_list(l):
    a = []

    for i in l:
        if not isinstance(i,str):
            a.append(i)
    return a

```


```python
filter_list([1,2,'aasf','1','123',123])
```




    [1, 2, 123]

**In this program, we are required to, given a string, replace every letter with its position in the alphabet.
If anything in the text isn't a letter, we have to ignore it and don't return it.**


```python
def alphabet_position(text):
    result = ''
    alpha = list('abcdefghijklmnopqrstuvwxyz')
    for i in text:
        if i.isalpha():
            i=i.lower()
            result=result+str(alpha.index(i)+1)+' '
    return result[0:-1]
```


```python
alphabet_position('I am Roshan Shrestha')
```




    '9 1 13 18 15 19 8 1 14 19 8 18 5 19 20 8 1'
    
**Complete the solution so that it splits the string into pairs of two characters. If the string contains an odd number of characters then it should replace the missing second character of the final pair with an underscore ('_').**

Examples:

solution('abc') should return ['ab', 'c_']  
solution('abcdef') should return ['ab', 'cd', 'ef']  

My solution  
```python
def solution(s):
    if len(s) % 2==0:
        b =[s[i:i+2] for i in range(0,len(s),2)]
    else:
        s+='_'
        b =[s[i:i+2] for i in range(0,len(s),2)]
    return b
    
```


```python
solution('abc')
```


