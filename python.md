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

**This simple program automates the plotting for linear and quadratic function for now**


```python
import numpy as np
import matplotlib.pyplot as plt
import sys
def linear(m,c):
    x=np.linspace(-20, 20)
    y=m*x+c
    plt.plot(x,y, color = 'orchid', marker = '.')
    plt.xlabel('x')
    plt.ylabel('y')
    plt.title('Plot of y={}x+{}'.format(m,c))
    plt.show()

def quadratic(a,b,c):
    x=np.linspace(-20,20)
    y=a*x**2+b*x+c
    plt.plot(x,y, color = 'black', marker = '.')
    plt.xlabel('x')
    plt.ylabel('y')
    plt.title('Plot of y={}x^2+{}x+{}'.format(a,b,c))
    plt.show()
running = True
while running:
    print("What do you want to plot?")
    print('1) Linear function     2) Quadratic function     3)None')
    x = input(">> ")
    if x == "1":
        m=float(input('Enter slope: '))
        c=float(input('Enter y-intercept: '))
        linear(m,c)
        sys.exit(0)
              
    elif x == "2":
        a=float(input('Enter a: '))
        b=float(input('Enter b: '))
        c=float(input('Enter c: '))
        quadratic(a,b,c)
        sys.exit(0)
        
        
    elif x =='3':
        running = False
    else:
        print('Please try again!!!')
print('Program ending')

```





