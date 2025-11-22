### 使用turtle库

#### 导入

在使用turtle库之前，你需要先通过如下语句导入turtle库：

```python
import turtle
```
#### 前进
你可以通过`forward`语句让海龟前进：
```python
import turtle
turtle.forward(100)	# 向前移动100步
```

<img src="C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20250920121617989.png" alt="image-20250920121617989" style="zoom:50%;" />

#### 旋转

海龟的默认方向朝东(0°)。 你可以通过`left`(逆时针和`right`(顺时针)改变海龟的方向：

```python
import turtle
turtle.forward(100)
turtle.left(90)	# 向左旋转90度
turtle.forward(100)
turtle.right(90)	# 向右旋转90度(回到原本的零度)
turtle.forward(100)
```



<img src="C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20250920121853681.png" alt="image-20250920121853681" style="zoom:40%;" />

#### 画笔抬起与落下

你可以使用`penup`抬起画笔，抬起画笔后海龟在运动过程中就不会留下痕迹，你也可以使用`pendown`让抬起的画笔重新落下

```python
import turtle
turtle.forward(50)
turtle.penup()	# 抬起
turtle.forward(25)
turtle.pendown()	# 落下
turtle.forward(50)
turtle.penup()	# 抬起
turtle.forward(25)
turtle.pendown()	# 落下
turtle.forward(50)
# 可以使用turtle.isdown()检测是否落下，但只能使用not turtle.isdown()检测是否抬起
```

<img src="C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20250920122349590.png" alt="image-20250920122349590" style="zoom:50%;" />

#### 画圆

你可以直接通过`circle(radius)`语句绘制半径为`radius`的圆形

```python
import turtle
turtle.circle(100)	# 绘制一个半径为100的圆
```



<img src="C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20250920122338700.png" alt="image-20250920122338700" style="zoom:50%;" />

#### 点

你可以使用`dot()`语句绘制点：

```python
import turtle
turtle.dot()
turtle.forward(50)
turtle.dot()
turtle.forward(50)
turtle.dot()
turtle.forward(50)
```

<img src="C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20250920122534488.png" alt="image-20250920122534488" style="zoom:50%;" />

#### 画笔属性

你可以使用`pensize(width)`改变画笔粗细，使用`pencolor(color)`改变画笔颜色

```python
import turtle
turtle.pensize(5)
# 使用turtle.pensize()可以检测当前笔大小
turtle.pencolor('red')
# turtle.pencolor() 会返回当前笔的颜色
turtle.circle(100)
```

<img src="C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20250920122651735.png" alt="image-20250920122651735" style="zoom:50%;" />

#### 操作 Turtle 窗口

你可以使用 `bgcolor(color)` 设置窗口背景色。  

```python
import turtle
turtle.bgcolor('lightblue')
```

#### 重置 Turtle 窗口

你可以使用`reset()`语句来清除绘图或重置窗口：

- 清除当前窗口中的所有绘图
- 将画笔颜色重置为黑色
- 将海龟重置到屏幕中心的初始位置
- **不会**重置窗口背景色

```python
import turtle
turtle.reset()
```

#### 将 Turtle 移动到指定位置

你可以使用 `goto(x, y)` 将海龟移动到指定坐标位置。

```python
import turtle
turtle.goto(0, 100)
turtle.goto(-100, 0)
turtle.goto(0, 0)
```

<img src="C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20250920123017258.png" alt="image-20250920123017258" style="zoom:50%;" />

运行效果：海龟会依次移动到 (0,100)、(-100,0)、(0,0)，形成一个三角形路径。

除了移动，还可以获取当前坐标：

- `turtle.pos()`：显示当前海龟的 **(X, Y) 坐标**
- `turtle.xcor()`：显示当前海龟的 **X 坐标**
- `turtle.ycor()`：显示当前海龟的 **Y 坐标**

#### 动画速度

你可以使用 `speed(speed)` 来设置海龟移动的速度。

- 参数 `speed` 的取值范围是 **0 ~ 10**
- 如果设为 `0`，海龟会立即完成所有移动（动画被禁用）

```python
import turtle

turtle.speed(1)   # 最慢速度
turtle.forward(100)

turtle.speed(10)  # 最快速度
turtle.forward(100)

turtle.speed(0)   # 立即完成（无动画）
turtle.forward(100)
```

#### 隐藏与显示 Turtle

你可以使用`hideturtle()`语句来隐藏，`showturtle()`显示海龟光标：

- 隐藏海龟图标
- 不会影响图形的绘制，仅仅是隐藏光标

```python
import turtle

turtle.forward(100)
turtle.hideturtle()   # 隐藏海龟
turtle.showturtle()	# 显示海龟
```

#### 显示文本

你可以使用 `write(text)` 在 Turtle 窗口中显示文本。

- 参数 `text` 是需要显示的字符串
- 文本的左下角会出现在海龟的 **X、Y 坐标** 位置

```python
import turtle
turtle.write("Hello, World!") 
```

<img src="C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20250920123444172.png" alt="image-20250920123444172" style="zoom:50%;" />

#### 填充图形

要用颜色填充图形，可以按以下步骤操作：

1. 在绘制图形之前，使用 `turtle.begin_fill()`
2. 绘制图形
3. 绘制完成后，使用 `turtle.end_fill()`
4. 当执行到 `turtle.end_fill()` 时，图形会被当前的填充颜色填充

```python
import turtle

turtle.fillcolor('red')   # 设置填充颜色
# turtle.fillcolor() 会返回当前填充色
turtle.begin_fill()       # 开始填充
turtle.circle(100)        # 绘制一个圆
turtle.end_fill()         # 结束填充
```

<img src="C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20250920123543363.png" alt="image-20250920123543363" style="zoom:50%;" />

#### 使用对话框获取输入
你可以使用对话框函数`numinput()`来获取用户输入。
  ```python
  import turtle
  age = turtle.numinput('Input', 'Enter your age')
  ```

<img src="C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20250920123729120.png" alt="image-20250920123729120" style="zoom:50%;" />

##### 指定范围

你可以在 `numinput()` 中指定 **默认值、最小值和最大值**。

```python
import turtle

num = turtle.numinput('Input', 'Enter a number',
                      default=10, minval=0, maxval=100)
```

对话框会显示一个默认值 10，输入的值必须在 0 到 100 之间，如果输入小于 minval 或大于 maxval，会显示错误信息

<img src="C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20250920123900560.png" alt="image-20250920123900560" style="zoom:50%;" />

#### 保持图形窗口打开

在 **IDLE 之外** 运行 Turtle 图形程序时，程序结束后图形窗口会立即关闭。

为防止这种情况发生，可以在程序最后添加：

```python
turtle.done()
```

这样窗口就会一直保留直到用户主动关闭

## 条件语句
