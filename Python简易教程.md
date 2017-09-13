 # <center>Python基础笔记</ceneter>

## Python简介
### Python历史
Python 是由 Guido van Rossum 在八十年代末和九十年代初，在荷兰国家数学和计算机科学研究所设计出来的。
Python 本身也是由诸多其他语言发展而来的,这包括 ABC、Modula-3、C、C++、Algol-68、SmallTalk、Unix shell 和其他的脚本语言等等。
像 Perl 语言一样，Python 源代码同样遵循 GPL(GNU General Public License)协议。
现在 Python 是由一个核心开发团队在维护，Guido van Rossum 仍然占据着至关重要的作用，指导其进展。

目前流行的是Python2.x，最新的Python目前是Python3.x。
### Python特征
1. 易于学习：Python有相对较少的关键字，结构简单，和一个明确定义的语法，学习起来更加简单。
2. 易于阅读：Python代码定义的更清晰。
3. 易于维护：Python的成功在于它的源代码是相当容易维护的。
4. 一个广泛的标准库：Python的最大的优势之一是丰富的库，跨平台的，在UNIX，Windows和Macintosh兼容很好。
5. 互动模式：互动模式的支持，您可以从终端输入执行代码并获得结果的语言，互动的测试和调试代码片断。
6. 可移植：基于其开放源代码的特性，Python已经被移植（也就是使其工作）到许多平台。
7. 可扩展：如果你需要一段运行很快的关键代码，或者是想要编写一些不愿开放的算法，你可以使用C或C++完成那部分程序，然后从你的Python程序中调用。
8. 数据库：Python提供所有主要的商业数据库的接口。
9. GUI编程：Python支持GUI可以创建和移植到许多系统调用。
10. 可嵌入: 你可以将Python嵌入到C/C++程序，让你的程序的用户获得"脚本化"的能力。
11. 解释性和编译性：Python语言写的程序不需要编译成二进制代码，可以直接运从源代码运行程序，但是需要解释器。这点类似于Java，或者Matlab。Python也可以编译后执行程序，这样速度优于直接从源代码执行的速度。
12. 面向对象编程：Python支持面向过程的编程也支持面向对象的编程。与其他的语言如C++和Java相比，Python以一种非常强大而又简单的方式实现面向对象编程。
13. 高级语言：使用Python语言编写程序，无需考虑诸如管理内存一类的底层。
14. 丰富的库：

### Python应用场景
国外：
- Google：实现Web爬虫和搜索引擎中的很多组件
- YaHoo： 管理讨论组以及其他技术
- NASA：NASA在他的几个系统中既实用Python开发，又作为脚本语言
- YouTube： 视频分享服务大部分都是由Python编写的

国内：
- 豆瓣：前后台使用Python
- 还有其他很多的现在也是用Python作为前后台开发的

## Python安装
### Linux下Python环境搭建
大多数Linux发行版都默认自带Python，一般都是Python2.x
如果没有安装可以通过源码进行安装：
   ```python
   # ./configure --prefix=/usr/local
   # make && make install
   # make clean 
   # make distclean
   ```
然后命令行直接输入python，打开python解释器，如图：
![](http://i.imgur.com/mLTIuJy.png)
>说明：因为当前没有linux环境，就使用cywin演示了一下，效果是跟linux的一样的。


### Windows下Python环境搭建
Windows下安装很方便，根据系统版本可下载相对应的Python MSI的安装包，按照步骤点击下一步，即可，默认安装在c:\Python2.x目录，不建议更改它的安装目录。
>注意：在安装的过程最好勾选path那个选项，这样Python在安装完毕会自动建立系统环境变量，这样直接通过cmd窗口就可以输入python，打开Python解释器。

安装完毕通过cmd窗口打开python，如图：
![](http://i.imgur.com/lJ3l2dQ.png)

## Python的文件类型
- 源代码：Python的源代码文件以"py"为扩展名，由Python程序解释，不需要编译，可直接运行，特点：可直接运行，方便修改源代码
- 字节代码：Python源文件经过编译后生成的扩展名为"pyc"的文件，特点：运行速度快
  编译方法：
     ```python
     import py_compile
     py_compile("hello.py")
    ```
- 优化代码：经过优化后的源文件扩展名为".pyo"，特点：运行速度快
  优化方法：
   ```python
   python -O -m py_compile hello.py
   ```
- 以上三种均可以直接运行

## Python变量
变量就是给数据起一个名字，写过shell脚本的，应该知道其中的变量，跟他类似。
变量是计算机内存中的一块区域，变量可以存储规定范围内的值，而且值可以改变。
### 变量的命名：
- 变量名可由字母、数字、下划线组成
- 数字不能开头
- 不可以使用关键字

### 变量的赋值：
  - 是变量声明和定义的过程

### 实例演示：
   ```python
   >>>a = 1
   >>>a
   1
   ```
  >说明：给变量a赋值为1，并显示变量a的赋值结果，相当于我有个同学叫1，但是我先麻烦，所以我就给他另起了一个名称a，这样我直接叫a就可以了，当然叫1也行。变量赋值中间的等号严格意义上需要前后有空格，当然没有空格也行，推荐加空格。

### 设定变量的好处：
方便在脚本或者程序中，简化数据长度或者便于一次性修改脚本或者程序中多次使用的值。
  举个简单的例子，如下：
   ```python
   # coding=utf-8
   #!/bin/bash/env python
   #设定变量a并赋值为50
   a = 50
   
   print "我买本Python学习书籍价格"， a
   print "我喝的可乐价格"， a
   print "我买的车价格是"，  a
   ```
  在上述的脚本中，如果价格发生变化，你是不是得每行去修改，如果内容多，那是不是更麻烦，为了减少这种不必要的操作浪费时间，就在开头设定变量a，然后赋值价格，这样，如果价格发生变化我们只需要修改变量a的值即可。简化数据这个有点跟这个相似，就是如果值的的数据很长，这样会增加代码的可读性难度，设定变量就容易多了。
## 运算符和表达式
### 赋值运算符：
- 赋值运算符符号：`=`
- 最常见的就是对于变量赋值，如： a = 1

### 算数运算符：
算术运算符的优先级跟往常的算数运算符优先级一样，遇到其他特殊的网上再查下，后面再整理。
- 加法： `+`,例如： x+y
- 加等于: `+=`,例如：x += 2相当于x = x+2
- 减法： `-`,例如： x -y
- 减等于: `-=`,例如：x -= 2相当于x = x-2
- 乘法： `*`,例如： x*y
- 乘等于: `*=`,例如：x *= 2相当于x = x*2
- 实数除法： `/`,例如： 3/2,3.0/2
- 整除法： `//`,例如： 5.6/2，5.6//2
- 除等于: `/=`,例如：x /= 2相当于x = x/2
- 求余数： `%`,例如： 17%8余1
- 求余等于： `%=`，例如：x %= 2相当于x = x%2
- 求幂运算: `**`,例如： 2**3 = 8

 >注意：使用除法的时候默认是整除，如果想带小数点，后面必须添加小数点（例如：3.0/2）运算符号只适合在数值中使用，如果放在字符串中就另有其意，后面遇到再说。

### 关系运算符：
- 小于号： `<`,例如： 1 < 2
- 大于号： `>`,例如： 2 > 1
- 小于等于号： `<=`,例如： 1 <= 1,1小于等于1
- 大于等于号： `>=`,例如： 2 >= 2,2大于等于2
- 不等于号： `!=`,例如： 1 != 2，1不等于2
- 完全等于号： `==`,例如： 2 == 2，2等于2

 >注意：运算符号前后建议留出一个空格。

### 逻辑运算符：
- 逻辑与： `and`，例如：1 and 2，判断结果必须同时满足1和2，否则不成立
  - 举个小例子：
     ```python
     # coding=utf-8
     #!/bin/bash/env python

     if 1 == 1 and 1 < 2 :
        print "OK"
     else:
     print "Failed"
    ```
  - 运行上面的脚本，返回值如下：
    ![](http://i.imgur.com/tBczrzR.png)
  - 将上面的1 < 2改为 1 == 2，再次运行脚本，返回值如下：
     ![](http://i.imgur.com/xqCbw3x.png)
  >通过以上实例得知逻辑与（and）必须同时满足and前后两个条件，才会成立，否则不成立。
- 逻辑或： `or`,例如：1 or 2，判断结果只要满足其中一个就成立
  - 将上面例子中的脚本的and改为or：
     ```python
     # coding=utf-8
     #!/bin/bash/env python

     if 1 == 1 or 1 == 2 :
        print "OK"
     else:
     print "Failed"
    ```
  - 再次运行一下，返回值如下：
    ![](http://i.imgur.com/d9aCpAm.png)
  >通过以上实例得知逻辑或（or）只要满足其中一个条件即可成立。
- 逻辑非： `not`,例如： not 0，非0，取反
  - 在上面例子中的脚本的or 后面再添加一个逻辑非（not）：
     ```python
     # coding=utf-8
     #!/bin/bash/env python

     if 1 == 1 and  not 1 == 2 :
        print "OK"
     else:
     print "Failed"
    ```
  - 运行返回结果如下：
     ![](http://i.imgur.com/d9aCpAm.png)
  >在未添加逻辑非（not）时，这个条件是不成立的，因为1不会等于2的，添加逻辑非（not）后，告诉1就是不等于2，所以判断成立，返回OK。

### 表达式：
是将不同数据（包括变量、函数）用运算符号按照一定规则连接起来的一种方式。
- 加号表达式： `+`，用于字符串拼接
  - 如下分别定义一个变量a = "Hello"，b = "World"，想让Hello和World变成一句话，可以使用`+`进行拼接：
     ```python
     >>> a = "Hello"
     >>> b = "World"
     >>> a+b
     'HelloWorld'
     ```
- 乘号表达式：`*`，用于字符串重复出现，`*`后面跟重复的次数
  - 如下定义一个变量a = "Hello"，我想让它重复5次，可以使用a*5，如下：
     ```python
      >>> a = "Hello"
      >>> a*5
      'HelloHelloHelloHelloHello'
    ```
    >注意：使用运算符号作为表达式，进行拼接或者重复出现时，变量的赋值必须是字符串（也就是等号后面的值必须用双引号`""`或者单引号`''`包起来）

## Python数据类型

### 数字
#### 整型
- 整型`int`表示的范围-2，147，483，648到2，147，483，648
  - 例如：1，100，200，-100，-200
- 实例演示，通过给num赋值123，可以通过`type()`查看当前变量的属性：
    ```python
    >>> num=123
    >>> type(num)
    <type 'int'>
    ```

#### 长整型
- 长整型（long）的范围很大，几乎可以说任意大的整数都可以存储，当定义的数值超过整型（int）的范围时，就会使用长整型（long）
- 为了区分普通整型和长整型，需要在整数的后面加大写`L`或者小写`l`
  - 例如：5145677888L, -0x45677532L,建议使用大写`L`，避免数字1与小写`l`混合，造成不必要的麻烦
- 实例演示,定义给一个变量num赋值1L，可以通过type()查看当前变量的属性：
    ```python
    >>> num=1L
    >>> type(num)
    <type 'long'>
    ```
  也可以直接给num赋值一个超过整型(int)范围的数值：
    ```python
    >>> num=99999999999999999999999999999999999999999
    >>> type(num)
    <type 'long'>
    ```
#### 浮点型
- 浮点型（float）也就是常说的小数点类型，例如：3.7.-1.8. 3e+8等等
- 实例演示，通过定义变量num赋值2.3，可以通过type()查看当前变量的属性：
    ```python
    >>> num=1.2
    >>> type(num)
    <type 'float'>
    ```

#### 复数型
- Python对复数（complex）提供内嵌支持，这是其他大部分软件所没有的,使用抛物线经常用到
- 复数类型（complex）通过给数值后面添加`j`来实现，如：3.4j,5.67j,32e-56j
- 实例演示，通过定义变量num赋值2.3j，可以通过type()查看当前变量的属性：
    ```python
    >>> num=1.2j
    >>> type(num)
    <type 'complex'>
    ```

### 字符串
- 使用引号（双引号`""`或者单引号`''`)定义的一组可以包含数字，字母，符号（非特殊符号）的集合
  - 例如：
      ```python
      Name = 'My name is Tom'
      Pay = "This is pay"
      Car = """this is a car"""
      ```
    >- 三重引号（docstring)`""" """`通常用来制作字符串后面再详说。
    >- 如果字符串中存在单引号`''`时可以使用双引号`""``，或者通过转义符`\`来进行转义

## 序列
- 列表、元组和字符串都是序列
- 序列的两个主要特点：索引操作和贴片操作符
  - 索引操作符让我们可以从哪个序列中抓取一个特定的项目
  - 切片操作符让我嫩能够获取序列的一个切片，即一部分序列

### 索引
- 索引操作符是序列后跟一个方括号`[]`，方括号中有一对可选的数字
- 索引同样可是负数，位置是从序列尾部开始计算的
  - 例如，当我们想取出a="12345678"中的8，可以这样做：
      ```python
      >>> a = "12345678"
      >>> a[7]
      '8'
     ```
  - 因为索引可以是负数，也可以这样取值：
       ```python
       >>> a[-1]
       '8'
      ```
    >索引位置从左往右是：01234567，从右往左就是：-1，-2，-3，-4，-5，-6，-7，0

>例如：shop[-1]便是序列的最后一个元素，而shop[-2]抓取到的是序列的倒数第二个元素

### 切片
- 切片操作符是序列后跟一个方括号`[]`，方括号中有一对可选的数字，并用冒号分割
  - 这与索引操作符很相似，不过需要使用`:`，并却是必须的
  - 切片操作符中的第一个数（冒号`:`之前）表示切片开始的位置，第二个数（冒号`:`之后）表示切片到哪里结束（不包含这个位置的元素）。如果不指定第一个数，Python就从序列的首位开始。如果没有指定第二个数，Python则会停止在序列的尾部。
    - 例如，定义变量a赋值字符串'12345678'，然后切取23456：
       ```python
       >>> a = "12345678"
       >>> a[1:6]
       '23456'
       ```
      >说明：计算机中`0`是默认开始位置，所以上述12345678对应的位置就是01234567，当我们要切取23456的字符串时，就得从1开始，按照切片取值定义想取到字符串6就得定位到6（这里的6不是字符串6，是7的位置）
    - 从位置1开始取值，不指定第二个位置，将会取到2345678：
       ```python
       >>> a = "12345678"
       >>> a[1:]
       '2345678'
       ```
    - 如果只有`[:]`将会打印出所有的值：
       ```python
       >>> a = "12345678" 
       >>> a[:]
       '12345678'
       ```
    - 当出现`[::]`时，后面没有步长值，默认位置为1，打印效果：
       ```python
       >>> a = "12345678" 
       >>> a[:：]
       '12345678'
       ```
    - 当`[::]`里面设定步长值后，如设置步长值为2：[::2]，打印效果：
       ```python
       >>> a = "12345678" 
       >>> a[:：2]
       '1357'
       ```
      >`[::2]`其实就是起到步长值得作用，后面的数字2就是走两步取后面一个值，上述的例子中，从位置1开始取值，然后从1位置走两步（也就是到位置3）取后面值3，然后从位置3走两步（也就是位置5）取后面值5，然后从位置5走两步（也就是位置7）取后面值7，最后取出来为1357.这里所说的走2步就是从位置1开始走到位置2算一步，然后到位置3就是第二步。

### 序列的基本操作
- `len()`:求序列长度
  - 例如求a = "12345678"的长度：
     ```python
     >>>a = "12345678"
     >>> len(a)
     8
     ```
- `+`:连接2个序列：
   - 例如：
      ```python
      >>> a = "Hello"
      >>> b = "World"
      >>> a + b
      'HelloWorld'
      ```
- `*`:重复序列：
  - 例如将hello重复5次：
       ```python
       >>> a = "Hello"
       >>> a*5
       'HelloHelloHelloHelloHello'
      ```
- `in`：判断元素是否在序列中
   - 例如判断c是否在a = "Hello"中：
      ```python
      >>> a = "Hello"
      >>> 'c' in a
      False
      ```
     >返回Fasle说明不存在
- `max()`:返回最大值
   - 例如查看a = "12345678"中的最大值：
       ```python
       >>> a = "12345678"
       >>> max(a)
       '8'
       ```
- `min()`:返回最小值
   - 例如查看a = "12345678"中的最小值：
       ```python
       >>> a = "12345678"
       >>> min(a)
       '1'
       ```
- `cmp(tuple1, tuple2)`:比较2个序列的值是否相等
   - 例如判断a = "3"与b = "4",返回结果：
       ```python
       >>> a = "3"
       >>> b = "4"
       >>> cmp(a, b)
       -1
       ```
   - 如果a与b换个位置在进行比较一下看下返回结果：
       ```python
       >>> cmp(b, a)
       1
       ```
   - 如果a和b的值相等，看下返回值：
       ```python
       >>> a = "3"
       >>> b = "3"
       >>> cmp(b, a)
       0
       ```
   >通过以上例子可以看出，当使用`cmp（tuple1，tuple2）`进行比较的时候，如果前面的数值大于后面的会返回1，小于时会返回-1，等于时会返回0，另外如果字符串是字母的时候它一般会按照英文字母的顺序进行比对，通常是后面的字母大于前面的，如：

    ```python  
    >>> a = "c"
    >>> b = "d"
    >>> cmp(b, a)
    1
    ```
- `filter()`：返回函数（项目）为真的序列项。 如果函数为None，则返回true。 如果sequence是元组或字符串，返回相同类型，否则返回一个列表。
  语法：
  ```python
  filter(function or None, sequence) -> list, tuple, or string
  ```
  >说明：后面的序列` sequence`是要又迭代作用的，字符串，列表，元组

  实例演示：
  ```python
  >>> filter(None,'hello')
  'hello'
  ```
  ```python
  >>> a = range(10)
  >>> a
  [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
  >>> def fun(x):
  ...     if x > 5:
  ...         return True
  ...
  >>> filter(fun,a)
  [6, 7, 8, 9]
  ```
  ```python
  >>> a = 'hello'
  >>> def fun(x):
  ...     if x == 'h':
  ...         return 'this is h'
  ...     elif x == 'o':
  ...         return 'this is o'
  ...
  >>> filter(fun,a)
  'ho'
  ```
  >说明：`filter()`也可以说是过滤的意思，根据第一个参数函数的定义，然后从第二个参数列表中过滤出符合条件的元素，并且同样以列表的形式输出，稍微有点像`for`循环，如果定义的第二个参数中的列表中不符合第一个参数函数的条件就会返回一个空的列表 ,字符串也一样，不符合就返回空字符串，`需要注意一点的是第二个参数序列是要具有迭代作用的，它是依次向前面的函数传递值，进行判断的`  
- `zip()`：并行遍历，返回一个元组列表，其中每个元组包含每个参数序列中的第i个元素。 返回的列表的长度被截断为最短参数序列的长度。
  语法：
  ```python
   zip(seq1 [, seq2 [...]]) -> [(seq1[0], seq2[0] ...), (...)]
  ```
  实例演示：
  ```python
  >>> a = 'well'
  >>> zip(a)
  [('w',), ('e',), ('l',), ('l',)]
  ```
  ```python
  >>> name = ['tom','jack','black']
  >>> age = [21,23,24]
  >>> num = [123,234,456]
  >>> zip(name,age,num)
  [('tom', 21, 123), ('jack', 23, 234), ('black', 24, 456)]
  >>> num = [123,234]
  >>> zip(name,age,num)
  [('tom', 21, 123), ('jack', 23, 234)]
  ```
  >可以看得出输出的结果是对应同一个位置的元素为一个元组，三个列表的元素个数一样位置也一一对应，如果其中一个列表少一个元素，那么最后输出的结果就会少一组元组

- `map()`：也是属于并行遍历的，将函数应用的结果列表返回到参数序列的项目（这句话是说将函数执行的代码块应用到第二个参数序列中，翻过来就是后面的参数序列传参到前面的函数参数中，然后执行函数返回函数的执行结果)。 如果给出多个序列，则使用由每个序列的相应项(其实也就是列表位置对应的元素）构成的参数列表调用该函数，当不是所有序列的长度相同时，将None替换为缺失值。 如果函数为None，则返回序列项目的列表（或多个序列的元组列表）。
  语法：
  ```python
  map(function, sequence[, sequence, ...]) -> list
  ```
  实例演示：
  ```python
  >>> map(None,name,age,num)
  [('tom', 21, 123), ('jack', 23, 234), ('black', 24, None)]
  ```
  ```python
  >>> def fun(x,y):
  ...     return x*y
  ...
  >>> a = [1,3,5]
  >>> b = [2,4,6]
  >>> map(fun,a,b)
  [2, 12, 30]
  ```
  >说明：以上例子可以看出，`map()`除了做并行遍历之外，还是可以使用函数参数做函数定义的执行操作，需要注意一点`function`与`None`是同级别的，也就是使用`function`的时候后面的序列长度必须一致，否则报错（TypeError: unsupported operand type(s) for *: 'int' and 'NoneType'） 

### 元组
- 元组和列表十分相似，只不过元组和字符串一样是不可变得，即你不能修改元组
- 元组通过圆括号`()`和其中的逗号`,`来分割项目，例如：（1，2，3，4）
- 元组通常用在使语句和用户定义的函数能够安全的采用一组固定（这里的固定式说这组的值不能随意更改）的值得时候使用。
- 定义元组可以包含字符串、列表、数字等，通过逗号`,`分隔。
- 元组的好处，定义范围广
- 元组是不可变类型的数据
- 创建元组:
  - 一个空元组由一对空的圆括号`( )`组成，例如： a = ()
  - 含有单个元素的元组，如：
    - a = (2`,`)
    >注意：定义一个单个元组，元素后面必须有一个逗号`,`这个比较特殊一些。

  - 一般元组, 如：
    -  name = ('Tom','Joy','jack')
    -  user_pay = ('Tom','egg',20)
  - 可以通过type()函数来当前变量的属性：
     ```python
     >>> a = (2,)
     >>> type(a)
     <type 'tuple'>
     ```
    >- 看到tuple就说明此变量为元组
- 元组操作：
  - 元组和字符串类型一样都是属于序列类型，可以通过索引和切片操作
  - 定义好的元组，值不能改变
- 实例演示，定义一个元组a = ('Tom',30,'male')
  - 试图更改元组里面的元素，这里试图修改一个值：
     ```python
     >>> a = ('Tom',30,'male')
     >>> a[1] = 31
     Traceback (most recent call last):
       File "<stdin>", line 1, in <module>
     TypeError: 'tuple' object does not support item assignment
     ```
     >修改其中一个元素报错：告诉我们元组是不支持组分配指定的，也就说不能修改。
  - 拆分元组操作：
     ```python
     >>> a = ('Tom',30,'male')
     >>> name
     'Tom'
     >>> age
     30
     >>> sex
     'male'
     >>> name,age,sex
     ('Tom', 30, 'male')
     ```
### 列表
- 列表(List)是处理一组有序项目的数据结构，即你可以在一个列表中存储一个序列的项目
- 列表是可变类型的数据
- 列表跟元组一样，定义范围广，元素可以是字符串、数字，其中也可以有列表和元组，不过元组不能修改
- 列表的组成：用方括号`[]`表示列表，包含多个元素以逗号`,`分隔，如：
  - List1 = ['Tom','列表',1]
  - List2 = [1,2,3,4,5]
  - List3 = ["python","Linux","wiondows"]
  - List4 = [1]
    >列表不像元组，单个元素的的列表后面需要添加逗号`,`
  - 以上实例可以通过`type()`函数查看器属性，返回结果如下：
       ```python
       >>> List1 = ['Tom','列表',1]
       >>> type(List1)
       <type 'list'>
       ```
       ```python
       >>> List2 = [1,2,3,4,5]
       >>> type(List2)
       <type 'list'>
       ```
       ```python
       >>> List3 = ["python","Linux","wiondows"]
       >>> type(List3)
       <type 'list'>
       ```
       ```python
       >>> List4 = [1]
       >>> type(List4)
       <type 'list'>
       ```
- 列表操作方法：
  - 取值：
    - 索引取值：
      定义一个列表：a = [1,2,3,4,5],通过索引取值：
      ```python
      >>> a = [1,2,3,4,5]
      >>> a[0]
      1
      >>> a[1]
      2
      >>> a[4]
      5
      ```
    - 切片取值：
      定义一个列表：a = [1,2,3,4,5],通过切片取值：
      - 从位置1开始取值，到列表位置结束：
        ```python
        >>> a = [1,2,3,4,5]
        >>> a[1:]
        [2, 3, 4, 5]
        ```
     - 从位置1取值，到位置4：
       ```python
       >>> a = [1,2,3,4,5]
       >>> a[1:4]
       [2, 3, 4]
       ```
     - 从位置4结束取值:
       ```python
        >>> a = [1,2,3,4,5]
        >>> a[:4]
        [1, 2, 3, 4]
       ```
     - 使用`[::]`设定步长值取值，此处设定步长值为2：
       ```python
        >>> a = [1,2,3,4,5]
        >>> a[::2]
        [1, 3, 5]
       ``` 
       >说明：从位置1开始取值（设定步长值后，起始位置为1），然后走2步到位置3取值3（位置3的值），然后从位置3开始走2步取值5（位置5的值），这里所说的走2步就是从位置1开始走到位置2算一步，然后到位置3就是第二步。
    - 添加值，使用属性`append`来实现：
      - 定义一个列表a = [1,2,3,4,5],然后通过`append`属性添加值：
        ```python
        >>> a = [1,2,3,4,5]
        >>> a.append(6)
        >>> a
        [1, 2, 3, 4, 5, 6]
        ```
       >说明：属性`append`属于给列表结尾追加值，存储空间会变化，可通过`id`来确认
    - 删除值：
      - 使用`del`删除列表中的元素：
        ```python
        >>> a = [1,2,3,4,5,6]
        >>> del(a[5])
        >>> a
        [1, 2, 3, 4, 5]
        ```
        >`del()`通过列表索引删除指定的元素，好处在于如果列表元素太长，使用`del()`能快速删除指定的元素，简单明了。而且可以直接删除整个列表。
     - 使用`remove`删除列表中的元素：
        ```python
        >>> a = [1,2,3,4,5]
        >>> a.remove(5)
        >>> a
        [1, 2, 3, 4]
        ```
       >`remove`直接指定列表的元素就可以删除
     
    - 修改值：
      - 通过`list[] = x`来对列表中的元素进行修改：
        ```python
        >>> a = [1,2,3,4]
        >>> a[3] = 5
        >>> a
        [1, 2, 3, 5]
        ```
       >通过索引重新赋值即可
   - 修改列表中的元素列表的存储空间不变（扩展说明），例：
      - 定义一个列表a = [1,2,3,4,5]
      - 首先查看列表a的存储空间id:
        ```python
         >>> a = [1,2,3,4,5]
         >>> id(a)
         7696579682248
        ```
      - 通过索引重新赋值修改其中一个元素的值：
        ```python
        >>> a = [1,2,3,4,5]
        >>> a[1] = 6
        >>> a
        [1, 6, 3, 4, 5]
        ```
     - 再次通过`id()`来查看列表a的存储空间id值：
       ```python
       >>> a = [1,6,3,4,5]
       >>> id(a)
       7696579682248
       ```
       >此时发现修改列表a的值后，通过`id()`查看存储空间id，未变化
    - 查找值：
      - 通过`var in list`来查找列表中是否有这个值：
        ```Python
        >>> a = [1,2,3,5]
        >>> a in a
        False
        >>> 5 in a
        True
        ```
       >说明：在列表中查找a，a不存在返回`False`，查找5存在则返回`True`
       
### 字典
- 字典是python中唯一的映射类型`{哈希表}`
- 字典对象是可变的，但是字典的键必须使用不可变对象，并且一个字典中可以使用不同类型的键值
- `keys()`或者`values()`返回列表或者值列表
- `items()`返回包含键值对的元组
- 创建字典：
  - 使用花括号`{}`,例如： a = {0:'id',1:'name',2:age'}，执行结果：
    ```python
    >>> a = {0:'id',1:'name',2:'age'}
    >>> a
    {0: 'id', 1: 'name', 2: 'age'}
    ```
  - 使用工厂方法`dict()`，这种方法慢，例如：fdict = dict((['x',1],['y',2])),执行结果：
    ```python
    >>> fdict = dict((['x',1],['y',2]))
    >>> fdict
    {'y': 2, 'x': 1}
    ```
    >注意：`dict()`圆括号里面是映射对象的`(key,value)对`中初始化新字典
    
    当然了也可以在关键列表中使用`name=value对`初始化新字典，例如：a = dict(one=1,two=2),执行结果如下：
    ```python
    >>> a = dict(one=1,two=2)
    >>> a
    {'two': 2, 'one': 1}
    ```
    
  - 内建方法：`fromkeys()`,字典中的元素具有相同的值，默认为None，例如：num = {}.fromkeys(('x','y'),-1),执行结果：
    ```python
    >>> num = {}.fromkeys(('x','y'),-1)
    >>> num
    {'y': -1, 'x': -1}
    ```
- 访问字典中的值：
  - 直接使用`key`：`key`不存在会报错，可以使用`has_key()`或者`in`和`not in`判断，`has_key()`方法即将被弃用,如判断字典 a =  {'age': 23, 'name': 'guo', 'sex': 'm'}中是否存在键值name，执行结果如下：
     ```python
     >>> a.has_key('name')
     True
     ```
     当然了也可以通过`in`和`not in`判断，判断键值name和aa是否存在在字典a中，执行结果如下：
     ```python
     >>> 'name' in a
     True
     >>> 'aa' not in a
     True
     ```
     >说明：返回值为`True`代表存在，`Fasle`代表不存在
  - 循环遍历,；例如：
     ```python
     for key in dict1.keys():
     ```
    实例：
     ```python
     >>> a = {'name':'guo','age':23,'sex':'m'}
     >>> a
     {'age': 23, 'name': 'guo', 'sex': 'm'}
     >>> a = {'name':'guo','age':23,'sex':'m'}
     >>> a
     {'age': 23, 'name': 'guo', 'sex': 'm'}
     ```
    打印key值：
      ```python
      >>> for key in a:
      ...     print key
      ...
      age
      name
      sex
     ```
    打印value值：
    ```python
    >>> for key in a:
    ...     a[key]
    ...
    23
    'guo'
    'm'
    ```
  - 使用迭代器，例如：
     ```python
     for key in dict1:
     ```
- 更新和删除：
  - 直接使用键值访问更新，内建的`update()`方法可以将整个字典的内容拷贝到另一个字典中，例如将字典b = {'room': 1, 'service': 220, 'number': 202}拷贝到字典a = {'age': 23, 'name': 'guo', 'sex': 'm'}中，执行结果如下：
    ```python
    >>> a = {'age': 23, 'name': 'guo', 'sex': 'm'}
    >>> b = {'room': 1, 'service': 220, 'number': 202}
    >>> a.update(b)
    >>> a
    {'name': 'guo', 'service': 220, 'room': 1, 'age': 23, 'number': 202, 'sex': 'm'}
    ```
    >说明：字典当中是无序排列，所以不管你添加还是修改，最后的输出都会与之前的序列不一致
  - `del dict1['a']`删除字典中键值为a的元素，例如删除字典d = {'car':'baoma','color':'blue'}中的color键和对应的值，执行结果如下：
      ```python
      >>> d = {'car':'baoma','color':'blue'}
      >>> d
      {'color': 'blue', 'car': 'baoma'}
      >>> del d['color']
      >>> d
      {'car': 'baoma'}
      ```
    - `dict11.pop('a')`删除并返回键为'a'的元素，例如删除字典a = {'car': 'baoma'},执行结果如下：
       ```python
       >>> a = {'car': 'baoma'}
       >>> d.pop('car')
       'baoma'
       >>> d
       {}
      ```
     >说明：字典内建方法`dict.pop()`与其他内建`pop()`有区别的，具体需要查看help手册(`help(object.pop))`
    - `dict1.clear()`删除字典所有的元素,例如删除字典d = {'car':'baoma','color':'blue'}中所有的元素，执行结果如下：
        ```python
        >>> d = {'car':'baoma','color':'blue'}
        >>> d
        {'color': 'blue', 'car': 'baoma'}
        >>> d.clear()
        >>> d
        {}
        ```  
    - `del dict1`删除整个字典，例如删除字典d = {'car':'baoma','color':'blue'}，执行结果如下：
        ```python
        >>> d = {'car':'baoma','color':'blue'}
        >>> d
        {'color': 'blue', 'car': 'baoma'}
        >>> del d
        >>> d
        Traceback (most recent call last):
          File "<stdin>", line 1, in <module>
        NameError: name 'd' is not defined
       ```
     >说明：底下报错d没有被定义，说明字典d已经不存在了
  - `dict1['a] = 'string'`添加一对键值，例如给c = {'id':1,'class':23,'location':345}添加一对键值'pay':45，执行结果如下：
    ```python
     >>> c = {'id':1,'class':23,'location':345}
     >>> c['pay'] = 45
     >>> c
     {'pay': 45, 'location': 345, 'id': 1, 'class': 23}
    ```
- 字典相关的内建函数：
  - `type()`、`str()`、`cmp()`（cmp很少用于字典比较，
比较依次是字典的大小、键、值）。
  - 工厂函数`dict()`，例如：a = dict((['x','y'],[1,2]))，b = (one=1,two=2),执行结果如下：
     ```python
     >>> a = dict((['x','y'],[1,2]))
     >>> a
     {'x': 'y', 1: 2}
     ```
     ```python
     >>> b = dict(one=1,two=2)
     >>> b
     {'two': 2, 'one': 1}
     ```
  - 使用`dict()`生成字典比用`copy慢，因此这种情况下推荐使用`copy()`，例如：将字典 t = {'x':1,'y':2}的元素拷贝给新的字典c，使其拥有字典t一样的键值，执行结果如下：
    ```python
    >>> t = {'x':1,'y':2}
    >>> c = t.copy()
    >>> c
    {'y': 2, 'x': 1}
    ```
   >说明：`copy()`属于字典内建函数，所以直接使用`help(copy)`是无法查看其帮助信息的，应该是`help(t.copy)`才能查看其帮助信息，这个与python中`import copy`有区别的，虽然用法差不多一样，简单说，查看字典内建函数的帮助信息用法`help(t.copy)`其中的`t`是字典的对象，`copy`是其内建方法（也就是内建函数）
   
    - 具体事例如下，首先得创建一个字典，如：a = {'x':1,'y':2}
    - 先查看字典`a`对象的所有的帮助信息，执行以下步骤：
      ```python
       >>> help(a)
       Help on dict object:
       
       class dict(object)
      |  dict() -> new empty dictionary
      |  dict(mapping) -> new dictionary initialized from a mapping object's
      |      (key, value) pairs
      |  dict(iterable) -> new dictionary initialized as if via:
      |      d = {}
      |      for k, v in iterable:
      |          d[k] = v
      |  dict(**kwargs) -> new dictionary initialized with the name=value pairs
      |      in the keyword argument list.  For example:  dict(one=1, two=2)
      |
      |  Methods defined here:
      |
      |  __cmp__(...)
      |      x.__cmp__(y) <==> cmp(x,y)
      |
      |  __contains__(...)
      |      D.__contains__(k) -> True if D has a key k, else False
      |
      |  __delitem__(...)
      |      x.__delitem__(y) <==> del x[y]
      
      ......
      
      |  clear(...)
      |      D.clear() -> None.  Remove all items from D.
      |
      |  copy(...)
      |      D.copy() -> a shallow copy of D
      |
      |  fromkeys(...)
      |      dict.fromkeys(S[,v]) -> New dict with keys from S and values equal to v.
      |      v defaults to None.
      ```
      >说明：这就显示当前字典`a`所有的类和方法的帮助信息
    
   - 查看字典中`copy()`的帮助信息，执行一下步骤：
     ```python
     >>> help(a.copy)
     Help on built-in function copy:
	 
     copy(...)
         D.copy() -> a shallow copy of D
     (END)
     ```
    >说明：这里面就是字典内建函数`copy()`的查看帮助信息，其他的也是这样弄得，执行命令就得`字典对象.内建函数()`,例：`a.copy()`
- 字典内建函数方法小结：
  - `len()`，输出字典长度，其实也是系统内建函数,列表、元组变量都能使用，使用方法：`len(object)`，例如：
    ```python
    >>> a = {'x':1,'y':2}
    >>>  len(a)
    2
    ```
    >说明：`len()`输出的长度在字典中是按一对键值来输出的，在列表、元组】变量中是按照里面的元素计算输出的，也就是说一对键值就是一个长度
  - `hash`,系统内建函数，用于判断某个对象是否可以做一个字典的建，非哈希类型的报TypeError错误，使用方法`hash(object)`,例如：
    ```python
    >>> a = {'x':1,'y':2}
    >>> hash(a)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: unhashable type: 'dict'
    ```
    ```python
    >>> a = {'x':1,'y':2}
    >>> hash(3)
    3
    ```
    >备注简单说只要hash的对象结果有返回值，并且不报错就可以最为一个字典的键值使用，`hash(object)`也可用配合关系运算符判断两个对象是否相等（对于两对象使用这个，感觉有点多次一举，具体的后面研究了再说把）
  - `dict.has_key(key)`判断字典中是否存在key（建议使用`in`和`not in`代替）,他属于字典内建函数方法，使用方法：
    ```python
    >>> a = {'x':1,'y':2}
    >>> a.has_key(2)
    False
    >>> a.has_key('x')
    True
    >>> a.has_key('y')
    True
    ```
    >备注：其实这个前面已经说过的，这个后续会摈弃这个方法的
  - `dict.items()`返回键值对元组的列表，属于字典内建函数方法，例如：
     ```python
     >>> a = {'x':1,'y':2}
     >>> a.items()
     [('y', 2), ('x', 1)]
     ```
     >说明：也就是说将字典里面的键值对组成元组，最后以一个列表的形式输出
  - `dict.iter*()`（里面的星号代表后面有个方法名称），返回迭代子而不是列表，使用方法：
    - `dict.iteritems()`：
       ```python
       >>> a = {'x':1,'y':2}
       >>> a.iteritems()
       <dictionary-itemiterator object at 0x6ffffbb8f70>
      ```     
    - `dict.iterkeys()`:
       ```python
       >>> a = {'x':1,'y':2}
       >>> a.iterkeys()
       <dictionary-keyiterator object at 0x6ffffbb8fc8>
       ```
    - `dict.itervalues()`:
       ```python
       >>> a = {'x':1,'y':2}
       >>> a.itervalues()
       <dictionary-valueiterator object at 0x6ffffbb8f70>
       ```
      >备注：这个有点高大上了，这个迭代子目前不知道具体是干嘛用的，
  - `dict.get(key[,default=none])`,返回key的值，如果不存在返回default指定的值（命令中帮助参数中的`[]`代表可选，可有可无），这里的default指定是说当key不存在的时候，你可以任意指定一个返回值，例如：
    ```python
    >>> a = {'x':1,'y':2}
    >>> a.get('x')
    1
    >>> a.get('z', 'z is not exist')
    'z is not exist'
    ```
    >说明：第一次get x键值，因为存在，所以返回x键的值1，第二次get z，不存在，默认是返回none，也就是返回结果不会有任何提示，为了友好点，我们就指定一个不存在的提示语，执行后悔看到我们指定的提示语：'z is not exist'
  - 其他字典内建的函数方法，就不再说了，可以使用`help(object)`（这里的object就是字典的对象，如：a = {'x':1,'y':2}，对象就是a）查看所有的类和方法，英文的不明白，推荐去[RUNOOB.COM](http://www.runoob.com/python/python-tutorial.html)看下，这里讲的可比我总结的详细，我这是自己学习总结为了加深学习记忆而已。

## 流程控制
### `if`语句：
- Python的`if`语句类似于其他语言，`if`语句包含一个逻辑表达式，使用表达式比较，在比较的结果的基础上做出决定。
- 语法格式：
   ```python
   if expression: 如果表达式(等于、不等于、大于、小于、存在、不存在等)满足条件
       statement(s) 声明（执行代码或者显示需要显示的结果)
   ```
   >说明：Python语言使用缩进作为其语句（代码块）分组的方法，建议使用4个空格代替其他缩进格式（这也是官方推荐的，主要是为了兼容跨平台），缩进相同的被认为是一个代码块。
- 实例，判断1>2：如下：
   ```python
   >>> if 1 < 2:
   ...     print "1 小于 2正确"
   ...
   1 小于 2正确
   ```
   >注意：python当中的`if`语句跟其他语言的格式可能有点区别的
   
   比如shell当中是这样的：
   ```python
   if expression;
   then
       statement(s)
   fi
   ```
- `if`语句常用的逻辑值表达式（bool）：
  - 逻辑值（bool）用来表示诸如：对与错、真与假、空与非空等概念
  - 逻辑值包含了两个值：
    - True：表示非空的量（string，tuple，list，set，dictonary等），所有非空零数
    - False：表示0，None，空的量等
  - 作用：主要用在判断语句中进行判断：
    - 一个字符串是否空的
    - 一个运算是否为零
    - 一个表达式是否可用

   >说明：True就是真实存在的，比如：判断1<2，本来1肯定小于2，所以结果肯定是True了，False就是不存在，例如：1>2，根本不可能的，所以结果是False
  - 实例：
    - 判断条件为True，查看返回结果：
       ```python
        # vi python.py
        #!/bin/env python
	    
        if True:
            print "True is ok"
        print "Fasle and True"
       ```
       ```python
        # python python.py
        True is ok
        Fasle and True
      ```
      >备注：当条件为True时，所有的print都返回,这里写在3脚本是为直观
   - 判断条件为False，查看返回结果：
      ```python
      # vi python
      #!/bin/env python
	  
       if True:
           print "True is ok"
       print "Fasle and True"
     ```
     ```python
     # python python
     Fasle and True
     ```
     >备注：此时，当条件为`False`时，返回结果只`print "Fasle and True"`，之所以这里还会仍旧显示这个，是因为`print "Fasle and True"`跟`if`同级别的，不在`if`的判断里面
- else语句：
  - else语句不能单独使用，必须配合if使用
  - 语法格式：
    ```python
    if expression:   如果表达式成立
        statement(s) 执行代码
    else:            否则 
        statement(s) 执行这个代码
    ```
   >备注：`else`是个可选的语句，并且一个`if`语句中只能使用一个`else`语句
  - 实例：
    判断如果用户输入一个数字1返回ok，否则返回error：
    ```python
    # cat p.py
    #!/bin/env python
    
    a = raw_input("please input number: ")
    
    if a == "1":
        print "your input is ok"
    else:
        print "your input is Error"
    ```
    ```python
     # python p.py
     please input number: 1
     your input is ok
    ```
    ```python
    # python p.py
     please input number: 2
     your input is ok 
    ```
- `elif`语句：
  - `elif`语句存在的意义，当需要多个表达式为真值时执行一段代码，`elif`可以存在多个，并且它也是可选的，比如说,当用户输入1-5的数字时，执行一段代码告诉他相对应的结果，否则就告诉他失败
  - 语法格式：
    ```python
    if expression:     如果满足条件
        statement(s)   执行这个代码
    elif expression2:  如果也满足这个条件
        statement(s)   执行这个代码
    elif expression3:
        statement(s)
    ......
    else:              否则
        statement(s)   执行这个代码
    ```  
  - 实例：：
    判断如果用户输入1-5就返回相应的结果，否则就返回error：
    ```python
    # vi p.py
    #!/bin/env python

    a = int(raw_input("pleae your number: "))
    
    if a == 1:
        print "your input number is 1 ok"
    elif a == 2:
        print "your input number is 2 ok"
    elif a == 3:
        print "your input number is 3 ok"
    elif a == 4:
        print "your input number is 4 ok"
    elif a == 5:
        print "your input number is 5 ok"
    else:
        print "your input number is %s error" % a
    ```
   
    ```python
    # python p.py
    pleae your number: 1
    your input number is 1 ok
    ```
    ```python
    # python p.py
    pleae your number: 6
    your input number is 6 error
    ```
     >备注：就演示一下输入1和输入6就可以达到目的了,这里面的`%s`和`%`输出格式化的字符串和格式化字符串
- 逻辑语：`and`、`or`,`not`
  直接使用案例解说吧，`and、`or`、`not`含义在上面的【运算符和表达式】已经说过了，这里再简单回顾下。
 - `and`:两个条件必须同时满足才成立
 - `or`:有一个条件满足就成立
 - `not`:非，取反的意思，例如：
   ```python
   >>> not 1 > 2
   True
   >>> 1 > 2
   False
   ```

### `for`循环语句
  循环是一个结构，是一个程序重复`一定次数`
  条件循环也是如此，当条件变为假，循环结束
- `for`循环：在python `for`循环遍历序列，如一个列表或者一个字符。这个遍历跟其他的差不多
- `for`循环语法：
  ```python
  for iterating_var in sequence:
      statement(s)
  ```
  >注意：如果一个序列包含一个表达式列表，他是第一个执行，然后该序列中的第一项赋值给迭代变量`iterating_var`  。接下来，执行语句块（代码块）。列表中的每个项目分配到`itering_var`,代码块被执行，知道整个列表被耗尽。这有点想公安扫黄一样，酒店就是个大列表，其中所有的住的人就是元素也就是`itering_var`,公安就是下面的代码块，遍历酒店，将每个房子里面的人赋值给`itering_var`.最后注意了格式要遵循代码块缩进原则。

  - 举个小例子：
    ```python
    >>> a = [1,2,3,4,5,6]
    >>> for i in a:
    ...     print i
    ...
    1
    2
    3
    4
    5
    6
    ```
- 迭代序列指数（索引）：遍历每个项目的另一种方法是由序列本身的偏移指数（索引）
  - 实例：
    ```python
    # vi p.py
    #!/bin/env python

    a = ['name','age','number']
    
    for index in range(len(a)):
        print 'result: ', a[index]
    print 'good bye'
    ```
    >说明：`len()`是取值列表a的长度，`range()`是将其长度生成一个范围的列表
    >注意：迭代指重复执行一个指令
    
    `len()`、`range()`函数演示结果：
    ```python
    >>> a = ['name','age','number']
    >>> len(a)
    3
    >>> range(3)
    [0, 1, 2]
    ```
    
    执行结果：
    ```python
    # python p.py
    result:  name
    result:  age
    result:  number
    good bye
    ```
    >说明：定义一个含有name，age，number的列表a，使用`len()`得出列表a的长度，然后使用`range()`将`len()`得出的长度返回一个整数列表（也就是列表a的索引），然后遍历`range()`得出的列表，依次赋值给迭代函数`index`，然后通过列表索引取值方法，使用迭代变量`index`作为列表a的里面元素的索引，打印出对应位置的元素。
- `range`函数：
  - 循环结构是用于迭代多个项的`for`语句，迭代形式可以循环序列的所有成员
  - 语法：`range(i,j,[,步进值])`，后面的步进值可选跟之前切片里面的步进值一样，默认为1，从1开始
    - `i`为初始值，也就是起始范围
    - `j`为终止值，也就是结束范围，但不包括在使用范围内，跟切片取值一样
    - `i`不选，默认为0开始，一般如果只有一个值代表就是结束值
    - 步进值默认开始为1，步进值就是就是从当前值开始走选取设定步数位置的值
  - 实例：
    - 起始值为1，结束值6，执行结果：
      ```python
      >>> range(1,6)
      [1, 2, 3, 4, 5]
      ```
    - 当前`range()`只有一个值时（也就是终止值）为6时，执行结果：
      ```python
      >>> range(6)
      [0, 1, 2, 3, 4, 5]
      ```
    - 起始值为1，终止值为9，步进值为2（也就是走两步取一个值），执行i结果如下：
      ```python
      >>> range(1,9,2)
      [1, 3, 5, 7]
      ```
      >备注：步进值详细的可以看下【切片】里面的解说,只有有起始值和结束值时才能设定步长值（至于为什么，不用说就应该晓得吧）
      
    - 1加到100的值：
      ```python
      >>> n = 0
      >>> for i in range(1,101):
      ...     n = i + n
      ...     print n
      1
      3
      6
      10
      15
      ......
      4656
      4753
      4851
      4950
      5050
      ```
      >最终的5050就是1加到100的值，语法解说：定义一个变量n赋值为0，然后使用`for`循环遍历1到100，将其遍历的值依次赋值给迭代变量`i`,然后将迭代变量`i`的值赋值给变量n（也就是存储在n中），然后将下次遍历的值赋值给迭代变量`i`，然后让`i`与存储的值变量`n`相加，直到遍历结束为止（到达100），如果不理解可以这样来看，比如说我想算出1加到9的值，通常我们使用：`1+2+3+4+5+6+7+8+9`来计算得出结果为45，这个理解就简单多了，加到9就是不停的原来基础上相加，从而得到1加到9的值，结束，遍历就是一遍一遍的去查看列表里面的值，迭代就是在原有的基础上不停的追加，
  
### 循环控制
- `break`：用来终止循环语句（跳出整个循环），即循环条件没有False或者序列还没有被完全递归完，也会停止循环语句，如果在嵌套循环中使用，`break`语句将停止最深层的循环，并且开始执行下一个代码。用在`while`和`for`语句中。
  - 语法：
    ```python
    break
    ```
  - 实例演示：
    ```python
    #coding=UTF-8
    #!/bin/env python
    
    for i in 'Python':
        if i == 'h':
            break  #当迭代变量等于5时退出循环
        print '打印当前输入字母:', i
    var = 10
    while var > 0:
        var -= 1
        if var == 5: #当变量等于5时退出循环
            break
        print '打印出当前变量值:', var
    print 'good bye'
    ```
   执行结果：
    ```python
   # python p.py
  打印当前输入字母: P
  打印当前输入字母: y
  打印当前输入字母: t
  打印出当前变量值: 9
  打印出当前变量值: 8
  打印出当前变量值: 7
  打印出当前变量值: 6
  good bye
  ```
  >说明:有以上结果看的出来，当其中的if语句中的条件满足后执行`beak`后面的字符就不会在打印出来，也就是跳出整个循环了，如果取消`break`将会打印所有的。
- `continue`：跳出当前循环的剩余语句，然后继续进行下一轮循环，用在`while`和`for`语句中。
  - 语法：
    ```python
    continue
    ```
  - 实例演示：
    ```python
    #coding=UTF-8
    #!/bin/env python
    
    for i in 'Python':
        if i == 'h': #跳出本次循环，也就是不打印h
            continue
        print '打印当前输入字母:', i
    var = 10
    while var > 0:
        var -= 1
        if var == 5: #当变量等于5时退出本次循环，也就是跳过5不打印它
            continue
        print '打印出当前变量值:', var
    print 'good bye'
    ```
    执行结果：
    ```python
    # python p.py
    打印当前输入字母: P
    打印当前输入字母: y
    打印当前输入字母: t
    打印当前输入字母: o
    打印当前输入字母: n
    打印出当前变量值: 9
    打印出当前变量值: 8
    打印出当前变量值: 7
    打印出当前变量值: 6
    打印出当前变量值: 4
    打印出当前变量值: 3
    打印出当前变量值: 2
    打印出当前变量值: 1
    打印出当前变量值: 0
    good bye
    ```
    >说明：以上 结果看出，当满足`if`语句条件时，执行`continue`跳出本次循环继续下次循环，不打印满足条件的，`for`是遍历循环，当列表循环完毕就停止，`while`不一样，他是条件为真就一直循环，所以在使用`while`的时候，注意点防止死循环。

- `pass`：是空语句，是为了保持程序结构的完整性，不做任何事情，一般用做占位语句。
   - 语法：
    ```python
    pass
    ```
  - 实例演示：

    ```python
    #coding=UTF-8
    #!/bin/env python
    
    for i in 'Python':
        if i == 'h':
            pass
            print '打印pass'
        print '打印当前输入字母:', i
    print 'good bye'
    ```
    执行结果：
    ```python
    # python p.py
    打印当前输入字母: P
    打印当前输入字母: y
    打印当前输入字母: t
    打印pass
    打印当前输入字母: h
    打印当前输入字母: o
    打印当前输入字母: n
    good bye
    ```
   >说明：`pass`就是占位，占着位置不做任何事，其实说准确一点就是相当于将`pass`上面的语句注释掉，不让他执行
- `exit()` ：Python内建函数，当执行`exit()`直接退出Python程序，交互模式下推出交互模式
  - 语法：
    ```python
    exit()
    ```
  - 实例演示：
    ```python
    #coding=UTF-8
    #!/bin/env python
    
    for i in 'Python':
        if i == 'h':
            exit()
            print '打印pass'
        print '打印当前输入字母:', i
    print 'good bye'
    ```
   执行结果：
   ```python
   # python p.py
   打印当前输入字母: P
   打印当前输入字母: y
   打印当前输入字母: t
   ```
   >说明：看上面的结果当满足`if`中的条件时执行`exit()`后，后面只打印到t，就不再显示了，说明退出程序了，`exit()`好像用的少。

### `while`循环语句
- `while`循环：直到表达式变为假，表达式是一个逻辑表达式，必须返回一个`True`或者`False`值，如果条件为真就一直循环，如果想循环结束必须添加结束条件（比如：`break`)所以在使用`while`循环条件为`True`时注意避免产生死循环.
- 语法：
  ```python
  while expression:
      statement(s)
  ```
  >说明：遵循代码缩进原则
- 实例演示：
  `while`条件为`True`：
  ```python
  #coding=UTF-8
  #!/bin/env python
  
  while True:
    print "hello"
    x = int(raw_input('number: '))
    if x == 5:
        break
  ```
  执行结果：
  ```python
  # python p.py
  hello
  number: 4
  hello
  number: 7
  hello
  number: 8
  hello
  number: 5
  ```
  >说明：当x不等于5时一直循环，当等于5时跳出所有的循环，不管循环还是单个语句，都是遵循由上而下的执行，也就说，上面的`while`为真，然后打印hello，然后进行判断，如果不满足就一直打印。
  
  `wihle`条件为表达式： 
   ```python
   #coding=UTF-8
   #!/bin/env python
   
   x = " "
   while  x != 5:
       print "hello"
       x = int(raw_input('number: '))
   ```
   执行结果：
   ```python
   # python p.py
   hello
   number: 1
   hello
   number: 3
   hello
   number: 5
   ```
   >说明：其实这个跟上面的相似，只不过使用if作为判断跳出了，这里的`x`为全局变量赋值为空，下面的`x`是对其重新赋值。
   
   直接按回车结束：
   ```python
   #coding=UTF-8
   #!/bin/env python
   
   x = " "
   while  x != '5':
       print "hello"
       x = raw_input('number: ')
       if not x:
           break
   ```
   >说明：空如果当作布尔值就是False，如果x为空是什么不输入，输入`if x:`为False，代码不执行，所以加个`not`取反，也就说`while`循环语句条件必须满足为真才执行，不然就不执行，这跟`if`和`for`是有区别的，上面的例子中`x`为空字符串，`while`条件中`x != '5'`不等于5为真所以执行，当输入回车后（为空），到`if not x:`时，判断是`x`不为空，而结果是空，就执行`break`，有人想了，既然输入为空，那么`if`判断正好为空，也就是满足`if`条件，那就应该执行啊。
   >`在Python程序语言指定任何非0和非空（null）值为true，0 或者 null为false,`
   >`只有“判断条件成立时（非零）才会执行后面的语句（代码）非print，因为为空也是能打印的`，所以这里必须取反，也就是将`False`通过`not(非)`变成`True(真,not False)`,当`if`判断是条件`not x`非空为真，如果输入的为非空就一直执行，如果为空，那么就执行`break`，也就是条件为假停止循环，跟上面`while x != '5'`一样的道理。
   
  执行结果,输入5结束：
  ```python
   # python p.py
   hello
   number: 4
   hello
   number: 6
   hello
   number: 5
   ```
   执行结果,输入回车结束：
    ```python
   # python p.py
   hello
   number: u
   hello
   number: t
   hello
   number:
   ```
  - `while`语句中也是可以使用`else`语句，例如：
    ```python
    #coding=UTF-8
   #!/bin/env python
   
   x = " "
   while  x != '5':
       print "hello"
       x = raw_input('number: ')
       if not x:
           break
   else:
        print "game over "
   ``` 
   执行结果：
   ```python
   # python p.py
   hello
   number: 4
   hello
   number: 8
   hello
   number: 9
   hello
   number: 5
   game over
   ```
   >注意：这里当输入5时退出循环，并打印game over，但是输入回车不会打印game over是因为这里的`else`是跟`while`同级别的。

## 函数
- 函数简介：
  - 函数就是完成特定功能的一个语句组，这组语句可以作为一个单位使用，并且给他去一个名字。
  - 可以通过函数名在程序的不同地方多次执行（这种通常叫做函数调用），却不需要在所有的地方都重复编写这些语句。
  - 自定义函数：用户自己编写的
  - 预定义的Python函数：系统自带的一些函数，还有一些第三方编写的函数，如其他程序员编写的一些函数，对于这些现成的函数用户可以直接拿来使用。
- 使用函数的好处：
  - 降低编程的难度：使用函数可以将代码分块处理，将复杂问题分解，单独一个一个处理，这样使代码简单明了，方便修改、调用代码块
  - 代码重用：我们定义的函数可以在一个程序的多个位置使用，也可以用于多个程序。此外，我们也可以把函数放到一个模块中供其它程序员使用，同时，我们也可以使用其他程序员定义的函数，这样避免了重复的劳动，也大大提高了工作效率。
- 如何实现函数
  - 函数的定义：
    - 语法：
      ```python
      def 函数名(可选参数列表)：
          函数体
      ```
    - 函数名的组成：函数名称的组成跟变量差不多，可以使字母，数字，下划线，但是数字不可以开头，如果函数的名字由两个以上的单词开头的，第二个单词首字母大写。
    - 实例演示：
      ```python
      >>> a = 100
      >>> b = 200
      >>> def aaa():
      ...     c = a + b
      ...     print c
      ...
      >>> aaa()
      300
      ```
  - 函数的调用：
    - 语法：
      ```python
      函数名(可选参数)
      ```
      >备注：调用跟上面函数定义里面的方法一样`aaa()`这样的，在脚本中也是这样，如果不调用，函数是不执行的。  
- 形式参数和实际参数
  - 在定义函数时，函数后面圆括号中的变量名称叫做“形式参数”，或者简称“形参”
  - 在调用函数时，函数后面圆括号中的变量名称叫做“实际参数”，或者简称“实参” 
  - 实例演示：
    ```python
    >>> def fun(x): #形参
    ...     print x
    ...
    >>> fun(100)  #实参
    100
    ```
    >说明：定义函数时括号里面的变量是形参，调用函数是括号里面的是实参，并且形参和实参的数量保持一致，也就是说有几个形参，就得有几个实参，不然就会报错。
    
  - 多个形参和实参演示：
    ```python
    #coding=utf-8
    #!/bin/env python
    
    def fun(x,y):
        if x == y:
            print x, '=', y
        else:
            print x, '!=', y
    s1 = raw_input("please input your content1: ")
    s2 = raw_input("please input your content2: ")
    
    fun(s1,s2)
    ```
    执行结果：
    ```python
    # python test1.py
    please input your content1: 1
    please input your content2: 1
    1 = 1
    ```
    ```python
    # python test1.py
    please input your content1: 1
    please input your content2: 2
    1 != 2
    ```
    此时如果调整实参`fun(s1,s2)`为`fun(s2,s1)`结果如何：
    ```python
    #coding=utf-8
    #!/bin/env python
    
    def fun(x,y):
        if x == y:
            print x, '=', y
        else:
            print x, '!=', y
    s1 = raw_input("please input your content1: ")
    s2 = raw_input("please input your content2: ")
    
    fun(s2,s1)
    ```
    执行结果：
    ```python
    # python test1.py
    please input your content1: 1
    please input your content2: 1
    1 = 1
    ```
    ```python
    # python test1.py
    please input your content1: 1
    please input your content2: 2
    2 != 1
    ```
    >说明：输出结果都是通过赋值给变量`print x, '!=', y`打印出来的，当`fun(s1,s2)`时，输入1、2打印出`1 != 2`对应的变量是`x, '!=', y`，当`fun(s2,s1)`时，输入1、2打印出`2 != 1`对应的变量也是`x, '!=', y`，由此可见，形参和实参的位置是对应的，不会因为实参里面参数顺序调整而影响形参的顺序。

- 函数缺省参数（默认参数）
  - 设置两个默认参数，实例演示：
    - 当用户什么也不输入就使用默认参数：
      ```python
       #coding=utf-8
       #!/bin/env python
       
       def eatfood(x=3,y='奶油'):
           print "支付:", x, "元", "购买[", y, "]口味的冰激凌"
       
       #s1 = raw_input("请支付金融: ")
       #s2 = raw_input("请输入冰激凌口味: ")
       
       eatfood()
      ```
      执行结果：
      ```python
      # python mm.py
      支付: 3 元 购买[ 奶油 ]口味的冰激凌
      ```
    - 当用户输入`eatfood(10,'草莓')`，就是用传入的参数：
      ```python
       #coding=utf-8
       #!/bin/env python
       
       def eatfood(x=3,y='奶油'):
           print "支付:", x, "元", "购买[", y, "]口味的冰激凌"
       
       #s1 = raw_input("请支付金融: ")
       #s2 = raw_input("请输入冰激凌口味: ")
       
       eatfood(10,'草莓')
      ```
      执行结果：
      ```python
      # python mm.py
      支付: 10 元 购买[ 草莓 ]口味的冰激凌
      ```
      >说明：这里的脚本只是简单的演示缺省参数的使用
  - 只传一个实参实例演示：
    - 只传入价格实参：
      ```python
      #coding=utf-8
      #!/bin/env python
      
      def eatfood(x=3,y='奶油'):
          print "支付:", x, "元", "购买[", y, "]口味的冰激凌"
      
      #s1 = raw_input("请支付金融: ")
      #s2 = raw_input("请输入冰激凌口味: ")
      
      eatfood(10)
      ```
      执行结果：
      ```python
      # python mm.py
      支付: 10 元 购买[ 奶油 ]口味的冰激凌
      ```
      >说明：此时显示正常，也是符合形参和实参的位置是对应的原则
    - 只传入口味形参：
      ```python
      #coding=utf-8
      #!/bin/env python
      
      def eatfood(x=3,y='奶油'):
          print "支付:", x, "元", "购买[", y, "]口味的冰激凌"
      
      #s1 = raw_input("请支付金融: ")
      #s2 = raw_input("请输入冰激凌口味: ")
      
      eatfood('柠檬')
      ```
      执行结果：
      ```python
      # python mm.py
      支付: 柠檬 元 购买[ 奶油 ]口味的冰激凌
      ```
      >说明：此时显示就有问题了，价格位置变成口味了，因为按照形参和实参位置对应的关系，如果没有特别指定，那么第一个默认就是对应形参第一个也就是这里的`x`。
    - 解决方法：在传递实参的时候也固定的指定`y='柠檬'`即可，修改后执行结果：
      ```python
      #coding=utf-8
      #!/bin/env python
      
      def eatfood(x=3,y='奶油'):
          print "支付:", x, "元", "购买[", y, "]口味的冰激凌"
      
      #s1 = raw_input("请支付金融: ")
      #s2 = raw_input("请输入冰激凌口味: ")
      
      eatfood(y='柠檬')
      ```
      执行结果：
      ```python
      # python mm.py
      支付: 3 元 购买[ 柠檬 ]口味的冰激凌
      ```
      >备注：此时结果显示正常
  - 设定一个默认参数：
    - 设定`eatfood(x=3,y)`，实参传值为`eatfood(y='柠檬')`时：
      ```python
      #coding=utf-8
      #!/bin/env python
      
      def eatfood(x=3,y):
          print "支付:", x, "元", "购买[", y, "]口味的冰激凌"
      
      #s1 = raw_input("请支付金融: ")
      #s2 = raw_input("请输入冰激凌口味: ")
      
      eatfood(y='柠檬')
      ```
      执行结果如下：
      ```python
      # $python mm.py
        File "mm.py", line 5
          def eatfood(x=3,y):
      SyntaxError: non-default argument follows default argument
      ```
      >说明：语法错误，以下默认参数没有默认参数
    - 如果调换形参位置`eatfood(x=3,y)`，实参传值为`eatfood(y='柠檬')`时：
      ```python
      #coding=utf-8
      #!/bin/env python
      
      def eatfood(y,x=3):
          print "支付:", x, "元", "购买[", y, "]口味的冰激凌"
      
      #s1 = raw_input("请支付金融: ")
      #s2 = raw_input("请输入冰激凌口味: ")
      
      eatfood(y='柠檬') 
      #此时了按照形参和实参位置对应的关系，这里也是可以不用写y=的
      ```
      执行结果如下：
      ```python
      # python mm.py
      支付: 3 元 购买[ 柠檬 ]口味的冰激凌
     ```
    >说明：此时显示正常,无报错，由此看得出， `缺省参数（默认参数）只能从右向左赋值`,也就是说给`eatfood()`设定形参必须是`eatfood(y,x=3)`或者`eatfood(x,y='奶油')`，否则报错。
- 变量作用域
  - 局部变量：在函数中定义的变量一般只能在该函数内部使用，这些只能在程序内部的特定部分使用的变量，称之为局部变量。
    - 实例演示：
      ```python
      #coding=utf-8
      #!/bin/env python

      a = "全局变量a"
      
      def fun():
          x = "局部变量x”
          print x
      
      print a
      fun()
      ```
      执行结果如下：
      ```python
      # python var.py
      全局变量a
      局部变量x
      ```
      >说明：局部变量与全局变量之间的区别，通过演示不太明显。
  - 全局变量：在一个文件顶部定义的变量可以供该文件中的任何函数或者程序调用，这些可以为整个程序和函数使用的变量，称之为全局变量。
    - 实例演示：
      ```python
      #coding=utf-8
      #!/bin/env python
      
      a = "全局变量a"
      
      def fun():
          x = "局部变量x"
          print x
          print a
      
      print a
      fun()
      print x
      ```
      执行结果如下：
      ```python
      # python var.py
      全局变量a
      局部变量x
      全局变量a
      Traceback (most recent call last):
        File "var.py", line 12, in <module>
          print x
      NameError: name 'x' is not defined
      ```
     >注意：当我们分别`print a`、`fun()`并且在`fun()`中调用打印`a`，都是打印正常，当`print x`时，报错：名称错误：名称`x`没有被定义，明明定义了变量`x`呀为啥还报错，查看代码`x`是定义在函数内部的，根据局部变量的含义，它只能在函数内部被使用，所以当`x`超出函数内部范围时，变量就失效，此时就看出了局部变量和全局变量的区别了，局部变量只能在函数内部使用，全局变量在整个程序和函数使用。
- 局部变量和全局变量重名
  局部变量和全局变量重名会执行代码会如何了？
  执行下面代码看看效果：
  ```python
  #coding=utf-8
  #!/bin/env python
  
  x = "全局变量x"
  
  def fun():
      x = "局部变量x"
      print x
  
  print x
  fun()
  ```
  执行结果如下：
  ```python
  # python var.py
  全局变量x
  局部变量x
  ```
  >说明：由上面的结果得知，全局变量和局部变量不会因为重名而导致结果一样，也印证了局部变量只适用于函数内部。当然了，如果此局部变量通过`global`强制声明为全局变量后，那么全局变量输出的结果将会被`global`强制声明的局部变量的值替换掉`（想要实现此效果必须是在函数调用之后`，如果在函数调用之前使用此重名变量依旧会打印文件顶端定义的全局变量，不会被覆盖）`
- 使用`global`使局部变量当全局变量使用
  当我们想将局部变量在全局中使用，也就是函数以外，整个程序的其他地方使用时，可以通过使用`global`强制声明此局部变量，将其变成全局变量
  - 语法：
    ```python
    global  变量名
    ```
  - 实例演示：
    ```python
   #coding=utf-8
   #!/bin/env python
   
   def fun():
       global x
       x = "局部变量x"
       print x
   
   fun()
   print  "这是通过global声明的全局变量", x
    ```
    执行结果如下：
    ```python
    # python var.py
    局部变量x
    这是通过global声明的全局变量 局部变量x
    ```
    >备注：在函数中通过`global`强制声明局部变量为全局变量后，如果想使用此变量必须先调用执行此函数才能使用`global`强制声明的全局变量。
- 函数返回值  
  - 函数被调用后会返回一个指定的值
    实例演示：
    ```python
    >>> def fun(x,y):
    ...     return x+y
    ...
    >>>
    >>> fun(2,3)
    5
    >>> z = fun(2,3)
    >>> z
    5
    ```
    >说明：`z = fun(2,3)`就是函数调用
  - 函数返回值默认返回`None`
    ```python
    >>> def fun(x,y):
    ...     print x+y
    ...
    >>> fun(2,3)
    5
    >>> z = fun(2,3)
    5
    >>> z
    >>> print z
    None
    ```
    >说明：此时调用返回`None`
  - 语法： `return 返回值`,在函数中不管多少个`return`只要第一个执行，函数调用执行完毕
    ```python
    >>> def f():
    ...     return "one"
    ...     return "two"
    ...
    >>> z = f()
    >>> z
    'one'
    ```
  - 返回值可以是任意类型
    ```python
    >>> def f():
    ...     return "Hello World"
    ...
    >>> z = f()
    >>> z
    'Hello World'
    ```
     ```python
    >>> def f():
    ...     return range(6)
    ...
    >>> z = f()
    >>> z
    [0, 1, 2, 3, 4, 5]
    ```
  - 区分返回值和打印
    `print`是屏幕输出，返回值是给调用者返回函数执行的结果，而不至于函数执行了，而调用者不知道函数是否执行，执行结果如何了。
    比如说我们通过函数计算2+3的求和的值：
    不带`return`效果：
    ```python
    >>> def f(x,y):
    ...     print "screen inut:", x+y
    ...     x+y
    ...
    >>> f(2,3)
    screen inut: 5
    >>> z = f(2,3)
    screen inut: 5
    >>> z
    >>>
    ```
    >说明：有上面实例看出，不带`return`，当`z`调用`f(2,3)`后，执行`z`不会有任何结果，也就说`z`根本不知道函数执行到底如何
    
    带`return`执行结果：
    ```python
    >>> def f(x,y):
    ...     print "screen inut:", x+y
    ...     return "fan hui zhi:", x+y
    ...
    >>> f(2,3)
    screen inut: 5
    ('fan hui zhi:', 5)
    >>> z = f(2,3)
    screen inut: 5
    >>> z
    ('fan hui zhi:', 5)
    ```
    >说明：当带有`return`后，执行`z`会有结果，`return "fan hui zhi:", x+y`中也可以跟`print`一样添加一些提示语句。
- 多类型传值
  - 向函数传元组
   - 语法：
     ```python
     fun(*t)
     ```
     >说明：`t`是一个元组
   - 实例演示：
     定义一个元组`t = ('name','age')`传给函数`fun(x,y)`：
     ```python
     >>> t = ('name','age')
     >>> def fun(x,y):
     ...     print x, y
     ...
     >>> fun(*t)
     name age
     ```
     >说明：想将元组里面的元素分别传给对应的函数的形参，可以通过在元组前添加`*`，如`fun(*t)`实现元素传给对应的形参，形参与实参的位置是对应的也就是x=name,y=age，`但是要注意，元组的长度必须与函数形参长度一致，否则报错。`  
   - 如果有默认参数的情况下：
      ```python
      >>> def fun(name='tom',age=0):
      ...     print 'name: %s' % name
      ...     print 'age: %s' % age
      ...
      >>> fun()
      name: tom
      age: 0
      >>> fun('jack',30)
      name: jack
      age: 30
      ```
   - 如果有个元组tt=(35,'juck')往上面的例子传值结果：
     ```python
     >>> def fun(name='tom',age=0):
     ...     print 'name: %s' % name
     ...     print 'age: %s' % age
     ...
     >>> tt = (30,'juck')
     >>> fun(*tt)
     name: 30
     age: juck
     ```
     >备注：此时输出效果就有问题了，那怎么解决了，这就用到了字典了
 - 向函数传字典：
   - 语法：
     ```python
     fun(**d)
    ```
    >说明：`d`为字典
   - 实例演示：
     ```python
     >>> tt = {'name':'tom','age':34}
     >>> tt
     {'age': 34, 'name': 'tom'}
     >>> def fun(name='tom',age=0):
     ...     print 'name: %s' % name
     ...     print 'age: %s' % age
     ...
     >>> fun(**tt)
     name: tom
     age: 34
     ```
    >说明：想将字典里面的值分别传给函数里面对应的形参，可以通过在字典前面添加`**`，如`fun(**d)`实现值传给对应的形参，
    >`但是要注意，定义字典传递给函数的形参的时候，必须保证函数形参的名字跟字典的名字一样，`
    >`也就说定义一个字典 tt = {'name':'tom','age':34},那么函数里面的形参也必须是fun(name,age)，否则报错`
    
     实例演示：
     定义一个字典dd = {'name':'tom','num':34},然后传递给函数`fun(name,age)`结果：
     ```python
     >>> dd = {'name':'tom','num':34}
     >>> dd
     {'num': 34, 'name': 'tom'}
     >>> def fun(name,age):
     ...     print name
     ...     print age
     ...
     >>> fun(**dd)
     Traceback (most recent call last):
       File "<stdin>", line 1, in <module>
     TypeError: fun() got an unexpected keyword argument 'num'
    >>> fun(**tt)
    tom
    34
    >>> tt
    {'age': 34, 'name': 'tom'}
    ```
    >说明：看的出来当我们定义字典`dd = {'name':'tom','num':34}`，往函数里面传递参数是报错：`fun()`得到一个异常的参数`num`，也就说得到一个没有对应的参数，当将字典`tt`传递给函数，输出正常，其实也是可以这么理解的：字典里面的键值对，键就相当于函数里面的形参（`{'age': 34, 'name': 'tom'}等于fun('age'=34, 'name'='tom')`），所以字典键必须跟函数的形参的名称一样，不然报错。
  
   当然了如果真想传递就通过`f(dd['name'],dd['num'])`实现：
   ```python
     >>> dd = {'name':'tom','num':34}
     >>> dd
     {'num': 34, 'name': 'tom'}
     >>> def fun(name,age):
     ...     print name
     ...     print age
     ...
     >>> fun(dd['name'],dd['num'])
     tom
     34
     >>> fun(dd['num'],dd['name'])
     34
     tom
     ```
     >说明：不过此时，就得遵守形参和实参位置对应的关系了，不然传递输出顺序就不一样了，如果是直接传递字典就不用考虑了，因为字典是无序的
     
    可以看下这个例子：
    ```python
    >>> def fun(name,num):
    ...     print name
    ...     print num
    ...
    >>> fun(**dd)
    tom
    34
   ```
   ```python
   >>> def fun(num,name):
   ...     print name
   ...     print num
   ...
   >>> fun(**dd)
   tom
   34
   ```
   ```python
    >>> def fun(num,name):
   ...     print name
   ...     print num
   ...
   >>> fun(12,'na')
   na
   12
   >>> fun('na',12)
   12
   na
   ```

   >备注：此时看到不管形参的位置怎么变都不会改变输入结果的（前提是print不变），最后一个例子一样，当`fun(12,'na')`对应` def fun(num,name)`也就是说`num=12,name=na`，输出结果是先`name`后`num`打印正常，当` fun('na',12)`对应` def fun(num,name)`也就是说`num=na,name=12`，此时输出结果就`name=12，num=na`明显不符合要求了，所以了，用字典可以不靠考虑顺序问题，不过需要注意形参和实参的名字
- 传值冗余
  传值冗余就是处理当函数定义一个形参的时候，实参却给了两个实参，例如：`函数fun(x)`给传值`fun(2,3)`，这种肯定会报错
  - 以元组方式存储多余实参：
    - 语法：
      ```python
      fun(x,*args)
      ```
      >说明：起手`args`式可以任意定义的
    - 实例演示：
      当定义一个函数`fun(x)`时，传递两个实参，执行结果如下：
      ```python
      >>> def fun(x):
      ...     print x
      ...
      >>> fun(2,3)
      Traceback (most recent call last):
        File "<stdin>", line 1, in <module>
      TypeError: fun() takes exactly 1 argument (2 given)
      ```
     此时传递两实参就会报错，为了避免传递两个实参而报错那就使用以元组方式存储多余实参的方式来解决这个问题，如下：
      ```python
      >>> def fun(x,*args):
      ...     print x
      ...     print args
      ...
      >>> fun(2,3)
      2
      (3,)
      ```
  - 以字典的方式存储多余的实参：
    - 语法：
      ```python
      fun(x,**args)
     ```
     >说明：此处的`args`可以任意定义，其实不难发现这个跟之前向函数传递元组和字典的语法形式是一样的，不同的是向函数传递元组和字典是元组的元素和字典里面的键值对跟函数的形参长度是一样的。 
     >使用以字典的方式存储多余的实参主要是解决存在映射关系的实参，比如：`fun(x=1,y=2)`这种的。
    - 实例演示：
      当定义一个函数`fun(x)`时，传递两个实参，执行结果如下：
      ```python
      >>> def fun(x):
      ...     print x
      ...
      >>> fun(x=1,y=2)
      Traceback (most recent call last):
        File "<stdin>", line 1, in <module>
      TypeError: fun() got an unexpected keyword argument 'y'
      ```
      >备注：这个报错就跟前面向函数传递字典一样
      
     那么刚刚学习了通过以元组的方式存储多余实参，用它能解决问题吗，执行结果看下：
     ```python
     >>> def fun(x,*tem):
     ...     print x
     ...     print tem
     ...
     >>> fun(x=1,y=2)
     Traceback (most recent call last):
       File "<stdin>", line 1, in <module>
     TypeError: fun() got an unexpected keyword argument 'y'
     ```
     >说明：依旧报相同的错误，看下实参:`x=1,y=2`这是属于映射关系了， 那么映射关系肯定用字典最好了， 下面我们以字典的方式执行下。
     
     以字典的存储方式来解决存在映射关系的实参：
     ```python
     >>> def fun(x,*tem,**dict):
     ...     print x
     ...     print tem
     ...     print dict
     ...
     >>> fun(x=1,y=2)
     1
     ()
     {'y': 2}
     ```
     >说明：此时通过以字典存储的方式处理多余实参就解决了这个问题， 而且从结果当中我们也看到y=2以字典的形式输出了，
     >为啥x=1就只显示1，而y=2就显示字典形式了，因为按照形参和实参位置对应的关系，实参x=1肯定对应x了(当然也可以直接输入1），而后面的y=2因为形参里面没有对应的位置，传进来是当作y和2两个值，因此存在这种映射关系的也就是有字典处理。

## `Lambda`表达式
- 匿名函数：`lambda`函数是一种快速定义单行的最小函数，是从`Lisp`借用来的，可以在任何需要函数的地方。
- 语法：
  ```python
  def fun(x,y):
      return x*y
  ```
  以上函数可以通过`lambda`定义成一下形式，也就是其语法了
  ```python
  g = lambda x,y:x:y
  ```
- 实例演示：
  定义一个普通的函数`fun(x,y)`：
  ```python
  >>> def fun(x,y):
  ...     return x*y
  ...
  >>> fun(2,3)
  6
  ```
  通过`lambda`简化上述函数：
  ```python
  >>> g = lambda x,y:x*y
  >>> g(2,3)
  6
  ```
  >说明：这里面的`g`就是一个通过`lambda`定义的一个匿名函数。
- 使用`lambda`的使用范围和好处：
  - 使用Python写一些执行的脚本时，使用`lambda`可以省去定义函数的过程，让代码更加精简。
  - 对于一些抽象的，不会被别的地方再复用的函数。
  - 使用`lambda`不需要考虑命名的问题，比如说你不知道如何定义函数的名称的时候，使用`lambda`就可以解决。
  - 使用`lambda`在某些时候能让代码更容易理解，也主要是其短小精简，就一句话而已。
- `lambda`语法细说
  - `lambda`语句中，冒号(：)前面是参数，可以有多个，用逗号(,)隔开，冒号(:)右边是返回值，不需要写`return`语句。
  - `lambda`其实是构建一个函数的对象，例如：
     ```python
     >>> g = lambda x,y:x*y
     >>> g
     <function <lambda> at 0x6ffffe677d0>
     ```
     >说明：下面的`<function <lambda> at 0x6ffffe677d0>`是其对象，这里的`g`就是将等号后面的`lambda`函数对象赋值给`g`(`g`也叫做实例)
- `lambda`应用实例
  - `reduce`：为逐次操作List里面的每个项，接受参数为2个，最后返回一个结果，有点像`for`循环遍历
  - 实例演示：
    ```python
    >>> def fun(x,y):
    ...     return x+y
    ...
    >>> sum = reduce(fun,(1,2,3))
    >>> sum
    6
    ```
    >说明：定义函数，然后使用`reduce`从(1,2,3)中逐次取两个值，先取出1和2，相加后，留下来然后与3相加（相加得出的结果也算一个值，所以此处就取一个3了），根据定义函数计算得出和为6。
    
    也可以将上面的通过`lambda`实现：
    ```python
    >>> reduce(lambda x,y:x+y,(1,2,3))
    6
    ```
    >说明：此处其实直接使用对象形式输出结果的，一般都是要给对象定义个实例也就是别名了，如：g = reduce(lambda x,y:x+y,(1,2,3)),也可以说就是给g赋值。

## 实现分支结构（`switch`)
- `switch`语句用于编写多分支结构的程序，类似于`if...elif..else`语句
- `switch`语句表达的分支结构比`if..elif...else`语句表达的更清晰，代码的可读性更高
- 但是Python中并没有提供`switch`语句。
- Python可以通过字典实现`switch`语句的功能
- 实现方法分为两步：
  - 首先，定义一个字典
  - 其次，调用字典的`get()`获取相应的表达式
  - 通过字典调用函数实现`switch`的效果：
    ```python
    {1:case1,2:case2}.get(x,lambda *arg,**key:)()
    ```
    >说明：后面的`*arg`,`**key`是解决传值冗余的问题，也就是传入实参的长度大于形参的长度，避免错误发生。
  - 实例演示:
    ```python
    #coding=utf-8
    #!/bin/env python
    
    from __future__ import division
    
    def jia(x,y):
        return x+y
    
    def jian(x,y):
        return x-y
    
    def cheng(x,y):
        return x*y
    
    def chu(x,y):
        return x/y
    
    jisuan = {"+":jia,"-":jian,"*":cheng,"/":chu}
    
    def fun(x,o,y):
        print jisuan.get(o)(x,y)
    
    a = int(raw_input("请输出数字1："))
    b = int(raw_input("请输出数字2："))
    c = raw_input("请输出运算符：")
    fun(a,c,b)
    ```
    执行结果：
    ```python
    # python cal.py
    请输出数字1：2 
    请输出数字2：3
    请输出运算符：+
    5
    ```
    >说明：上述脚本中通过字典`jisuan = {"+":jia,"-":jian,"*":cheng,"/":chu}`实现了`switch`分支结构的功能
    >其中脚本顶部的`from __future__ import division`(前后下划线是两个)是一个用于算数运算符计算的模块，主要解决包含小数计算类的问题，例如：2/5，如果不使用这个模块那么计算出的结果是0，如果导入这个模块，计算出的结果就是0.4。

## 内置函数
可以直接使用的函数，无需导入模块调用
- 绝对值`abs()`:返回参数的绝对值
  - 实例演示：
    ```python
    >>> abs(10)
    10
    >>> abs(-10)
    10
    ```
    >说明：也就是说绝对值就是值到零之间的距离
- 最大值`max()`:使用单个可迭代参数返回其最大项。有两个或多个参数，返回最大的参数。
  ```python
  >>> max(1,2,3,4)
  4
  ```
  >说明：数组当中最大的值
  
  - 传入的值必须至少两个
    如果传入一个值：
    ```python
    >>> max(1)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: 'int' object is not iterable
    ```
    >报错：类型错误：整型对象不能被迭代,如果提供了一个位置参数，则iterable必须是非空的iterable（如非空字符串，元组或列表）
  - 当传入的参数数据类型不一致时，传入的所有参数将进行隐藏式数据类型转换后在比较，如果不能进行隐藏式数据类型转换会报错
    - 整数与浮点数可取最大值
      ```python
      >>> max(1,2,3,1.3E1)
      13.0
      ```
    - 数值与字符串不能取最大值 
      ```python
       >>> max(1,2,3,'hello world')
      'hello world'
      ```
      >说明：：对于这个验证结果有点让人意外，官方目前也么有查到相关信息
    - 列表与列表可以取最大值
      ```python
      >>> max([1,2],[1,3])
      [1, 3]
      ```
    - 列表与元组不能取最大值
      ```python
      >>> max([1,2],(1,3))
      (1, 3)
      ```
      >说明：：对于这个验证结果有点让人意外，官方目前也么有查到相关信息
    - 元组与元组可以取最大值
      ```python
      >>> max((1,2),(1,3))
      (1, 3)
      ```
  - 当存在多个相同的最大值时，返回的时最先出现的那个最大值
    ```python
    >>> a = 1
    >>> b = 2
    >>> c = 2
    >>> id(a)
    25769903896
    >>> id(b)
    25769903872
    >>> id(c)
    25769903872
    >>> d = max(a,b,c)
    >>> id(d)
    25769903872
    >>> id(d) == id(b)
    True
    ```
  - 默认数值型参数，取最大值
    ```python
    >>> max(1,2,3,4)
    4
    ```
  - 字符型参数，取字母排序靠后的
    ```python
    >>> max('abcde')
    'e'
    ```
  - 序列型参数，依次按索引位置的值进行比较取最大值
    ```python
    >>> max(['ab','ac','ad'])
    'ad'
    ```
  - 还可以传入命名参数`key`，指定取最大值
    传入求绝对值的函数，则参数都会进行求绝对值后再去较大值
    ```python
    >>> max(-1,0,key=abs)
    -1
    ```
    >说明：可选的`key`参数指定一个单参数排序函数，如用于`list.sort()`。的关键参数，如果提供的话，必须在关键字的形式（例如，min(a,b,c,key=func)）。也就是说`key`后面是一个函数参数。（在版本2.5中更改：增加了对可选键参数的支持），保留还是不太明白。
  - `key`参数的另一个作用是，不同类型对象本来不能比较取最大值，传入适当的`key`函数，变得可以比较能取最大值了
    ```python
    >>> max(1,2,3,'3',key=int)
    3
    ```
    >说明：这个还是有点郁闷，之前不加`key`也能得出最大值区别在于输出的结果是字符串'3'，而此时是整型3，对于网上的不加`key`会报错，我这测试是没有报错， 目前还是懵逼状态，未得到解答，暂时保留，以后再研究
    
  - 当只传入的开一个可迭代对象时，而且可迭代对象为空，则必须指定命名参数`default`，用来指定最大值不存在，函数返回默认值
   例如空迭代不能取最大值
    ```python
    >>> max(())
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    ValueError: max() arg is an empty sequence
    ```
    空迭代对象，指定`default`参数为默认值：
    ```python
    >>> max((), default=0)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: max() got an unexpected keyword argument
    ```
    >我不知道是什么鬼情况，这是参考网上说法，网上返回结果是0，官方我没找到，还是先保留，后面再看吧
    
- 最小值`min()`:
  看了下帮助跟max的差不多,这里就不再多说了，参考max吧，反正max我总结的都还没全部搞懂：
  ```python
  min(...)
    min(iterable[, key=func]) -> value
    min(a, b, c, ...[, key=func]) -> value

    With a single iterable argument, return its smallest item.
    With two or more arguments, return the smallest argument.
    ```
    扔个实例:
    ```python
    >>> min(1,2,3)
    1
    ```
- `len`计算对象长度：
   ```python
   >>> a = [1,2,3,4,5,6]
   >>> len(a)
   6
   ```
   >说明：`len`函数就只有计算长度的，没有其他的了（返回序列或集合的项目数。）

- `divmod()`:返回商和余
   语法：
   ```python
   divmod（x，y） - >（商(div)，余数(mod)）
   返回元组（x // y，x％y）不变量：div * y + mod == x
   ```
   实例：
   ```python
   >>> divmod(2,5)
   (0, 2)
   >>> divmod(2//5,2%5)
   (0, 0)
   ```
   >说明：`不变量：div * y + mod == x`其实就是`0*5+2=2`,这个就是算数中得出除数总数的（可能说的不明朗，差不多吧）

- `pow()`：有两个参数，相当于x \** y。 使用三个参数，
     相当于（x ** y）％z，但是可能更有效（例如对于长时间）。
   语法：
   ```python
   pow(x, y[, z])
   ```
   >说明：函数是计算x的y次方，如果z在存在，则再对结果进行取模（余），其结果等效于pow(x,y) %z

   实例演示：
   ```python
   >>> pow(2,4)
   16
   ```
   >说明;计算2的4次方也就是2x2x2x2=16

   三个参数：
   ```python
   >>> pow(2,4,3)
   1
   ```
   >说明：计算2的4次方，然后除于3得出余数（模）1，也就是2x2x2x2/3得出余数1

- `round()`:返回浮点数，将数字舍入到十进制数字的给定精度（默认为0位数）。这总是返回一个浮点数。精度可能为负。
   语法：
   ```python
   round(number[, ndigits]) 
   ```
   >说明：方括号为可选，为取值的精度

   实例演示：
   ```python
   >>> round(1.444)
   1.0
   ```
   ```python
   >>> round(1.6789,1)
   1.7
   >>> round(1.6789,2)
   1.68
   >>> round(1.6789,3)
   1.679
   >>> round(1.6789,4)
   1.6789
   >>> round(1.6789,5)
   1.6789
   ```
   >说明：从上面第一个实例中看出，如果后面不参数（也就是精度，小数点取值几位）就精度到0（默认为0），如果后面精度为1，那么会根据四舍五入的原则，小数点后面一位会加一，精度为2，就去两位，如果小数点第二位大于等于5就加一，精度超出小数点后面的长度后，就会显示所有的精度。
 
- `callable()`:测试函数是否能被调用，如果能调用返回`True`，否则`False`，返回对象是否可调用（即某种功能）。
     请注意，类是可调用的，与\__call __（）方法的实例一样。
   语法：
   ```python
   callable(object)
   ```
  实例演示：
  ```python
  >>> callable(pow)
  True
  ```
  ```python
   >>> f = 100
   >>> callable(f)
   False
   >>> def f():
   ...     pass
   ...
   >>> callable(f)
   True
   ```
- `isinstance()`：判断对象类型，返回对象是否是类的实例或其子类。
    使用类型作为第二个参数，返回是否为对象的类型。
     使用元组的形式，isinstance（x，（A，B，...））是一个快捷方式
     （x，A）或实例（x，B）或...（等）。
  语法:
  ```python
  isinstance(object, class-or-type-or-tuple)
  ```
  >说明：如果判断对象的类型是第二哥参数里面的类型就返回True，否则False。

  实例演示：
  ```python
  >>> l = [1,2,3,4,5]
  >>> isinstance(l,list)
  True  
  >>> isinstance(l,int)
  False  
  ```
  后面提到的使用元组形式，前面的`x`就是要判断的对象，圆括号里面的`A,B,...`要判断的多个对象类型，为什么会这么解释，因为其中这句话`使用类型作为第二个参数，返回是否为对象的类型。`告诉我们第二个参数就是要判断的对象的类型，下面通过实例演示下：
   1.后面圆括号中存在非对象类型的值：
     ```python
     >>> isinstance('hhhhhh',(int,list,1))
     Traceback (most recent call last):
       File "<stdin>", line 1, in <module>
     TypeError: isinstance() arg 2 must be a class, type, or tuple of classes and types
     ```
     >说明：报错，告诉我们isinstance 参数2必须是一个类，类型或者类的元组，也就是说必须是类型

   2.后面的圆括号中全部是类型：
     ```python
     >>> isinstance('hhhhhh',(int,list,str))
     True
     ```
     >说明：这种相当于`('hhhhhh',int)`,`('hhhhhh',list)`,`('hhhhhh'str)`，从实例中也不难看出，只要有一个符合就返回True，有点像`逻辑或的关系`

- `cmp()`:两参数大小比较，必须是两个参数
  语法：
  ```python
   cmp(x, y) 
  ```
  >说明：结果为`-1`：x<y，结果为`0`：x=y，结果为`1`:x>y

  实例演示：
  ```python
  >>> cmp(1,2)
  -1
  >>> cmp(3,2)
  1
  >>> cmp(2,2)
  0
  ```
  >说明：字母比较，是排序后面的大于前面的，例如：a<b
- `xrange()`：像range（），而不是返回一个列表，返回一个对象
 根据需要生成范围内的数字。 为了循环，这是略高于range（）和更高的内存效率。也就是说它返回一个对象的长度范围，多数是用在循环中，为了提高运行效率,也可以叫做生成器。
  语法：
  ```python
  xrange(stop) 
  xrange(start, stop[, step])
  ```
  >说明：这里面的参数跟`range()`一样：start起始值（不选默认为0），stop结束值（取结束位置前一位的值），step步进值（可选，默认为1）

  实例演示：
  ```python
  >>> l = xrange(9)
  >>> l
  xrange(9)
  ```
  >说明：这里返回的就是一个xrange object这个看着不清晰，下面通过`for`循环来具体演示

  这里通过一个`for`循环来具体演示：
  只有结束值：
  ```python
  >>> l = xrange(9)
  >>> l
  xrange(9)
  >>> for i in l:
  ...     print i
  ...
  0
  1
  2
  3
  4
  5
  6
  7
  8
  ```
  有起始值和结束值：
  ```python
  >>> l = xrange(1,9)
  >>> for i in l:
  ...     print i
  ...
  1
  2
  3
  4
  5
  6
  7
  8
  ```
  有起始值，结束值，并且步进值是2（默认是1这样看不出效果）：
  ```python
  >>> l = xrange(1,9,2)
  >>> for i in l:
  ...     print i
  ...
  1
  3
  5
  7
  ```
  >说明：`xrange()还有很多的方法了，简单说下把

  `xrange()`方法使用：
  通过`help(xrange)`得到`xrange`定义的方法：
   ```python
   Help on class xrange in module __builtin__:

   class xrange(object)
   |  xrange(stop) -> xrange object
   |  xrange(start, stop[, step]) -> xrange object
   |
   |  Like range(), but instead of returning a list, returns an object that
   |  generates the numbers in the range on demand.  For looping, this is
   |  slightly faster than range() and more memory efficient.
   |
   |  Methods defined here:
   |
   |  __getattribute__(...)
   |      x.__getattribute__('name') <==> x.name #这个先保留，没搞明白
   |
   |  __getitem__(...)
   |      x.__getitem__(y) <==> x[y] #说明：相当于索引取值，例如：List[0]
   |
   |  __iter__(...)
   |      x.__iter__() <==> iter(x) #说明：返回一个迭代对象,例如：iter(l)，<rangeiterator object at 0x6ffffe748a0>
   |
   |  __len__(...)
   |      x.__len__() <==> len(x)  #说明：计算元素长度，例如：l = [1,2,3],len(l),长度为3
   |  __reduce__(...)              #说明：逐次取值，有点像`for`循环，接受两参数，取一个值就返回一个值
                                    使用方法： reduce(function, sequence[, initial]) -> value
                                    其中function是函数，sequence为序列，可选initial为初始值
                                    实例演示：
                                    >>> l
                                    xrange(1, 9, 2)
                                    >>> reduce(lambda x,y:x+y,l)
                                    16
                                    >>> for i in l:  # 这里的for是为了清晰的看出变量l里面生成的值
                                    ...     print i
                                    ...
                                    1
                                    3
                                    5
                                    7

   |
   |  __repr__(...)
   |      x.__repr__() <==> repr(x) #说明：以规范字符串的形式，返回对象，例如：>>> repr(l)返回'xrange(1, 9, 2)'

   |
   |  __reversed__(...) #说明：返回反向迭代器，例如：reversed(l)返回<rangeiterator object at 0x6ffffe74210>，跟iter结果一样
   |      Returns a reverse iterator.
   |
   |  ----------------------------------------------------------------------
   |  Data and other attributes defined here:
   |
   |  __new__ = <built-in method __new__ of type object>
   |      T.__new__(S, ...) -> a new object with type S, a subtype of T
   ```
   >说明：`<==>`后面的就是它的简化操作，没有就直接使用的例如，里面讲解`reduce`的用法。像`__repr__(...)`这种解说不详细的可以通过`help()`获取到详细的说明

## 类型转换函数
- `type()`：返回对象的类型
  语法：
  ```python
  type(object) -> the object's type
  type(name, bases, dict) -> a new type
  ```
  >说明：name:类的名称，nases：基类的元组，dict：字典，类内定义的命名空间变量  

  实例演示：
  ```python
  >>> a = 1
  >>> type(a)
  ```
  ```python
  >>> class X(object):
  ...     a = 1
  ...
  >>> X = type('X', (object,), dict(a=1))
  >>> X
  <class '__main__.X'>
  ```
  >备注：这个是定义类，有点高大上了，搞不懂了，等了解了类定义后再看吧，先知道就行。  

- `int()`：将数字或字符串转换为整数，如果没有参数，则返回0，给出。 如果x是浮点数，则转换截止为零。
  - 如果x在整数范围之外，则函数返回一个long
  - 如果x不是数字(1e+1，1e-1虽然也是数字，浮点型的，不过这里也是当作非数字吧)，或者如果给出基数，则x必须是字符串Unicode对象表示给定基数中的整数文字。该字面可以在前面加上'+'或' - '，并被空格包围。也就是说不是数字或者给出了基数（也就是进制），那么字符串Unicode对象必须能表示给定基数的整数文字（能转换成对应进制的整数文字），不然会报错的，这个好像只能去尝试）,+_+、-好像只能用在浮点值，例如：1e+1,1e-1，纯字母的字符串可以转换，比如：'hhh' int('hhh',20)为：7157，
  - 基数默认为10.有效基数为0和2-36。 基数0表示将字符串中的基数解释为整数文字，也就是进制数，10代表十进制。
  语法：
  ```python
  int(x=0) -> int or long
  int(x, base=10) -> int or long
  ```
  >说明：`base`基数看上面说明
  
  实例演示：
  ```python
  >>> type(int(x=1)) #也就是type(int(1))
  <type 'int'>
  >>> int(x=1)
  1
  ```
  ```python
  >>> type(int('12345'))
  <type 'int'>
  >>> int('12345')
  12345
  ```
  ```python
  >>> type(int())
  <type 'int'>
  >>> int()
  0
  ```
  ```python
  >>> type(int(999999999999999999999999999999))
  <type 'long'>
  >>> int(999999999999999999999999999999)
  999999999999999999999999999999L
  ```
  ```python
  >>> type(int(1.2))
  <type 'int'>
  >>> int(1.2)
  1
  ```
  ```python
  >>> int('hhh',20) #测试了一下此处将字母字符串转换成整数基数最小是18，也就是18进制，
                     这个好像只有你根据所需的进制来转换，不能说你想转换哪一个就哪一个
  7157
  >>> type(int('hhh',20))
  <type 'int'>
  ```
  ```python
  >>> int(1e+5)
  100000
  >>> type(int(1e+5))
  <type 'int'>
  ```
  ```python
  >>> type(int(1e-5))
  <type 'int'>
  >>> int(1e-5)
  0
  ```
#### `总结下`：
  
  1. 如果字符串为'123'这种的可以任意转换，例如：
     ```python
     >>> int('0110')
    110
    >>> int('0110',2)
    6
    >>> int('0110',8)
    72
    >>> int('0110',9)
    90
    >>> int('0110',16)
    272
    ```
 2. 如果是0.1（不能加引号，不然都不能转换）这种只能转换10进制，其他都报错，例如：
    ```python
    >>> int(0.1)
    0
    >>> int(0.1,2)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: int() can't convert non-string with explicit base
    >>> int(0.1,8)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: int() can't convert non-string with explicit base
    >>> int(0.1,10)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: int() can't convert non-string with explicit base
    >>> int(0.1,16)
    ```
  3. 如果是1e+1或者是1e-1，同样只能转换十进制，其他都报错，例如：
     ```python
    >>> int(1e+1)
    10
    >>> int(1e+1,2)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: int() can't convert non-string with explicit base
    >>> int(1e+1,8)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: int() can't convert non-string with explicit base
    >>> int(1e+1,16)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: int() can't convert non-string with explicit base
    ```
    >备注：2和3例子中的值都是属于浮点值，这种不能使用引号

  4. 如果是'A123'(必须引号）只能16进制以后，例如：
     ```python'
     >>> int('A123')
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    ValueError: invalid literal for int() with base 10: 'A123'
    >>> int('A123',2)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    ValueError: invalid literal for int() with base 2: 'A123'
    >>> int('A123',8)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    ValueError: invalid literal for int() with base 8: 'A123'
    >>> int('A123',16)
    41251
    >>> int('A123',18)
    58683
    ```
  5. 如果是'hhh'这种只能从18进制开始，例如：
     ```python
     >>> int('hhh',16)
     Traceback (most recent call last):
       File "<stdin>", line 1, in <module>
     ValueError: invalid literal for int() with base 16: 'hhh'
     >>> int('hhh',17)
     Traceback (most recent call last):
       File "<stdin>", line 1, in <module>
     ValueError: invalid literal for int() with base 17: 'hhh'
     >>> int('hhh',18)
     5831
     >>> int('hhh',36)
     22661
     ```
  6. 另外纯字母的字符串，如果长度过长也会限制其进制转换的基数的，如果是''Helloworld',只能从33开始，例如:
     ```python
     >>> int('Helloworld',32)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    ValueError: invalid literal for int() with base 32: 'Helloworld'
    >>> int('Helloworld',33)
    809608041709942
    >>> int('Helloworld',36)
    1767707668033969
    ```
    >备注：至于规律和原因，暂时没找到    

- `long()`：将数字或字符串转换为长整数，如果没有参数，则返回0L给出。 如果x是浮点数，则转换截止为零。
   语法：
   ```python
   long(x=0) -> long
   long(x, base=10) -> long
   ```
   >说明：用法跟`int()`一样，不同之别是转换长整型数。
   
   实例演示：
   ```python
   >>> long('0110',2)
   6L
   >>> long(5)
   5L
   >>> long('A5',16)
   165L
   >>> long(1e+1)
   10L
   >>> long(1e-1)
   0L
   >>> long('hhh',18)
   5831L
   ```
- `float()`：如果可能，将字符串或数字转换为浮点数。
   语法：
   ```python
   float(x) -> floating point number
   ```
   >说明：这个比较简单，至于方法暂时就不说了，想看通过`help(floadt)`看吧

   实例演示：
   ```python
   >>> float('12e3')
   12000.0
   >>> float('123')
   123.0
   >>> float(123)
   123.0
   >>> float(123e-12)
   1.23e-10
   >>> float('123e-12')
   1.23e-10
   >>> float('123e+12')
   123000000000000.0
   >>> float(123e+12)
   123000000000000.0
   >>> float(123e1-12)
   1218.0
   ```
   >说明：这个貌似不支持纯字母字符串的转换
- `complex()`：从实部和可选的虚部创建一个复数。这相当于（true + imag * 1j），其中imag默认为0。
  语法：
  ```python
  complex(real[, imag]) -> complex number
  ```
  >说明：real：实数，imag：可选虚数,通过给`数值后面添加j`来实现，如：3.4j,5.67j,32e-56j,使用抛物线经常用到

  实例演示：
  ```python
  >>> complex(1,2)
  (1+2j)
  >>> complex(1.2,2)
  (1.2+2j)
  >>> complex(1.2)
  (1.2+0j)
  ```
  >说明：同样的，只能是数值也就是阿拉伯数字：123，3.2等等
- `str()`：返回一个字符串表示的对象，如果参数是一个字符串，则返回值是相同的对象。
  语法：
  ```python
  str(object='') -> string
  ```
  >说明：`object=''`是说对象对于后面的字符串可不是参数（a='123')这样的，不然error
  
  实例演示：
  ```python
  >>> str(123)
  '123'
  >>> str('123')
  '123'
  ```
  `str()`内置函数部分解说：
  `S.capitalize()`
  语法：
  ```python
  S.capitalize() -> string
  ```
  >说明：返回字符串S的副本，其第一个字符大写,也就说首字母大写

  实例演示：
  ```python
  >>> s = 'hello world'
  >>> s
  'hello world'
  >>> s.capitalize()
  'Hello world'
  ```
  `S.replace()`
  语法：
  ```python
   S.replace(old, new[, count]) -> string
  ```
  >说明：返回一个字符串S的副本，所有出现的子字符串old被替换为新的。 如果给出了可选参数计数，则仅替换第一个计数事件。

  实例演示：
  ```python
  >>> s
  'hello world'
  >>> s.replace('h','M')
  'Mello world'
  ```
  ```python
  >>> s = 'helloworldhellowellcomehello'
  >>> s.replace('h','M',2)
  'MelloworldMellowellcomehello'
  ```
  >说明：`[,count]`：替换字符的个数
  
  `s.split()`
  语法：
  ```python
  S.split([sep [,maxsplit]]) -> list of strings
  ```
  >说明：返回字符串S中的单词列表，使用`sep`作为分隔符字符串。 如果给出`maxsplit`，最多`maxsplit`拆分完成。 如果没有指定`sep`或没有，任何空白字符串是一个分隔符，空字符串被删除从结果。这从帮助里面看到的语法不清晰，实际使用是这样的`s.split('sep'[,maxsplit])`，其中`sep`是分隔符需要用`引号`包住，后面可选的`[,maxsplit]`是分割的次数，具体实例看下面的演示

  实例演示：
  ```python
  >>> a
  'hello word'
  >>> a.split()
  ['hello', 'word']
  ```
  >说明：不指定`sep`和`maxsplit`将默认使用字符串里面的空白符作为分隔符分割
  
  ```python
  >>> a = 'hello,world,wellcome,to,china'
  >>> a.split(',')
  ['hello', 'world', 'wellcome', 'to', 'china']
  >>> a.split(,)
    File "<stdin>", line 1
      a.split(,)
              ^
  SyntaxError: invalid syntax
  ```
  >说明：仅使用字符串里面的逗号`,`分隔如此,必须加引号（双引号也行）`''`不然报错
  
  ```python
  >>> a = 'hello,world,wellcome,to,china'
  >>> a.split(',',2)
  ['hello', 'world', 'wellcome,to,china']
  >>> a.split(',',3)
  ['hello', 'world', 'wellcome', 'to,china']
  ```
  >说明：添加分割次数`[,maxsplit]`也就是上面例子中的2和3，为2的时候，就以两个逗号分割，3个就以三个逗号分割，如果分割次数超过字符串里面的分隔符会以最大值显示
  
  如下：
  ```python
  >>> a.split(',',5)
  ['hello', 'world', 'wellcome', 'to', 'china']
  ```
  >注意：分隔符必须是字符串里面存在的，如果不存在返回原来的字符串并以列表格式保存为一个单一的列表元素


- `list()`：返回一个列表`[]`
  语法：
  ```python
  list() -> new empty list
  list(iterable) ->
  new list initialized from iterable's items
  从迭代项目中初始化一个列表
  ```
  实例演示：
  ```python
  >>> list()
  []
  >>> list('123456')
  ['1', '2', '3', '4', '5', '6']
  >>> list(xrange(6)) 
  #第二种需要迭代项目，所以就用`xrange`搞一个
  [0, 1, 2, 3, 4, 5]
  ```
  >说明：如果想将一串数字或者英文字母变为列表，必须加`引号`才能生成一个列表，纯数字1234不能被迭代，纯字母是当作函数或者变量素以不行
- `tuple()`：生成一个元组，如果参数是元组，则返回值是相同的对象。
  语法：
  ```python
   tuple() -> empty tuple
   tuple(iterable) -> 从迭代项目中初始化一个元组
  ```
  >说明：使用此方法必须是具有迭代得项目，单纯得数字(1234是不能得）不行,其实不难发现，单纯使用`tupble()`这样得函数，是要具有迭代功能得值才能生成对应得序列等

  实例演示:	
  ```python
  >>> tuple('123456')
  ('1', '2', '3', '4', '5', '6')
  >>> tuple()
  ()
  >>> tuple(xrange(6))
  (0, 1, 2, 3, 4, 5)
  ```
- `hex()`：返回整数或长整数的十六进制表示形式。
  语法：
  ```python
   hex(number) -> string
  ```
  实例演示：
  ```python
  >>> hex(1234)
  '0x4d2'
  >>> hex('123')
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  TypeError: hex() argument can't be converted to hex
  >>> hex(1.2)
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  TypeError: hex() argument can't be converted to hex
  ```
  >说明：由结果看出，参数只能是整型数字，其他都不行
- `oct()`：返回整数或长整数的八进制表示。
  语法：
  ```python
   oct(number) -> string
  ```
  实例演示：
  ```python
  >>> oct(123)
  '0173'
  >>> oct('123')
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  TypeError: oct() argument can't be converted to oct
  >>> oct(1.2)
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  TypeError: oct() argument can't be converted to oct
  ```
  >说明：由结果看出，参数只能是整型数字，其他都不行
- `chr()`：用序数i（准确说应该是整型数值）返回一个字符串; `0 <= i <256`。
  语法：
  ```python
  chr(i) -> character
  ```
  实例演示：
  ```python
  >>> chr(1)
  '\x01'
  ```
  ```
  >>> chr(2)
  '\x02'
  ```
  ```
  >>> chr(23)
  '\x17'
  ```
  ```
  >>> chr(2.3)
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  TypeError: integer argument expected, got float
  ```
  ```
  >>> chr('hh')
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  TypeError: an integer is required
  ```
  ```
  >>> chr()
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  TypeError: chr() takes exactly 1 argument (0 given)
  ```
  >说明：由上面得实例可能的出来，只能是`整型数值`，其他的都报错，不行
- `ord()`：返回一个`单字符串`的整数序数。
  语法：
  ```python
  ord(c) -> integer(整数）
  ```
  实例演示：
  ```python
  >>> ord()
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  TypeError: ord() takes exactly one argument (0 given)
  ```
  ```python
  >>> ord('')
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  TypeError: ord() expected a character, but string of length 0 found
  ```
  ```
  >>> ord('0')
  48
  ```
  ```
  >>> ord('1')
  49
  ```
  ```
  >>> ord('2')
  50
  ```
  ```
  >>> ord('7')
  55
  ```
  ```
  >>> ord('8')
  56
  ```
  ```
  >>> ord('9')
  57
  ```
  ```
  >>> ord('h')
  104
  ```
  ```
  >>> ord(5)
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  TypeError: ord() expected string of length 1, but int found
  ```
  ```
  >>> ord(5.5)
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  TypeError: ord() expected string of length 1, but float found
  ```
  >说明：由上面的实例得出，参数只能是`单个字母的字符串('h')`或者是`单个整型数字的字符串('1')`，换成其他的就不行
  
## 模块
- 模块是Python组织代码得基本方式
- Python得脚本都是使用扩展名为py得文本文件保存得，一个脚本可以单独运行，也可以导入另一个脚本中运行。当脚本被导入运行时，我们将其称为模块（module）
- 模块名与脚本得文件名时相同得
  - 例如我们编写一个脚本test.py，则可以在另外一个脚本中使用`import test`语句导入它
- Python得模块可以按目录组织为包
- 创建一个包得步骤是：
  - 建立一个名字为包名字得文件夹（名字自定义，可根据项目而定）
  - 在该文件夹下创建一个`__init__.py`文件（`__`是两下划线）
  - 根据需要在该文件夹下存放脚本，已编译扩展及子包
  - import pack.m1,import pack.m2
  - 程序再导入模块时默认是从当前位置查找模块
- 导入模块和包得方式：`import`,`import as`,`from import`等语句
  - `import`：直接导入脚本，例如: test.py,import test
  - `import as`：设置模块别名，例如：import test as c
  - `from import`：从模块中导入函数等，例如： from test import fun
- 导入模块实例演示：
  创建一个脚本：
  ```python
  # vi tt.py
  # coding=utf-8
  #!/bin/bash/env python
  
  if 1 == 1 or not 1 == 2 :
      print "OK"
  else:
      print "Failed"
  ```
  再创建一个脚本导入上面得脚本，执行结果：
  ```python
  # vi p.py
  #coding=UTF-8
  #!/bin/env python
  import tt
  # python p.py
  OK
  ```
- 按照包得导入实例演示：
  创建包目录：
  ```python
  # mkdir My
  ```
  进入My目录创建`__init__.py`文件:
  ```python
  # cd My
  # touch.exe  __init__.py
  ```
  再My目录再创建两个脚本：
  ```python
  # vi tt.py
  # coding=utf-8
  #!/bin/bash/env python
  
  if 1 == 1 or not 1 == 2 :
      print "OK"
  else:
      print "Failed"
  ```
  ```python
  # vi var.py
  #coding=utf-8
  #!/bin/env python
  
  def fun():
      global x
      x = "局部变量x"
      print x
  
  fun()
  print  "这是通过global声明的全局变量", x
  ```
  返回上级目录，编写一个脚本，导入`tt.py`和`var.py`执行结果：
  ```python
  # vi p.py
  #coding=UTF-8
  #!/bin/env python
  print "import My.var"
  import My.var
  print "import My.tt"
  import My.tt

  # python p.py
   python p.py
   import My.var
   局部变量x
   这是通过global声明的全局变量 局部变量x
   import My.tt
   OK
  ```
## 正则表达式
- 正则表达式（或者RE）是一种小型的、高度专业化的编程语言，(再Python中)它内嵌再Python中，并通过`re`模块实现。
  - 可以为想要匹配的相应字符集指定规则
  - 该字符集可能包含英文语句、email地址、命令或者任何你想搞定的东西
  - 可以问诸如“这个字符串匹配该模式吗？”
  - “在这个字符串中是否有部分匹配该模式呢？”
  - 你也可以使用`RE`以各种方式来修改或者分割字符串
  - 正则表达式被编译成一系列的字节码，然后用C编写的匹配引擎执行
  - 正则表达式语言相对小型和受限（功能有限）
    - 并非所有字符串处理都能用正则表达式完成
- 字符匹配
  - 普通字符匹配
    - 大多数字母和字符一般都会和自身匹配
    - 如正则表达式test会和字符串'test'完全匹配
  - 元字符
    - `.`,`^`,`$`,`*`,`+`,`?`,`{}`,`[]`,`\`,`|`,`()`
- `[]`:
   - 常用来指定一个字符集：[abc],[a-z]
   - 元字符再字符集中不起作用：[akm$]
   - 补集匹配不在区间范围内的字符：[^5]不匹配5
   - 实例演示：
     ```python
     >>> s = r'abc'
     >>> import re
     >>> re.findall(s,'ahellobworldc')
     ['a', 'b', 'c']
     ```
     ```python
     >>> re.findall(s,'ahellldc')
     ['h', 'e', 'l', 'l', 'l', 'd', 'c']
     ```
     >说明：字符串前加`r`可以反斜杠`\`不会特殊处理
- `^`:
   - 匹配首行，除非设置`MULTILINE`标志，他只是匹配字符串的开始，在`MULTILINE`模式里，他可以直接匹配字符串中的每个换行
   - 实例演示：
     ```python
     >>> s = "hello ok, good hello"
     >>> sr = r"^hello"
     >>> re.findall(sr,s)
     ['hello']
     ```
- `$`:
   - 匹配行尾，行尾被定义为要么是字符串尾，要么是一个换行字符串后面任何位置。
   - 实例演示：
     ```python
     >>> s = "hello ok, good china"
     >>> sr = r"china$"
     >>> re.findall(sr,s)
     ['china']
     ```
    >说明：正则表达式的语法就不说了，网上单独找吧，反正与其他语法的都一样，后面单独整理

- 使用正则表达式
  - `re`模块提供了一个正则表达式引擎的接口，可以让你将REstring编译成对象并用他们来进行匹配
  - 编译正则表达式
    ```python
    >>> p = re.compile("ab")
    >>> print p
    <_sre.SRE_Pattern object at 0x6ffffeec9b0>
    ```
    >说明：`re.compile`里面还可以添加属性，详细查看`help`
  - 执行匹配：
    - `RegexObject`：实例有一些方法和属性，完整的列表可查阅Python Library Reference
      - `match()`:决定RE是否在字符串刚开始的位置匹配
      - `search()`:扫描字符串，找到这个RE匹配的位置
      - `findall()`：找到RE匹配的所有子串，并且把他们作为一个列表返回
      - `finditer()`：找到RE匹配的所有子串，并且把他们作为一个迭代器返回
        >说明：如果没有匹配到，`match()`和`search()`将返回`None`。如果成功，就会返回一个`MatchObject`实例
      
      - `match()`实例演示：
        ```python
        >>> s = re.compile(r'hello',re.I)
        >>> s.findall('HELLO')
        ['HELLO']
        >>> s.findall('hello')
        ['hello']
        >>> s.match('hello')
        <_sre.SRE_Match object at 0x6ffffe051d0>
        >>> s.match('hell')
        >>>
        >>> s.match('world hello ')
        >>>
        ```
        >说明：`match()`只能匹配字符串刚开始得位置，也就是首位（有点是居于特定位置）
      
     - `search()`实例演示：
        ```python
        >>> s = re.compile(r'hello',re.I)
        >>> s.search('world hello ')
        <_sre.SRE_Match object at 0x6ffffe051d0>
        >>> s.search('hello world ')
        <_sre.SRE_Match object at 0x6ffffb8eb28>
        >>> s.search('world ')
        >>>
        ```
        >说明：`search()`是匹配包含这个关键字就显示出来，可以说是基于关键字匹配，不管你在开头中间还是结尾，只要匹配就打印，如果没有匹配返回空。

     - `findall()`实例演示：
     
        ```python
        >>> s.findall('world hello')
        ['hello']
        >>> s.findall('hello')
        ['hello']
        ```
        >说明：这个有点跟`search()`有点类似，不过返回得是列表

     - `finditer()`实例演示：
     
        ```python
        >>> s = re.compile(r"hello")
        >>> s.finditer('hello world')
        <callable-iterator object at 0x6ffffe73290>
        ```
        下面这一段代码主要是为了查看`finditer()`返回得结果

        ```python
        >>> x = s.finditer('hello world')
        >>> x.next()
        <_sre.SRE_Match object at 0x6ffffb8eb28>
        >>> s.match('hello')
        <_sre.SRE_Match object at 0x6ffffb8eb90>
        >>> x1 = s.match('hello')
        >>> x1
        <_sre.SRE_Match object at 0x6ffffb8eb28>
        >>> x1.group(0)
        'hello'
        ```
    - `MatchObject`实例方法：
      - `group()`：返回被RE匹配的字符串
      - `start()`：返回匹配开始的位置
      - `end()`：返回匹配结束的位置
      - `span()`：返回一个元组包含匹配(开始，结束)的位置
      - 实际程序中，最常见的做法是将`MatchObject`保存再一个变量中，然后检查他是否为`None`
      
        ```python
        >>> import re
        >>> p = re.compile(r"hello")
        >>> m = p.match("hello world everyone hello")
        >>> m
        <_sre.SRE_Match object at 0x6ffffe586b0>
        ```
        ```python
        >>> if m:
        ...     print "Match is found:", m.group()
        ... else:
        ...     print "Match is not found"
        ...
        Match is found: hello
        ```
        ```python
        >>> if m:
        ...     print "Match is found:", m.end()
        ... else:
        ...     print "Match is not found"
        ...
        Match is found: 5
        ```
        ```python
        >>> if m:
        ...     print "Match is found:", m.start()
        ... else:
        ...     print "Match is not found"
        ...
        Match is found: 0
        ```
        ```python
        >>> if m:
        ...     print "Match is found:", m.span()
        ... else:
        ...     print "Match is not found"
        ...
        Match is found: (0, 5)
        ```
        >说明：由上面的例子看得出来，`start()`、`end()`也是按照序列中索引的位置定位的，起始位为0，结束位为hello后面的位置，不然显示不全hello
        
       `group()`实例演示：

        ```python
        >>> import re
        >>> p = re.compile(r"(hello) (world) (ok)")
        >>> print p.match("hello world ok").group(0)
        hello world ok
        >>> print p.match("hello world ok").group(1)
        hello
        >>> print p.match("hello world ok").group(2)
        world
        >>> print p.match("hello world ok").group(3)
        ok
        ```
        >说明：`group()`里面的数字就是匹配里面从左到右对应的匹配选项

    - 模块级函数
      - re模块也提供了顶级函数调用如：`match()`、`search()`、`sub()`、`subn()`、`findall()`等等
      - `sub()`：替换字符或者数值
        - 语法：
          ```python
          sub(pattern, repl, string, count=0, flags=0)
          ```
        - 说明：共五个参数，其中三个必须选参数：`pattern`、`repl`、`string`，两个可选参数：`count`、`flags`
        - 第一个参数`pattern`：表示正则中的模式字符串，也就是正则匹配的内容
          - 需要注意的是：反斜杠加数字（`\N`)，则对应着匹配的组，比如：`\6`，表示匹配前面pattern中的第6个组，这就意味着前面是存在对应的第6个组，然后才去去能引用，这个有点像shell中的`$1`,`$2`
          - 实例演示：
            ```python
            >>> s = "hello tom, wellcom tom"
            >>> re.sub(r"hello (\w+), wellcom \1", "ok", s)
            'ok'
            ```
         - 第二个参数`repl`：就是replacement，被替换的字符串，可以是字符串也可以是函数
           - 如果repl是字符串，其中的任何反斜杠转字符都会被处理的
             - `\n`：会被处理对应的换行符
             - `\r`：会被处理为回车符
             - 其他不能识别的转义字符，则只是被识别为普通的字符，如：`\j`会被处理为这个字母的本身
             - 反斜杠加g以及中括号内一个名字，即：\g<name>,对应着命了名的组
             - 实例演示：
               ```python
               >>> s = "hello tom, wellcom tom"
               >>> re.sub(r"hello (\w+), wellcom \1", "\g<1>", s)
               'tom'
               ```
               对应的带命名的组的版本是：
               ```python
               >>> s = "hello tom, wellcom tom"
               >>> re.sub(r"hello (?P<name>\w+), wellcom (?P=name)", "\g<name>", s)
               'tom'
               ```
         - repl是函数：
            ```python
            # vi repl.py

            #coding=utf-8
            #!/bin/env python
            import re
            
            def pythonReSubDemo():
                inputStr = "hello 123 world 456"
                def _add111(matched):
                    intStr = matched.group("number") #123
                    intValue = int(intStr)
                    addedValue = intValue + 111 #234
                    addedValueStr = str(addedValue)
                    return addedValueStr
                replacedStr = re.sub("(?P<number>\d+)", _add111, inputStr)
                print "replacedStr=",replacedStr #hello 234 world 567
            
            #####################################################################

            if __name__=="__main__":
                pythonReSubDemo()
            
            # python repl.py
            replacedStr= hello 234 world 567
            ```
         - 第三个参数`string`:即表示要被处理，要被替换的那个string的字符串，原始字符串
         - 第四个参数`count`： 计数，也就是处理匹配的个数
         - 实例演示：
             ```python
             >>> s = "hello world,hello ok,hello good,hello evryone"
             >>> re.sub(r"hello", "wellcome", s, 2)
             'wellcome world,wellcome ok,hello good,hello evryone'
             ```
        - 第五个参数`flags`：这个暂时未明白
     - `subn()`:与`sub()`唯一不同之处就是返回的结果以元组的形式返回替换的新字符串和替换的次数
        - 语法：
          ```python
          subn(pattern, repl, string, count=0, flags=0)
          ``` 
       - 实例演示：
         ```python
         >>> s = "hello world,hello ok,hello good,hello everyone"
         >>> re.subn(r"hello", "wellcome", s, 2)
         ('wellcome world,wellcome ok,hello good,hello everyone', 2)
         ```
         >说明：后面的2是替换的次数

     - `slpit()`:切割字符串
        - 语法：
          ```python
          split(pattern, string, maxsplit=0, flags=0)
          ```
        - 实例演示：
         ```python
         >>> s = "hello+wolrd-wellcome*world"
         >>> re.split(r'[+\-\*]', s)
         ['hello', 'wolrd', 'wellcome', 'world']
         ```
         >说明：`-`、`*`具有特殊含义，所以需要转义，`-`除了相减还有负数的含义和范围，`*`除了相乘还有返回一个呗重复若干次数的字符串的含义，特殊含义就是脱离本身的含义之外，又赋予新的含义（具有独特性的）

   - 编译标志-`flags`
     - `DOTALL,S`:使`.`匹配包括换行在内的所有字符
     - `IGNORECASE,I`：使匹配对大小写不敏感
     - `LOCALE,L`：做本地化识别（locale-aware）匹配`.`法语等
     - `MULTILINE,M`：多行匹配，影响`^`和`$`
     - `VERBOSE,X`：能够使用`REs`的verbose状态，使之被组织的更清晰易懂
     - `DOTALL,S`实例演示：
        ```python
        >>> import re
        >>> s = r"fly.org"  #这里的点是符号，不是域名的
        >>> re.findall(s, "www.fly.org")这里面的是域名的
        ['fly.org']
        >>> re.findall(s, "www.flyoorg")
        ['flyoorg']
        >>> re.findall(s, "www.fly\norg")
        []
        >>> re.findall(s, "www.fly\norg",re.S)
        ['fly\norg']
        ```
        >说明：当不出现换行符这种的，匹配正常，出现换行符后，就会无法匹配，这时就得添加flags才能匹配

     - `IGNORECASE,I`实例演示：
       ```python
       >>> s = r"fly"
       >>> re.findall(s,"Fly fly FLy fLY")
       ['fly']
       >>> re.findall(s,"Fly fly FLy fLY",re.I)
       ['Fly', 'fly', 'FLy', 'fLY']
       ```
       >说明：`I`flags主要是为了忽略大小写匹配
    - `LOCALE,L`：locales 是 C 语言库中的一项功能，是用来为需要考虑不同语言的编程提供帮助的。举个例子，如果你正在处理法文文本，你想用 "w+ 来匹配文字，但 "w 只匹配字符类 [A-Za-z]；它并不能匹配 "é" 或 "?"。如果你的系统配置适当且本地化设置为法语，那么内部的 C 函数将告诉程序 "é" 也应该被认为是一个字母。当在编译正则表达式时使用 LOCALE 标志会得到用这些 C 函数来处理 "w 後的编译对象；这会更慢，但也会象你希望的那样可以用 "w+ 来匹配法文文本。
    -  `MULTILINE,M`：定义的字符串是多行时使用
      ```python
      >>> s = """
      ... hello world
      ... wellcome world
      ... hello you
      ... where is you
      ... hello me
      ... """
      >>> s
      '\nhello world\nwellcome world\nhello you\nwhere is you\nhello me\n'
      >>> re.findall(p,s)
      []
      >>> re.findall(p,s,re.M)
      ['hello', 'hello', 'hello']
      ```
    - `VERBOSE,X`：定义的正则时多行时使用
      ```python
      >>> s = r"""
      ... \d{3,4}
      ... -?
      ... \d{8}
      ... """
      >>> s
      '\n\\d{3,4}\n-?\n\\d{8}\n'
      >>> re.findall(s,'010-12345678')
      []
      >>> re.findall(s,'010-12345678',re.X)
      ['010-12345678']
      ```
   - 分组：`()`
     实例演示：
     ```python
     >>> email = r"\w{3}@\w+(\.com|\.cn)"
     >>> re.match(email,'myy@fly.com')
     <_sre.SRE_Match object at 0x6ffffe676c0>
     >>> s = re.match(email,'myy@fly.com')
     >>> s.group()
     'myy@fly.com'
     ```
     ```python
     >>> s = """ disk we hello src=fly yes check
     ... start src=123 yes bengin
     ... src=567 yes
     ... hello src=python yes linux
     ... """
     >>> s
     ' disk we hello src=fly yes check\nstart src=123 yes bengin\nsrc=567 yes\nhello src=python yes linux\n'
     >>> print s
      disk we hello src=fly yes check
     start src=123 yes bengin
     src=567 yes
     hello src=python yes linux
     
     >>> p = r"hello src=.+ yes"
     >>> re.findall(p,s)
     ['hello src=fly yes', 'hello src=python yes']
     >>> p = r"hello src=(.+) yes"
     >>> re.findall(p,s)
     ['fly', 'python']
     ```
     >说明：在使用分组时，`findall`优先返回分组匹配项

   - 爬虫实例：
     抓取这里：
     ![](http://i.imgur.com/9LMmGfF.png)
     ![](http://i.imgur.com/miAn8LT.png)

     ```python
     # coding=utf-8
     '''
     Created on 2017年7月22日
     
     @author: g
     '''
     #print "Created on 2017年7月22日"
     import re 
     import urllib
     
     def gethtml(url):
         page = urllib.urlopen(url)
         html = page.read()
         return html
     
     def getimage(html):
         reg = r'img src="(.*?\.gif)">'
         image = re.compile(reg)
         imglist = re.findall(image, html)
         x= 0
         for imgurl in imglist:
             #下载图片，并重命名
             urllib.urlretrieve(imgurl,'%s.gif' % x)
             x+=1
             
     html =  gethtml("http://sc.chinaz.com/biaoqing/160320526130.htm")
     getimage(html)
     print "download is comlete"
     ```
     执行结果如下：
     ![](http://i.imgur.com/QmgHfDj.png)

## Python对内存得使用
- 使用深浅拷贝通过导入copy实现：`import copy`
- 浅拷贝：就是对引用的拷贝（只拷贝父对象）
- 浅拷贝实例：
  定义一个变量： a = [1,2,3,['a','b','c']]
  ```python
  >>> import copy
  >>>
  >>> a = [1,2,3,['a','b','c']]
  >>> b = a #仅是改变标签
  >>> b
  [1, 2, 3, ['a', 'b', 'c']]
  >>> c = copy.copy(a)
  >>> c
  [1, 2, 3, ['a', 'b', 'c']]
  ```
  >说明：定义a，并且将a的对象引用到b，然后将a拷贝给c，然后查看a、b、c三者的对象都有一样

  查看三者的区别，通过id查看地址空间：
  ```python
  >>> id(a)
  7696579754248
  >>> id(b)
  7696579754248
  >>> id(c)
  7696579794632
  ```
  >说明：通过id查看地址空间，a、b相同（b仅是对a一个标签改变），而c的地址空间发生改变了

  c与a和b的地址空间发生变化，那么改变a、b的值是否影响c了：
  ```python
  >>> a.append('d')
  >>> a
  [1, 2, 3, ['a', 'b', 'c'], 'd']
  >>> b
  [1, 2, 3, ['a', 'b', 'c'], 'd']
  >>> c
  [1, 2, 3, ['a', 'b', 'c']]
  ```
  >说明：给a增加一个值，b也同时改变（因为a、b只是改变标签而已），而c却未改变，此时就是一个浅拷贝，仅对父对象拷贝，里面改变的子对象并未全部拷贝出来

  通过id验证a、c父对象的地址空间是否相同：
  ```python
  >>> id(a[0])
  25769903896
  >>> id(c[0])
  25769903896
  >>> id(a[1])
  25769903872
  >>> id(c[1])
  25769903872
  >>> id(a[2])
  25769903848
  >>> id(c[2])
  25769903848
  ```
  >说明：通过id查看a、c里面的父对象的地址空间是一样的，对于父对象增加值，不会影响浅拷贝的值，如果改变里面的值了，会如何下面验证下

  改变父对象a里面的值（注意：改变值是改变可变对象的值（列表和字典））,改变a中的可变对象列表`['a','b','c']：
  
  未改变之前的地址空间一样：
  ```python
  >>> id(a[3])
  7696579754536
  >>> id(c[3])
  7696579754536
  ```
  改变a中的列表值后：
  ```python
  >>> a[3].append('d')
  >>> a
  [1, 2, 3, ['a', 'b', 'c', 'd'], 'd']
  >>> b
  [1, 2, 3, ['a', 'b', 'c', 'd'], 'd']
  >>> c
  [1, 2, 3, ['a', 'b', 'c', 'd']]
  ```
  >说明：因为a中的列表和c中的裂变占用的地址空间是一样的所以改变a，c也会改变，之前a里面增加d，c未改变是因为整个a的父对象和c的父对象所占用的空间是不一样的（这里的a的整个父对象是指修改后的），所以说它只是拷贝了一个外层的对象

- 深拷贝：就是对对象的资源的拷贝（把所有的数据拷贝出来）
- 深拷贝实例：
  ```python
  >>> a
  [1, 2, 3, ['a', 'b', 'c', 'd'], 'd']
  >>> d = copy.deepcopy(a)
  >>> d
  [1, 2, 3, ['a', 'b', 'c', 'd'], 'd']
  ```
  通过id查看a、d的地址空间：
  ```python
  >>> id(a)
  7696579754248
  >>> id(d)
  7696579753312
  ```
  >说明：此时a、d的地址空间不一样

  通过id查看a、d内部存储空间：
  ```python
  >>> id(a[0])
  25769903896
  >>> id(d[0])
  25769903896
  >>> id(a[1])
  25769903872
  >>> id(d[1])
  25769903872
  >>> id(a[2])
  25769903848
  >>> id(d[2])
  25769903848
  >>> id(a[3])
  7696579754536
  >>> id(d[3])
  7696579682248
  >>> id(a[4])
  7696581158632
  >>> id(d[4])
  7696581158632
  ```
  >说明：通过id查看a、d内部地址空间，仅发现`a[3]`与`d[3]`的地址空间不一致

  对a增加一个值：
  ```python
  >>> a.append('e')
  >>> a
  [1, 2, 3, ['a', 'b', 'c', 'd'], 'd', 'e']
  >>> d
  [1, 2, 3, ['a', 'b', 'c', 'd'], 'd']
  ```
  >说明：此时a发生变化，d任然未变化

  对`a[3]`列表增加值：
  ```python
  >>> a[3].append('x')
  >>> a
  [1, 2, 3, ['a', 'b', 'c', 'd', 'x'], 'd', 'e']
  >>>
  >>> d
  [1, 2, 3, ['a', 'b', 'c', 'd'], 'd']
  ```
  >说明：此时深拷贝却未发生变化（内部地址空间不一致），浅拷贝是发生变化的（内部空间地址一致）

- 总结：
   - 浅拷贝：是对对对象父对象内边的子对象拷贝（引用），所以当父对象里面的可变的子对象值发生变化，浅拷贝里面的可变的子对象也发生变化（里面所有的子对象地址空间是一样的），当父对象的地址空间发生变化，浅拷贝的父对象地址空间不会变化（增加父对象的子对象），里面的子对象依旧保持为未变化前的父对象的子对象
   - 深拷贝：是对对对象父对象及其里面的子对象拷贝，两者是完全独立的，里面可变的子对象的地址空间会发生变化，与原来的父对象里面的可变的子对象的地址空间不一样了，当父对象的地址空间（增加子对象的值）和里面可变的子对象的地址空间发生变化（增加或修改子对象的值），深拷贝的父对象及其里面的子对象的值依旧保持原来为未变化前的父对象及其子对象
   - 深浅拷贝的区别：浅拷贝的父对象的地址空间发生变化，里面的子对象空间不发生变化，深拷贝，父对象发生变化，里面的可变的子对象发生变化，也就是说浅拷贝干不了的事情，深拷贝肯定不行了，主要就是浅拷贝里面可变的子对象不变，深拷贝不一样

## 文件与目录
- 文件的打开和创建
  语法：
  ```python
  open('filename','mode')
  file'(filename','mode')
  ```
  >说明：使用`open`或者`file`打开文件，后面的`mode`为模式（可读，可写等等）。`file`属于类，但是与`open`基本上类似

  `mode`说明：

|模式|说明|
|:---|:---|
|`r`  |只读  |
|`r+` |读写|
|`w`  |写入，先删除原文件，再重新写入，如果文件不存在则创建|
|`w+` |读写，先删除原文件，再重新写入，如果文件不存在则创建（可以写入输出）|
|`a`  |写入，在文件末尾追加新的内容，文件不存在则创建|
|`a+` |读写，在文件的末尾追加新的内容，文件不存在则创建|
|`b`  |打开二进制的文件，可以与`r`,`w`,`a`,`+`结合使用|
|`U`  |支持所有的换行符号，`\r`,`\n`,`\r\n`|

  实例演示：
  ```python
  >>> fo = open('2.txt')
  >>> fo
  <open file '2.txt', mode 'r' at 0x6ffffe9d660>
  ```
  >说明：这里只是打开，所以没有任何的输出，单独输出fo可以看到他的对象，并且模式默认是读取的
  
- 文件的读取
  语法：
  ```python
  object.read()
  ```
  >说明：`object`是定义的打开文件的对象，然后通过方法read读取里面的内容

  实例演示：
  ```python
  >>> fo = open('2.txt')
  >>> fo.read()
  'test1\ntest2\ntest3\n'
  ```
- 文件的关闭
  语法：
  ```python
  object.close()
  ```
  >说明：object为打开文件定义的变量对象

  实例演示：
  ```python
  >>> fo = open('2.txt')
  >>> fo.read()
  'test1\ntest2\ntest3\n'
  >>> fo.close()
  >>> fo.read()
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  ValueError: I/O operation on closed file
  ```
  >说明：当使用`close`关闭文件后，再次读取文件就发生了错误，提示文件已经关闭了
- 文件的写入
  语法：
  ```python
  open('filename',['r+'|'w'|'w+'])
  object.write('string')
  object.close()或者object.flush()
  ```
  >说明：首先必须打开文件，并且赋写入的模式（`'r+'`、`'w'`、`'w+'`），然后通过`write`写入需要添加的内容，然后通过`close`或者'flush`将内容从缓存区域写入文件

  实例演示：
  首次以写入模式打开文件，并读取里面的内容
  ```python
  >>> fo = open('2.txt','r+')
  >>> fo.read()
  'test1\ntest2\ntest3\n'
  ```
  然后写入内容，再次读取为空：
  ```python
  >>> fo.write('hello world')
  >>> fo.read()
  ''
  ```
  然后关闭文件，再次打开读取，内容已经写入文件：
  ```python
  >>> fo.close()
  >>> fo = open('2.txt','r+')
  >>> fo.read()
  'test1\ntest2\ntest3\nhello world'
  ```
  另外通过`flush`也能写入文件，不用关闭，有点实时写入的效果：
  ```python
  >>> fo = open('2.txt','r+')
  >>> fo.read()
  'test1\ntest2\ntest3\nhello world'
  >>> fo.write('china good')
  >>> fo.flush()
  ```
  此时读取是没有数据， 但是打开文件是显示有数据了：
  ![](http://i.imgur.com/lO6XhHM.png)
  
  当我们写入数据过程中不进行读取操作出现前面几行内容被覆盖：
  ```python
  >>> fo = open('2.txt','r+')
  >>> fo.write('good')
  >>> fo.close() #fo.flush()
  ```
  ![](http://i.imgur.com/63v6RJP.png)
  >说明：为什么会这样了，因为里面有一个隐形的指针，最开始是在起始位置，在读取的数据的时候，指针一个字母一个字母指一边才会将所有的字符显示完，当所有的数据显示完，指针就是在最后的位置，所以这个时候写入数据是在最后的位置添加数据，也就是说文件内容写入的位置是指针最后指向的位置，指针指在哪里，内容就写在哪里，如果指针指向的位置有数据就直接覆盖掉了
- 内容查找和替换
  - 文件查找：
    文件内容：
    ```python
    # cat 2.txt
    www.fly.com
    www.web.com
    www.php.com
    www.nginx.com
    www.zabbix.com
    www.google.com
    hello world
    wellcome to china
    ```
    查找包含有fly字段的：
    ```python
    >>> fo = open('2.txt')
    >>> s = r"fly"
    >>> ss = fo.read()
    >>> import re
    >>> re.findall(s,ss)
    ['fly']
    >>> re.findall(s,ss)
    ['fly']
    ```
    文件替换：
    写入新的文件：
    ```python
    >>> fo = open('2.txt')
    >>> fo2 = open('22.txt','w')
    >>> for i in fo.readlines():
    >>> for i in fo.readlines():
    ...     fo2.write(i.replace("fly","hello"))
    ...
    >>> fo.close()
    >>> fo2.close()
    ```
    查看文件内容：
    ```python
    # cat 22.txt
    www.hello.com
    www.web.com
    www.php.com
    www.nginx.com
    www.zabbix.com
    www.google.com
    hello world
    wellcome to china
    ```
    写入原来的文件：
    ```python
    # cat 2.txt
    www.fly.com
    www.web.com
    www.php.com
    www.nginx.com
    www.zabbix.com
    www.google.com
    hello world
    wellcome to china
    ```
    ```python
    >>> fo = open('2.txt','r+')
    >>> s = fo.read()
    >>> fo.seek(0,0)
    >>> fo.write(s.replace("hello","Computer"))
    >>> fo.close()
    ```
    ```python
    # cat 2.txt
    www.fly.com
    www.web.com
    www.php.com
    www.nginx.com
    www.zabbix.com
    www.google.com
    Computer world
    wellcome to china
    ```
    >说明：这样做的替换会将文件里面所有匹配的进行替换，还有一点，使用`replace`替换，如果替换的字符长度小于被替换的，是不能完全覆盖的，使用`sub`应该是可以解决此问题的
- 文件删除、复制、重命名（这个放在下节OS模块中说)
- 目录操作（这个放在下节OS模块中说)

## 文件对象方法
- `FileObject.close()`:关闭文件
  >说明：上面已经举过例子不再演示了
- `String = FileObject.readline([size])`:于从文件读取整行，包括 "\n" 字符。如果指定了一个非负数的参数，则返回指定大小的字节数，包括 "\n" 字符。
  语法：
  ```python
  FileObject = open('finlename')
  FileObject.readline([size])
  ```
  >说明：打印一个整行,这里的size也是大小的意思
  
  实例演示：
  不带size:
  ```python
  # cat 2.txt
  www.fly.com
  www.web.com
  www.php.com
  www.nginx.com
  www.zabbix.com
  www.google.com

  >>> fo = open('2.txt')
  >>> fo.readline()
  'www.fly.com\n'
  ```
  带size：
  ```python
  >>> fo = open('2.txt')
  >>> fo.readline(2)
  'ww'
  ```
  >说明：`readline`就是打印一个整行，当带参数时，则打印与参数匹配的字符个数，如上述里面的参数为2，则打印出一个整行的前两个字符：ww
- `String = FileObject.readlines([size])`：用于读取所有行(直到结束符 EOF)并返回列表，该列表可以由 Python 的 for... in ... 结构进行处理。如果碰到结束符 EOF 则返回空字符串。读取所有行并返回列表，若给定size>0，返回总和大约为sizeint字节的行, 实际读取值可能比size较大, 因为需要填充缓冲区，这里的size指的是文件的大小了（默认以B计算）
  语法：
  ```python
  FileObject = open('finlename')
  FileObject.readlines([size])
  ```
  >说明：打印所有的行，并且以列表的形式输出，可选的大小参数（如果给出）是一个近似的界限返回行中的总字节数。

  实例演示：
  不带size参数的：
  ```python
  >>> fo = open('2.txt')
  >>> fo.readlines()
  ['www.fly.com\n', 'www.web.com\n', 'www.php.com\n', 'www.nginx.com\n', 'www.zabbix.com\n', 'www.google.com']
  ```
  带size参数的：
  已经说明此处的size是文件的大小，那么我们就用下面1.1MB大小的文件做测试验证下（经过测试文件小于1M无法得到效果，也就是因为接近界限，所以返回总行数中的总字节数）
  ```python
  # ls -lh 4.txt
  -rw-r--r-- 1 g None 1.1M 8月  27 22:25 4.txt
  ```
  因为`readlines中是以B计算大小的，那么我们将1.1M换算成B大小的为：80896，然后随便娶个大小，这里取524288：
  ```python
  >>> fo = open('4.txt')
  >>> for i in fo.readlines(524288):
  ...     s = open('yy.txt','a+')
  ...     tt = s.write(i)
  ...     s.close()
  ...
  >>> fo.close()
  ```
  >说明：打开文件4.txt，然后使用`readlines`读取524288`B`大小的内容，然后写入yy.txt文件中，大多数情况下，返回的字节数总是大于给定的字节数，看下下面的演示，生成的yy.txt实际大小为520Kb（532480B），出最后一次调用（因为之前的已经大于了）

  然后通过`wc -l`查看新产生的文件行数，与之前的对比：
  ```python
  # wc -l 4.txt
  70960 4.txt
  # wc -l yy.txt
  32890 yy.txt
  # ls -lh 4.txt
  -rw-r--r-- 1 g None 1.1M 8月  27 22:25 4.txt
  # ls -lh yy.txt
  -rw-r--r-- 1 g None 520K 8月  27 22:45 yy.txt
  ```
  >说明：`readline`与`readlines`中的可选参数`size`都是大小（字节B）不过在操作中`readline`返回的是文件中一整行中参数指定的字符个数，而`readlines`返回的是指定大小的整行内容（不是一个整行），而且如果文件小于1M，不管设定多大的size，返回都是整个文件内容，这个是我自己总结的，其他暂未得到比较正式一点或者官方性的说明
  
- `List = FileObject.read([size])`：读取文件内容，里面的`size`是读取的字节，也可以说读取字符串的个数
  语法：
  ```python
   fileObject.read([size])--> read at most size bytes, returned as a string.
  ```
  >说明：如果size参数为负数或省略，则读取直到达到EOF。请注意，在非阻塞模式下，即使没有给出大小参数，也可能返回比请求的数据少的数据。

  实例演示：
  不带size的：
  ```python
  >>> s = open('2.txt')
  >>> s.read()
  'www.fly.com\nwww.web.com\nwww.php.com\nwww.nginx.com\nwww.zabbix.com\nwww.google.com'
  ```
  带size的：
  ```python
  >>> s = open('2.txt')
  >>> s.read(3)
  'www'
  ```
  >说明：`read`跟`readlines`有点相似，不加参数都是读取文件所有的行，区别在于`read`是以字符串形式输出，`readline`是以列表输出，而`read`跟`readline`加参数的效果一样，会截取字符的个数
- `FileObject.next()`：在文件使用迭代器时会使用到，在循环中，next()方法会在每次循环中调用，该方法返回文件的下一行，如果到达结尾(EOF),则触发 StopIteration
  语法：
  ```python
  FieObject.next()
  ```
  实例演示：
  普通情况下执行next，知道遍历完毕会报错，有点for的味道：
  ```python
  >>> s = open('2.txt')
  >>> s.next()
  'www.fly.com\n'
  >>> s.next()
  'www.web.com\n'
  >>> s.next()
  'www.php.com\n'
  >>> s.next()
  'www.nginx.com\n'
  >>> s.next()
  'www.zabbix.com\n'
  >>> s.next()
  'www.google.com'
  >>> s.next()
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  StopIteration
  ```
  `for`循环本身就是遍历，跟这个差不多，所以这里使用`while`：
   ```python
   >>> fo = open('2.txt')
   >>> while True:
   ...     ss = fo.next()
   ...     print ss
   ...
   www.fly.com
   
   www.web.com
   
   www.php.com
   
   www.nginx.com
   
   www.zabbix.com
   
   www.google.com
   Traceback (most recent call last):
     File "<stdin>", line 2, in <module>
   StopIteration
   ```
   >说明：这里仅仅是演示`next`在循环中的应用，后面的报错暂时忽略，目前也不知道怎么解决
- `FileObject.write('string')`：写入内容
  >说明：上面的例子已经演示过不再演示了
- `FileObject.writelines(List)`：用于向文件中写入一序列的字符串。这一序列字符串可以是由迭代对象产生的，如一个字符串列表。换行需要制定换行符 \n。
  语法：
  ```python
   writelines(sequence_of_strings) -> None.  Write the strings to the file.
  ```
  >说明：请注意，不添加换行符。 该序列可以是任何可迭代的对象
  生产字符串。 这相当于为每个字符串调用write（）。强调一点：必须是`字符串的序列`(列表或者元组应该也行都是要字符串的)
  
  实例演示：
  ```python
   >>> fo = open('2.txt','a+')
   >>> s = ['1','2','3']
   >>> fo.writelines(s)
   >>> fo.close()
   >>> fo = open('2.txt')
   >>> fo.read()
   'www.fly.com\nwww.web.com\nwww.php.com\nwww.nginx.com\nwww.zabbix.com\nwww.google.com\n123'
  ```
- `FileObject.seek(偏移量，选项)`：用于移动文件读取指针到指定位置。偏移量：开始的偏移量，也就是代表需要移动偏移的字节数，选项：可选，默认值为 0。给偏移量参数一个定义，表示要从哪个位置开始偏移；0代表从文件开头开始算起，1代表从当前位置开始算起，2代表从文件末尾算起。
  语法：
  ```python
  seek(offset[, whence]) -> None.  Move to new file position(位置).
  ```
  >说明：参数offset是一个字节数。 可选参数whence默认为0（从文件起始偏移量，offset应为> = 0）; 其他值为1（相对于当前位置移动，正或负）和2（相对于文件结尾移动，通常为负数，尽管许多平台允许在文件结尾之外寻找）。 如果文件以文本模式打开，则只有由tell（）返回的偏移是合法的。 使用其他偏移会导致未定义的行为。
  请注意，并不是所有的文件对象都可以查找。简单说：`offset`：开始偏移量，也就是代表需要移动偏移的字节数，`whence`：可选（默认0），给`offset`定义一个参数，表示从那个位置开始偏移，0代表开头，1代表当前位置，2代表文件末
 
  实例演示：
  先读取文件整个内容：
  ```python
  >>> fo = open('3.txt')
  >>> fo.read()
  'hello world python\n'
  >>> fo.read()
  ''
  ```
  >说明：`read`是读取所有的行，并且指针会停留在最后一行结尾，所以二次`read`为空

  然后使用`seek`，刚开始使用0显示所有的字符，然后使用2则从第三个字符显示剩余字符:
  ```python
  >>> fo.seek(0)
  >>> fo.read()
  'hello world python\n'
  >>> fo.read(2)
  ''
  >>> fo.seek(2)
  >>> fo.read()
  'llo world python\n'
  ```
  >说明：这些是通过正向偏移,也就是从文件开头选取，；另外了，偏移量为0（带参数0）和偏移量为1时（默认不带参数whence）是一样的输出，如果offset只为0，就打印所有的字符，说到1为当前位置，就是从剩余字符开头第一个算起，2很简单了，文件末尾了，`记住一点1的当前位置不能使用read这些读取的，再次seek，因为他们指针会回到结尾`

  设定`whence`参数：
  从文件末尾偏移-4：
  ```python
  >>> fo.seek(-4,2)
  >>> fo.read()
  'hon\n'
  ```
  >说明：从可选参数设定为2，那么offset只能为负数了，不然按照正数，后面肯定为空了（2代表字符结尾啊）,另外了，可以通过`tell()`查看指针偏移的位置
- `FleObject.flush()`：用来刷新缓冲区的，即将缓冲区中的数据立刻写入文件，同时清空缓冲区，不需要是被动的等待输出缓冲区写入。一般情况下，文件关闭后会自动刷新缓冲区，但有时你需要在关闭前刷新它，这时就可以使用 flush() 方法。
  语法：
  ```python
   flush() -> None.  Flush the internal I/O buffer. 
  ```
  实例演示：
  ```python
  >>> fo = open('2.txt','a+')
  >>> fo.write("hello world\n wellcome to china")
  >>> fo.flush()
  >>> fo.read()
  ''
  >>> fo.seek(0,0)
  >>> fo.read()
  'www.fly.com\nwww.web.com\nwww.php.com\nwww.nginx.com\nwww.zabbix.com
  \nwww.google.com\n123hello world\n wellcome to china'
  ```
  >说明：当写入数据后，执行`flush`将缓存数据写入文件后，因为指针停留在文件的尾行，所以当`read`读取时，显示为空，这时候想读取数据就得使用`seek`将指针指向文件起始位置，这样就可以读取文件内容了。

## OS模块
- 目录操作就是通过python来实现目录的创建，修改，遍历等功能
- `import os`：目录操作需要调用os模块，比如：os.mkdir('/root/test')
- 常用os模块函数(`os.xxx`)（还有很多，后续再完善)

|函数|说明|
|---|---|
|`mkdir('path'[,mode=0777])`|创建目录后面mode为权限，可选|
|`makedirs('name',mode=511)`|用于递归创建目录|
|`rmdir('path')`|用于删除指定路径的目录。仅当这文件夹是空的才可以, 否则, 抛出OSError|
|`removedirs('path')`|用于递归删除目录。像rmdir(), 如果子文件夹成功删除, removedirs()才尝试它们的父文件夹,直到抛出一个error(它基本上被忽略,因为它一般意味着你文件夹不为空)。|
|`listdir('path)`|用于返回指定的文件夹包含的文件或文件夹的名字的列表。这个列表以字母顺序。 它不包括 '.' 和'..' 即使它在文件夹中。(仅支持Windows和Unix)
|`getcwd()`|用于返回当前工作目录|
|`chdir('path)`|用于改变当前工作目录到指定的路径|
|`walk(top,topdown=True,onerror=None)`|用于通过在目录树种游走输出在目录中的文件名，向上或者向下。在Unix，Windows中有效。递归查询|
>备注：
- top -- 根目录下的每一个文件夹(包含它自己), 产生3-元组 (dirpath, dirnames, filenames)【文件夹路径, 文件夹名字, 文件名】。
- topdown --可选，为True或者没有指定, 一个目录的的3-元组将比它的任何子文件夹的3-元组先产生 (目录自上而下)。如果topdown为 False, 一个目录的3-元组将比它的任何子文件夹的3-元组后产生 (目录自下而上)。
- onerror -- 可选，是一个函数; 它调用时有一个参数, 一个OSError实例。报告这错误后，继续walk,或者抛出exception终止walk。
- followlinks -- 设置为 true，则通过软链接访问目录。

- 实例演示：
  - `mkdir('path'[,mode=0777])`，创建目录：
    ```python
    >>> import os
    >>> os.mkdir('filename')
    ```
    查看是否创建名为filename的目录：
    ```python
    $ls
    12.py*  3.txt*   filename/  p.py*          repl.py*   tt*
    2.txt*  4.txt*   mm.py*     p.pyc*         split*     tt.pyc*
    22.txt  cal.py*  My/        python_study/  test1.py*
    ```
  - `makedirs(name,mode=511)`,递归创建目录（mode也可选）：
    ```python
    >>> import os
    >>> os.makedirs('mulu/1/2')
    ```
    查看生成的递归目录mulu/1/2`:
    ```python
    # tree.exe  mulu/
    mulu/
    `-- 1
        `-- 2
    
    2 directories, 0 files
    ```
    >说明：使用`tree`可以查看目录结构

  - `rmdir('path')`，删除制定空目录：
     ```python
     >>> import os
     >>> os.rmdir('filename')
     ```
     查看刚才创建的filename是否删除：
    ```python
    # ls
    12.py*  3.txt*   mm.py*  p.py*          repl.py*   tt*
    2.txt*  4.txt*   mulu/   p.pyc*         split*     tt.pyc*
    22.txt  cal.py*  My/     python_study/  test1.py*
    ```
  - `removedirs('path')`,删除递归空目录：
    ```python
    >>> import os
    >>> os.removedirs('mulu/1/2')
    ```
    >注意使用`removedirs('path')`目录时，必须是递归目录的完成目录，不然报错，无法删除

    查看mulu是否删除：
    ```python
    # ls
    12.py*  22.txt  4.txt*   mm.py*  p.py*   python_study/  split*     tt*
    2.txt*  3.txt*  cal.py*  My/     p.pyc*  repl.py*       test1.py*  tt.pyc*
    ```
  - `listdir('path)`，返回指定文件夹包含的文件an或文件夹名字的列表：
    ```python
     >>> import os
    >>> os.listdir('My')
    ['mulu', 'tt.py', 'tt.pyc', 'var.py', 'var.pyc', '__init__.py', '__init__.pyc']
    ```
    >说明：`listdir('path)`是返回指定目录里面的所有的文件和目录的`名字`，并以列表的形式输出
  - `getcwd()`，返回当前工作目录：
    ```python
    >>> import os
    >>> os.getcwd()
    '/home/g'
    ```
    >说明：当前工作目录就是脚本或者解释器当前所在的位置
  - `chdir('path)`,改变当前工作目录到指定位置：
    ```python
    >>> import os
    >>> os.chdir('My')
    ```
    >说明：改变当前目录到My目录

    刚好可以使用上面的`getcwd()`查看当前位置了：
    ```python
    >>> os.getcwd()
    '/home/g/My'
    ```
  - `walk(top,topdown=True,onerror=None)`,用于通过在目录树种游走输出在目录中的文件名，向上或者向下:
    ```python
    >>> os.walk('.')
    <generator object walk at 0x6ffffdca190>
    ```
    >说明：直接使用`os.walk()`返回的是一个生成器，如果想查看其中的内容可以使用遍历查看

    使用`for`循环可以查看其中的内容：
    ```python
    >>> for i in os.walk('.'):
    ...     print i
    ...
    ('.', ['My', 'python_study'], ['.bashrc', '.bash_history', '.bash_profile', '.inputrc', '.lesshst', '.minttyrc', '.profile', '.viminfo', '12.py', '2.txt', '22.txt', '3.txt', '4.txt', 'cal.py', 'mm.py', 'p.py', 'p.pyc', 'repl.py', 'split', 'test1.py', 'tt', 'tt.pyc'])
    ('./My', ['mulu'], ['tt.py', 'tt.pyc', 'var.py', 'var.pyc', '__init__.py', '__init__.pyc'])
    ('./My/mulu', [], [])
    ('./python_study', [], ['color.txt', 'test.py', 'test1.py', 'test10.py', 'test11.py', 'test2.py', 'test3.py', 'test4.py', 'test5.py', 'test6.py', 'test7.py', 'test8.py', 'test9.py'])
    ```
    >说明：它将当前目录里面所有的文件和目录已元组的形式输出，其中每个元组的第一个元素都是遍历的当前的目录路劲，第二个元素是一个包含当前目录里面所有文件夹目录的列表，第三个元素是包含当前目录里面所有文件的大列表；等到顶级目录遍历完毕就开始遍历顶级目录里面的目录与内容，知道结束位置

    - 其中`top`指的是当前需要遍历的目录，`topdown`指的是遍历目录的顺序，如果`topdown`为`True`或者不指定，默认从当前指定的顶级目录依次遍历，如果为`False`就从当前目录的最里面的位置开始遍历知道顶级目录；
    - `onerror`和`followlinks`暂时没懂，先留着
