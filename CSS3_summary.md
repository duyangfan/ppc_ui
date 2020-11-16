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
###过渡属性
```aidl
  transition-property 过渡属性
           transition-duration:过渡时间
           transition-timing-function:设置过渡速度  用来控制速度  linear(匀速)  ease-in(加速)
           transition-delay 设置过渡延时   超过时间后执行动画
           可以复合使用：transition:all linear 1s 2s
           
 eg:
  #box:hover{
                 width: 500px;
                 background-color:black;
                 transiton-property:width;
                 transition-duration: 3s;
                 transition-timing-function:ease-in;
                 transition-delay:1s;
             }
```
###2d变换：
```aidl

            #box{
                width: 300px;
                height: 300px;
                background-color: rgb(228,141,141);

                transition:all 2s;
            }

            #box:hover{
                /* 变换：位移     变换中心点：transform-origin:x，y   center/top/left/right*/
                transform: translateX(200px);
                transform: translateY(200px);
                transform: translate(200px,300px);
                /*  旋转  */
                transform: rotate(-90deg);
                /* 缩放 x,y
                */
                transform: scaleX(0.6);
                /* 斜*/
                transform: skew(15deg);
            }
            #box{
                width: 300px;
                height: 300px;
                background-color: rgb(228,141,141);

                transition:all 2s;
            }

            #box:hover{
                /* 变换：位移     变换中心点：transform-origin:x，y   center/top/left/right*/
                transform: translateX(200px);
                transform: translateY(200px);
                transform: translate(200px,300px);
                /*  旋转  */
                transform: rotate(-90deg);
                /* 缩放 x,y
                */
                transform: scaleX(0.6);
                /* 斜*/
                transform: skew(15deg);
            }
```
####动画
```aidl
 关键帧动画
            @keyframes name{
                from{

                }
                to{

                }
            }
            @keyframes name{
                0%{

                }
                10%{

                }
            }
调用方式：animation属性调用
        animation-name: action;
        animation-duration: 1s; !*持续时间*!
        animation-delay: 2s;!*延时*!
        animation-timing-function: cubic-bezier(0.79,-0.6, 1, 1.7); !*动画播放速度 linear：匀速-ease-in-out ease-in ease-out step()步长*!
        animation-iteration-count: 2; !*播放次数 默认播放一次 无限 infinite*!
        animation-fill-mode:backwards ; !*动画结束状态  backwards :默认恢复到开始 forwards:结束状态*!
        animation-play-state: running; !*动画播放和暂停属性   默认running  paused  暂停*!
        animation-direction:alternate ;!* 默认normal   倒放 alternate 倒放*!
        animation: action 2s linear 2 alternate forwards running;
        
```

####补充属性
```aidl
半透明属性：opacity: 0.6;
```