# Angular2学习指南

## ng2新添特性
+ Form Builder 表单创建器
+ Change Detection 
+ Templating 模板
+ Routing 路由
+ Annotations 注解
+ Observables
+ Shadow DOM 
+ 以组件而非DOM为核心 

## ng2依赖的库的解释
+ systemjs - 通用模块加载器，支持AMD、CommonJS、ES6等各种格式的JS模块加载

## ng1和ng2的区别
+ 移除了$scope,$watch
+ 主要用component来替代以前的directive,除此之外还有属性指令，结构指令
+ 采用ES6的模块化机制
+ 采用typescript，所以一定要预编译

## ES6相关

### 类

```javascript
class Hamburger {
  constructor() {
    // 这是构造器.
  }
  listToppings() {
    //这是Hamburger类的一个方法
  }
}
```

### ...spread

```
const add = (a,b) => a + b;
let args = [3,5];
add(...args);//等价于 add(args[0],args[1]) 或 add.apply(null,args)
```


```
let cde = ['c','d','e'];
let scale = ['a','b',...cde,'f','g'];//等价于 ['a', 'b', 'c', 'd', 'e', 'f', 'g']
```

## TS相关
为了玩ts,我们需要装相关的npm包

~~~

C:\Users\1> npm install -g typescript <--安装ts相关的npm

C:\Users\1>tsc <--检测是否安装成功
Version 1.8.10
Syntax:   tsc [options] [file ...]

Examples: tsc hello.ts
          tsc --out file.js file.ts
          tsc @args.txt

Options:
 --allowJs                           Allow javascript files to be compiled.
 --allowSyntheticDefaultImports      Allow default imports from modules with no default export. This does not affect code emit, just typechecking.
 --allowUnreachableCode              Do not report errors on unreachable code.
 --allowUnusedLabels                 Do not report errors on unused labels.
 -d, --declaration                   Generates corresponding '.d.ts' file.
 --experimentalDecorators            Enables experimental support for ES7 decorators.
 --forceConsistentCasingInFileNames  Disallow inconsistently-cased references to the same file.
 -h, --help                          Print this message.
 --init                              Initializes a TypeScript project and creates a tsconfig.json file.
 --jsx KIND                          Specify JSX code generation: 'preserve' or 'react'
 --mapRoot LOCATION                  Specifies the location where debugger should locate map files instead of generated locations.
 -m KIND, --module KIND              Specify module code generation: 'commonjs', 'amd', 'system', 'umd' or 'es2015'
 --moduleResolution                  Specifies module resolution strategy: 'node' (Node.js) or 'classic' (TypeScript pre-1.6).
 --newLine NEWLINE                   Specifies the end of line sequence to be used when emitting files: 'CRLF' (dos) or 'LF' (unix).
 --noEmit                            Do not emit outputs.
 --noEmitOnError                     Do not emit outputs if any errors were reported.
 --noFallthroughCasesInSwitch        Report errors for fallthrough cases in switch statement.
 --noImplicitAny                     Raise error on expressions and declarations with an implied 'any' type.
 --noImplicitReturns                 Report error when not all code paths in function return a value.
 --noImplicitUseStrict               Do not emit 'use strict' directives in module output.
 --outDir DIRECTORY                  Redirect output structure to the directory.
 --outFile FILE                      Concatenate and emit output to single file.
 --preserveConstEnums                Do not erase const enum declarations in generated code.
 --pretty KIND                       Stylize errors and messages using color and context. (experimental)
 -p DIRECTORY, --project DIRECTORY   Compile the project in the given directory.
 --reactNamespace                    Specifies the object invoked for createElement and __spread when targeting 'react' JSX emit
 --removeComments                    Do not emit comments to output.
 --rootDir LOCATION                  Specifies the root directory of input files. Use to control the output directory structure with --outDir.
 --sourceMap                         Generates corresponding '.map' file.
 --sourceRoot LOCATION               Specifies the location where debugger should locate TypeScript files instead of source locations.
 --suppressImplicitAnyIndexErrors    Suppress noImplicitAny errors for indexing objects lacking index signatures.
 -t VERSION, --target VERSION        Specify ECMAScript target version: 'ES3' (default), 'ES5', or 'ES2015' (experimental)
 -v, --version                       Print the compiler's version.
 -w, --watch                         Watch input files.
 @<file>                             Insert command line options and files from a file.
~~~

比如我们创建一个ts文件：

```
class Pizza {
  toppings: string[];
  constructor(toppings: string[]) {
    this.toppings = toppings;
  }
}
```

然后我们就可以用编译成原始的js(命令tsc 1.js)

```
var Pizza = (function () {
    function Pizza(toppings) {
        this.toppings = toppings;
    }
    return Pizza;
}());

```

ng2目录里的tsconfig.json主要就是ts相关的配置

### 定义函数

```javascript
function add(a:number,b:number){
    return a + b;
}

add(1,3);
add(1,'3');//会报错
```

### typings
我们观察ng2的文件目录会发现里面有一个文件叫typings.json

```
{"ambientDependencies": {"es6-shim": "github:DefinitelyTyped/DefinitelyTyped/es6-shim/es6-shim.d.ts#7de6c3dd94feaeb21f20054b9f30d5dabc5efabd","jasmine": "github:DefinitelyTyped/DefinitelyTyped/jasmine/jasmine.d.ts#5c182b9af717f73146399c2485f70f1e2ac0ff2b"}}
```

当使用外部JavaScript库或新的宿主API时,我们需要创建一个这个文件。

### typescript类别信息
+ boolean(true/false)
+ number 
+ string
+ [] 数组，如果这个数组用来存数字类型的，可以用number[],如果是布尔型的，可以用boolean[]
+ {} 对象字面量
+ undefined
+ enum 枚举类型 比如{Red,Blue,Green}
+ any 可以用任何类型
+ void 

```
let isDown:boolean = false;
let decLiteral = 6;
let hexLiteral:number = 0xf00d;
let name:string = 'bob';
let list:number[] = [1,23,3];
let list:Array<number> = [1,2,3];
let x:[string,number] = ['hello',0];
enum Color {Red,Green,Blue};
let notSure:any = 4;
function warnUser():void{
    alert("This is my warning message");
}
let strLength:number = (<string>someValue).length;
let someValue:any = "this is a string";
```


## bootstap(启动，不是指twitter的bootstrap)
在main文件中，我们需要这样初始化：

```javascript
import {Component,bootstrap} from 'angular2/angular2';
@Component({
    selector:"my-app",
    template:"<h1>Hello {{name}}</h1>"
})

class MyApp{
    constructor(){
        this.name = 'Max';
    }
}

bootstrap(MyApp);
```

## components
为了创建一个ng2应用你应该定义一组components,每一个UI组件、路由。一个应用包含一个根组件和一系列其他组件，换句话说，每个ng2会包含一棵component树。Application是根组件。
比如我们创建一个talk-cmp的组件：

```javascript
//TalkCmp.ts
@Component({
  selector: 'talk-cmp',
  directives: [FormattedRating, WatchButton, RateButton],
  templateUrl: 'talk_cmp.html'
})
class TalkCmp {
  @Input() talk: Talk;
  @Output() rate: EventEmitter;
  //...
}
```

```html
<!--talk_cmp.html-->
{{talk.title}}
{{talk.speaker}}
<formatted-rating [rating]="talk.rating"></formatted-rating>
<watch-button [talk]="talk"></watch-button>
<rate-button [talk]="talk"></rate-button>
```

一个组件有input和output属性，这二个属性可以通过decorator来定义：

```javascript
class TalkCmp{
    @Input() talk:Talk;
    @Output() rate: EventEmitter;
}
```

如何理解decorator:

```javascript
@Component({
    selector:"app",
    template:"Hello World"
})
class App{}
```

上面的代码相当于：

```
class App{}
Component({
    selector:'app',
    template:'Hello world'
})(App)
```

input和output属性是组件的暴露在外的公共api,你可以通过下列方式来调用：

```html
<talk-cmp [talk]="someExp" (rate)="eventHandler($event.rating)"></talk-cmp>
```

一个组件有模板，用来定义这个组件是如何在页面中是如何渲染：

```javascript
@Component({
    selector:"talk-cmp",
    directives:[FormattedRating,WatchButton,RateButton],
    templateUrl:"talk_cmp.html"
})
```

```html
<!--talk_cmp.html-->
{{talk.title}}
{{talk.speaker}}
<formatted-rating [rating]="talk.rating"></formatted-rating>
<watch-button [talk]="talk"></watch-button>
<rate-button [talk]="talk"></rate-button>
```

或者你可以把组件和模板写在一起：

```javascript
@Component({
  selector: 'talk-cmp',
  directives: [FormattedRating, WatchButton, RateButton],
  template: `
    {{talk.title}}
    {{talk.speaker}}
    <formatted-rating [rating]="talk.rating"></formatted-rating>
    <watch-button [talk]="talk"></watch-button>
    <rate-button [talk]="talk"></rate-button>
  `
})
```

## 生命周期钩子(Component Lifecycle)
+ ngOnChanges - 当一个input,output的属性改变的时候会触发这个方法
+ ngOnInit - 当ngOnChanges调用完了之后
+ ngDoCheck - 开发者自定义的change触发的时候
+ ngAfterContentInit - 当组件内容初始化的时候
+ ngAfterContentChecked - 当组件内容改变的时候
+ ngAfterViewInit - 每次检查组件的视图的时候触发
+ ngOnDestroy - 组件销毁之前会触发


比如，我们可以这样：

```javascript
@Component({selector:"cares-about-changes"})
class CareAboutChange{
    @Input()field1;
    @Input()field2;
    onChange(changes){

    }
}
```

```java
// Annotation section
@Component({
  selector: 'street-map',
  template: '<map-window></map-window><map-controls></map-controls>',
})
// Component controller
class StreetMap {
  ngOnInit() {
    // Properties are resolved and things like
    // this.mapWindow and this.mapControls
    // had a chance to resolve from the
    // two child components <map-window> and <map-controls>
  }
  ngOnDestroy() {
    // Speak now or forever hold your peace
  }
  ngDoCheck() {
    // Custom change detection
  }
  ngOnChanges(changes) {
    // Called right after our bindings have been checked but only
    // if one of our bindings has changed.
    //
    // changes is an object of the format:
    // {
    //   'prop': PropertyUpdate
    // }
  }
  ngAfterContentInit() {
    // Component content has been initialized
  }
  ngAfterContentChecked() {
    // Component content has been Checked
  }
  ngAfterViewInit() {
    // Component views are initialized
  }
  ngAfterViewChecked() {
    // Component views have been checked
  }
}
```
## providers
组件可以注入很多providers

```javascript
@Component({
    selector:"conf-app",
    providers:[ConfAppBackend,Logger]
})
class TalksApp{

}
class TalksApp{

}
class TalksCmp{
    constructor(backend:ConfAppBackend){

    }
}
```

## components是自我描述的
+ 组件知道如何和宿主元素交互
+ 组件知道如何渲染自身
+ 组件配置依赖注入
+ 组件有自定义的input和output的属性

## zone.js
ng2内置了zone.js,不再需要一堆的scope.$apply代码

## Annotations

```javascript
@Component({
  selector: 'tabs'
})
@View({
  template: `
    <ul>
      <li>Tab 1</li>
      <li>Tab 2</li>
    </ul>
  `
})
export class Tabs {

}
```

@view的使用使得我们可以期待不远的将来我们可以让ng2支持ios和android原生的开发。

## 事件

```javascript
import {Component} from 'angular2/core';

@Component({
  selector: 'counter',
  template: `
    <div>
      <p>Count: {{ num }}</p>
      <button (click)="increment()">Increment</button>
    </div>
  `
})
export class Counter {
  num: number = 0;

  increment() {
    this.num++;
  }
}
```

## 双向数据绑定

```javascript
<input [(ngModel)]="name" >

```

## Projection

```javascript
import {Component, Input} from 'angular2/core';

@Component({
  selector: 'child',
  template: `
    <h4>Child Component</h4>
    <ng-content></ng-content>
  `
})
class Child {}
```

## ngIf,ngSwitch,ngFor

```html
<div *ngIf="hero">{{hero}}</div>
<div *ngFor="#hero of heroes">{{hero}}</div>
<div [ngSwitch]="status">
  <template [ngSwitchWhen]="'in-mission'">In Mission</template>
  <template [ngSwitchWhen]="'ready'">Ready</template>
  <template ngSwitchDefault>Unknown</template>
</div>
```

```

@Component({
    selector:"products-list",
    properties:{
        products:"products"
    },
    events:['click']
})
@View({
    directives:[For,ProductRow],
    template:`
    <div class="product-list">
        <product-row *for="#product of products"
            [product]="product"
            (click)="clicke3d(product)">
        </product-row>    
    </div>
})

class ProductsList{
    products:Array<product>;
    click:EventEmitter;

    constructor(){
        this.click = new EventEmitter();
    }

    clicked(product){
        this.click.next(product);
    }
}

```

## 用component来替代控制器和指令

```javascript
angular.module('app',[])
.component('app',{
    restrict:"E",
    template:``,
    controller:class App{
        constructor(){
            this.myState = 'California'
        }
    }
})
```

```
@Component({
    selector:'app',
    template:'<div></div>'
})

class App{
    myState = 'California'
}
```

## 事件处理

```javascript
angular.module('app',[])
.component('app',{
    restrict:'E',
    template:'',
    controller:class App{
        action(e){
            console.log(e);
        }
    }
})
```

```javascript
@Component({
    selector:'app',
    template:,

})

class App{
    action(e){
        console.log(e);
    }
}
```


```javascript
var metaData = {
    selector:'home',
    template:`
        <button (click)='getData()'>Get Server Data</button>
    `
}
@Component(metadata)
class Home{
    text = {};
    getData(e){
        setTimeout(() => {
            this.text = {res:'something else'};
            this.text = {res:'data'}
        },1000)
    }
}
```

```
@Component({
    selector:'home',
    providers:[providers],
    template:
})

class Home{
    constructor(public service:Service){

    }
}
```


## 路由

```javascript
@Component(...)
@RouteConfig([
    {path:"",component:IndexCmp},
    {path:"email/:id",component:EmailCmp},
    {path:"search",component:SearchCmp}
])
class AppCmp {}

```


## 引入样式
+ style
+ styleUrls

## 知识清单
+ bootstrap(MyAppComponent,[MyService,provide(...)]);  引导根组件为MyAppComponent的应用，配置 依赖入入的服务
+ <input [value]="firstName"> 属性value的值设为firstName
+ <div [attr.role]="myAriaRole"> 属性role的值设为myAriaRole
+ <div [class.extra-sparkle="isDelightful"]> 如果isDelightful为true,则添加css类名extra-sparkle
+ <div [style.width.px]="mySize"> 将width设为mySize,单位可选
+ <button (click)="readRainbow($event)"> 点击事件触发时执行readRainbow($event)函数
+ <video #movieplayer...> 创建本地变量moviePlayer
+ @injectable声明一个有依赖的类

```
System.config({
    transpiler:'typescript',
    typescriptOptions:{emitDecoratorMetadata:true},
    package:{'app':{defaultExtension:'ts'}}
});
System.import("app/main").then(null,console.err.bind(console));
```


## angular API一览
### 指令
- CheckboxControlValueAccessor
- MinLengthValidator
- NgControlName
- NgForm
- NgIf
- NgPluralCase
- NgSwitch
- PatternValidator
- DefaultValueAccessor
- NgClass
- NgControlStatus
- NgFormControl
- NgModel
- NgSelectOption
- NgSwitchDefault
- RequireValidator
- MaxLengthValidator
- NgControlGroupd
- NgFor
- NgFormModel
- NgPlural
- NgStyle
- NgSwitchWhen
- SelecControlValueAccessor

### 路由相关
- RouterLink

```
@RouteConfig([
    {path:"/user",component:userCmp,as:"user"}
]);
class MyComp{}

<a [routerLink]="['./User']">Link to user component</a>
```

- RouterOutlet


### 组件
- Component
- Directive
- Injectable
- Pipe

### 动画
- Animation
- AnimationBuilder
- BrowserDetails
- CssAnimationBuilder
- CssAnimationOptions
- AbstractControl
- Control
- ControlGroup
- DecimalPipe
- i18nSelectPipe
- NgControl
- PercentPipe
- SlicePipe
- AbstractControlDirective
- ControlArray
- currencyPipe
- FormBuilder
- jsonPipe
- NgLocalization
- RadioButtonState
- UpperCasePipe
- AsyncPipe
- ControlContainer
- DatePipe
- LowerCasePipe
- NumberPipe
- ReplacePipe
- Validators

### 编译器
- attrAst
- BoundEventAst
- CompileTemplateMetaData
- ElementAst
- SourceModule
- TextAst
- XHR
- BoundDirectivePropertyAst
- BoundTextAst
- CompileTypeMeta
- EMbadedTemplateAst
- sourceWithmports
- UrlResolver
- BoundElementPropertyAst
- CompileDirectiveMetadata
- DirectiveAst
- NgContentAst
- TemplateCompiler
- VariableAst

### 核心
- AbstractProviderError


```javascript
export class QuestionBase<T>{
    value:T;
    key:string;
    label:string;
    required:boolean;
    order:number;
    controlType:string;

    constructor(options:{
        value?:T,
        key?:string,
        label?:string,
        required?:boolean,
        order?:number,
        controlType?:string
    } = {}){
        this.value = options.value;
        this.key = options.key || '';
        this.label = options.label || '';
        this.required = !!options.required;
        this.order = options.order === undefined?1:options.order;
    }

}
```