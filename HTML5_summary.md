HTML5简介
 ####html5的概念
 1.html5
 
 狭义：html超文本标记语言版本  
 广义：html5+css+新增的domAPI  
 新增语义标签、智能表单、多媒体、。。。  
 
 ##新增的结构化标签
 html 结构和样式分离 语法更加简介清晰 更加语义化
 ```bach
 header 头部标签
 footer 尾部标签
 section 块区域
 article 文章区域
 aside   侧边栏
 main   主体
 figure 媒介信息 figcation 作为标题 img 
 progress 进度条
 time 时间
 detail 详细信息 open 
 summary 汇总 p 
    <detail>
        <summary></summary>
        <p></p>
    </detail>
 hgroup 标题组
 mark 标记
 nav 导航
```

###结构化标签的兼容性写法
IE6 7 8 引入html5shiv.min.js (会把新标签创建出来，然后加入默认样式)
```$xslt
<!--[if lte IE 9]>
   <script src=""/>
<![end]-->
```
###新增的表单类型
```$xslt
<input type="email"> 邮箱类型 默认有正则
<input type=“tel"> 移动端弹出键盘
<input type="url"> 网址 默认正则http://
<input type=“num">在移动端输入不了字符
<input type="search">在移动端enter /开始
<input type'range" min="0" max="100" value="10" step:"10"/>范围
<input type="color">拾色器
<input type="time">
<input type="date">
<input type="datetime-local">
<input type="month">
<input type="week">

```


```$xslt
新增的属性
placeholder 占位符
autofocus  获取焦点
required 必填项
pattren  正则验证
```

###多媒体标签
```$xslt
<audio src="" loop="-1" controls></audio>
<audio  loop="-1" controls>
    <source src="">
</audio>

<video width height></video>
```

###自定义属性
```
dataset 可以设置获取自定义属性，（data-）
<div date-age="23"></div>
div.dataset.domStringMap{age:23}
```

####两个新的获取元素方式
```$xslt
document.querySelector()获取第一个
document.querySelectorAll()获取一个集合 参数可以css写选择器

```
###类名的操作
```$xslt
元素.classList
add()
remove()
toggle()
contains()
```
####地理定位 了解
####本地存储
```$xslt
sessionStorage:会话存储 生命周期  浏览器关闭就销毁
localStorage:本地存储 永久存储
cookie:浏览器缓存 会随着http协议进行通讯 4kb
方法：
setItme(key,value)
removeTtem(key)
getItem(key)
clear
object.key(obj) 获取keys
object.values(obj) 获取values
object.entrys(obj)
```
###监听网络端口
```$xslt
必须通过addEventListener()绑定
online
ofline
```
###文件读取对象 FileReader()
```$xslt
本地上传  拖拽上传
tml5 FileReader() 内置对象 类比new Date()
var fr=new FileReader();
fr.readAsText();读取文本 返回字符串 默认utf-8
fr.readAsBinary():字节读取
fr.readAsDataurl():读取任意类型文件

fr:事件机制
onbort:读取文件中断触发
onerror:读取错误时触发
onload:读取成功时触发
onloaded:读取文件完毕触发
onloadstart:读取文件开始触发
onprogress:读取过程触发
//预览
fr.onload=function(){
    var img=docuemnt.createElement("img");
    img.src=this.result;
    body.appendChild(img)        
}
```
####ajax上传
```$xslt
var xhr=new XMLHttpRequet();
xhr.open("post","url",true);
var fd=new FormData();
fd.append("file",files[i]);
xhr.send(fd);

xhr.upload.onprogress=function(e){
    e.total//总的文件大小
    e.loaded//已经上传文件的大小
    //进度条
}
xhr.onload=function(){
    //监听上传是否成功
}

```
###拖拽
```$xslt
    应用于拖拽元素的事件
    ondrag 整个拖拽会调用
    ondragstart:当开始拖拽时候调用
    ondragleave:当鼠标离开拖拽元素的时候调用
    
    应用于目标元素事件
    ondragenter:当拖拽元素进入时调用
    ondragover:当停留在目标元素的时候 持续调用
    ondrop:当在目标元素上松开鼠标时调用
    ondragleave:当鼠标离开目标元素时调用
    
ondrop 事件 --ev.dataTransfer.files去获取文件
```

