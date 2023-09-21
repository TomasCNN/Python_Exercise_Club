# Exercise for Python

## Exercise_1  Arithmetic Formatter

### Assignment

Students in primary school often arrange arithmetic problems vertically to make them easier to solve. For example, "235 + 52" becomes:

```python
  235
+  52
-----
```



Create a function that receives a list of strings that are arithmetic problems and returns the problems arranged vertically and side-by-side. The function should optionally take a second argument. When the second argument is set to `True`, the answers should be displayed.

### For example

Function Call:

```python
arithmetic_arranger(["32 + 698", "3801 - 2", "45 + 43", "123 + 49"])
```

Output:

```python
   32      3801      45      123
+ 698    -    2    + 43    +  49
-----    ------    ----    -----
```

Function Call:

```python
arithmetic_arranger(["32 + 8", "1 - 3801", "9999 + 9999", "523 - 49"], True)
```

Output:

```python
  32         1      9999      523
+  8    - 3801    + 9999    -  49
----    ------    ------    -----
  40     -3800     19998      474
```

### Rules

The function will return the correct conversion if the supplied problems are properly formatted, otherwise, it will **return** a **string** that describes an error that is meaningful to the user.

- Situations that will return an error:
  - If there are **too many problems** supplied to the function. The limit is **five**, anything more will return: `Error: Too many problems.`
  - The appropriate operators the function will accept are **addition** and **subtraction**. Multiplication and division will return an error. Other operators not mentioned in this bullet point will not need to be tested. The error returned will be: `Error: Operator must be '+' or '-'.`
  - Each number (operand) should only contain digits. Otherwise, the function will return: `Error: Numbers must only contain digits.`
  - Each operand (aka number on each side of the operator) has a max of four digits in width. Otherwise, the error string returned will be: `Error: Numbers cannot be more than four digits.`
- If the user supplied the correct format of problems, the conversion you return will follow these rules:
  - There should be a single space between the operator and the longest of the two operands, the operator will be on the same line as the second operand, both operands will be in the same order as provided (the first will be the top one and the second will be the bottom.
  - Numbers should be right-aligned.
  - There should be four spaces between each problem.
  - There should be dashes at the bottom of each problem. The dashes should run along the entire length of each problem individually. (The example above shows what this should look like.)

### Development

Write your code in `arithmetic_arranger.py`. For development, you can use `main.py` to test your `arithmetic_arranger()` function. Click the "run" button and `main.py` will run.

### Testing

The unit tests for this project are in `test_module.py`. We imported the tests from `test_module.py` to `main.py` for your convenience. The tests will run automatically whenever you hit the "run" button.

### Submitting

Copy your project's URL and submit it to freeCodeCamp.



## 练习题_1  算术格式化程序

### 赋值

小学生经常把算术题竖着排，这样更容易解。例如，"235 + 52"变成:

```python
  235
+  52
-----
```

创建一个函数，接收算术问题字符串列表，并返回垂直排列和并排排列的问题。该函数应该可选地接受第二个参数。当第二个参数设置为“True”时，应该显示答案。

### 举例

函数调用:

```python
arithmetic_arranger(["32 + 698", "3801 - 2", "45 + 43", "123 + 49"])
```

输出:

```python
   32      3801      45      123
+ 698    -    2    + 43    +  49
-----    ------    ----    -----
```

函数调用:

```python
arithmetic_arranger(["32 + 8", "1 - 3801", "9999 + 9999", "523 - 49"], True)
```

输出:

```python
  32         1      9999      523
+  8    - 3801    + 9999    -  49
----    ------    ------    -----
  40     -3800     19998      474
```

### 规则

如果提供的问题被正确格式化，该函数将返回正确的转换，否则，它将返回一个描述对用户有意义的错误的字符串。会返回错误的情况:

1. 如果有太多的program**提供给该函数。限制是** 5，再多则返回: `Error: Too many problems.`
2. 函数将接受的合适运算符是**加法**和**减法**。乘法和除法将返回一个错误。其他在这一点上没有提到的操作将不需要进行测试。返回的错误将是:Error: Operator must be '+' or '-'.
3. 每个数字(操作数)应该**只包含数字**。否则，该函数将返回:`Error: Numbers must only contain digits.`
4. **每个操作数(即操作符两边的数字)的宽度最多为4位**。否则，返回的错误字符串将是: `Error: Numbers cannot be more than four digits.`

如果用户提供了正确的问题格式，您返回的转换将遵循以下规则:

1. 在操作符和两个操作数中最长的操作数之间应该有一个空格，操作符将与第二个操作数在同一行，两个操作数的顺序将与提供的相同(第一个操作数将是顶部，第二个操作数将是底部)。
2. 数字应该右对齐。
3. 每个问题之间应该有四个空格。
4. 每个问题的底部都应该有破折号。破折号应该沿着每个问题的整个长度单独运行。(上面的例子显示了这应该是什么样子。)

### 发展

在' arithmetic_arranger.py '中编写代码。对于开发，您可以使用' main.py '来测试' arithmetic_arranger() '函数。点击“run”按钮，“main.py”将运行。

### 测试

这个项目的单元测试在' test_module.py '中。为了方便您，我们将测试从' test_module.py '导入到' main.py '。当您点击“运行”按钮时，测试将自动运行。

### 提交

复制项目的URL并提交到freeCodeCamp。

 

## 练习题1_题解

### 代码示例：

Exercise_1.py如下所示：

```python
# This entrypoint file to be used in development. Start by reading README.md
from tkinter import TRUE
from arithmetic_arranger import arithmetic_arranger
from unittest import main


print(arithmetic_arranger(["32 + 698", "3801 - 2", "45 + 43", "123 + 49"],TRUE))


# Run unit tests automatically
main(module='test_module', exit=False)
```

arithmetic_arranger.py如下所示：

```python
def arithmetic_arranger(problems, val=False):
    arranged_problems = ''
    if len(problems) > 5:
        arranged_problems = "Error: Too many problems."
        return arranged_problems

    # list of all operations in str format
    operations = list(map(lambda x: x.split()[1], problems))
    if set(operations) != {'+', '-'} and len(set(operations)) != 2:
        arranged_problems = "Error: Operator must be '+' or '-'."
        return arranged_problems

    numbers = []  # list of all operands in str format
    for i in problems:
        p = i.split()
        numbers.extend([p[0], p[2]])

    if not all(map(lambda x: x.isdigit(), numbers)):
        arranged_problems = "Error: Numbers must only contain digits."
        return arranged_problems

    if not all(map(lambda x: len(x) < 5, numbers)):
        arranged_problems = "Error: Numbers cannot be more than four digits."
        return arranged_problems

    top_row = ''
    dashes = ''
    values = list(map(lambda x: eval(x), problems))
    solutions = ''
    for i in range(0, len(numbers), 2):
        space_width = max(len(numbers[i]), len(numbers[i+1])) + 2
        top_row += numbers[i].rjust(space_width)
        dashes += '-' * space_width
        solutions += str(values[i // 2]).rjust(space_width)
        if i != len(numbers) - 2:
            top_row += ' ' * 4
            dashes += ' ' * 4
            solutions += ' ' * 4

    bottom_row = ''
    for i in range(1, len(numbers), 2):
        space_width = max(len(numbers[i - 1]), len(numbers[i])) + 1
        bottom_row += operations[i // 2]
        bottom_row += numbers[i].rjust(space_width)
        if i != len(numbers) - 1:
            bottom_row += ' ' * 4

    if val:
        arranged_problems = '\n'.join((top_row, bottom_row, dashes, solutions))
    else:
        arranged_problems = '\n'.join((top_row, bottom_row, dashes))
    return arranged_problems
```

### 函数说明：

#### map()函数

map()是一个 Python 内建(置)函数，它允许你不需要使用循环就可以编写简洁的代码。它的作用是将一个函数作用于一个可迭代对象的所有元素上，并返回一个新的可迭代对象，其元素为原可迭代对象元素经过该函数处理后的结果。

##### 一、Python map() 函数

这个map()函数采用以下形式：

```python
map(function, iterable, ...)
```

它需要两个必须的参数：

`function` - 针对每一个迭代调用的函数
	`iterable` - 支持迭代的一个或者多个对象。在 Python 中大部分内建对象，例如 lists, dictionaries, 和 tuples 都是可迭代的。
在 Python 3 中，map()返回一个与传入可迭代对象大小一样的 map 对象。在 Python 2中，这个函数返回一个列表 list。

map()是 Python 内置的高阶函数，它接收一个函数 f 和一个 list，并通过把函数 f 依次作用在 list 的每个元素上，得到一个新的 list 并返回。

例如，对于list [1, 2, 3, 4, 5, 6, 7, 8, 9]

如果希望把list的每个元素都作平方，就可以用map()函数：

因此，我们只需要传入函数f(x)=x*x，就可以利用map()函数完成这个计算：

```python
def f(x):
    return x*x
print map(f, [1, 2, 3, 4, 5, 6, 7, 8, 9])


```

输出结果：

```python
[1, 4, 9, 10, 25, 36, 49, 64, 81]
```

注意：map()函数不改变原有的 list，而是返回一个新的 list。

利用map()函数，可以把一个 list 转换为另一个 list，只需要传入转换函数。

由于list包含的元素可以是任何类型，因此，map() 不仅仅可以处理只包含数值的 list，事实上它可以处理包含任意类型的 list，只要传入的函数f可以处理这种数据类型。

任务
	假设用户输入的英文名字不规范，没有按照首字母大写，后续字母小写的规则，请利用map()函数，把一个list（包含若干不规范的英文名字）变成一个包含规范英文名字的list：

输入：['adam', 'LISA', 'barT']
	输出：['Adam', 'Lisa', 'Bart']

```python
def format_name(s):
    s1=s[0:1].upper()+s[1:].lower();
    return s1;

print map(format_name, ['adam', 'LISA', 'barT'])
```


map（）函数是python内置的高阶函数，对传入的list的每一个元素进行映射，返回一个新的映射之后的list

使用map()函数可以实现将其他类型的数转换成list，但是这种转换也是有类型限制的，具体什么类型限制，在以后的学习中慢慢摸索吧。这里给出几个能转换的例子：

```python
***将元组转换成list***

>>> map(int, (1,2,3))
[1, 2, 3]
```

```python
***将字符串转换成list***
>>> map(int, '1234')
[1, 2, 3, 4]
```

```python
***提取字典的key，并将结果存放在一个list中***
>>> map(int, {1:2,2:3,3:4})
>>> [1, 2, 3]
```

```python
***提取字典的key，并将结果存放在一个list中***
>>> map(int, {1:2,2:3,3:4})
>>> [1, 2, 3]
```

```python
#将小写转成大写
def u_to_l (s):
	return s.upper()
	print map(u_to_l,'asdfd'

print map(None, [2,4,6],[3,2,1])
```

**判断list 中重复出现的次数**

方法一：   

```python
mylist = [1,2,2,2,2,3,3,3,4,4,4,4]
myset = set(mylist)  #myset是另外一个列表，里面的内容是mylist里面的无重复 项
for item in myset:
	print("the %d has found %d" %(item,mylist.count(item)))
```

方法二：	

```python
List=[1,2,2,2,2,3,3,3,4,4,4,4]
a = {}
for i in List:
	if List.count(i)>1:
    meia[i] = List.count(i)
print (a)
```

方法三：利用字典的特性来实现。

```python
>>> from collections import Counter
>>> Counter([1,2,2,2,2,3,3,3,4,4,4,4])
Counter({1: 5, 2: 3, 3: 2})
```

这里再增补一个只用列表实现的方法：

```python
l=[1,4,2,4,2,2,5,2,6,3,3,6,3,6,6,3,3,3,7,8,9,8,7,0,7,1,2,4,7,8,9]

count_times = []
for i in l :
  count_times.append(l.count(i))

m = max(count_times)
n = l.index(m)
print (l[n])
```

方法四：

```python
len(list) == len(set(list))
```

map() 会根据提供的函数对指定序列做映射。

第一个参数 function 以参数序列中的每一个元素调用 function 函数，返回包含每次 function 函数返回值的新列表。

Python 2.x 返回列表。

Python 3.x 返回迭代器。

**Python2.x 实例**

```python
>>> def square(x) :            # 计算平方数
...     return x ** 2
... 
>>> map(square, [1,2,3,4,5])   # 计算列表各个元素的平方
[1, 4, 9, 16, 25]
>>> map(lambda x: x ** 2, [1, 2, 3, 4, 5])  # 使用 lambda 匿名函数
[1, 4, 9, 16, 25]

# 提供了两个列表，对相同位置的列表数据进行相加
>>> map(lambda x, y: x + y, [1, 3, 5, 7, 9], [2, 4, 6, 8, 10])
[3, 7, 11, 15, 19]
```

**Python3.x 实例**

```python
>>> def square(x) :         # 计算平方数
...     return x ** 2
... 
>>> map(square, [1,2,3,4,5])    # 计算列表各个元素的平方
<map object at 0x100d3d550>     # 返回迭代器
>>> list(map(square, [1,2,3,4,5]))   # 使用 list() 转换为列表
[1, 4, 9, 16, 25]
>>> list(map(lambda x: x ** 2, [1, 2, 3, 4, 5]))   # 使用 lambda 匿名函数
[1, 4, 9, 16, 25]
>>>
```

**注意：**

如果函数有多个参数, 但每个参数的序列元素数量不一样, 会根据最少元素的序列进行：

```python
>>> listx = [1,2,3,4,5,6,7]       # 7 个元素
>>> listy = [2,3,4,5,6,7]         # 6 个元素 
>>> listz = [100,100,100,100]     # 4 个元素
>>> list_result = map(lambda x,y,z : x**2 + y + z,listx, listy, listz)
>>> print(list(list_result))
[103, 107, 113, 121]
```

明显可以看出是由于 lambda 中的 z 参数,实际是使用了 listz, 而 listz 里面只有 4 个元素, 所以即使 listx 有 7 个元素, listy 有 6 个元素,也不会继续执行了，只执行了 4 个元素的的计算。

让我们看看一个例子，更好地解释map()函数如何运作的。假如我们有一个字符串列表，我们想要将每一个元素都转换成大写字母。

想要实现这个目的的一种方式是，使用传统的for循环:

```python
directions = ["north", "east", "south", "west"]
directions_upper = []

for direction in directions:
	d = direction.upper()
	directions_upper.append(d)
    
print(directions_upper)
```

输出：

```python
['NORTH', 'EAST', 'SOUTH', 'WEST']
```

使用 map() 函数，代码将会非常简单，非常灵活。

```python
def to_upper_case(s):
	return s.upper()

directions = ["north", "east", "south", "west"]
directions_upper = map(to_upper_case, directions)
print(list(directions_upper))
```

我们将会使用list()函数，来将返回的 map 转换成 list 列表：

输出：

```python
['NORTH', 'EAST', 'SOUTH', 'WEST']
```

如果返回函数很简单，更 Python 的方式是使用 lambda 函数：

```python
directions = ["north", "east", "south", "west"]
directions_upper = map(lambda s: s.upper(), directions)
print(list(directions_upper))
```

一个 lambda 函数是一个小的匿名函数。
下面是另外一个例子，显示如何创建一个列表，从1到10。

```python
squares = map(lambda n: n*n , range(1, 11))
print(list(squares))
```

输出：

```python
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

`range()` 函数生成一系列的整数。

##### 二、对多个迭代对象使用map()

你可以将任意多的可迭代对象传递给map()函数。回调函数接受的必填输入参数的数量，必须和可迭代对象的数量一致。

下面的例子显示如何在两个列表上执行元素级别的操作：

```python
def multiply(x, y):
return x * y

a = [1, 4, 6]
b = [2, 3, 5]
result = map(multiply, a, b)

print(list(result))
```

输出：

```python
[2, 12, 30]
```

同样的代码，使用 lambda 函数，会像这样：

```python
a = [1, 4, 6]
b = [2, 3, 5]
result = map(lambda x, y: x*y, a, b)

print(list(result))
```

当提供多个可迭代对象时，返回对象的数量大小和最短的迭代对象的数量一致。

让我们看看一个例子，当可迭代对象的长度不一致时：

```python
a = [1, 4, 6]
b = [2, 3, 5, 7, 8]
result = map(lambda x, y: x*y, a, b)
```

print(list(result))
超过的元素 （7 和 8 ）被忽略了。

```python
[2, 12, 30]
```



##### 三、总结

Python 的 map()函数作用于一个可迭代对象，使用一个函数，并且将函数应用于这个可迭代对象的每一个元素。

#### lambda（）函数

##### 一、Python lambda() 函数

Lambda函数也被称为匿名(没有名称)函数，它直接接受参数的数量以及使用该参数执行的条件或操作，该参数以冒号分隔，并返回最终结果。为了在大型代码库上编写代码时执行一项小任务，或者在函数中执行一项小任务，便在正常过程中使用lambda函数。

`lambda` 关键字可以用来创建一个 lambda 函数，紧跟其后的是参数列表和用冒号分割开的单个表达式。例如，`lambda x: 2 * x` 是将任何输入的数乘2，而 `lambda x, y: x+y` 是计算两个数字的和。

这个lambda()函数采用以下形式：

```python
lambda argument_list:expersion
```

`argument_list`是参数列表，它的结构与`Python`中函数(`function`)的参数列表是一样的.`expression`是一个关于参数的表达式，表达式中出现的参数需要在`argument_list`中有定义，并且表达式只能是单行的。

匿名函数使用注意点：

**1.不要返回任何值**

**2.不要忘记更好的选择**

**3.不要将它赋值给变量**

**4.不要忘记列表推导式**

##### 二、普通函数与 lambda() 函数的区别

**1.没有名称**
	Lambda函数没有名称，而普通操作有一个合适的名称。**

**2.Lambda函数没有返回值**
	使用`def`关键字构建的普通函数返回值或序列数据类型，但在Lambda函数中返回一个完整的过程。假设我们想要检查数字是偶数还是奇数，使用lambda函数语法类似于下面的代码片段。

```go
b = lambda x: "Even" if x%2==0 else "Odd"
b(9)
```

**3.函数只在一行中**
	Lambda函数只在一行中编写和创建，而在普通函数的中使用缩进

**4.不用于代码重用**
	Lambda函数不能用于代码重用，或者不能在任何其他文件中导入这个函数。相反，普通函数用于代码重用，可以在外部文件中使用。

下面是一些lambda函数示例：

lambda x, y: x*y；函数输入是x和y，输出是它们的积x*y；
	lambda:None；函数没有输入参数，输出是None；
	lambda *args: sum(args); 输入是任意个数的参数，输出是它们的和(隐性要求是输入参数必须能够进行加法运算)；
	lambda **kwargs: 1；输入是任意键值对参数，输出是1。

##### 三、Python lambda() 函数的四种用法

1.将lambda函数赋值给一个变量，通过这个变量间接调用该lambda函数；

```python
c=lambda x,y,z:x*y*z
c(2,3,4)

>> 24
```

也可以在函数后面直接传递实参:

```python
(lambda x:x**2)(3)


>> 9
```

2.将lambda函数赋值给一个变量，通过这个变量间接调用该lambda函数；

3.将lambda函数赋值给一个变量，通过这个变量间接调用该lambda函数；

4.将lambda函数作为参数传递给其他函数。

**filter函数。**此时lambda函数用于指定过滤列表元素的条件。例如filter(lambda x: x % 3 == 0, [1, 2, 3])指定将列表[1,2,3]中能够被3整除的元素过滤出来，其结果是[3]。

```python
fliter(lambda x:x%3==0,[1,2,3,4,5,6])


>> [3,6]
```

**sorted函数。**此时lambda函数用于指定对列表中所有元素进行排序的准则。例如sorted([1, 2, 3, 4, 5, 6, 7, 8, 9], key=lambda x: abs(5-x))将列表[1, 2, 3, 4, 5, 6, 7, 8, 9]按照元素与5距离从小到大进行排序，其结果是[5, 4, 6, 3, 7, 2, 8, 1, 9]。

创建由元组构成的列表：

```python
a=[('b',3),('a',2),('d',4),('c',1)]

# 按照第一个元素排序
sorted(a,key=lambda x:x[0])
>> [('a',2),('b',3),('c',1),('d',4)]

# 按照第二个元素排序
sorted(a,key=lambda x:x[1])
>> [('c',1),('a',2),('b',3),('d',4)]
```

**map函数。**此时lambda函数用于指定对列表中每一个元素的共同操作。例如map(lambda x: x+1, [1, 2,3])将列表[1, 2, 3]中的元素分别加1，其结果[2, 3, 4]。

**reduce函数。**此时lambda函数用于指定列表中两两相邻元素的结合条件。例如reduce(lambda a, b: '{}, {}'.format(a, b), [1, 2, 3, 4, 5, 6, 7, 8, 9])将列表 [1, 2, 3, 4, 5, 6, 7, 8, 9]中的元素从左往右两两以逗号分隔的字符的形式依次结合起来，其结果是'1, 2, 3, 4, 5, 6, 7, 8, 9'。

```python
from functools import reduce
print(reduce(lambda a,b:'{},{}'.format(a,b),[1,2,3,4,5,6,7,8,9]))

>> 1,2,3,4,5,6,7,8,9
```

另外，部分Python库函数也接收函数作为参数，例如gevent的spawn函数。此时，lambda函数也能够作为参数传入。

#### split()函数

split()函数是Python字符串函数。split() 通过指定分隔符对字符串进行切片。如果指定了整型参数num，则仅分隔num + 1个子字符串（即分割num次）。使用split()函数将字符串分割后，返回的是一个列表，列表中存储着分割后的每个子串。

```python
str.split(str="", num=string.count(str)).
```

- str -- 分隔符，默认为所有的空字符，包括空格、换行(\n)、制表符(\t)等。
- num -- 分割次数。默认为 -1, 即分隔所有。
- 返回分割后的字符串列表。

##### 一、split()函数示例

**1. 所有参数都省略**

```python
s = 'Hello world!'
d = s.split()
print(d)
```

输出结果为：

```python
['Hello', 'world!']
```

**2. 仅指定分隔符**

```python
s = 'Hello world！ I am Python&I am not Java!'
d = s.split('&')
print(d)
```

输出结果为：

```python
['Hello world！ I am Python', 'I am not Java!']
```

**3. 指定分隔符和分割次数**

```python
s = 'I am Python&I am not Java!&Python is Interesting'
d = s.split('&', 1)
print(d)
```

输出结果为：

```python
['I am Python', 'I am not Java!&Python is Interesting']
```

**注意事项：**

**1. 使用split()后，有效分隔符不会存在于任何子串中。**

有效分隔符：待分割的字符串中存在该分隔符，且num参数有效。

```python
>>> s = "list&index&out&of&range"
>>> s_l = s.split("&")
>>> s_l.count("&")
0
>>> s_l
['list', 'index', 'out', 'of', 'range']
```

**2. 使用空字符串作为分隔符时，Python会报错**

当使用空字符串作为分隔符时，Python会抛出ValueError。

```python
>>> demo = "a, b, c, d"
>>> demo.split("")
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: empty separator
```

#### set函数



#### isdigit()函数



#### eval(x)函数



#### format(x)函数
