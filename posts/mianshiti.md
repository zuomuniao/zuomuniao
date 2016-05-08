# JavaScript面试题精选(一)


- person1和person2的区别：

```javascript
function Person(){}, 
var person1 = Person()
var person2 = new Person()
```


- 按下面的结果自定义一个duplicate函数

```javascript
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]
```

- 写出下面的结果

```javascript
var foo = 10 + '20';
```

- 写一个add函数实现下面的功能

```javascript
add(2, 5); // 7
add(2)(5); // 7
```


- 写出下面的结果是多少

```javascript
"i'm a lasagna hog".split("").reverse().join("");
```


- 写出下面的结果是多少

```javascript
( window.foo || ( window.foo = "bar" ) );
```

- 写出下面的结果是多少

```javascript
var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
})();
alert(foo + bar);
```

- foo.x的结果是多少

```javascript
var foo = {n: 1};
var bar = foo;
foo.x = foo = {n: 2};
```

- HTTP状态码及其含义

- mouseover/mouseout与mouseenter/mouseleave的区别与联系

- 如何检测Null、Undefined、空、NaN

- 下列代码的结果是多少,怎么解决打印出来的结果是0,1,2,3,4

```javascript
for (var i=0; i<5; i++) {
    setTimeout(function(){
        console.log(i); 
    }, 1000 * (i+1));
}  

```



- jQuery中的detach remove方法的区别是什么


- 写出下面的结果是多少

```javascript
var a=12;
    for(var i=0;i<10;i++){
        setTimeout(function(){
            a++;
        },1000)
    }
    console.log(a); //输出12;
```


- 如何严格的判断一个数据是数组（Array）类的实例，下面实例正确的是( )

```javascript
    A function isArray(val){ return Object.prototype.toString.call(val)='[object Array]'; }
    B function isArray(val){ return Object.prototype.toString.call(val)===[object Array]; }
    C function isArray(val){ return Object.prototype.toString.call(val)===='[object Array]'; }
```


- alert({})弹出的结果是什么？
    + A [object object] 
    + B [object Object] 
    + C [Object Object] 
    + D [Object object]




- 在Javascripte中有类数组概念，或者说伪数组，下面哪些符合类数组( )
    + A 函数的argument参数 
    + B getElementsByTagName返回的对象 
    + C document.childNodes返回的对象 
    + D getElementById()返回的值


- 匹配邮箱的正则表达式，请把正则表达式写出来？
    
- indexOf和lastIndexOf的功能是什么？有什么区别？下列选项哪个正确( )
    + A indexOf(str)返回字符串中参数字符串第一次出现的位置，从前向后检索。
      lastIndexOf(str)返回字符串中最后一处出现的索引，从后向前检索。
    + B indexOf(str)如果没有匹配项，返回-1
      lastIndexOf(str)如果没有匹配项，返回-1
    + C indexOf(str)如果存在匹配项，输出是正值
      lastIndexOf(str)如果没有匹配项，输出是负值





