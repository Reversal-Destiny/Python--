### 嵌套循环(Nested Loop)

#### 简介

一个循环体里面嵌入另一个循环的形式被称作嵌套循环，**内层循环会在外层循环的每一次迭代中完整执行所有循环次数**，因此内层循环的执行速度通常比外层快。嵌套循环的总迭代次数等于**内层循环迭代次数 × 外层循环迭代次数**。这种结构常用于处理二维数据（如矩阵或表格）或需要多层遍历的场景。

#### 语法

##### for嵌套

```python
for iterating_var in sequence:
   for iterating_var in sequence:
      statements(s)
   statements(s)
```

##### while嵌套

```python
while expression:
   while expression:
      statement(s)
   statement(s)
```

#### 示例

```python
i = 2
while(i < 100):
   j = 2
   while(j <= (i/j)):
      if not(i%j): break
      j = j + 1
   if (j > i/j) : print i, " 是素数"
   i = i + 1
 
print "Good bye!"
"""
执行结果：
2 是素数
3 是素数
5 是素数
7 是素数
11 是素数
13 是素数
17 是素数
19 是素数
23 是素数
29 是素数
31 是素数
37 是素数
41 是素数
43 是素数
47 是素数
53 是素数
59 是素数
61 是素数
67 是素数
71 是素数
73 是素数
79 是素数
83 是素数
89 是素数
97 是素数
Good bye!
"""
```
