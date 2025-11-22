### 字符串比较 (Comparing Strings) 

- 字符串可以使用 `==` 和 `!=` 运算符进行比较  
- 字符串比较是 **区分大小写** 的  
- 字符串还可以使用 `>`, `<`, `>=`, `<=` 运算符进行比较  

#### 规则
- 比较时逐字符进行，依据每个字符的 **ASCII 值**  

  <img src="C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20250920125759640.png" alt="image-20250920125759640" style="zoom:30%;" />

- 如果短字符串是长字符串的子串，则长字符串大于短字符串  

#### 示例
```python
print("apple" == "apple")   # True
print("apple" != "Apple")   # True （大小写不同）
print("cat" > "car")        # True （因为 't' 的 ASCII 值大于 'r'）
print("dog" < "dogs")       # True （短字符串是长字符串的子串）
```
