# angular.js中关于$rootScope

测了半天都打印出来undefined，后来突然想到了，要想用服务必须把相关的依赖引进来，果然就行了，测试代码如下:

```javascript
var myApp = angular.module('myApp', []);
    myApp.controller('a', ['$scope', '$rootScope',function ($scope,$rootScope) {
        console.log($rootScope);
    }])
```        
