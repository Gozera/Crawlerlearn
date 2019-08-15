# 语法
- 正则表达式用于描述字符串匹配的模式，检查子串是否相符，替换子串以及取出匹配的子串。
- 例子1: runoo+b +号表示前面的字符('o')至少出现1次或多次.使用runoob,runooob,runooooob均符合
- 例子2: runoo*b *号表示前面的字符至少出现0或多次，比上面多了runob
- 例子3: colou?r ?号表示前面的字符出现0或1次，即匹配color与colour
## python3的正则表达式
- [具体教程](https://www.runoob.com/python3/python3-reg-expressions.html)
- 采用re模块使python拥有所有的正则表达式功能。
- re.match(pattern,string,flags=0)，其中pattern为正则表达式，string为要匹配的字符串，flags为标志位（参考可选标志），表示从起始位置匹配一个模式，不是则返回none
- re.seach(......)表示匹配整个字符串
- re.match只匹配字符串的开始，如果字符串开始不符合正则表达式，则匹配失败，函数返回None；而re.search匹配整个字符串，直到找到一个匹配。
- - 看到findall
- 在字符串中找到正则表达式所匹配的所有子串，并返回一个列表，如果没有找到匹配的，则返回空列表。
