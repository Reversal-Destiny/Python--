### matplotlib库

Matplotlib 是 Python 的绘图库，它能让使用者很轻松地将数据图形化，并且提供多样化的输出格式。Matplotlib 可以用来绘制各种静态，动态，交互式的图表。

#### 安装

由于`matplotlib​`库为第三方库，无法直接进行导入，因此我们需要在控制台使用`pip`指令安装

```bash
pip install matplotlib
```

#### 导入

在安装完成后我们通过如下代码将库引入

```python
import matplotlib
```

`matplotlib`包包含一个名为`pyplot`的模块，该模块是绘制各类图表的核心工具，使用前需导入。

```python
import matplotlib.pyplot as plt
```

#### 折线图

使用`plot`函数可创建折线图，该图表通过直线连接一系列点。

##### 折线图的坐标轴

折线图具有水平的 X 轴和垂直的 Y 轴。

##### 折线图的坐标点

图表中的每个点都位于 (X, Y) 坐标处。

##### 示例

```python
import matplotlib.pyplot as plt

# 定义X和Y坐标数据
x = [0, 1, 2, 3, 4]
y = [0, 3, 1, 5, 2]

# 绘制折线图
plt.plot(x, y)
# 显示图表
plt.show()
```

##### 坐标轴范围设置函数

可通过`xlim`函数设置 X 轴的上下限，通过`ylim`函数设置 Y 轴的上下限。

```python
plt.xlim(xmin=1, xmax=100)
plt.ylim(ymin=10, ymax=50)
```

上述代码会将 X 轴的范围设置为从 1 到 100，Y 轴的范围设置为从 10 到 50。

##### 刻度标签自定义函数

- 可通过`xticks`函数自定义 X 轴的刻度标签，通过`yticks`函数自定义 Y 轴的刻度标签。这两个函数均接受两个列表作为参数：
  - 第一个列表是刻度标记的位置。
  - 第二个列表是在指定位置显示的标签。

```python
import matplotlib.pyplot as plt

x = [0, 1, 2, 3, 4]
y = [0, 1, 2, 3, 4, 5]

# 自定义X轴和Y轴刻度标签
plt.xticks([0, 1, 2, 3, 4], ['2016', '2017', '2018', '2019', '2020'])
plt.yticks([0, 1, 2, 3, 4, 5], ['$0m', '$1m', '$2m', '$3m', '$4m', '$5m'])

# 绘制折线图（此处仅为演示刻度标签，实际绘图需补充数据）
plt.plot(x, [0, 1, 2, 3, 4])
plt.show()
```

#### 柱状图

使用`matplotlib.pyplot`模块中的`bar`函数可创建柱状图。该函数需要两个列表：

- 一个列表用于指定每个柱形左边缘的 X 坐标。
- 另一个列表用于指定每个柱形沿 Y 轴的高度。

```python
import matplotlib.pyplot as plt

# 柱形左边缘的X坐标
x = [0, 1, 2, 3, 4]
# 柱形的高度
heights = [5, 3, 7, 2, 6]

# 绘制柱状图
plt.bar(x, heights)
plt.show()
```

##### **柱状图柱形宽度的设置方法**

###### 柱形的默认宽度

柱状图中每个柱形在 X 轴上的默认宽度是 0.8。

###### 柱形宽度的自定义方法

可通过向`bar`函数传递第三个参数来修改柱形宽度。

###### 示例

```python
import matplotlib.pyplot as plt

# 柱形左边缘的X坐标
left_edges = [0, 10, 20, 30, 40]
# 柱形的高度
heights = [100, 200, 300, 400, 500]
# 自定义柱形宽度
bar_width = 5

# 绘制柱状图
plt.bar(left_edges, heights, bar_width)
plt.show()
```

##### **柱状图柱形颜色的设置方法**

###### 柱形颜色的设置参数

`bar`函数包含`color`参数，可用于修改柱形的颜色。

###### 颜色参数的取值要求

传递给该参数的参数是一个包含一系列颜色代码的元组。

###### 颜色代码对照表

| 颜色代码 | 对应颜色 |
| -------- | -------- |
| 'b'      | Blue     |
| 'g'      | Green    |
| 'r'      | Red      |
| 'c'      | Cyan     |
| 'm'      | Magenta  |
| 'y'      | Yellow   |
| 'k'      | Black    |
| 'w'      | White    |

###### 示例

```python
import matplotlib.pyplot as plt

left_edges = [0, 1, 2, 3, 4]
heights = [5, 3, 7, 2, 6]
# 自定义柱形颜色
colors = ('b', 'g', 'r', 'c', 'm')

plt.bar(left_edges, heights, color=colors)
plt.show()
```

##### **柱状图坐标轴标签与刻度标签的设置方法**

###### 坐标轴标签设置

- 使用`xlabel`函数为 X 轴添加标签。
- 使用`ylabel`函数为 Y 轴添加标签。

###### 坐标轴刻度标签设置

- 使用`xticks`函数自定义 X 轴的刻度标签。
- 使用`yticks`函数自定义 Y 轴的刻度标签。

###### 示例

```python
import matplotlib.pyplot as plt

left_edges = [0, 1, 2, 3, 4]
heights = [5, 3, 7, 2, 6]
x_labels = ['A', 'B', 'C', 'D', 'E']
y_tick_labels = ['0', '2', '4', '6', '8']

# 绘制柱状图
plt.bar(left_edges, heights)
# 设置坐标轴标签
plt.xlabel('Category')
plt.ylabel('Value')
# 设置坐标轴刻度标签
plt.xticks(left_edges, x_labels)
plt.yticks([0, 2, 4, 6, 8], y_tick_labels)
plt.show()
```

#### 饼图

使用`matplotlib.pyplot`模块中的`pie`函数可创建饼图。

##### `pie`函数的参数要求

调用该函数时，需传递一个数值列表作为参数：

- 列表中数值的总和将作为 “整体” 的取值。
- 列表中的每个元素将成为饼图的一个扇区。
- 扇区的大小代表该元素值占整体的百分比。

```python
import matplotlib.pyplot as plt

# 各部分的数值
sizes = [30, 20, 25, 15, 10]

# 绘制饼图
plt.pie(sizes)
plt.show()
```

##### **饼图扇区标签的设置方法**

`pie`函数包含`labels`参数，可用于为饼图的扇区显示标签。

###### 标签参数的取值要求

传递给该参数的是一个包含所需标签（字符串类型）的列表。

###### 示例

```python
import matplotlib.pyplot as plt

sizes = [30, 20, 25, 15, 10]
# 扇区标签列表
labels = ['A', 'B', 'C', 'D', 'E']

plt.pie(sizes, labels=labels)
plt.show()
```

##### **饼图扇区颜色的设置方法**

`pie`函数会自动按以下顺序为扇区设置颜色：蓝色、绿色、红色、青色、品红、黄色、黑色、白色。可通过向`pie`函数的`colors`参数传递一个包含颜色代码的元组，来指定一组不同的颜色。

###### 示例

```python
import matplotlib.pyplot as plt

values = [30, 20, 25, 15, 10]
# 自定义扇区颜色
colors = ('r', 'g', 'b', 'w', 'k')

plt.pie(values, colors=colors)
plt.show()
```

上述代码执行后，饼图扇区的颜色将依次为红色、绿色、蓝色、白色、黑色。
