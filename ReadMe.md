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

 