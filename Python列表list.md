# Python 列表 (Sequence Type - list)

There are three basic sequence types: lists, tuples, and range objects. Additional sequence types tailored for processing of binary data and text strings are described in dedicated sections.

[3.6官方文档](https://docs.python.org/3/library/stdtypes.html#sequence-types-list-tuple-range)  

[中文参考](http://www.runoob.com/python3/python3-list.html)

# 列表操作符

* len(list) 长度
* + 组合
* * 重复
* in 元素是否存在于列表中
* for x in list: 迭代
* list[1] list[-1]选取元素
* list[1:] 切片

# Python列表函数 &　方法

### 内建函数

1. len(list) 返回 列表元素个数
2. max(list) 返回 列表元素最大值
3. min(list) 返回 列表元素最小值
4. list(seq) 返回 元祖转换为列表


### 内建方法
1. list.append(obj) 在列表末尾添加新的对象
2. list.count(obj) 统计某个元素在列表中出现的次数
3. list.extend(seq) 在列表末尾一次性追加另一个序列中的多个值
4. list.index(obj) 从列表中找到某个值第一个匹配项的索引位置
5. list.insert(index, obj) 将对象插入列表
6. list.pop(obj=list[-1]) 移除列表中的一个元素(默认最后一个元素,并且返回该元素的值)
7. list.remove(obj) 移除列表中某个值的第一个匹配项
8. list.reverse() 反向列表中元素
9. list.sort() 对原列表进行排序
10. list.clear() 清空列表
11. list.copy() 复制列表

