### While循环

#### 基本形式

```python
while 判断条件(condition)：
    执行语句(statements)……
```

#### 流程

`while` 循环被称为 **前测试循环 (pretest loop)**：

- 在执行迭代之前先测试条件。
- 如果一开始条件为 `False`，循环将不会执行

当循环开始后，如果想让循环停止执行，必须在循环体中让条件变为 **False**。

![img](https://www.runoob.com/wp-content/uploads/2013/11/886A6E10-58F1-4A9B-8640-02DBEFF0EF9A.jpg)
#### 示例
```python
count = 0
while (count < 9):
   print 'The count is:', count
   count = count + 1
 
print "Good bye!"
"""
执行结果：
The count is: 0
The count is: 1
The count is: 2
The count is: 3
The count is: 4
The count is: 5
The count is: 6
The count is: 7
The count is: 8
Good bye!
"""
```

##### 无限循环（Infinite Loops）

- **循环必须包含终止方式**
  - 在 `while` 循环中，循环体内必须有代码能最终使条件为 **False**。
- **Infinite loop（无限循环）**：没有停止条件的循环
  - 循环会一直执行，直到程序被手动中断。
  - 常见原因：程序员忘记在循环体中写入终止条件的更新语句。

```python
var = 1
while var == 1 :  # 该条件永远为true，循环将无限执行下去
   num = raw_input("Enter a number  :")
   print "You entered: ", num
 
print "Good bye!"	# 永远不可达
```

#### While循环作为计数器

`while` 循环本质上是**条件控制循环**只要布尔条件为 **True**，就会重复执行。也可以通过 **计数器变量（counter variable）** 来控制循环次数将 `while` 循环作为**计数控制循环**

**计数器变量的特点：**

- 在每次迭代时被赋予一个新的唯一值。
- 通过计数器变量可以统计循环执行的次数。

要实现将while循环作为计数循环需要完成**以下三个步骤**：

- **Initialization**
  在循环开始前，计数器变量必须被初始化为一个合适的起始值。

- **Comparison**
  循环必须将计数器变量与一个合适的结束值进行比较，以决定循环是否继续执行。
- **Update**
  在每次迭代中，循环必须更新计数器变量为一个新值。

<img src="C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20250920155843499.png" alt="image-20250920155843499" style="zoom:50%;" />
