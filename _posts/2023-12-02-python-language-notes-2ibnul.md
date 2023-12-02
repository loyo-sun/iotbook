---
layout: post
title: Python语言笔记
date: '2023-12-02 15:12:28'
permalink: /post/python-language-notes-2ibnul.html
published: true
---

# Python语言笔记

## 数学运算

|运算符|描述|例子|
| --------| --------| -----------|
|+|加|3+4=7|
|-|减|3-4=-1|
|*|乘|3*4=12|
|/|除|3/2=1.5|
|%|取模|103%100=3|
|<span style="font-weight: bold;" data-type="strong">|幂|3</span>2=9|
|//|取整除|10//3=3|

## 判断

if，如果

if else，如果，那么

elif，否则如果

## 循环

for，有限循环

```py
for i in range(5): # 表示从 0 开始取到 5 之前，即 0，1，2，3，4
for i in range(2,5): #标 识从 2 开始取到 5 之前，即 2，3，4，5，6
for i in range(3,10,2): # 标识从 3 开始取到 10 之前，每 2 次出一个数，即 3，5，7，9 => 3,4|5,6|7,8|9,10
for i in range(3,10,3): #3,4,5|6,7,8|9,10
```

while，无限循环

```py
while guess_num != 20: #若变量不等于 20，执行后续操作，然后返回 while 继续执行。
```

## 终止

break，终止

```py
count = 0 #count的值是0
guess_num = 30 #变量值围 30
while guess_num !=20 and count <= 10: #若变量不等于 20，并且 cpunt 小于等于 10，那么：
	guess_num += 1 #变量+1，注意，这里变量气出的值围 20，每次循环+1，变量永远都到不了 20
	count += 1 #count+1，这里 count 加到 10 次后，就会停止这个循环，这样可以避免死循环
```

```py
count = 0
guess_num = 10
while guess_num != 20:
    guess_num += 1
    count += 1
    if count > 10: # 在循环中嵌套了一个判断，如果 count 大于 10，那么停止
        break
    print(guess_num) # 打印，这个打印是和判断平级的，所以如果 cpunt 大于 10 就会执行打印动作，也就是每一次变量+1 都会被打印
print(guess_num) # 打印，这个打印是在循环外的，即完成循环后，变量的值为 20，那么这个打印只会打印 20
```

continue，跳过

```py
for i in range(10): #循环，给 i 赋值 0，1，2，3，4，5，6，7，8，9
    if i % 2 == 0: #如果 i 除以 2 的余数是 0，即 i 可以被 2 整除
        continue    # 跳过，开始新一轮的 for
    print(i) #否则就打印i
```

## 数据种类

### list列表

[...]表示列表

写数据flies = [1,2,3]

取数据 files[0]

列表是右顺序的，正着取第一个是 0，反着取第一个是-1。

```py

files = ["f1.txt", "f2.txt", "f3.txt", "f4.txt", "f5.txt"] #正：0，1，2，3，4；反：-5，-4，-3，-2，-1
	#		0			1		2			3		4
	#		-5			-4		-3			-2		-1
#单个数据取值
print("files[0] ", files[0]) # 取第 0 位，即1
print("files[3] ", files[3]) # 取第 3 位，即 4
print("files[-1] ", files[-1]) #取倒数第 1 位，即 5
print("files[-3] ", files[-3]) # 取倒数第 3 位，即 3
#一次性取多个值
print("files[:3] ", files[:3]) # 从 0 取到 3 位
print("files[2:4] ", files[2:4])
print("files[-3:] ", files[-3:])
```

list 中改数据

```py
print("old files[1] ", files[1]) # 旧数据的值
files[1] = 12 #给列表中的第 2 个数赋值；
print("new files[1] ", files[1]) 打印第二个值
```

list 中可以放字符、数字和列表

```py
l = [1, "file", ["2", 3.2]]
#	0		1	2-0		2-1
print(l)
l[2][0] = "new string" #通过两次索引，在 list 的 2 序号的的 list 的 0 序号中赋值
print(l)
```

### Dict 字典

字典就是给列表 List 打标签

```py
files = {"ID": 111, "passport": "my passport", "books": [1,2,3]}  #我在列表 files 中存了三个数据，分别给他们做了标签
print(files)
print(files["books"]) #索引 books 这个 Dict 的值
```

字典中的内容是可以修改的，且字典没有顺序

```py
files["ID"] = 222 #给列表中 ID 字典的值赋值
print(files)
files["ID"] = [2,3,4] #重新赋值
print(files)
```

### Tuple元组

元组用（）标识

与列表和字典不同的是，元组中的内容是不能被改变的

```py
files = ("file1", "file2", "file3")
print(files[1])
files[1] = "file4"   # 这里会报错
```

### Set 集合

集合常备用在去重的时候，用他来做交并集，在集合中是没有顺序的。

```py
my_files = set(["file1", "file2", "file3"]) #set（）标识集合，集合中右数据 1，2，3
print(my_files) #打印 1,2,3
my_files.add("file3") #在变量中增加一个数据3
print(my_files) #打印 1，2，3
my_files.add("file4") #在变量种增加一个数据 4
print(my_files) #打印 1，2，3，4
my_files.remove("file3") #在变量中一处 3
print(my_files) #打印 1，2，4
```

数据初始化和交并集操作

```py
print("my_files", my_files) #打印一个原始数据做对比，现在是 1，2，4
your_files = {"file1", "file3", "file5"} #你的数据中包括了 1，3，5
print("your_files", your_files) #打印 1，3，4
print("交集 ", your_files.intersection(my_files)) # 交集案例
print("并集 ", your_files.union(my_files)) # 并集案例
print("补集 ", your_files.difference(my_files)) # 补集案例，my 和 you 各自的全数范围内缺失的部分
```

### 在循环中的应用

```python
files = ["f1.txt", "f2.txt", "f3.txt", "f4.txt", "f5.txt"]
for i in range(len(files)):
if files[i] == "f3.txt":
print("I got f3.txt")
```

这段 Python 代码创建了一个名为 `files`​ 的列表，其中包含了五个文件名字符串。然后，使用 `for`​ 循环遍历 `files`​ 列表的索引值。在每次循环中，通过索引值 `i`​ 获取当前文件名，并与字符串 `"f3.txt"`​ 进行比较。如果它们相等，就会打印出字符串 `"I got f3.txt"`​。

换句话说，这段代码的作用是在 `files`​ 列表中查找文件名为 `"f3.txt"`​ 的文件，并打印出相应的消息。如果找到了该文件名，将会输出 `"I got f3.txt"`​。如果没有找到，将不会有任何输出。

请注意，代码中的缩进对于 Python 是非常重要的，它们用于表示代码块的层次结构。在这段代码中，`print`​ 语句是在 `if`​ 语句的代码块中，只有在条件满足时才会执行。

```python
files = {"ID": 111, "passport": "my passport", "books": [1,2,3]}
for key in files.keys(): 
    print("key:", key)

for value in files.values():
    print("value:", value)

for key, value in files.items():
    print("key:", key, ", value:", value)
```

代码的解释如下：

1. ​`files`​ 是一个字典，包含了三对键值对。键包括 `"ID"`​、`"passport"`​ 和 `"books"`​，对应的值分别是 `111`​、`"my passport"`​ 和 `[1, 2, 3]`​。
2. 第一个 `for`​ 循环使用 `files.keys()`​ 方法遍历字典中的所有键。在每次迭代中，将当前键赋值给变量 `key`​，然后执行缩进的代码块。在这个例子中，代码块中的内容是打印出当前键的值。因此，会依次打印出 `"key: ID"`​、`"key: passport"`​ 和 `"key: books"`​。
3. 第二个 `for`​ 循环使用 `files.values()`​ 方法遍历字典中的所有值。在每次迭代中，将当前值赋值给变量 `value`​，然后执行缩进的代码块。在这个例子中，代码块中的内容是打印出当前值。因此，会依次打印出 `"value: 111"`​、`"value: my passport"`​ 和 `"value: [1, 2, 3]"`​。
4. 第三个 `for`​ 循环使用 `files.items()`​ 方法遍历字典中的所有键值对。在每次迭代中，将当前键赋值给变量 `key`​，将当前值赋值给变量 `value`​，然后执行缩进的代码块。在这个例子中，代码块中的内容是打印出当前键和值。因此，会依次打印出 `"key: ID, value: 111"`​、`"key: passport, value: my passport"`​ 和 `"key: books, value: [1, 2, 3]"`​。

```python
files = []
for i in range(5):
    files.append("f"+str(i)+".txt") # 添加
    print("has", files)

for i in range(len(files)):
    print("pop", files.pop())   # 从最后一个开始 pop 出
    print("remain", files)
```

代码的解释如下：

1. 首先，创建一个空列表 `files`​。
2. 第一个 `for`​ 循环使用 `range(5)`​ 来迭代 5 次，从 0 到 4。在每次迭代中，执行缩进的代码块。
3. 在代码块中，使用 `files.append("f"+str(i)+".txt")`​ 将字符串 `"f"+str(i)+".txt"`​ 添加到列表 `files`​ 中。这里的 `"f"+str(i)+".txt"`​ 是一个字符串拼接的过程，将 `i`​ 转换为字符串，并将其与其他字符串拼接起来。因此，`files`​ 列表将依次包含 `"f0.txt"`​、`"f1.txt"`​、`"f2.txt"`​、`"f3.txt"`​ 和 `"f4.txt"`​。
4. 在添加元素后，使用 `print("has", files)`​ 打印出当前的 `files`​ 列表。在每次迭代中，都会打印出更新后的列表。
5. 第二个 `for`​ 循环使用 `range(len(files))`​ 来迭代列表 `files`​ 的长度次数。在每次迭代中，执行缩进的代码块。
6. 在代码块中，使用 `files.pop()`​ 来从列表 `files`​ 中移除最后一个元素，并返回该元素的值。这个操作会改变列表 `files`​ 的长度和内容。
7. 使用 `print("pop", files.pop())`​ 打印出被移除的元素的值。由于是从最后一个元素开始移除，所以每次迭代会打印出不同的值。
8. 使用 `print("remain", files)`​ 打印出移除元素后的列表 `files`​ 的当前内容。在每次迭代中，都会打印出更新后的列表。

通过这段代码，我们可以看到列表 `files`​ 的动态变化过程。在第一个 `for`​ 循环中，我们向列表 `files`​ 中添加了 5 个元素。然后，在第二个 `for`​ 循环中，我们从列表 `files`​ 中逐个移除元素，并观察列表的变化。

```python
files = ["f1.txt", "f2.txt"]

# 扩充入另一个列表
files.extend(["f3.txt", "f4.txt"])
print("extend", files)

# 按位置添加
files.insert(1, "file5.txt")     # 添加入第1位（首位是0哦）
print("insert", files)

# 移除某索引
del files[1]
print("del", files)

# 移除某值 
files.remove("f3.txt")
print("remove", files)
```

## 函数

def 去定义函数

```python
def modify_name(filename): 
    filename += ".txt"
    filename = "my_" + filename
    print(filename)

modify_name("f1")
modify_name("f2")
```

这段代码定义了一个名为 `modify_name`​ 的函数，该函数接受一个参数 `filename`​，并对其进行一系列操作。

函数的解释如下：

1. 首先，函数 `modify_name`​ 被定义，它接受一个参数 `filename`​。
2. 在函数内部，`filename += ".txt"`​ 将字符串 `".txt"`​ 连接到参数 `filename`​ 的末尾。这样，`filename`​ 将变为 `"f1.txt"`​（对于第一个函数调用）或 `"f2.txt"`​（对于第二个函数调用）。
3. 接下来，`filename = "my_" + filename`​ 将字符串 `"my_"`​ 连接到参数 `filename`​ 的前面。这样，`filename`​ 将变为 `"my_f1.txt"`​（对于第一个函数调用）或 `"my_f2.txt"`​（对于第二个函数调用）。
4. 最后，使用 `print(filename)`​ 打印出变量 `filename`​ 的值。

在主程序中，`modify_name("f1")`​ 和 `modify_name("f2")`​ 分别调用了 `modify_name`​ 函数，传入不同的参数。

对于第一个函数调用，输出为 `"my_f1.txt"`​。对于第二个函数调用，输出为 `"my_f2.txt"`​。

```python
def modify_name(filename):
    filename += ".txt"
    filename = "my_" + filename
    return filename

new_filename = modify_name("f1")
print(new_filename)
```

在这段代码中，`return`​ 关键字用于从函数中返回一个值。它表示函数的执行结果，并将该结果传递给调用函数的代码。

在函数 `modify_name`​ 的定义中，`return filename`​ 表示将变量 `filename`​ 的值作为函数的返回值。在函数内部，`filename`​ 经过一系列操作后得到了新的值，即 `"my_f1.txt"`​。因此，当调用 `modify_name("f1")`​ 时，函数返回的值就是 `"my_f1.txt"`​。

```python
def f(x, a=1, b=1, c=0): #给参数 a，b，c默认值
    return a*x**2 + b*x + c*1

print(f(2, a=2))
print(f(2))
```

‍

‍

## Class 类

用 `class File`​ 来创建一个大概念（类），<span style="font-weight: bold;" data-type="strong">注意我们通常约定类的名字要首字母大写</span>。

用`my_file = File()`​ 来创建一个具体的文件。

​`self`​ 是作为类自己的一个索引

每当你进行一次 `my_file = File()`​ 这种操作的时候，把类给实例化的时候， `File`​ 类都会触发一次 `__init__`​ 功能，所以这是一个功能，用于初始化一些设置。

```python
class File:
    def __init__(self):
        self.name = "f1"
        self.create_time = "today"

my_file = File()
print(my_file.name)
print(my_file.create_time)
```

修改 Class 中的属性

```python
my_file.name = "new_name"
print(my_file.name)
```

### 标准化

利用__init__功能设置默认值

```python
class File:
    def __init__(self, name, create_time="today"):
        self.name = name
        self.create_time = create_time

my_file = File("my_file")
print(my_file.name)
print(my_file.create_time)
```

### 多函数

```python
class File:
    def __init__(self, name, create_time="today"):
        self.name = name
        self.create_time = create_time
  
    def change_name(self, new_name):
        self.name = new_name

my_file = File("my_file")
print(my_file.name)
# 调用实例中，类的功能
my_file.change_name("new_name") 
print(my_file.name)
```

### return

```python
class File:
    def __init__(self, name, create_time="today"):
        self.name = name
        self.create_time = create_time
  
    def get_info(self):
        return self.name + " is created at" + self.create_time

my_file = File("my_file")
print(my_file.get_info())
```

### 继承

```python
class File:
    def __init__(self, name, create_time="today"):
        self.name = name
        self.create_time = create_time
  
    def get_info(self):
        return self.name + "is created at" + self.create_time

class Video(File):  # 继承了 File 的属性和功能
    def __init__(self, name, window_size=(1080, 720)):
        # 将共用属性的设置导入 File 父类
        super().__init__(name=name, create_time="today") 
        self.window_size = window_size

class Text(File): # 继承了 File 的属性和功能
    def __init__(self, name, language="zh-cn"):
        # 将共用属性的设置导入 File 父类
        super().__init__(name=name, create_time="today") 
        self.language = language
  
    # 也可以在子类里复用父类功能
    def get_more_info(self):
        return self.get_info() + ", using language of " + self.language

v = Video("my_video")
t = Text("my_text")
print(v.get_info())     # 调用父类的功能
print(t.create_time)    # 调用父类的属性
print(t.language)       # 调用自己的属性
print(t.get_more_info()) # 调用自己加工父类的功能

```
