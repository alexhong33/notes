# Python字典(dict)内置函数&方法

[Python 直接赋值、浅拷贝和深度拷贝解析](http://www.runoob.com/w3cnote/python-understanding-dict-copy-shallow-or-deep.html)


## 字典特性
##### 关于键
* 不允许同一个键出现两次．　创建时如果同一个键被赋值两次，　后一个值会被记住．
* 键必须不可变，　所以可以用数字，字符串或元组充当．不可用列表

##### 关于值
* 字典值可以没有限制地取任何python对象, 既可以是标准的对象, 也可以是用户定义的.


## 内置函数

* len(dict) 计算字典元素个数, 即键的总数
* str(dict) 输出字典, 以可打印的字符串表示
* type(dict) 返回输入的变量类型, 如果变量是字典就返回字典类型


## 内置方法

#### 组1
1. dict.clear() 删除字典内所有元素
2. dict.copy() 返回一个字典的浅复制
3. dict.fromkeys(seq[, value]) 创建一个新字典, 以序列seq中元素做字典的键, value为字典 所有键 对应的初始值
4. dict.get(key, default=None) 返回指点键的值, 如果值不在字典中返回default值
5. key in dict 如果键在字典dict里返回true, 否则返回false


#### 组2
1. dict.items() 以列表返回可遍历的(键,值)元组数组
2. dict.keys() 以列表返回一个字典所有的键
3. dict.setdefault(key, default=None) 与get()方法类似, 如果键不存在与字典中, 将会添加键并将值设为默认值
4. dict.update(dict2) 将dict2的键值对更新到dict中
5. dict.values() 


#### 组3
1. dict.pop(key[, default]) 删除字典给定键key所对应的值, 返回值为被删除的值. 
2. dict.popitem() 随机返回并删除字典中的一对键和值. 如果字典已经为空, 却调用了此方法, 报出KeyError异常

