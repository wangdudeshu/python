### 小白Python笔记- Python 变量与数据类型

​    在Python中，标准的数据类型可以分为如下几种：字符串、数字、列表与元组与字典。本文将会对对应的数据类型进行简单的介绍

#### 1.1 数字

##### 1.1.1 数字的赋值

​    Python数字数据类型用于存储数值。其中包括整型(Int)，浮点型(float)，复数(complex)。(基于Python3中，Int类型可以充当Long类型使用)

​    关于数字的数据类型的相关实例如下：

```python
#int 类型
int_example = 6
print(type(int_example))

#float类型
float_example = 5.1
print(type(float_example))

#complex 类型
complex_example = 1+2j
complex_example_2 = complex(1, 2)
print(type(complex_example))
print(complex_example == complex_example_2)

'''
outputs:
<class 'int'>
<class 'float'>
<class 'complex'>
True
'''
```

####  1.2 字符串

##### 1.2.1 字符串的赋值

​     字符串即使一系列字符，在Python中，用引号扩起来的内容即是字符串。可以是单引号也可以是双引号。

```python
string1 = 'wangdudeshu'
string2 = "wangdudeshu"
print(string1 == string2)
"""
outputs:
True
"""
```

##### 1.2.2 字符串的访问与修改

​    字符串可以通过索引来访问字符串元素：

```python
#下标访问字符串元素
string1 = 'wangdudeshu'
print('string1的第一个字母是：',  string1[0])
print('string1的前两个字母是：'， string[0:2])

'''
outputs:
string1的第一个字母是： w
string1的第一个字母是： wa
'''
```

​    但字符串不可以通过访问下标的方式对字符串的相关内容进行修改：

```python
string1 = 'wangdudeshu'
string1[2] = 'c'
print(string1)
'''
outputs:
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object does not support item assignment
'''
```

​    可以使用字符串的切片功能来对字符串进行重新赋值达到修改某个字符串元素的目的。

```python
string1 = 'wangdudeshu'
string1 = string1[:2] + 'c' + string1[3:]
print(string1)
'''
outputs:
'wacgdudeshu'
'''
```

##### 1.2.3 字符串的复制与拼接

​    字符串的常用操作包括了字符串的复制以及不同字符串的拼接。

​    字符串的复制通过对字符串变量进行乘法得到对应的复制后的字符串。

​    对于两个字符串，可以通过'+'实现对字符串的简单拼接。

```python
string1 = '忘读的书'
string2 = string1 * 3

print('复制后的字符串为', string2)
print('\n')

string3 = '求关注!!'
string4 = string1 + string3
print('拼接后的字符串为：', string4)
'''
outputs:
复制后的字符串为 忘读的书忘读的书忘读的书

拼接后的字符串为： 忘读的书求关注
'''
```

#### 1.3 列表

##### 1.3.1 列表的赋值

​    列表由一系列按照特定顺序排列的元素组成。可以存放相同的数据类型也可以存放不同的数据类型。

​     在Python中，用方括号（[]）来表示列表，用逗号分隔其中的元素。除此之外，可以使用内置函数list()对列表进行定义。

​    相关列表定义的实例如下：

```python
list1 = [1,2,3]
print(list1)

list2 = list((1,2,3))
print(list2)

list3 = [1, '2', 3.0]
print(list3)

'''
outputs:
[1, 2, 3]
[1, 2, 3]
[1, '2', 3.0]
'''
```

##### 1.3.2 列表的访问与修改

​    在列表中，列表的索引由0开始。列表可以通过索引对列表中的某个元素进行访问，也可通过列表中的索引对列表中的值进行修改。    

```python
list1 = [1,2,3]
print('第一个元素是：', list1[0])

print('修改之前的列表值为：', list1)
list1[2] = 4
print('修改后的列表值为: ', list1)

'''
outputs:
第一个元素是： 1
修改之前的列表值为： [1, 2, 3]
修改后的列表值为:  [1, 2, 4]
'''
```

##### 1.3.3 列表元素的添加与删除

​    在实际使用中，常需要对列表进行添加与删除的操作。

​    其中，添加元素常用的函数为append()与insert()。append()函数仅会在列表的末尾进行元素的添加。insert()函数可以指定位置对列表进行元素的添加。

​    而删除元素的操作包括了del(), pop(),remove()。当知道要删除的元素在列表中的位置时，使用del语句。pop()函数可以删除末尾的元素也能删除置顶位置的元素。remove()根据值对列表进行元素的删除。

```python
#append添加元素
list1 = [1,2,3]
print('append 添加元素示例：')
print('添加元素之前的列表值为：', list1)
list1.append(4)
print('添加元素之后的列表值为：'， list1)

#insert 添加元素
list1 = [1,2,3]
print('insert 添加元素示例：')
print('添加元素之前的列表值为：', list1)
list1.insert(3, 4)
print('添加元素之后的列表值为：', list1)

#del 删除
list1 = [1,2,3]

print('del 删除示例：')
print('删除之前的列表值为：', list1)
del list1[0]
print('删除之后的列表值为：', list1)

#pop删除
list1 = [1,2,3]
print('第一种pop删除示例：')
print('删除之前的列表值为：', list1)
pop_num = list1.pop()
print('被删除的元素为：', pop_num)
print('删除之后的列表值为：', list1)

#根据位置使用pop删除
list1 = [1,2,3]
print('第二种pop删除示例：')
print('删除之前的列表值为：', list1)
pop_num = list1.pop(0)
print('被删除的元素为：', pop_num)
print('删除之后的列表值为：', list1)

#根据remove删除元素
list1 = [1,2,3]
print('remove删除示例：')
print('删除之前的列表值为：', list1)
list1.remove(1)
print('删除之后的列表值为：', list1)

'''
outputs:
append 添加元素示例：
添加元素之前的列表值为： [1, 2, 3]
添加元素之后的列表值为： [1, 2, 3, 4]

print('insert 添加元素示例：')
添加元素之前的列表值为： [1, 2, 3]
添加元素之后的列表值为： [1, 2, 3, 4]

del 删除示例：
删除之前的列表值为： [1, 2, 3]
删除之后的列表值为： [2, 3]

第一种pop删除示例：
删除之前的列表值为： [1, 2, 3]
被删除的元素为： 3
删除之后的列表值为： [1, 2]

第一种pop删除示例：
删除之前的列表值为： [1, 2, 3]
被删除的元素为： 1
删除之后的列表值为： [2, 3]

remove删除示例：
删除之前的列表值为： [1, 2, 3]
被删除的元素为： 1
删除之后的列表值为： [2, 3]
'''
```

##### 1.3.4 列表的复制与拼接

​    列表与字符串类似，与数字的乘法可以实现简单的列表的复制，通过加法（+）可以实现对列表的拼接

```python
list1 = [1,2,3]
print('列表的复制：')
print('复制前的列表：', list1)
print('复制后的列表: ', list1*3)

print('列表的拼接：')
list1 = [1,2,3]
print('第一个列表的值为： ', list1)
list2 = [1, 2.5, 'bob']
print('第二个列表的值为： ', list2)
print('拼接后的结果为：', list1 + list2)

'''
列表的复制：
复制前的列表： [1, 2, 3]
复制后的列表:  [1, 2, 3, 1, 2, 3, 1, 2, 3]

列表的拼接：
第一个列表的值为：  [1, 2, 3]
第二个列表的值为：  [1, 2.5, 'bob']
拼接后的结果为： [1, 2, 3, 1, 2.5, 'bob']
'''
```

##### 1.3.5 列表的遍历

​    在实际使用时，一些操作需要遍历列表中的所有元素。对列表的遍历，常用的有如下的三种方法：（1） 通过索引对列表的元素进行遍历 （2）通过对元素进行遍历（3）通过enumerate()函数进行列表的遍历，相关示例如下：

```python
list1 = ['Python', '是', '最好的', '语言']
#通过索引进行遍历
for i in range(len(list1)):
  print(list1[i])

#通过元素进行遍历
list2 = ['不服', '你', '来', '打我呀']
for char in list2:
  print(char)
  
#通过enumerate()遍历
list3 = ['这', '是', '个', '正经', '公众号']
for i, char in enumerate(list3):
  print(i, char)
```

#### 1.4 元组

​    列表时可修改的，但在某些情况，希望创建一系列不可修改的元素。即可用刀元组。在Python中，元组的定义由圆括号来表示，也可以与列表一样通过索引访问元素，但不可以通过索引改变元组的内容。

```python
tuple1 = (1, 2, 3)
tuple2 = 1, 2, 3     #不要括号之后可以直接赋值，默认是一个tuple
tuple3 = tuple([1,2,3])

print(type(tuple1) == type(tuple2))
print(tuple1 == tuple3)
'''
outputs:
True
True
'''
```

   虽然元组的元素不可以被修改，但元组内如果存在于列表这样可修改元素的数据类型，则该元组中的列表的数据时可以被修改的：

```python
tuple1 = (1, 2, 3)
print('示例1:')
try:
  tuple1[0] = 10
except:
  print("tuple的元素不能修改")

tuple2 = ([1,2,3], 'a', 'b')
print('示例2:')
try:
    tuple2[0][0] = 'wangdudeshu'
    print(tuple4[0])
except:
    print("tuple的元素不能修改")
    
'''
outputs:
tuple的元素不能修改
['wangdudeshu', 2, 3]
'''
```

#### 1.5 字典

##### 1.5.1 字典的赋值

​    字典在Python中指的是**键-值**，由键值反映变量之间的关系。

​    我们可通过键来访问其相关联的值，字典中的键，可以使用数字，字符串，元组的数据类型（列表不可以），而字典中的值可以是数字、字符串、列表、元组、字典。

​    在Python中，字典的定义用花括号('{}')表示，键值之间用冒号(':')连接，相关示例如下：

```python
dict1 = {1:'a', 2:'b'}
dict2 = {'a':1, 'b':2}
dict3 = {(1,):"wang", (2,):"du", (3,):"de", (4,):"shu"}
print('第一个字典的值是: ', dict1)
print('第二个字典的值是: ', dict2)
print('第三个字典的值是: ', dict3)
'''
outputs:
第一个字典的值是:  {1: 'a', 2: 'b'}
第二个字典的值是:  {'a': 1, 'b': 2}
第三个字典的值是:  {(1,): 'wang', (2,): 'du', (3,): 'de', (4,): 'shu'}
'''
```

##### 1.5.2 访问字典的元素

​    若想获取字典中与键关联的值，可将指定的键值放入方括号内放于字典之后，即可以访问对应的字典的值。也可以使用内置函数dict.get()来获取对应的相应的示例如下：

```python
dict1 = {1:'a', 2:'b'}
dict2 = {'a':1, 'b':2}
dict3 = {(1,):"wang", (2,):"du", (3,):"de", (4,):"shu"}
dict4 = {'求': 'qiu', '关': "guanzhu", '注':'zhu'}

print("第一个字典与'1'对应的值为", dict1[1])
print("第二个字典与'b'对应的值为", dict2['b'])
print("第三个字典与'(1,)'对应的值为", dict3[(1,)])
print("第四个字典与'求'对应的值为'", dict4.get('求', 0))
'''
outputs:
第一个字典的与'1'对应的值为 a
第二个字典的与'b'对应的值为 2
第三个字典的与'(1,)'对应的值为 wang
第四个字典与'求'对应的值为' qiu
'''
```

##### 1.5.3 字典元素的遍历

​    对字典遍历有着三个重要的方法，分别为keys(), values(),items()，可通过与for循环结合，完成对字典元素的遍历。

​    当不使用到字典的值时，可以使用keys()，取出字典中所有的键，再进行遍历。

​    同样，当不使用字典中的键时，使用values()，取出字典中的值，进行遍历。

​    当同时需要使用到字典中的键-值对时，可以使用items()，对字典中的键值对进行遍历。

```python
dict1 = {'忘':'求', '读':'关', '的':'注', '书':'！'}

for key in dict1.keys():
  print(key)
for value in dict1.values():
  print(value)

dict2 = {'真':'的', '不':'关', '注':'一', '下':'吗'}
for k,v in dict2.items():
  print(k)
  print(v)
'''
outputs:
忘
读
的
书
求
关
注
！
真
的
不
关
注
一
下
吗
'''
```

