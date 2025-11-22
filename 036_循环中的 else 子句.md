### 循环中的 else 子句

循环中的 `else` 子句常用于配合 `break` 使用，它只会在循环**正常执行完毕**时运行，而不会在循环因 `break` 提前退出时运行。这一机制常被用来处理“循环是否完整执行”的逻辑，例如搜索中找到目标时 `break`，未找到目标时执行 `else`。

```python
for i in range(10, 1, -1):
    print(i)
    if i == 5:
        break
else:
    print("loop finished successfully")	# 此句不会执行，因为在i==5的时候循环终止了
```

## 函数
