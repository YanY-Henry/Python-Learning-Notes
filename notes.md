# CSCI2040: Introduction to Python
YAN Yuhang, Fall 2023
## 0. Introduction
```python
# Input and output
new_name = input("Please enter a name: ") # enter a name and assign it 
age = int(input("Enter the age of the person above: "))
print("hello world !!")
print("I love " + new_name + ", I believe he is ", age, "years old.")
print("BTW I guess CSCI" + "2040" + " will be boring")
```
```text
Please enter a name: Henry
Enter the age of the person above: 21
hello world !!
I love Henry, I believe he is 21 years old.
BTW I guess CSCI2040 will be boring
```
## 1. Variables, Strings, and Numbers
### 1.1 Variables
Naming rules: 小写+下划线
```python
print( "Hello world" )      # Hello world
message = "Hello world"
print( message )            # Hello world
msg = ", yyh!"
print( message , msg )      # Hello world , yyh!    *会被空格分隔
```
```text
# Reserved Words
False       class       finally     is          return
None        continue    for         lambda      try
True        def         from        nonlocal    while
and         del         global      not         with
as          elif        if          or          yield
assert      else        import      pass
break       except      in          raise
```
### 1.2 Strings
#### 1.2.1 Changing cases for the string
```python
word = 'abcDE'
word.title()    # 'AbcDE'
word.upper()    # 'ABCDE'
word.lower()    # 'abcde'
```
#### 1.2.2 Combine strings - Concatenation（串联）
```python
first_name = 'Henry'
last_name = 'YAN'
full_name = first_name + ' ' + last_name    # 'Henry YAN'
full_name_wrong = first_name + last_name    # 'HenryYAN'    *没有空格分隔
```
#### 1.2.3 Control characters
```text
\n      # 换行
\t      # 缩进四格
\'      # '
\"      # "
\\      # \
```
#### 1.2.4 Stripping（除去） white spaces
```python
test = ' CUHK '
test.lstrip()   # 'CUHK '   * left
test.rstrip()   # ' CUHK'   * right
test.strip()    # 'CUHK'    * both
```
#### 1.2.5 Indexes
```python
digits = '0123456789'
print( digits[7] )              # 7
print( digits[2]+digits[-1])    # 29
print( digits[1:5] )            # 1234  * 左闭右开
print( digits[:])               # 0123456789
print( digits[2:])              # 23456789
print( digits[5:2] )            #       * 为空
print( digits[-2:3] )           #       * 为空
print( digits[3:-2] )           # 34567
# string[start:stop:step]
print( digits[::-1] )           # 9876543210
print( digits[1:8:2] )          # 1357
```
#### 1.2.6 Splitting Strings
```python
message = "CSCI2040 is really boring !!!, really very boring."      # 分隔符' '会被直接删除
words = message.split(' ')      # ['CSCI2040', 'is', 'really', 'boring', '!!!,', 'really', 'very', 'boring.']
```
#### *1.2.7 Functions*
| Operation | Result |               Description               |
|:---------:|:------:|:---------------------------------------:|
| `"Hello, world!".capitalize()` | `"Hello, world!"` |        将字符串的第一个字符转换为大写，其余字符转为小写         |
| `string.capwords("hello, world!")` | `"Hello, World!"` | 将字符串中的每个单词的首字母转换为大写  （需要`import string`） |
| `"Hello, world!".count("o")` | `2` |            返回子字符串在字符串中出现的次数             |
| `"Hello, world!".find("o")` | `4` |     返回子字符串在字符串中首次出现的位置的索引，如果未找到返回-1     |
| `"Hello, world!".index("o")` | `4` |    返回子字符串在字符串中首次出现的位置的索引，如果未找到则抛出异常     |
| `"Hello, world!".rfind("o")` | `8` |     返回子字符串在字符串中最后出现的位置的索引，如果未找到返回-1     |
| `"Hello, world!".rindex("o")` | `8` |    返回子字符串在字符串中最后出现的位置的索引，如果未找到则抛出异常     |
| `"Hello, world!".lower()` | `"hello, world!"` |             将字符串中的所有字符转换为小写             |
| `"Hello, world!".join(["1", "2", "3"])` | `"1Hello, world!2Hello, world!3"` |     使用字符串作为分隔符，将列表中的所有元素合并为一个新的字符串      |
| `" Hello, world! ".strip()` | `"Hello, world!"` |               去除字符串首尾的空格                |
| `"Hello, world!".upper()` | `"HELLO, WORLD!"` |             将字符串中的所有字符转换为大写             |
| `"Hello, world!".replace("world", "Python")` | `"Hello, Python!"` |             将字符串中的old替换为new             |



### 1.3 Numbers and numerics
```python
# floating points
print (0.1+0.1)     # 0.2
print (0.1+0.2)     # 0.30000000000000004   * WTF???

# operators
print( 3+5 )        # 8
print( 3-5. )       # -2.0
print( 3*5 )        # 15
print( 3/5 )        # In Python 3.*: 0.6.   In Python 2.7: 0. 
print( 3/5. )       # 0.6
print( 3//5 )       # 0
print( 2**3 )       # 8
print( 5%3 )        # 2
print( 5.%3 )       # 2.0
print( 'CU'+'HK' )  # CUHK
print( 'Yeah!'*3 )  # Yeah!Yeah!Yeah!
```
### 1.4 If Statement
```python
# 是elif
# 写冒号！！！！！
score = 100
if score == 100:
    grade = 'A+'
elif score>=90 and score<100:
    grade = 'A'
else:
    grade = 'not A'
```
### 1.5 Control Flow
```python
# for loop写range()！！！！！
# Fibonacci
a, b = 0, 1
while b<10:
    print('a =',a,'\t b =', b)
    a, b = b, a+b
print()
for i in range(1,4):    # range(a=0, b) -> [a,b)
    print(i)
```
```text
a = 0 	 b = 1
a = 1 	 b = 1
a = 1 	 b = 2
a = 2 	 b = 3
a = 3 	 b = 5
a = 5 	 b = 8

1
2
3
```
### *1.6 Others*
#### *1.6.1 type(), dir() and help()*
```python
# I do do do not think this will be tested. So strange. :(
stuff = 'hello world'
print(type(stuff))
print(dir(stuff)) # show all built-in functions of tyis type
help(stuff.capitalize)
```
```text
<class 'str'>
['__add__', '__class__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mod__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__rmod__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', 'capitalize', 'casefold', 'center', 'count', 'encode', 'endswith', 'expandtabs', 'find', 'format', 'format_map', 'index', 'isalnum', 'isalpha', 'isascii', 'isdecimal', 'isdigit', 'isidentifier', 'islower', 'isnumeric', 'isprintable', 'isspace', 'istitle', 'isupper', 'join', 'ljust', 'lower', 'lstrip', 'maketrans', 'partition', 'removeprefix', 'removesuffix', 'replace', 'rfind', 'rindex', 'rjust', 'rpartition', 'rsplit', 'rstrip', 'split', 'splitlines', 'startswith', 'strip', 'swapcase', 'title', 'translate', 'upper', 'zfill']
Help on built-in function capitalize:

capitalize() method of builtins.str instance
    Return a capitalized version of the string.
    
    More specifically, make the first character have upper case and the rest lower
    case.


```
#### *1.6.2 Comments*
```python
# Please do not ask me to write this. :(
```
#### *1.6.3 Operator*
```text
Return True or False:
<   >   <=  >=  ==  !=  not and or
```
## 2. Lists and Tuples
### 2.1 List
#### 2.1.1 Foundation
```python
# 中括号[] 逗号,     可修改
squares = [1, 4, 9, 16, 25]
squares.append(36)              # 添加元素到末尾
print( squares[1:4] )           # [4, 9, 16]                    * 同string
squares[1:4] = [5, 29]          # suares = [1, 5, 29, 25, 36]   * 可做数量不同的替换
len(squares)                    # 5

print( 1 in squares )           # True
print( 2 in squares )           # False
```
#### 2.1.2 For statement
`range(initial=0, final, step=1)`
```python
# 注意不能索引超过范围（如10，-10等）
universities = ['HKU', 'CUHK', 'UST'] 
for x in universities:
    print (x, len(x))
    
print()
    
a = ['Mary', 'had', 'a', 'little', 'lamb'] 
for i in (range(len(a))):
    print (i, a[i])

print ()

cse_teachers = ['john c. s. lui', 'patrick p. c. lee', 'james cheng', 'wei Meng']
for index, teacher in enumerate(cse_teachers):      # enumerate(list): return index, list[index]
    position = str(index) 
    print("Position: " + position + " Teacher: " + teacher.title())
```
```text
HKU 3
CUHK 4
UST 3

0 Mary
1 had
2 a
3 little
4 lamb

Position: 0 Teacher: John C. S. Lui
Position: 1 Teacher: Patrick P. C. Lee
Position: 2 Teacher: James Cheng
Position: 3 Teacher: Wei Meng
```
#### *2.1.3 List Operations*
|                    Operation                     |                 Result                  |           Description           |
|:------------------------------------------------:|:---------------------------------------:|:-------------------------------:|
|      `['apple', 'banana'].append('cherry')`      |     `['apple', 'banana', 'cherry']`     |        向列表末尾添加元素'cherry'        |
| `['apple', 'banana'].extend(['cherry', 'date'])` | `['apple', 'banana', 'cherry', 'date']` | 将列表['cherry', 'date']添加到现有列表的末尾 |
|  `['apple', 'banana', 'apple'].count('apple')`   |                   `2`                   |      计算元素'apple'在列表中出现的次数       |
|  `['apple', 'banana', 'apple'].index('apple')`   |                   `0`                   |     返回元素'apple'在列表中第一次出现的索引     |
|           `['apple', 'banana'].pop()`            |               `'banana'`                |       **返回并删除**列表中的最后一个元素       |
|      `['apple', 'banana'].pop(0)`       |                `'apple'`                |       **返回并删除**列表中索引为0的元素       |
|  `['apple', 'banana', 'apple'].remove('apple')`  |          `['banana', 'apple']`          |       搜索元素'apple'并从列表中删除它       |
|     `['apple', 'banana'].reverse()`     |     `['banana', 'apple']`      |           将列表中的元素顺序反转           |
|      `['banana', 'apple', 'cherry'].sort()`      |     `['apple', 'banana', 'cherry']`     |          将列表中的元素排序成升序           |
|    `['apple', 'banana'].insert(1, 'cherry')`     |     `['apple', 'cherry', 'banana']`     |      在索引为1的位置插入元素'cherry'       |
### 2.2 Tuple
```python
# ::括号() 逗号,    不可修改
tup = (1,7,3,1,7,3)
print( 3 in tup )       # True
list(tup)               # [1, 7, 3, 1, 7, 3]
tuple(['a', 'b', 'c'])  # ('a', 'b', 'c')
print( 'a','b','c' )    # ('a', 'b', 'c')
x, y = 1, 2
```
## 3. Functions
### 3.1 Modules
A few common modules:  
`math`: mathematics functions
`sys`: system utilities such as file open, read/write etc
`random`: random number generator for simulations


|             math.func              |                 Description                  |
|:----------------------------------:|:--------------------------------------------:|
|             ceil( x )              | $$\left \lceil x \right \rceil$$ |
|             floor( x )             |      $$\left \lfloor x \right \rfloor$$      |
|              exp( x )              |                   $$e^x$$                    |
|             fabs( x )              |             $$\lvert x \rvert$$              |
|            pow( x , y )            |                   $$x^y$$                    |
|             sqrt( x )              |                 $$\sqrt{x}$$                 |
|      log( x )<br/>log10( x )       |        $$\log x$$<br/>$$\log_{10} x$$        |
| sin( x )<br/>cos( x )<br/>tan( x ) |   $$\sin x$$<br/>$$\cos x$$<br/>$$\tan x$$   |
```python
import sys                              # sys.exit()
from math import e as eConst            # eConst    * 防止name collision
from math import *                      # exp(2)
from random import randint, random      # randint(1, 5)     * [1, 5]
```
```python
# Create your own module. Useful!!!
# 如果运行my_module.py，会直接print；如果只是import时，'__main__'就不会被运行

# my_module.py
def hello_world():
    print("Hello, world!")

if __name__ == '__main__':
    hello_world()
```
### 3.2 Syntax
```python
def functionName( parameters ):
    '''function_docstring'''
    statements
    return [expression]
```
**Pass By Reference**:  
int, float: pass by value  
the others: pass by reference
使用`global`设置全局变量
```python
a = 1

def func():
    global a
    a = 2

func()
print(a)        # 2
```
#### 3.2.1 Keyword arguments
```python
def foo(x, y):
    print("{} {}" .format(x, y))
    
foo(x=3, y=2)   # 3 2
foo(y=2, x=3)   # 3 2
foo(3, y=2)     # 3 2
foo(2, x=3)     # Wrong
foo(y=2, 3)     # Wrong     * 默认按顺序，一旦用了=，后面就必须都要用
```
#### 3.2.2 Default arguments
```python
def foo(x, y=2):                    # def foo(x=3, y)  不可以，non-default必须在前面
    print("{} {}" .format(x, y))

foo(3)          # 3 2
foo(3, y=2)     # 3 2
foo(x=3, y=2)   # 3 2
```
#### 3.2.3 Return
```python
import random

def func(x):
    m = random.randint(0,5)
    
    if m==0:
        return              # None
    elif m==1:
        return 0            # value
    elif m==2:
        return x            # expression
    elif m==3:
        return x ** 2       # expression
    elif m==4:
        return [x, x+1]     # list
    elif m==5:
        return x, x-1       # tuple
    else:
        return False        # bool
```
#### 3.2.4 Nested Function
```python
def outerFun(a, b):
    def innerFun(c, d):
        return c + d
    return innerFun(a, b)

print( outerFun(5, 10) )    # 15
print( innerFun(5, 10) )    # Wrong
```
#### 3.2.5 Recursive
```python
def Fib(x):
    if x==0:
        return 0
    elif x==1:
        return 1
    else:
        return Fib(x-1) + Fib(x-2)
```
### 3.3 List Comprehensions
```python
list1 = [ x for x in range(1,20) if x % 2 == 1 ]                # [1, 3, 5, 7, 9, 11, 13, 15, 17, 19] 
list2 = [ x**2 for x in range(1,20) if x**2 in range(1,20) ]    # [1, 4, 9, 16]
d = {1:'fred', 7:'sam', 8:'alice', 22:'helen'}
list3 = [d[i] for i in d.keys() if i%2==0]                      # ['alice', 'helen']
def ListofSquares( a ):
    return [ x*x for x in a ]
l = ListofSquares([1, 2, 3])                                    # [1, 4, 9]
```
### 3.4 Lambda function
`lambda arguments: expression`
```python
def even(x):
    return x % 2 == 0
a = [1,2,3,4,5]
print (list(filter(even, a)))                       # [2, 4]

print (list(filter( lambda x : x % 2 == 0, a)))     # [2, 4]
```
### 3.5 Raise exception
```python
def divide(x, y):
    try:
        result = x // y # Floor Division : Gives only Fractional
    except ZeroDivisionError:
        print ("Sorry ! You are dividing by zero ")
    except TypeError as e:
        print(e)
        print()
        raise RuntimeError("Sorry ! Your input are not numbers ") from e
    else:
        print ("Yeah ! Your answer is :", result)

divide(3, 2)
divide(3, 0)
divide(3,'1')
```
```text
Yeah ! Your answer is : 1
Sorry ! You are dividing by zero 
unsupported operand type(s) for //: 'int' and 'str'

Traceback (most recent call last):
  File "/Users/y/Library/Mobile Documents/com~apple~CloudDocs/Yyh./CUHK/课程/CSCI/CSCI 2040/practice.py", line 3, in divide
    result = x // y # Floor Division : Gives only Fractional
TypeError: unsupported operand type(s) for //: 'int' and 'str'

The above exception was the direct cause of the following exception:

Traceback (most recent call last):
  File "/Users/y/Library/Mobile Documents/com~apple~CloudDocs/Yyh./CUHK/课程/CSCI/CSCI 2040/practice.py", line 14, in <module>
    divide(3,'1')
  File "/Users/y/Library/Mobile Documents/com~apple~CloudDocs/Yyh./CUHK/课程/CSCI/CSCI 2040/practice.py", line 8, in divide
    raise RuntimeError("Sorry ! Your input are not numbers ") from e
RuntimeError: Sorry ! Your input are not numbers 
```
## 4. File Operations, Pickle & Dictionary
### 4.1 input and eval
```python
input('Please input: ')     # ()中内容可省略，返回string
int('2040')                 # 2040
float('2040')               # 2040.0
int('12 int')               # Wrong
int('12.34')                # Wrong
int('12 ')                  # 12
int('1010', 2)              # 10    * int(x, base=10)进制转换
eval('36')                  # 36
eval('2+3*6')               # 20
```
### 4.2 File operations
#### 4.2.1 Foundation
`file_handle = open( filename, mode )`

|  Mode  |                Operation                |
|:------:|:---------------------------------------:|
| `'r'`  |                   只读                    |
| `'w'`  |            写入，如果文件不存在，创建新文件             |
| `'a'`  |  追加，如果文件存在，写入的数据将添加到文件末尾；如果文件不存在，创建新文件  |
| `'r+'` |     读写，如果文件存在，不会删除文件内容；如果文件不存在，操作失败     |
| `'rb'` |               以二进制格式读取文件                |
| `'w+'` |     读写，如果文件存在，则清空文件内容；如果文件不存在，创建新文件     |
| `'wb'` | 以二进制格式写入文件，如果文件存在，则清空文件内容；如果文件不存在，创建新文件 |

|        Method        |               Operation                |
|:---------------------:|:--------------------------------------:|
| `f = open("filename")` |             打开一个文件，返回文件对象              |
| `f = open("filename", encoding)` | 使用指定的编码打开一个文件（`'utf-8'`/`'ascii'`/...） |
| `f.read()`            |               返回文件的所有内容                |
| `f.read(n)`           |               返回文件的前n个字符               |
| `f.readline()`        |                返回文件的下一行                |
| `f.readlines()`       |            返回文件的所有行，结果是一个列表            |
| `f.write(s)`          |               将字符串s写入文件                |
| `f.writelines(lst)`   |             将列表lst的内容写入文件              |
| `f.close()`           |                  关闭文件                  |
#### *4.2.2 readline*
```python
# The same
f = open('message.txt')
for line in f:
    print (line)
f.close()

f = open('message.txt')
line = f.readline()
while line:
    print(line)
    line = f.readline()  # 读取下一行
f.close()
```
#### *4.2.3 Exceptions*
```python
# Method 1
try:
    f = open('input.txt')
except IOError as e:
    print ('unable to open the file with error: "{}"'.format(e.args[-1]))
else:
    print ('Successfully opening.')
    f.close()
    
# Method 2
with open('hello.txt', 'w', encoding='utf-8') as outf:
    outf.write("Hello world")
    print(outf.closed) # prints True
    print ('continue with processing')
```
#### *4.2.4 Operating System Command*
```python
import os
os.remove("gone.txt")                       # removing file 
dir = os.curdir                             # get current directory
os.rename('oldfile.txt', 'newfile.txt')
```
#### *4.2.5 Standard I/O*
`print()` writes characters to a file normally attached to display 
window.（命令行界面）  
`input()` functions read from a file attached to keyboard.（键盘）  
These files can be accessed through `sys` module.  
Input file : `sys.stdin`, output file: `sys.stdout`, error messages: `sys.stderr`.  
`stderr` normally goes also to `stdout`.
```python
import sys
sys.stdout = open('output.txt', 'w')
sys.stderr = open('error.txt', 'w')
print ("see where this goes")
print (5/4)
print (7.0/0)
sys.stdout.close()
sys.stderr.close()
```
In output.txt: 
```text
see where this goes
1.25
```
In error.txt: 
```text
Traceback (most recent call last):
    File "try1.py", line 6, in <module>
        print (7.0/0)
ZeroDivisionError: float division by zero
```
#### *4.2.6 OS functions*
`sys.exit("message")` terminate the running Python program  
`sys.argv` is a list of command line options being passed  
(`python script.py arg1 arg2` -> `['script.py', 'arg1', 'arg2']`)
### 4.3 Pickle
```python
import pickle

data = {'a': 1, 'b': 2, 'c': 3}

with open('data.pkl', 'wb') as f:
    pickle.dump(data, f)

with open('data.pkl', 'rb') as f:
    loaded_data = pickle.load(f)

print(loaded_data)                  # {'a': 1, 'b': 2, 'c': 3}
```
### 4.4 Dictionary
```python
dct = {}
dct['name'] = 'Henry'
dct['age'] = 21
dct['courses'] = ['CSCI', 'ENGG', 'SEEM']
for d in dct:
    print(d)
# name
# age
# courses
```
| Methods       | Description                                |
|---------------|--------------------------------------------|
| `len(d)`      | 返回字典 `d` 中元素的数量                            |
| `d[k]`        | 返回键为 `k` 的元素，如果 `d` 中不存在 `k`，则会引发 `KeyError` |
| `d[k]=v`      | 设置键为 `k` 的元素的值为 `v`                        |
| `d.clear()`   | 移除字典 `d` 中的所有元素                            |
| `d.copy()`    | 创建字典 `d` 的浅拷贝                              |
| `k in d`      | 如果字典 `d` 中存在键 `k`，返回 `True`，否则返回 `False`   |
| `d.items()`   | 返回字典 `d` 中的所有 (键, 值) 对list                 |
| `d.keys()`    | 返回字典 `d` 中的所有键的list                        |
| `d.values()`  | 返回字典 `d` 中的所有值的list                        |
| `d.get(k)`    | 与 `d[k]` 相同，但如果 `k` 在 `d` 中不存在，返回 `None`   |
| `d.get(k, v)` | 如果 `k` 是有效的，则返回 `d[k]`，否则返回 `v`            |
| `del d[k]`    | 删除字典 `d` 中键为 `k` 的元素                       |
## 5. More on Functions
###### (Most of the content here has been mentioned before.)  
**LEGB**  
LEGB 规则按照以下顺序搜索名称：Local（局部）、Enclosing（封闭）、Global（全局）、Built-in（内建）  
  
区分local/global variable  
```commandline
>>> b = 2
>>> def scopeTest (a):
...     global b
...     b = 4
...     print ('inside func, b is ', b)
... 
>>> a = 1
>>> scopeTest(a)
inside func, b is 4
>>> print ('after func, b is ', b)
after func, b is 4
```
loop不会创造block scope（循环中创建的变量循环外也能用）  
```commandline
>>> for i in range(5):
...     print (i) if i%2 == 0 else print (-i)
... print (i)
0
-1
2
-3
4
4
```
**Dir Function**
`dir()`返回当前作用域的变量、方法和定义的类型列表。  
`dir('hello')`返回字符串的所有属性和方法。  
global variable只显示在最高层。
```commandline
>>> dir()
['__annotations__', '__builtins__', '__doc__', '__loader__', '__name__', '__package__', '__spec__']
>>> dir([5, 29])
['__add__', '__class__', '__class_getitem__', '__contains__', '__delattr__', '__delitem__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__gt__', '__hash__', '__iadd__', '__imul__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__reversed__', '__rmul__', '__setattr__', '__setitem__', '__sizeof__', '__str__', '__subclasshook__', 'append', 'clear', 'copy', 'count', 'extend', 'index', 'insert', 'pop', 'remove', 'reverse', 'sort']
>>> def func():
...     a = 10
...     b = '100'
...     print(a, b)
... 
>>> dir(func)
['__annotations__', '__builtins__', '__call__', '__class__', '__closure__', '__code__', '__defaults__', '__delattr__', '__dict__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__get__', '__getattribute__', '__globals__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__kwdefaults__', '__le__', '__lt__', '__module__', '__name__', '__ne__', '__new__', '__qualname__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__']
>>> dir(func())     # dir(None)
10 100
['__bool__', '__class__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__le__', '__lt__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__']

>>> b = 1
>>> def test():
...     a = 10
...     global b
...     b = 20
...     c = 30
...     return c
... 
>>> dir(test)
['__annotations__', '__builtins__', '__call__', '__class__', '__closure__', '__code__', '__defaults__', '__delattr__', '__dict__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__get__', '__getattribute__', '__globals__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__kwdefaults__', '__le__', '__lt__', '__module__', '__name__', '__ne__', '__new__', '__qualname__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__']
>>> dir()
['__annotations__', '__builtins__', '__doc__', '__loader__', '__name__', '__package__', '__spec__', 'b', 'test']

>>> x = 1
>>> def fun():
...     y = 2
...     global x
...     x = 3
...     def funfun():
...             z = 4
...     print(dir())
... 
>>> fun()
['funfun', 'y']
```
**Arbitrary Number of Arguments**
```python
# 一个*: tuple
def example_function(arg_1, arg_2, *arg_3):
    print('arg_1:', arg_1)
    print('arg_2:', arg_2)
    print('arg_3:', arg_3)
    for i in arg_3:
        print(i)
    print()

example_function(1, 2)
example_function(1, 2, 3)
example_function(1, 2, 3, 4)
```
```text
arg_1: 1
arg_2: 2
arg_3: ()

arg_1: 1
arg_2: 2
arg_3: (3,)
3

arg_1: 1
arg_2: 2
arg_3: (3, 4)
3
4
```
```python
# 两个*: dictionary
def example_function(arg_1, arg_2, **kwargs):
    print('arg_1:', arg_1)
    print('arg_2:', arg_2)
    print('kwargs:', kwargs)
    for key, value in kwargs.items():
        print(f'{key}: {value}')
    print()

example_function('a', 'b')
example_function('a', 'b', value_3='c')
example_function('a', 'b', value_3='c', value_4='d')
```
```text
arg_1: a
arg_2: b
kwargs: {}

arg_1: a
arg_2: b
kwargs: {'value_3': 'c'}
value_3: c

arg_1: a
arg_2: b
kwargs: {'value_3': 'c', 'value_4': 'd'}
value_3: c
value_4: d

```
## 6. Object-Oriented Programming
### 6.1 Foundation
```python
# An example for OOP
# 记得写self！！！
from math import sqrt
class Rocket(object):
    count = 0                                   # Class variables
    def __init__(self, x=0, y=0):               # Initialization
        Rocket.count += 1
        self.x = x
        self.y = y
        
    def move_up(self):
        self.y += 1

    def get_distance(self, other_rocket):
        distance = sqrt((self.x-other_rocket.x)**2+(self.y-other_rocket.y)**2)
        return distance
```
```commandline
>>> a = Rocket()
>>> b = Rocket()
>>> print (Rocket.count)
2

>>> my_rocket = Rocket(5)
>>> for counter in range(3):
...     my_rocket.move_up() # invoke class function
...
>>> print('my_rocket x is = ', my_rocket.x, ", my rocket y is = ", my_rocket.y)
my_rocket x is = 5 , my rocket y is = 3

>>> rocket_0 = Rocket()
>>> rocket_1 = Rocket(10,5)
>>> distance = rocket_0.get_distance(rocket_0)
>>> print("The rockets are %f units apart." % distance)
The rockets are 0.000000 units apart.
>>> distance = rocket_0.get_distance(rocket_1)
>>> print("The rockets are %f units apart." % distance)
The rockets are 11.180340 units apart.
```
### 6.2 Inheritance
```python
from rocket import Rocket           # 从rocket.py调用
class Shuttle(Rocket): # Shuttle is a child of the Rocket() class, 
    def __init__(self, x=0, y=0, flights_completed=0): 
        super().__init__(x, y) # it first calls its super class init()  * super()调用父类
        self.flights_completed = flights_completed 

shuttle = Shuttle(10,0,3)
print(shuttle)
print("This shuttle has x = ", shuttle.x, "y = ", shuttle.y, "number of completed flights ", shuttle.flights_completed)
# This shuttle has x = 10 y = 0 number of completed flights 3
```

```python
from bankaccount import BankAccount
class CheckAccount(BankAccount):  # CheckAccount, a child of BankAccount, inherits balance 
    def __init__(self, initBal=0):
        BankAccount.__init__(initBal)  # 用super()也可以
        self.checkRecord = {}  # checkRecord is a new dict attribute

    def processCheck(self, number, toWho, amount):
        self.withdraw(amount)  # self.调用父类中的method
        self.checkRecord[number] = (toWho, amount)

    def checkInfo(self, number):
        if number in self.checkRecord:
            return self.checkRecord[number]
```
### 6.3 Overriding 
```python
class CheckAccount(BankAccount):
    # the same
    def withdraw(self, amount):             # same name and arguments, 如果还想用父类的方法，用super()
        print ('withdrawing ', amount)
        BankAccount.withdraw(self, amount)
```
### 6.4 Scopes, Names, and References
```python
# Interesting!!!
class Box(object):
    def __init__(self, v):
        self.value = v

def newScope(x):
    y = x
    y.value = 42            # .value被共享了，如果传入的x没有.value，会出现error
    
a = Box(3)
newScope(a)
print (a.value)             # 42
```
class将name space存在`__dict__`中
### *6.5 Types & Tests*
Each class definition creates a new type
```commandline
>>> myAccount = BankAccount()
>>> print (type(myAccount))
<class '__main__.BankAccount'>
>>> print (type(BankAccount))
<type 'type'>
```
`isinstance(object, classinfo)`判断*object*是否是类*classinfo*或其子类的实例
```commandline
>>> newAccount = CheckAccount(4000)
>>> sndAccount = BankAccount(100)
>>> print (isinstance(newAccount, BankAccount))
True
>>> print (isinstance(newAccount, CheckAccount))
True
>>> print (isinstance(sndAccount, CheckAccount))
False
```
`issubclass(A,B)`返回`True`，如果A是B的子类
```commandline
>>> print (issubclass(CheckAccount, BankAccount))
True
```
也可以对built-in types进行`type()`检查
```commandline
>>> isinstance(3, int)
True

>>> import types
>>> def f():
...     pass
... 
>>> isinstance(f, types.FunctionType)
True
```
## 7. Functional Programming
function name也可以传递
```commandline
>>> import math
>>> mySqrt = math.sqrt
>>> mySqrt(4)
2.0
```
### 7.1 Mapping
`map(func, seq)`list中的每个元素逐个带入function中
```python
def map_func1(x):
    return x*2 + 1
my_variable = [1,2,3,4,5]
my_variable = list (map(map_func1, my_variable))    # Python 3.x中要转化为list()
print("my_variable is:", my_variable)               # my_variable is: [3, 5, 7, 9, 11]

def my_add (x,y): 
    return x+y
my_variable = list(map(my_add, range(0,10), range(0,10)))
print(my_variable)                                  # [0, 2, 4, 6, 8, 10, 12, 14, 16, 18]

print (list(map(lambda x : x*2 + 1, range(1, 6))))  # [3, 5, 7, 9, 11]
```
### 7.2 Filtering
`filiter(func, seq)`保留list中可以通过function过滤的元素
```python
def my_func1(x): 
    return x % 3 == 0 or x % 5 == 0
def my_func2(x): 
    return (x+1)%2 == 0
my_variable = list(filter(my_func1, range(1,25)))
print("1. my_variable = ", my_variable)                     # 1. my_variable =  [3, 5, 6, 9, 10, 12, 15, 18, 20, 21, 24]
my_variable = [ x for x in filter(my_func2, range(1,6))]
print("2. my_variable = ", my_variable)                     # 2. my_variable =  [1, 3, 5]

print (list(filter( lambda x : x % 2 == 0, range(1, 6))))   # [2, 4]
```
### 7.3 Reduction
`reduce(func, seq)`按顺序计算list中的function，使用前需要`from functools import reduce`
```python
from functools import reduce
def my_add(x,y):                    # 必须是两个参数的函数
    return x+y
print(reduce(my_add, range(1,6)))   # 15    * ((((1+2)+3)+4)+5)=15

print (reduce( lambda x, y: x + y, range(1, 6)))        # 15
```
## 8. NumPy (& SciPy) in Python
### 8.1 Basic
```python
import numpy as np

# 一维
a = np.array([1, 4, 5, 8], float)
print(a)            # [1. 4. 5. 8.]
print (type(a))     # <class 'numpy.ndarray'>
print(a[:2])        # [1. 4.]
print(a[3])         # 8.0
a[3] = 100.0
print(a)            # [  1.   4.   5. 100.]

# 多维
a = np.array([[1,2,3], [4,5,6]], float)
print (a)
# [[1. 2. 3.]
#  [4. 5. 6.]]
a[0,0] = 15.0 
a[1][0] = 12.0
print('a =',a)
# a = [[15.  2.  3.]
#  [12.  5.  6.]]

# Slicing
a = np.array([[1,2,3], [4,5,6]], float)
print('a[1,:]=', a[1,:])            # a[1,:]= [4. 5. 6.]
print('a[:,2]=', a[:,2])            # a[:,2]= [3. 6.]
print('a[:1,0:2] =', a[:1,0:2])     # a[:1,0:2] = [[1. 2.]]
print('a[-1:,-2:] =', a[-1:, -2:])  # a[-1:,-2:] = [[5. 6.]]
```
### 8.2 Array
```python
import numpy as np

# shape
a = np.array([[1,2,3], [4,5,6]], int)
print(a.shape)                                  # (2, 3)
print (a.dtype)                                 # int64
print('length of the first axis =', len(a))     # length of the first axis = 2
print('length of the second axis =', len(a[0])) # length of the second axis = 3

# in
a = np.array([[1,2,3], [4,5,6]], float)
print ("Is 2 in a? ", 2 in a)                   # Is 2 in a?  True
print ("Is 9 in a? ", 9 in a)                   # Is 9 in a?  False
a = np.array(range(10), float)
print('float a =', a)                           # float a = [0. 1. 2. 3. 4. 5. 6. 7. 8. 9.]
a = np.array([range(3), range(3)], int)
print('integer a = ', a)
# integer a =  [[0 1 2]
#  [0 1 2]]

# reshape
a = np.array(range(10), float)
print('Before reshape(), a =', a)
# Before reshape(), a = [0. 1. 2. 3. 4. 5. 6. 7. 8. 9.]
a = a.reshape(2,5)
print('After 1st reshape(), a =', a)
# After 1st reshape(), a = [[0. 1. 2. 3. 4.]
#  [5. 6. 7. 8. 9.]]
a = a.reshape(5,2)
print('After 2nd reshape(), a =', a)
# After 2nd reshape(), a = [[0. 1.]
# [2. 3.]
# [4. 5.]
# [6. 7.]
# [8. 9.]]

# reference
a = np.array(range(5), float)
b = a
c = a.copy()
print ('a=', a, 'b=', b, 'c=', c)   # a= [0. 1. 2. 3. 4.] b= [0. 1. 2. 3. 4.] c= [0. 1. 2. 3. 4.]
a[0] = 10.0
print ('a=', a, 'b=', b, 'c=',c)    # a= [10.  1.  2.  3.  4.] b= [10.  1.  2.  3.  4.] c= [0. 1. 2. 3. 4.]

# fill
a = np.array(range(5), float)
print('a =', a)                 # [0. 1. 2. 3. 4.]
a.fill(100)
print('a =', a)                 # [100. 100. 100. 100. 100.]

# concatenate
a = np.array([1,2], float)
b = np.array([3,4,5], float)
c = np.array([7,8,9,10], int)
d = np.concatenate((a,b,c))
print('d =',d)                  # d = [ 1.  2.  3.  4.  5.  7.  8.  9. 10.]

# arange
a = np.array(range(5), float)
print('a = ', a)                # a =  [0. 1. 2. 3. 4.]
b = np.arange(5, dtype=float)
print('b = ', b)                # b =  [0. 1. 2. 3. 4.]

# zeros and ones
a = np.zeros(7,dtype=int)
print('a=',a)
# a= [0 0 0 0 0 0 0]
b = np.ones((3,2),dtype=float)
print('b=',b)
# b= [[1. 1.]
#  [1. 1.]
#  [1. 1.]]
```
### 8.3 Matrix/Vector
```python
import numpy as np

# identify and eye
a = np.identity(3, dtype=float) # create a 3x3 identity matrix
print('a=',a)
# a= [[1. 0. 0.]
#  [0. 1. 0.]
#  [0. 0. 1.]]
a = np.eye(4, M=5, k=2, dtype=float) # 对角线右移k个单位
print(a)
# [[0. 0. 1. 0. 0.]
#  [0. 0. 0. 1. 0.]
#  [0. 0. 0. 0. 1.]
#  [0. 0. 0. 0. 0.]]

# calculation 形状相同，逐位运算
c = np.array([[1,2,3,4,5],[1,1,1,1,1]],int)
d = np.array([[5,4,3,2,1],[2,2,2,2,2]],float)
print('c+d =', c+d)
print('c-d =', c-d)
print('c*d =', c*d)
print('c/d =', c/d)
print('c%d =', c%d)
print('c**d =',c**d)
# c+d = [[6. 6. 6. 6. 6.]
#  [3. 3. 3. 3. 3.]]
# c-d = [[-4. -2.  0.  2.  4.]
#  [-1. -1. -1. -1. -1.]]
# c*d = [[5. 8. 9. 8. 5.]
#  [2. 2. 2. 2. 2.]]
# c/d = [[0.2 0.5 1.  2.  5. ]
#  [0.5 0.5 0.5 0.5 0.5]]
# c%d = [[1. 2. 0. 0. 0.]
#  [1. 1. 1. 1. 1.]]
# c**d = [[ 1. 16. 27. 16.  5.]
#  [ 1.  1.  1.  1.  1.]]

# calculation 有一维形状不同，逐维运算（任一维相等均可）
a = np.array([[1,2], [3,4], [5,6]], int)
b = np.array([-1,3], float)
print('a =', a)
print('b =', b)
print('a+b =', a+b)
print('a*b =', a*b)
# a = [[1 2]
#  [3 4]
#  [5 6]]
# b = [-1.  3.]
# a+b = [[0. 5.]
#  [2. 7.]
#  [4. 9.]]
# a*b = [[-1.  6.]
#  [-3. 12.]
#  [-5. 18.]]

# Iterations
a = np.array([[1,2],[3,4],[5,6]], dtype=int)
for num in a:
    print('number = ', num)
# number =  [1 2]
# number =  [3 4]
# number =  [5 6]
```

## 9. Visualization in Python
In my term, this chapter will not be tested. 🧐  
Waiting for you to perfect it! 🤩
## Appendenix
```python
# Lec 1
a, b = 10, 20
min = a if a < b else b     # min = 10

'{} {}'.format('one', 'two')            # 'one two'
'{} {}'.format(1, 2)                    # '1 2'
'{1} {0}'.format(4, 3)                  # '3 4'
'My name is {yyh}.'.format(yyh='Henry') # 'My name is Henry.'
```
```python
# Lec 4
d = {'name':'Batman', 'vehicle':['Batboat','Batcopter']}
b = d                                                       # copy of reference to d
c = d.copy()                                                # new object but shadow copy of d
print("c:",c)                                               # c: {'name': 'Batman', 'vehicle': ['Batboat', 'Batcopter']}
d['name']='Robin'
d['vehicle'][0]='Batcycle'
print("c:",c)                                               # c: {'name': 'Batman', 'vehicle': ['Batcycle', 'Batcopter']}
d.clear()
print("d:",d)                                               # d: {}
print("b:",b)                                               # b: {}
print("c:",c)                                               # d’elements referenced
```
```python
# Lec 5
import sys
sys.stdout = open('output.txt', 'w')                    # In output.txt
print ("see where this goes")                           # see where this goes
print (5/4)                                             # 1.25
print (7.0/0)
sys.stdout.close()
print (1/2) # where it goes?
sys.stdout = sys.__stdout__ # reset stdout to normal

import pickle # import to use
info = {'name':'Batman', 'age':82, 'weight':180}
w = open('pickle1.pyp','wb')
pickle.dump(info, w) # store the dictionary in a file
r = open('pickle1.pyp', "rb")
d = pickle.load(r)
for i in d.keys():
    print (f"{i}:{d[i]}",end=',')                       # name:Batman,age:82,weight:180
```
```python
# Lec 6
def silly():
    x = 12
    class A:
        x = 42              # class variable    * 不在LEGB中
        def foo(self):
            print(x)        # 12
            print(self.x)   # 42
    return A()
anA = silly()
anA.foo()

class A(object):
    def doa(self):
        print ("I'm a")
class B (object):
    def dob(self):
        print ("I'm b")
class C(A,B):
    def doc(self):
        print ("I'm c")
v=C()
v.doc()         # I'm c
v.doa()         # I'm a
v.dob()         # I'm b
```
```python
# Lec 7
# Iterators
# list返回元素，string返回字符，dictionary返回key...
class yrange:
    def __init__(self, n):
        self.i = 0
        self.n = n
    def __iter__(self): # this makes an object iterable
        return self
    def __next__(self): # this method implement element extraction
        if self.i < self.n:
            i = self.i
            self.i += 1
            return i
        else:
            raise StopIteration()

y = yrange(5)
print(next(y))              # 0
print(y.__next__())         # 1
print(next(y))              # 2
print(y.__next__())         # 3
```
```python
# Lec 8
# Some unuseful methods in NumPy & SciPy
```
# 🫶Good Luck and Keep Fighting!!! (ง •̀_•́)ง