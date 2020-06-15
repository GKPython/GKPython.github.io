---
title: Tkinter组件位置
date: 2020-05-19 20:25:42
tags: 技术
---
#### 1.最小界面组成

```
# 导入tkinter模块
import tkinter
# 创建主窗口对象
root = tkinter.Tk()
# 设置窗口大小(最小值：像素)
root.minsize(300,300)
# 设置初始化界面大小
root.geometry('300x400')
# 创建一个按钮组件
btn = tkinter.Button(root,text = 'Hello World!')
btn.pack()
# 加入消息循环
root.mainloop()
```

#### 2.组件的摆放方式

1.pack()方式 ->方向/方位摆放方法

2.grid()方式 ->网格摆放方法

3.place()方式 ->定位摆放方法

<div align=center>

![](/img/PythonPos.png)

</div>

#### 3.布局介绍

**pack()方式**
side 设置组件相对于父组件的摆放位置


```
# 导入tkinter模块
import tkinter
# 创建主窗口对象
root = tkinter.Tk()
# 设置窗口大小(最小值：像素)
root.minsize(500,500)
# 创建一个按钮组件
btn0 = tkinter.Button(root,text = '按钮1')
# 默认上边或 side = 'top'
btn0.pack()
btn1 = tkinter.Button(root,text = '按钮1')
# 下面
btn1.pack(side = 'bottom')
btn2 = tkinter.Button(root,text = '按钮2')
# 左边
btn2.pack(side = 'left')
btn3 = tkinter.Button(root,text = '按钮2')
# 右边
btn3.pack(side = 'right')
# 加入消息循环
root.mainloop()
```

ipadx，ipady 设置组件的内部间距

```
btn0 = tkinter.Button(root,text = '按钮1')
# 设置按钮中文字到边缘的间距
btn0.pack(ipadx = 20,ipady = 20)
```

padx，pady 设置多个组件外部间距
	
```
btn0 = tkinter.Button(root,text = '按钮1')
# padx设置组件外部左右间距，pady设置组件外部上下间距
btn0.pack(padx = 20,pady = 20)
```

fill 设置按钮站一行或者一列

```
btn1 = tkinter.Button(root,text = 'Hello World！！')# 该组件站水平方向的最大位
```

expand 设置side是否失效

```
btn1 = tkinter.Button(root,text = 'Hello World！！')
# yes时side失效，按钮位于窗口中间，按钮占用所有水平和垂直的空间，此时fill = both 按钮站全部空间
btn1.pack(expand = 'yes',fill = 'both')
```

注意：仅仅使用pack无法实现表格方式，必须借助Franme组件才可以实现，非常复杂。

**grid()方式**
row　　设置行数 默认为0
column　　设置列数 默认为0

```
btn1 = tkinter.Button(root,text = '按钮1')
btn1.grid()
btn2 = tkinter.Button(root,text = '按钮2')
btn2.grid(row = 1,column = 1)# 设置按钮位置
btn3 = tkinter.Button(root,text = '按钮3')
btn3.grid(row = 0,column = 1)
```

rowspan　　设置跨行数量
cloumnspan　　设置跨列数量
ipadx，ipady　　设置组件内部间距

```
btn1 = tkinter.Button(root,text = '按钮1')
btn1.grid()
btn2 = tkinter.Button(root,text = '按钮2')
btn2.grid(row = 1,column = 0)# 设置按钮位置
btn2 = tkinter.Button(root,text = '按钮2')
btn2.grid(row = 0,column = 2,rowspan = 2,ipady = 15)
btn2 = tkinter.Button(root,text = '按钮2')
btn2.grid(row = 2,column = 0,columnspan = 3,ipadx = 20)
```

**place()方式**
绝对定位布局：
x　　设置距离左上角的水平长度　　   单位都是像素
y　　设置距离左上角的垂直高度　　   单位都是像素
width　设置组件所占据的宽度　　     单位都是像素
height　　设置组件所占据的高度　　  单位都是像素

```
btn = tkinter.Button(root,text = '按钮')
# 位置距离左边100像素，距离上边20像素
btn.place(x = 100,y = 20)
btn1 = tkinter.Button(root,text = '按钮1')
# 设置按钮的宽度和高度
btn1.place(x = 100,y = 100,width = 100,height = 100)
```

相对定位布局：
relx　　设置距离左上角的水平长度　　   取值（0-1）
rely　　设置距离左上角的垂直高度　　   取值（0-1）　
relwidth　　设置组件所占据的宽度　　   取值（0-1）
relheight　　设置组件所占据的高度　    取值（0-1）

以上属性设置都是相对于界面宽度或者高度的百分比，可以更具界面的大小的改变而改变！

注意：禁止同时使用两种摆放方式！