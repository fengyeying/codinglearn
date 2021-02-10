@[TOC](目录)
## Python基础
### 1. 数据类型
> 1）整型(int)：整数 Python可以处理任意大小的整数，当然包括负整数，在程序中的表示方法和数学上的写法一模一样。
（2）浮点型(float)：浮点数也就是小数，之所以称为浮点数，是因为按照科学记数法表示时，一个浮点数的小数点位置是可变的。
（3）字符串(string)：字符串是以单引号 ```’ ```或双引号```" ```括起来的任意文本。
（4）布尔值(bool)：布尔值和布尔代数的表示完全一致，一个布尔值只有True、False两种值布尔值 布尔值可以用and、or和not运算。注意大小写
（5）空值：空值是Python里一个特殊的值，用None表示。**None不能理解为0**，因为0是有意义的，而None是一个特殊的空值。
（6）列表(list)：list是一种有序的集合，可以**随时添加和删除其中的元素**。表示方法为：集合名=[集合中的元素]。
（7）元组(tuple)：tuple和list非常类似，但是**tuple一旦初始化就不能修改**。表示方法为：集合名=(集合中的元素)。
（8）字典(dict)：dict的支持，dict全称dictionary，在其他语言中也称为map，使用键-值（key-value）存储，**具有极快的查找速度**。表示方法为：集合名={key:value}。
（9）集合(set)：set和dict类似，也是一组key的集合，但不存储value。由于key不能重复，所以，**在set中，没有重复的key**。表示方法为：集合名={集合中的元素)。

可变对象：list[]  dict{}  set{}
不可变对象：tuple() string int float bool

### 2. 运算符

```python
print(1+2)   # 加法
print(1-2)   # 减法
print(1*2)   # 乘法
print(1/2)   # 除法
print(1//2)  # 整除 (向下取整)
print(1%2)   # 取余数
print(2**2)  # 幂运算
print(2020- 5*5/2 +8**1)   #结合顺序和一般的数学运算符一样
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210210100111555.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzODI4MzMy,size_16,color_FFFFFF,t_70)
### 3. 循环
> ```for while if```
> ```break  continue  pass```
（1）使⽤ break 语句来完全终⽌循环。
（2）使⽤ continue 语句直接跳到循环的下⼀次迭代。
（3）使用 pass 做占位语句，不起任何作用。
### 4. 字符串的操作
#### 4.1 字符串的索引、切片
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210210101359372.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzODI4MzMy,size_16,color_FFFFFF,t_70)

切片的语法：[起始:结束:步长] 字符串[start: end: step] 这三个参数都有默认值，默认截取方向是从左往右的 start:默认值为0； end : 默认值未字符串结尾元素； step : 默认值为1；

如果切片步长是负值，截取方向则是从右往左的
```python
name[1]  
name[-4]
name[1:4]
name[::-1]
```
#### 4.2 count 计数
显示自定义字符在字符串中的个数（不可重叠）
```python
my_string = 'hello_world'
my_string.count('o')
2

my_string = 'aabcabca'
my_string.count('abca')
1
```
#### 4.3 find 、index 查找功能

###### 4.3.1 find 查找

返回从左第一个指定字符的索引，找不到返回-1
###### 4.3.2 index 查找
返回从左第一个指定字符的索引，找不到报错
#### 4.4 split 字符串的拆分
按照指定的内容进行分割
```python
my_string = 'hello_world'
my_string.split('_')

['hello', 'world']
```
#### 4.5 replace 字符串的替换
从左到右替换指定的元素，可以指定替换的个数，默认全部替换

```python
my_string = "I wish to wish the wish you wish to wish"
my_string.replace('wish','wish'.upper(), 3)

'I WISH to WISH the WISH you wish to wish'
```
#### 4.6 strip 字符串标准化
#### 4.7 字符串的变形
##### upper()
##### lower()
##### capitalize()
#### 4.8 字符串的格式化输出 
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210210102312392.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzODI4MzMy,size_16,color_FFFFFF,t_70)

```python
print('大家好！我叫%s，我的身高是%d cm, 数学成绩%.2f分,英语成绩%d分' % (name, hight, score_math, score_english))

大家好！我叫Molly，我的身高是170 cm, 数学成绩95.00分,英语成绩89分
#format用法
'Hello,{0}成绩提升了{1:.1f}分，百分比为 {2:.1f}%'.format('小明', 6, 17.523)

'Hello,小明成绩提升了6.0分，百分比为 17.5%'
#f-string用法
print(f"大家好！我叫{name}，我的身高是{hight:.3f} cm, 数学成绩{score_math}分,英语成绩{score_english}分")

大家好！我叫Molly，我的身高是170.400 cm, 数学成绩95分,英语成绩89分
```
### 5. list 相关操作
#### 5.1 append 添加 extend 合并

```python
list1 = ['a','b','c','d','e','f']
list1.append('g') # 在末尾添加元素
print(list1)
list1.insert(2, 'ooo')  # 在指定位置添加元素，如果指定的下标不存在，那么就是在末尾添加
print(list1)

['a', 'b', 'c', 'd', 'e', 'f', 'g']
['a', 'b', 'ooo', 'c', 'd', 'e', 'f', 'g']

list2 = ['z','y','x']
list1.extend(list2) #合并两个list   list2中仍有元素
print(list1)
print(list2)

['a', 'b', 'ooo', 'c', 'd', 'e', 'f', 'g', 'z', 'y', 'x']
['z', 'y', 'x']
```
#### 5.2 count 计数 index查找

```python
list1 = ['a','b','a','d','a','f']
print(list1.count('a')) 

3
list1 = ['a','b','a','d','a','f']
print(list1.index('a')) 

0
```
#### 5.3 删除元素

```python
list1 = ['a','b','a','d','a','f']
print(list1.pop(3)) 
print(list1)
list1.remove('a')
print(list1)

d
['a', 'b', 'a', 'a', 'f']
['b', 'a', 'a', 'f']
```
#### 5.4 生成列表

```python
list_2 = ['a','b','c_sv','d','e_sv']
[s for s in list_2 if s.endswith('sv')]

['c_sv', 'e_sv']
```
#### 5.5 生成器
##### 列表生成式

```python
g = (x * x for x in range(10))
next(g)
```
##### 基于函数

```python
def factor(max_num):
    # 这是一个函数  用于输出所有小于max_num的质数
    factor_list = []
    n = 2
    while n<max_num:
        find = False
        for f in factor_list:
            # 先看看列表里面有没有能整除它的
            if n % f == 0:
                find = True
                break
        if not find:
            factor_list.append(n)
            yield n            
        n+=1
g = factor(10)
next(g)
```
### 6. 函数

```python
def student_name(name):
    "打印学生的名字"
    print('姓名：', name)
    return {'姓名':name}
rst = student_name('Alice')
rst 

姓名： Alice
{'姓名': 'Alice'}
```
### 7. 参数传递
#### 7.1 位置参数
位置参数是最简单的一种函数调用的方式。位置参数须以正确的顺序传入函数、数量必须和声明时的一样。
```python
def student_name_and_age(name, age):
    print('姓名：%s 年龄 %s' %(name, age))
student_name_and_age('张三', 18)

姓名：张三 年龄 18
```
#### 7.2 缺省参数
调用函数时，缺省参数的值如果没有传入，则被认为是默认值。
```python
def student_name_and_age(name, age='不愿透露'):
    print('姓名：%s 年龄 %s' %(name, age))
student_name_and_age('张三')

姓名：张三 年龄 不愿透露
```
#### 7.3 可变参数
可变参数就是传入的参数个数是可变的，可以是1个、2个到任意个，还可以是0个。

```python
def all_student_names(*names):
    for name in names:
        print('姓名：', name)
all_student_names('张三','李四','王五')

姓名： 张三
姓名： 李四
姓名： 王五
```
#### 7.4 关键字参数
关键字参数允许你传入0个或任意个含参数名的参数，这些关键字参数在函数内部自动组装为一个dict

```python
def student_info(name, age, **kw):
    print(f'我的名字叫：{name},年龄：{age},其它信息：{kw}')
student_info('张三', 18, height=180)

我的名字叫：张三,年龄：18,其它信息：{'height': 180}
```
#### 7.5 命名关键字参数
要限制关键字参数的名字，就可以用命名关键字参数。

```python
def print_person_info(name, age, *, height, weight):
    print('我的名字叫：', name, '年龄：', age,'身高', height, '体重', weight)
print_person_info('张三', 18, height=180, weight=75)

我的名字叫： 张三 年龄： 18 身高 180 体重 75
```
### 8. 变量作用域
1. 局部变量 作用域:在函数内
2. 全局变量 作用域:在函数外
3. 函数优先使用局部变量 在没有局部变量的情况下， 使用全局变量
4. 定义在函数内部的变量，函数结束之后自动消亡
5. 不管外部变量的类型是什么，如果在函数内部想对它做赋值操作就必须使用global声明。
```python
def change_my_name():
    global name
    print('我的名字曾经是', name)
    name = '李四'
    print('我的名字现在是', name)
```
### 9. 函数
#### 9.1 lambda 匿名函数
python 使用 `lambda` 来创建匿名函数。
lambda 只是一个表达式，函数体比 def 简单很多。
lambda 的主体是一个表达式，而不是一个代码块。仅仅能在 lambda 表达式中封装有限的逻辑进去。
lambda 函数拥有自己的命名空间，且不能访问自有参数列表之外或全局命名空间里的参数。
虽然 lambda 函数看起来只能写一行，却不等同于 C 或 C++ 的内联函数，后者的目的是调用小函数时不占用栈内存从而增加运行效率。

```python
# 加法运算 接受两个参数，返回参数之和
add = lambda arg1, arg2: arg1 + arg2
add(1,2)

# 数字转字符串
int2str = lambda x : str(x)
int2str(5)
```
#### 9.2 高阶函数

```python
#函数的名字可以作为一个变量，传入其它函数
def func_x(x, f):
    return f(x)
func_x(-1, abs) 
1

# 一个函数可以接收另一个函数作为参数，这种函数就称之为高阶函数。
int2str = lambda x : str(x)
func_x(-112, int2str)
```
---
##### 9.2.1 map 函数
map()函数接收两个参数，一个是函数，一个是Iterable，map将传入的函数依次作用到序列的每个元素，并把结果作为新的Iterator返回。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210210104112336.png)

```python
fx = lambda x:x**2
ls = [1,2,3,4,5,6,7,8,9]
rst = map(fx, ls)
list(rst)

[1, 4, 9, 16, 25, 36, 49, 64, 81]
```
---
##### 9.2.2 reduce 函数
reduce：用传给 reduce 中的函数 function（有两个参数）先对集合中的第 1、2 个元素进行操作，得到的结果再与第三个数据用 function 函数运算，依此类推，最后得到一个结果。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210210104222438.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzODI4MzMy,size_16,color_FFFFFF,t_70)

```python
from functools import reduce
# 从python3开始，reduce函数移动到了functools这个包，每次使用前要先import
mul_xy = lambda x, y: x*y
reduce(mul_xy, [1, 3, 5, 7, 9])

945
```
##### 9.2.3 sorted 函数
排序也是在程序中经常用到的算法。无论使用冒泡排序还是快速排序，排序的核心是比较两个元素的大小。如果是数字，我们可以直接比较，但如果是字符串或者两个dict呢？直接比较数学上的大小是没有意义的，因此，比较的过程必须通过函数抽象出来。

```python
sorted([36, 5, -12, 9, -21], reverse=True)
sorted([36, 5, -12, 9, -21], key=abs)   # 按绝对值排序key指定的函数将作用于list的每一个元素上，并根据key函数返回的结果进行排序

points = [(5,2), (7,3), (3,4),(1,1),(2,6)]  # 按x坐标排序 y坐标排序 和0点距离排序
f_x = lambda x:x[0]
sorted(points, key=f_x)
f_y = lambda x:x[1]
sorted(points, key=f_y)
f_r = lambda x:x[0]**2+x[1]**2
sorted(points, key=f_r)
```
### 10. 装饰器
#### 10.1 函数作为返回值

```python
def lazy_sum(*args):
    def sum():
        ax = 0
        for n in args:
            ax = ax + n
        return ax
    return sum
f = lazy_sum(1, 3, 5, 7, 9)
f()

25
```
#### 10.2 闭包
python中的闭包从表现形式上定义（解释）为：如果在一个内部函数里，对在外部作用域（但不是在全局作用域）的变量进行引用，那么内部函数就被认为是闭包(closure).

```python
def create_pointer(my_string):
    def pointer(n):
        return my_string[n]
    return pointer
pointer = create_pointer('my name is Molly')
pointer(5)

'm'
```

#### 10.3 装饰器

```python
# 装饰器输入一个函数，输出一个函数
def print_working(func):
    def wrapper():
        print(f'{func.__name__} is working...')
        func()
    return wrapper
```

```python
@print_working
def worker1():
    print('我是一个勤劳的工作者！')

@print_working
def worker2():
    print('我是一个勤劳的工作者！')
worker1()
worker2()
```

```python
def arg_decorator(func):
    def wrapper(*args, **kw):
        print(f'{func.__name__} is working...')
        func(*args, **kw)
    return wrapper
# 带参数的装饰器
@arg_decorator
def student_info(name, age=18, *books, **kw):
    print(f'我的名字叫{name}, 今年{age}岁，我有很多本书：')
    for book in books:
        print(book)
    print(kw)
student_info('Molly',18, '语文书','数学书',height=170)
```
10.4 偏函数
通过设定参数的默认值，降低函数调用的难度

```python
def student_info(name, age, city='北京'):
    print(f'我的名字叫{name}, 今年{age}岁，来自{city}')
student_info('Molly',18)

我的名字叫Molly, 今年18岁，来自北京
#可通过partial修改默认值
from functools import partial
def student_info(name, age, city):
    print(f'我的名字叫{name}, 今年{age}岁，来自{city}')
student_info_beijing = partial(student_info, city='北京')
student_info_beijing('Molly',18)

我的名字叫Molly, 今年18岁，来自北京
```
##  面向对象
### 1. 类
#### 1.1 如何定义类
- 第一部分：class定义类的关键字，Athlete符合python标识符命名规则，：表示类内容的开始
- 第二部分：def定义函数的关键字，init 方法是一个特殊方法会在实例化对象时自动调用，我们会在这个方法中对数据进行赋值。self作为类中函数的第一个参数，方便该方法调用该类的其他属性和方法。
- 第三部分：自定义的属性和方法

```python
class Athlete:
    def __init__(self,a_name,a_dob=None,a_times=[]):
        self.name = a_name
        self.dob = a_dob
        self.times = a_times

    def top3(self):
        return sorted(set([self.sanitize(t) for t in self.times]))[0:3]
        
    def sanitize(self,time_string):
        if '-' in time_string:
            splitter = '-'
        elif ':' in time_string:
            splitter = ':'
        else:
            return (time_string)
        (mins,secs) = time_string.split(splitter)
        return (mins+'.'+secs)
```

##### 1.2 如何使用类
1. 创建对象

	对象名 = 类名(参数)

2. 使用.调用类的方法和属性

	对象.属性名

	对象.方法名()
	

```python
james = Athlete(james_name,james_dob,james_times)
print('姓名：%s,生日：%s,最快的3次成绩：%s' %(james.name,james.dob,james.top3()))
```

> 类属性：所有对象共享的数据
	定义：在 init 之上，或者说在类的范围内与方法同等级别，书写变量名=值
	调用：类名.类属性

> 类方法
> 定义：方法定义时，使用@classmethod标记
> 调用：
类名.类方法
对象.类方法

**私用的属性和方法的定义：**

在属性和方法名前加 __ 两个下划线
只能通过类中的方法来调用私有的属性和方法
##### 1.3 父类调用
- class 子类名(父类名)：
情况1，如果子类有新增的属性，那么需要在子类__init方法中，调用父类的__init__
情况2，如果子类没有新增的属性,子类不需要写__init__方法

```python
class Rugby(Athlete):
    def __init__(self,a_name,a_bod,a_squat,a_times):
        Athlete.__init__(self,a_name,a_bod,a_times)
        self.squat = a_squat
    def top3(self):
        return sorted([self.sanitize(t) for t in self.times])[-3:]
```
##### 1.4 多态
```python
def print_rugby(athlete):
   print(athlete.name)
   print(athlete.dob)
   print(athlete.squat)
   print(athlete.top3())
print_rugby(loren)
print_rugby(mark)
```
##### 1.5 多继承

```python
class Father(): 
   def talk(self):
       print("---爸爸的表达能力---")
class Mather():
   def smart(self):
       print("---妈妈聪明的头脑---")
class Child(Father,Mather):
   pass
child1 = Child()
child1.talk()
child1.smart()

---爸爸的表达能力---
---妈妈聪明的头脑---
```
### 2. 面向对象
代码通常称为类的方法，数据通常称为类的属性，实例化的对象称为实例
### 

## 文件操作
### 1. 打开文件

```python
with open('work/train_data_cor.txt') as f:
```
### 2. 文件内问题处理

```python
try:
   print('姓名：'+data.pop(0)+'生日：'+data.pop(0)+'时间：'+str(data))
except:
   pass
```
### 3. 文件处理函数
#### 3.1 f.read()
读取文件
#### 3.2 f.seek()
改变文件当前位置
#### 3.3 f.tell()
读取位置
#### 3.4 f.write() 
写入文件

## 进程线程
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210210125828410.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzODI4MzMy,size_16,color_FFFFFF,t_70)

```python
#只使用进程的方式
print('压缩作业开始了，请您耐心等待...')
infile = 'work/loren.txt'
outfile = 'work/myarchive.zip'
f = zipfile.ZipFile(outfile, 'w', zipfile.ZIP_DEFLATED)
f.write(infile)
f.close()
print('压缩作业结束了，请问还需要帮您做什么呢？')
```

```python
#使用进程+线程的方式
import threading, zipfile

class AsyncZip(threading.Thread):
    def __init__(self, infile, outfile):
        threading.Thread.__init__(self)
        self.infile = infile
        self.outfile = outfile

    def run(self):
        f = zipfile.ZipFile(self.outfile, 'w', zipfile.ZIP_DEFLATED)
        f.write(self.infile)
        f.close()
        print('压缩完成，您要的文件在:', self.outfile)

background = AsyncZip('work/loren.txt', 'work/myarchive.zip')

print('压缩作业开始了，请您耐心等待...')
background.start()
print('我正在为您压缩，请问还需要帮您做什么呢？')
background.join()
```

