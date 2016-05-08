
# title: CSS3效果一则

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        .demo{
            width: 100px;
            height: 100px;
            transform-origin:100% 100%;
            position: absolute;
            left:500px;
            top:150px;
        }
        .demo1{
            transform:rotate(-10deg) skew(50deg);
            background: blue;
        }
        .demo2{
            transform:rotate(30deg) skew(50deg);
            background: green;
        }
        .demo3{
            transform:rotate(70deg) skew(50deg);
            background: pink;
        }
        .demo4{
            transform:rotate(110deg) skew(50deg);
            background: purple;
        }
        .demo5{
            transform:rotate(150deg) skew(50deg);
            background: gold;
        }
        .demo6{
            transform:rotate(190deg) skew(50deg);
            background:red;
        }
        .demo7{
            transform:rotate(230deg) skew(50deg);
            background: gray;
        }
        .demo8{
            transform:rotate(270deg) skew(50deg);
            background: violet;
        }
        .demo9{
            transform:rotate(310deg) skew(50deg);
            background: orange;
        }

    </style>
</head>
<body>
    <div class="demo demo1"></div>
    <div class="demo demo2"></div>
    <div class="demo demo3"></div>
    <div class="demo demo4"></div>
    <div class="demo demo5"></div>
    <div class="demo demo6"></div>
    <div class="demo demo7"></div>
    <div class="demo demo8"></div>
    <div class="demo demo9"></div>
</body>
</html>
```
