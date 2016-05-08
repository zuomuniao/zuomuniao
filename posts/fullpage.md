# fullpage.js的使用

## 介绍
fullpage.js是一个使用很广泛的全屏滚动插件，下面教一下如何使用fullpage.js：

## 使用方法

### 引入js文件

```html
<script src="lib/jquery-1.12.2.js"></script>
    <!--
        当你配置了css3:false的时候，可以增加jquery.easings.min.js，这样你可以使用除了jQuery的linear,swing这二种默认运动方式
        确定可以自定义页面滚动的效果
    -->
    <script src="lib/jquery.easings.min.js"></script>
    <!--
        只有当你需要配置scrollOverflow:true这一项的时候才需要加jQuery.slimscroll.js
        对于内容比较多的页面，可以设置右侧的滚动条，但是默认情况下无法滚动，这个文件就是起这个作用的
    -->
    <script src="lib/jquery.slimscroll.js"></script>
    <script src="lib/jquery.fullpage.js"></script>
```

### 引入css文件

```html
<link rel="stylesheet" href="lib/jquery.fullpage.css">
```

### 引入html代码

```html
<!--fullpage这个id要加在body下面-->
<div id="fullpage">
    <div class="section">第一屏</div>
    <div class="section">第二屏</div>
    <div class="section">第三屏</div>
    <div class="section">第四屏</div>
</div>
```

默认是从第一屏开始的，如果你想优先加载某一屏，可以如下使用：

```html
<!--fullpage这个id要加在body下面-->
<div id="fullpage">
    <div class="section">第一屏</div>
    <div class="section">第二屏</div>
    <div class="section active">第三屏优先加载</div>
    <div class="section">第四屏<div></div></div>
</div>
```

每一屏里面加幻灯片效果，比如有三小屏，可以如下在每个div[class="section"]里面加上：

```html
<div class="section">
<div class="slide"> Slide 1 </div>
<div class="slide"> Slide 2 </div>
<div class="slide"> Slide 3 </div>
<div class="slide"> Slide 4 </div>
</div>
```

### 初始化fullpage.js

```javascript
$(document).ready(function() {
    $('#fullpage').fullpage();
});
```

下面是一个比较完整的代码示例：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <link rel="stylesheet" href="lib/jquery.fullpage.css">
</head>
<body>
<div id="fullpage">
    <div class="section">
            <div class="slide">第一屏的第一张幻灯片</div>
            <div class="slide">第一屏的第二张幻灯片</div>
            <div class="slide">第一屏的第三张幻灯片</div>
            <div class="slide">第一屏的第四张幻灯片</div>
    </div>
    <div class="section">Some section</div>
    <div class="section">Some section</div>
    <div class="section">Some section</div>
</div>
    <script src="lib/jquery-1.12.2.js"></script>
    <!--
        当你配置了css3:false的时候，可以增加jquery.easings.min.js，这样你可以使用除了jQuery的linear,swing这二种默认运动方式
        确定可以自定义页面滚动的效果
    -->
    <script src="lib/jquery.easings.min.js"></script>
    <!--
        只有当你需要配置scrollOverflow:true这一项的时候才需要加jQuery.slimscroll.js
        对于内容比较多的页面，可以设置右侧的滚动条，但是默认情况下无法滚动，这个文件就是起这个作用的
    -->
    <script src="lib/jquery.slimscroll.js"></script>
    <script src="lib/jquery.fullpage.js"></script>


        $(document).ready(function() {
            $('#fullpage').fullpage();
        });

</body>
</html>
```

这时候用键盘上的左右按键就会发现我们的第一屏会左右切换，如果按上下键就会发现第二屏第三屏会出现，但是我们发现没有任何样式，我们可以配置一下我们的$('#fullpage').fullpage()，如下：

```html

<style>
    body{
        text-align: center;
        font-size: 40px;
        font-weight: bold;
        color:#fff;
    }
</style>
   
<div id="fullpage">
    <div class="section firstPage">
            <div class="slide one">第一屏的第一张幻灯片</div>
            <div class="slide two">第一屏的第二张幻灯片</div>
            <div class="slide three">第一屏的第三张幻灯片</div>
            <div class="slide four">第一屏的第四张幻灯片</div>
    </div>
    <div class="section secondPage">第二屏</div>
    <div class="section thirdPage">第三屏</div>
    <div class="section forthPage">第四屏</div>
</div>
    <script src="lib/jquery-1.12.2.js"></script>
    <!--
        当你配置了css3:false的时候，可以增加jquery.easings.min.js，这样你可以使用除了jQuery的linear,swing这二种默认运动方式
        确定可以自定义页面滚动的效果
    -->
    <script src="lib/jquery.easings.min.js"></script>
    <!--
        只有当你需要配置scrollOverflow:true这一项的时候才需要加jQuery.slimscroll.js
        对于内容比较多的页面，可以设置右侧的滚动条，但是默认情况下无法滚动，这个文件就是起这个作用的
    -->
    <script src="lib/jquery.slimscroll.js"></script>
    <script src="lib/jquery.fullpage.js"></script>

        $(document).ready(function() {
            $('#fullpage').fullpage({
                controlArrows:true,//控制左右箭头是否显示，默认值是true,如果设置为false则不显示
                resize:true,//设置为true之后，缩小页面会相应的缩小页面里的字体
                sectionsColor:['#f2f2f2', '#4BBFC3', '#7BAABE', 'whitesmoke', '#000']//定义每个section的CSS背景演示
            });
        });


```

### 配置fullpage.js(见script里的配置)

```html


<style>
    body{
        text-align: center;
        font-size: 40px;
        font-weight: bold;
        color:#fff;
    }
</style>
 
 
<div id="fullpage">
    <div class="section firstPage">
            <div class="slide one">第一屏的第一张幻灯片</div>
            <div class="slide two">第一屏的第二张幻灯片</div>
            <div class="slide three">第一屏的第三张幻灯片</div>
            <div class="slide four">第一屏的第四张幻灯片</div>
    </div>
    <div class="section secondPage">第二屏</div>
    <div class="section thirdPage">第三屏</div>
    <div class="section forthPage">第四屏</div>
</div>
    <script src="lib/jquery-1.12.2.js"></script>
    <!--
        当你配置了css3:false的时候，可以增加jquery.easings.min.js，这样你可以使用除了jQuery的linear,swing这二种默认运动方式
        确定可以自定义页面滚动的效果
    -->
    <script src="lib/jquery.easings.min.js"></script>
    <!--
        只有当你需要配置scrollOverflow:true这一项的时候才需要加jQuery.slimscroll.js
        对于内容比较多的页面，可以设置右侧的滚动条，但是默认情况下无法滚动，这个文件就是起这个作用的
    -->
    <script src="lib/jquery.slimscroll.js"></script>
    <script src="lib/jquery.fullpage.js">
        $(document).ready(function() {
            $('#fullpage').fullpage({
                controlArrows:true,//控制左右箭头是否显示，默认值是true,如果设置为false则不显示
                resize:true,//设置为true之后，缩小页面会相应的缩小页面里的字体
                sectionsColor:['#f2f2f2', '#4BBFC3', '#7BAABE', 'whitesmoke', '#000'],//定义每个section的CSS背景演示
                loopTop:true,//默认值是false,如果设置成true则切换到第四屏的时候会再切到第一屏
                loopBottom:true,//默认值是false,如果设置成true则切换到第一屏的时候会再切到第四屏
                navigation:true,//默认值：false，如果设置为true，那他将会显示一个小圆圈组成的快速导航栏
            });
        });
    </script>
```
