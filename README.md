# commonJS
尚德前端公共方法
**前端公用文档**

`http://go.163.com/2015/public/common/js/common.min.js` 封装了前端项目常用方法，适用于移动端与PC端。

**文档介绍**


----------
common.min.js 封装的功能包括：

 1. 手机号格式检测；
 2. 常用UA检测；
 3. 手机横屏时，提示用户请竖屏浏览；
 4. 获取链接中指定的参数；
 5. 音乐与视频自动播放；
 
 
 **文档使用说明**
 
----------
对外提供了sunland对象，下面有几个可以使用的公用方法

首先引用common.min.js，引入到`<body></body>`标签内，作为第一个引入的js文件，如下 

``` xml
<!DOCTYPE html>
<html>
    <head>
    ...
    </head>
    <body>
    ...

    <script src="http://go.163.com/2015/public/common/js/common.min.js"></script>

    </body>
</html>
```

----------

**手机格式检测的使用说明**


html代码如下(将此段复制到body中)

``` stylus
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>         <!--Title替换成页面的标题--> 
    <script>
        var siteId = 111111     //用自己的站点ID替换111111
    </script>
    <script src="http://ggtf.sunland.org.cn/statistics/sunlandsLog.js"></script>
</head>
<body>
   <script src="http://ggtf.sunland.org.cn/statistics/interactive.js"></script>
    <!--页面代码开始-->  
	<input type="text" id="phone">
	<button id="btn">click me !</button>
    <!--页面代码结束-->
</body>
</html>
	
```

js代码如下
``` xml
<script>
	interactive.init('xiaoneng');
	document.getElementById('btn').onclick=function(e){      //用手机留言发起按钮的ID替换btn
		if(sunland.phoneTest("phone")){
			alert('恭喜您提交成功');
			console.log(sunland.phoneTest("phone"))
            interactive.submitMsg(e,'stPhone',sunland.phoneTest("phone"),'留言发起');
		}else{
			alert('请输入11位有效的手机号码');
		}
	}
</script>
```
----------

**15天循环倒计时**


html代码如下

``` stylus
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>         <!--Title替换成页面的标题--> 
    <script>
        var siteId = 111111     //用自己的站点ID替换111111
    </script>
    <script src="http://ggtf.sunland.org.cn/statistics/sunlandsLog.js"></script>
</head>
<body>
   <script src="http://ggtf.sunland.org.cn/statistics/interactive.js"></script>
    <!--页面代码开始-->  
	<span id="lastDate"></span>
    <!--页面代码结束-->
</body>
</html>
	
```

js代码如下

``` xml
<script>
	interactive.init('xiaoneng'); //初始化小能
	//应用代码 sunland.lastTime('id',截止天数);
	sunland.lastTime('lastDate',1);
</script>
```
----------
确保成功引入common.js后，调用方法lastTime('id',截止天数);
common.js引入位置为body结束标签之前
调用的方法lastTime在common.js之后
