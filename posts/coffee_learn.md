# coffee学习

## 安装

```
npm install --save-dev gulp-coffee
```

## 配置gulp

```
var gulp = require("gulp");
var gutil = require("gulp-util");
var coffee = require('gulp-coffee');
 
gulp.task('default', function() {
  gulp.src('./coffee/*.coffee')
    .pipe(coffee({bare: true}).on('error', gutil.log))
    .pipe(gulp.dest('./js/'));
});
```

## 语法

```javascript
# 我是看不见的注释

###
我是多行可以看见的注释
###

#条件赋值
isTrue = true
m = 100 if true
console.log m


#解构赋值
[a,b,c,d] = [1,2,3,4]
console.log a,b,c,d

[e,f,g] = [5..7]
console.log e,f,g


#类
class Person
    constructor:(name,age)->
        @name = name
        @age = age

    sayHello:->
        console.log "Hello world"
    run:->
        console.log "run"
    add:(a,b)->
        console.log a + b

#对象3
xiaoMing = new Person "eric",20

console.log xiaoMing

console.log xiaoMing.add 100,200
xiaoMing.sayHello()
xiaoMing.run()

#字面量对象
xiaoWang = 
    name:eric,
    age:10
    
console.log xiaoWang
```


