# week01
## Python中的数据科学
### 数据科学的技术和方法起源于计算机科学与统计学领域
### 数据科学是黑客技能，数学和统计知识的交集，以及丰富的专业知识
### 数据科学的思考在各种学科和职业中都是很有用的，他是一种处理途径和批判性思维能力的办法
> David Donoho 五十年的数据科学 第八节
将这个领域广泛地描述为六个活动组成
1. 数据探索和准备：清理数据和操控数据
2. 数据的表现和转换
3. 使用数据计算 （R和Python语言至关重要）现代数据科学项目可以跨越许多不同的语言程序和计算范式
4. 数据建模
5. 数据可视化和演示表达（可视化包括图表、图形以及三维可视化和交互式环境
6. 关于数据科学的科学（类似于元数据活动）

## Python函数回顾
### 定义一个函数
* 函数代码块以 def 关键词开头，后接函数标识符名称和圆括号()。
* 任何传入参数和自变量必须放在圆括号中间。圆括号之间可以用于定义参数。
* 函数的第一行语句可以选择性地使用文档字符串—用于存放函数说明。
* 函数内容以冒号起始，并且缩进。
* return [表达式] 结束函数，选择性地返回一个值给调用方。不带表达式的return相当于返回 None。
### 参数传递
* 在 python 中，类型属于对象，变量是没有类型的
* strings, tuples, 和 numbers 是不可更改的对象，而 list,dict 等则是可以修改的对象
* 关键字参数在位置参数后面
### return语句
* return语句退出函数，选择性地向调用方返回一个表达式。不带参数值的return语句返回None
 

## Python类型和序列
* Python有一个内置函数成为type，一些常见的类型包括字符串（string），None，整数（interger）和浮点（floating-point）变数。
* 元组是一个本身不可变的变量序列，使用括号表示()
* 列表和元组都是可以反复迭代的类型，里面的数据也可以存取，通过使用方括号运算程序叫索引运算程序。
* 列表的是一个项目从零开始，获取列表长度使用内置的len函数。
* 索引操作允许你使用多个数值，第一个参数是起始位置，第二个参数是切片的结尾（不包括）
* 字典（dictionaries）类似于列表和元组，包含一些集合的项目，没有排序的集合，使用大括号表示{}

Csv读取和存入
* 导入.csv程序模块
#### csv文件的读取
1.	通过列表下标读取：
 
* 直接用 open() 函数打开 csv 文件。使用csv.reader() 方法，其中参数为指针。因为该 csv 文件有表头，使用可以使用 next() 函数直接跳过第一组数据，即表头数据。然后直接通过列表下标获取想要的数据。
2.	通过key获取:
 
* 使用DictReader创建reader对象，不会包含表头那行的数据，而reader这个迭代器与reader创建的又不一样，遍历这个迭代器，返回来的是一个字典，不是列表。
#### csv文件的写入
1.	使用 writer 创建对象，writerow(s) 写入：
 
* 写入数据到 csv 文件，需要创建一个 writer 对象，才可以使用 writerow 写入一行，而 writerows 是全部写入。其中 默认下 newline=‘\n’ 即写入一行就会换行，所以需要改成空，数据都是存放在列表中。
2.	使用 DictWriter 创建对象，writerow(s) 写入：
* 当数据是存放在字典中可以使用 DictWriter 创建 writer 对象，其中，需要传两个参数，第一个是指针，第二个是表头信息。当使用 DictWriter 创建对象时，写入表头还需要执行 writeheader() 操作。
### Lambda及列表推导
* Lambda是python的方法创建不具名函数
* 声明一个lambda函数，用关键词lambda，后跟一个列表参数，其次是一个冒号，然后一个单一的表达式。
* 不能有lambda参数的默认值，不能在lambda本身内部有复杂的逻辑，因为lambda限于单个表达式
* List comprehension是浓缩的格式，他们可提供可读性和性能优势
### Numpy
* Numpy是一个广泛应用于数据科学界的软件套件，它使我们能够高效地工作在python中的数组（arrays）和矩阵（matrices）。

# Week02
## Pandas能处理什么样的数据？
* 要将数据手动存储在表中，请创建一个DataFrame。使用Python的列表字典时，字典键将用作列标题，而每个列表中的值将用作的行DataFrame。
* 探索，清理和处理数据在Pandas中，数据表称为DataFrame
* 竖着的列column通常放变数variables
* 横着的行row通常放观察observations
* 表格数据（例如存储在电子表格或数据库中的数据）是很常见的，最主流的数据结构和查询语言是SQL
* 树状文本数据（例如HTML, XML, JSON数据）是很常见的，HTML/XML最主流的查询语言是xpath
## 如何读写表格数据？
* pandas提供了read_csv()将存储为csv文件的数据读入pandas的功能DataFrame。pandas开箱即用地支持许多不同的文件格式或数据源（csv，excel，sql，json，parquet等），每种格式都有前缀read_*。
## 如何选择的子集DataFrame？
![Image text](https://github.com/xinyiLuo/pandas-/blob/master/photo/1.png)
## 如何从中选择特定的行和列DataFrame？
![Image text](https://github.com/xinyiLuo/pandas-/blob/master/photo/2.png)
### Tips：
* 选择数据子集时，使用方括号[]。
* 在这些括号内，您可以使用单个列/行标签，列/行标签列表，标签切片，条件表达式或冒号。
* loc使用行和列名称时选择特定的行和/或列
* iloc使用表格中的位置时选择特定的行和/或列
* 您可以基于loc/ 为选择分配新值iloc。




