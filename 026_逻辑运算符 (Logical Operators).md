### 逻辑运算符 (Logical Operators)

逻辑运算符：用于创建复杂的布尔表达式。

- **`and` 运算符** 和 **`or` 运算符**
  - 二元运算符
  - 用于将两个布尔表达式连接成一个复合布尔表达式

- **`not` 运算符**
  - 一元运算符
  - 用于取反布尔值（True 变 False，False 变 True）

#### 示例
```python
x = 5
y = 10

print(x > 0 and y > 0)   # True （两个条件都为真）
print(x > 0 or y < 0)    # True （其中一个条件为真）
print(not(x > 0))        # False （取反）
```
