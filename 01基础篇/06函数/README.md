#### 函数
> 函数：完成特定功能的一段代码！主要要实现可重用性！

> 三要素：函数名、函数参数（可有可无）、返回值（可有可无） 

##### 1、 函数定义

###### 函数声明和函数表达式

```
// 函数声明
function funcName (args) {
    return args
}
// 函数表达式
var funcName = function (args) {
    return args
}
```
> 区别：函数表达式和普通函数声明的区别在于，普通函数声明会提升，函数表达式不会提升


###### 使用Function构造函数声明
```
let func = new Function ([arg1[, arg2[, ...argN]],] functionBody)
```
> 这种声明方式，没有发现有什么优点，并不推荐使用。




##### 2、 匿名函数
> 匿名函数的最大作用在于作用域隔离，不污染全局作用域。如果没有匿名函数包裹，代码中声明的所有变量都会出现在全局作用域中，造成不必要的变量覆盖麻烦和性能上的损失。

```
(function(){
    ...
})();
```

> ES6增加了匿名函数写法，重点在函数作用域内可以使用this对象

```
setTimeout(() => {
    console.log('test');
});
```

##### 3、 函数调用

- 作为函数直接调用
- 作为对象方法调用
- 作为构造函数调用
- 通过call()和apply()间接调用

```
// 第一种：直接调用
function test(){
  	console.log(this);
}
test(); // window

// 第二种：作为对象的方法使用
var x = 45;
var test = function() {
    console.log(this.x);
}
var obj = {
    x: 23,
    test: test
};
obj.test(); // 此时的this指代的是当前对象，因此返回的是23
test(); // test是window下的方法，因此返回的是45

// 方法三：通过call() apply()方法
var obj1 = { name: 'obj1' };
var obj2 = { name: 'obj2' };
obj1.foo = function() {
    console.log(this.name);
}
obj1.foo();// obj1
obj1.foo.call(obj2);// obj2
obj1.foo.apply(obj2);// obj2

// call apply 综合应用
var fish = {
    name: "fish",
    swim: function(m, n) {
        console.log("i'm " + this.name + " i cam swim ___", m, n);
    }
};
var bird = {
    name: "polly",
    fly: function(m, n) {
        console.log("i'm:" + this.name + " i can fly ___", m, n);
    }
};
var me = {
    name: "ABC"
};

bird.fly(5, 6);
fish.swim.call(me, 3, 4); // call在参数传递的时候是散列的传递
bird.fly.apply(me, [7, 8]); //apply在参数传递的时候是数组的形式传递
var name = 11;
bird.fly.apply(null, [7, 8]); // null 指向的是全局主体，就是全局下进行bird.fly方法的调用
```

##### 4、 函数参数（实参、形参）
- 实参数量大于形参数量
    > 通过函数对象属性arguments获得实参

- 实参数量小于形参数量
    > 少的参数值为undefined，可以使用||来给出默认值

- 参数类型与传递方式（值传递、引用传递）


##### 5、 函数返回值
- 返回值可以直接赋予变量或用于表达式中

- return语句表示结束当前函数的执行，return语句可以不带表达式（例如：return;），return语句不带表达式时仍会返回值，该值为undefined
- 函数中可以不出现return语句，仍会返回值，该值为undefined


##### 6、 内置高阶函数
- map
- reduce
- filter
- sort
- Array


##### 7、 闭包
> 闭包是指有权访问另一个函数作用域中的变量的函数，简单说就是在函数中声明的函数，也就是嵌套函数。它能够延长父作用域部分变量的生命周期。他可以直接使用其所在函数的任何变量，这种使用是引用传递，而不是值传递，这一点很重要

```
function funcName (props) {
    return function (obj) {
        let value = obj[props]
        return value
    }
}
```