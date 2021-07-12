# Study005

Python全栈学习Day04 – 0709
@[TOC](目录)
# 布尔类型
	python中True表示真，False表示假，它们是布尔类型。
	判断数据类型可以用之前学到的type()函数：
	type(True)      <class 'bool'>
	type(False)     <class 'bool'>
bool的True和False是数值1和0的字符串表示格式，实际上**bool类型是int类型的一个子类**
```
>>> bool.__bases__
(<class 'int'>,)
```
**因为True/False是数值1和0的另一种表示方式，它们可以直接参与数值运算。**
```
>>> True + 3
4
>>> False + 4 - 1
3
```
## True/False的各种形式
	1、整数值0、浮点数值0.0等、空字符串都为假
	2、None为假
	3、空数据对象都是假，比如[]、{}、()等
实例
```
 Type         True                 False
----------------------------------------------
number:   1、1.1               0、0.0
string:   'a'                  ''
None:                          None
list:     ['a']、[1]           []
       [0]、['']、[None]
Set/Dict: {'a'}                {}
tuple:    ('a')、(1)           ()、('')、(0)、(None)
```
## None
**None是一种特殊的数据对象，像数值1、字符串'a'一样，只不过内存中这个数据对象里面存储的数据是我们不得而知的，但它永远表示为False。**
```
>>> a = None
>>> b = None
>>> a is b
True
```

1、在Python中，没有显式定义return语句的函数、方法并不意味着没有返回值，它们的默认返回值是None。比如print()函数：

	>>> a=print("aa")
	aa
	>>> print(a)
	None
### None的技巧
访问或设置超出列表长度的元素时会报错：
但是可以**预先将某些数量的None对象填充到列表中去**，这样列表就具备了元素，尽管它们都是None对象。
# 逻辑运算：and、or、not
**python中只支持字符形式的and、or、not逻辑运算，不支持符号类型的&&、||、!**
## and
	X and Y：X和Y都为真时，返回真
## or
	X or Y：X或Y为真，返回真
## not
	not X：X真假取反
**[具体运算参考上一篇博客](https://blog.csdn.net/qq_41546720/article/details/118615156)**
# 空、非空测试的建议
经常会遇到要测试数据是否为空。这里的空可能是None、""、[]、{}、()中的一种，建议不要使用len() == 0去测试：
```
if len(x) == 0:
if not len(x) == 0:
```
而是直接将数据作为真、假值进行判断：
```
if x:
if not x:
```
这就是今天的学习内容。
[大佬博客地址](https://www.cnblogs.com/f-ck-need-u/p/10124444.html)