# css学习笔记

+ 不要用b,i标签，用strong来用于强调文字
+ 不要使用br标签(这个我用得好像不少=^.^=)
+ 每个网页只能有一个h1标签
+ 如何理解怪异模式：如果你希望网页能够在web浏览器上准确无误的显示出来，就得在网页开头的文档类型声明中阐明，告诉网页浏览器你正在使用哪个版本的HTML,如果你的文档声明没有加或写错了，就会导致大部分浏览器进入一种怪异模式。怪异模式就是当现代的浏览器遇到一个没有正确文档类型的网页时，它就会以为：这一定是一个旧式浏览器上显示的网页，那么它真的会以旧的浏览器上的模式进行渲染。从而导致样式不正常。最经典的莫于过[IE盒子](https://zh.wikipedia.org/wiki/IE%E7%9B%92%E6%A8%A1%E5%9E%8B%E7%BC%BA%E9%99%B7)的问题。
+ IE8在前端技术忘记加了文档头或者用户按下了compatibility view按钮时，就会进入IE7模式，所以为了保证不会出问题，一般我们会加上<meta http-equiv="X-UA-Compatible" content="IE-edge" />
+ 测试IE6建议用virtual Box或vmware虚拟机里装xp操作系统，IE6审查元素用debugger bar
+ css类名规范：首字符必须是字母，区分大小写
+ :first-letter,:first-line选择器
+ IE6、IE7不支持content
+ li:first-child匹配的是li,同时li必须是别人的first-child
+ :hover,:focus伪类
+ 能继承的属性有：
```
azimuth
border-collapse
border-spacing
caption-side
color
cursor
direction
elevation
empty-cells
font-family
font-size
font-style
font-variant
font-weight
font
letter-spacing
line-height
list-style-image
list-style-position
list-style-type
list-style
orphans
pitch-range
pitch
quotes
richness
speak-header
speak-numeral
speak-punctuation
speak
speech-rate
stress
text-align
text-indent
text-transform
visibility
voice-family
volume
white-space
widows
word-spacing
```

+ 亲测感觉特实用的icon fonts[在线生成地址](http://fontello.com/)
+ 各个手机系统都有自己的默认字体，且都不支持微软雅黑，英文和数字字体可以使用Helvetica,各系统基本都支持
+ 每个浏览器都有一个预定的基准文本尺寸，在大部分浏览器上是16px
+ margin负值是合法的，它们被用来进行比较高级的布局
+ 边距折叠，解决方法：要么在div标签周围添加少量的padding,要么给它添加一条border,因为border和padding位于两个margin之间，margin就不会再碰到一起了
+ 用margin负值消除空格：margin负值不是在标签和它周围的元素之间增加空间，而是移除空间，因此你可以让文本段落与标题重叠，露出它的外围元素甚至让浏览器的某个边隐藏起来。
+ 只能给行内元素增加padding-left,padding-right,margin-left,margin-right
+ 表格
```
    <table>
        <thead>
            <tr>
                <th>标题单元格</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>单元格</td>
            </tr>
        </tbody>
    </table>
```

+ first-of-type,first-child
+ 相对于padding进行定位的

理解百分比
