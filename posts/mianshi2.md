# JavaScript面试题精选（二）

-  下列打印结果是多少说出理由：

```javascript
var foo = {n: 1};
var bar = foo;
foo.x = foo = {n: 2};
```

- 下列打印结果是多少说出理由：

```javascript
var Person = function(name,age){
    this.name = name;
    this.age = age;
    return {name:"moyu"};
}
var xiaoMing = new Person("xiaoMing",20);
```

- var obj = {}; obj的构造器是___?

- 如果一个字符串是一个基本数据类型，那为什么可以用split方法?

- 是否可以用typeof bar === 'object'决定bar是不是对象，如果不可以，一般要用啥方法?


- 下面的代码结果是多少并说出为什么?

```javascript
var myObject = {
    foo: "bar",
    func: function() {
        var self = this;
        console.log("outer func:  this.foo = " + this.foo);
        console.log("outer func:  self.foo = " + self.foo);
        (function() {
            console.log("inner func:  this.foo = " + this.foo);
            console.log("inner func:  self.foo = " + self.foo);
        }());
    }
};
myObject.func();
```


- 下面代码结果：

```javascript
(function() {
    console.log(1); 
    setTimeout(function(){console.log(2)}, 1000); 
    setTimeout(function(){console.log(3)}, 0); 
    console.log(4);
})();
```

- 执行下面的代码以后，点击第四个button,打印出来什么?

```javascript
for (var i = 0; i < 5; i++) {
  var btn = document.createElement('button');
  btn.addEventListener('click', function(){ console.log(i); });
  document.body.appendChild(btn);
}
```

- 下面代码结果：

```javascript
var arr1 = "john".split('');
var arr2 = arr1.reverse();
var arr3 = "jones".split('');
arr2.push(arr3);
console.log("array 1: length=" + arr1.length + " last=" + arr1.slice(-1));
console.log("array 2: length=" + arr2.length + " last=" + arr2.slice(-1));
```

- 下面代码结果：

```javascript
console.log(1 +  "2" + "2");//122
console.log(1 +  +"2" + "2");//32
console.log(1 +  -"1" + "2");//02
console.log(+"1" +  "1" + "2");//112
console.log( "A" - "B" + "2");//NaN2
console.log( "A" - "B" + 2);//NaN
```

- 下面代码结果：

```javascript
console.log("0 || 1 = "+(0 || 1));//1
console.log("1 || 2 = "+(1 || 2));//1
console.log("0 && 1 = "+(0 && 1));//0
console.log("1 && 2 = "+(1 && 2));//2
```

- 下面代码结果：

```javascript
console.log(false == '0');//true
console.log(false === '0');//false
```

```javascript
自身作为布尔值：0,NaN,''、null、undefined

if(){

}


两个等于号比较
1 [1] '1' --> true

```

- 下面代码结果：

```javascript
var a={},
    b={key:'b'},
    c={key:'c'};

a[b]=123;//a['[object Object]'] = 123;
a[c]=456;//a['[object Object]'] = 456;

console.log(a[b]);
```

- 下面代码结果：

```javascript
//递归
console.log((function f(n){return ((n > 1) ? n * f(n-1) : n)})(10));
```

- 下面代码结果

```javascript
(function(x) {
    return (function(y) {
        console.log(this);//window
        console.log(x);
    })(2)
})(1);
```

- 下面代码结果:

```javascript
var hero = {
    _name: 'John Doe',
    getSecretIdentity: function (){
        return this._name;
    }
};

var stoleSecretIdentity = hero.getSecretIdentity;

console.log(stoleSecretIdentity());
console.log(stoleSecretIdentity.call(hero));
console.log(hero.getSecretIdentity());
```


- 下面代码结果:

```javascript
var i=10;  
var j=3;  
function a() {  
    console.log(i);
    console.log(j); 
    var i = 2;  
    console.log(i);
};  
a();  
```
