# Python的字符串内建函数

[参考](http://www.runoob.com/python3/python3-string.html)

### 字母排序

#### 组1
1. capitalize()
2. center(width, fillchar)
3. count(str, begin=0, end=len(string))
4. bytes.decode(encoding="utf-8", errors="strict")
5. encode(encoding='UTF-8', errors='strict')


#### 组2
1. endswith(suffix, begin=0, end=len(string))
2. expandtabs(tabsize=8)
3. find(str, begin=0, end=len(string))
4. index(str, begin=0, end=len(string))
5. isalnum()


#### 组3
1. isalpha()
2. isdigit()
3. islower()
4. isnumeric()
5. isspace()


#### 组4
1. istitle()
2. isupper()
3. join(seq)
4. len(string)
5. ljust(width[, fillchar])


#### 组5
1. lower()
2. lstrip()
3. maketrans()
4. max(str)
5. min(str)


#### 组6
1. replace(old, new[, max])
2. rfind(str, begin=0, end=len(string))
3. rindex(str, begin=0, end=len(string))
4. rjust(width[, fillchar])
5. rstrip()


#### 组7
1. split(str="", num=string.count(str))
2. splitlines([keepends])
3. startswith(str, begin=0, end=len(string))
4. strip([chars])
5. swapcase()


#### 组8
1. title()
2. translate(table, deletechars="")
3. upper()
4. zfill(width)
5. isdecimal()

---------------------------------------------------------

### 功能排序

#### 判断

1. isalnum()
2. isalpha()
3. isdigit()
4. islower()
5. isnumeric()
6. isspace()
7. istitle()
8. isupper()
9. isdecimal()


#### 编码
1. bytes.decode(encoding="utf-8", errors="strict")
2. encode(encoding='UTF-8', errors='strict')

#### 移除字符
1. split(str="", num=string.count(str))
2. strip([chars])
3. rstrip()
4. lstrip()
5. splitlines([keepends])


#### 大小写切换
1. capitalize()
2. lower()
3. upper()
4. swapcase()
5. title()

#### 组合生成字符串
1. join(seq)


#### 更替
1. maketrans()
2. replace(old, new[, max])
3. expandtabs(tabsize=8)
4. translate(table, deletechars="")


#### 字符填充
1. center(width, fillchar)
2. ljust(width[, fillchar])
3. rjust(width[, fillchar])
4. zfill(width)


#### 检索字符串
1. count(str, begin=0, end=len(string))
2. endswith(suffix, begin=0, end=len(string))
3. find(str, begin=0, end=len(string))
4. index(str, begin=0, end=len(string))
5. rfind(str, begin=0, end=len(string))
6. rindex(str, begin=0, end=len(string))
7. len(string)
8. max(str)
9. min(str)
10. startswith(str, begin=0, end=len(string))
