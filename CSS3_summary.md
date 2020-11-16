###CSS3 简介
######css3
````$xslt
css层叠样式表的第三个版本
属性选择器  伪类选择器   阴影   圆角   渐变 背景尺寸设置  盒模型设置   颜色表示方式  过渡  2d 3d  icon-font flex-box...

````

####属性选择器
```$xslt
E[attr] 表示存在attr属性即可

E[attr=val]属性值完全等于val

E[attr*=val] 表示属性值里面包含val字符并且在“任意”位置

E[attr^=val] 表示属性值以val开头

E[attr￥=val] 表示属性值以val结尾
```

###伪类选择器
```$xslt
a：lvht   link active visited hover

E:first-child 第一个元素
E:last-child 最后一个元素

E:nth-child(n)第n个元素
E:nth-last-child(n):从后第几个元素

找同类型的元素
E:first-of-type:第一个元素
E:last-of-type:最后一个元素
E:nth-of-type():第n个元素
E:last-nth-of-type():从最后一个元素开始
```

####伪元素

```$xslt
e:after e:before old版本
e::after e::before   new 版本   兼容性

```

####颜色新的表示
```$xslt
RGBA() RGB  多了alpha 透明度通道
HSLA()
```
####阴影
```aidl
 文本阴影：text-shadow:水平偏移 垂直偏移 模糊程度 颜色
 
 盒子阴影
 box-shadow:水平偏移 垂直偏移 模糊程度  颜色 [inset](内阴影)
 
```

####盒模型
```aidl
box-sizing:规定盒元素的计算宽高方式
content-box:默认
border-box:元素的宽高以边框开始计算

移动端   *{box-sizing:border-box}
防止一些元素添加边框后，不影响布局

```

####圆角
```aidl
border-raduis:固定像素/百分比
每个角可以设置两个值：X值  Y值

```
####渐变
````aidl
渐变是基于背景图

线性渐变
background:linear-gradient()
属性1：方向 to  right/top/bottom/left  45deg
属性2:颜色
属性3：。。。。多个颜色
每个颜色后面可以通过添加 百分比来控制当前颜色所占的比重
````

###径向渐变
```aidl
radial-gradient()
属性1：半径 at 坐标点  50px 30px /center/top
属性2：颜色
属性3：。。。多个颜色

```
###背景尺寸
```aidl
background-size:设置背景尺寸的大小 X Y :会导致图片变形  不会随着盒子的宽高变化而变化
               cover：覆盖 尽可能覆盖整个盒子，不会导致背景变形，可能有一部分区域看不到
               contain：竟可能显示整个背景图，可能有一部分区域覆盖不到

```
