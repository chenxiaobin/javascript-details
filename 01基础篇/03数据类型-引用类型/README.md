
#### 引用类型

##### 1. Object
> 全局函数Object(),它是一个构造函数，js中所有的对象都继承Object函数的原型对象

- 获取object实例
    - 作为一个普通函数，把参数转成一个对象
    ```
    obj = Object([1,2,3]);  //[1, 2, 3]
    obj = Object({a:1});   //{a: 1}
    ```
    - 作为构造函数，创建对象实例
    ```
    var obj = new Object();
    ```
    - 通过字面量，创建一个对象实例
    ```
    var p3={
        name:name,
        age:age,
        aboutMe:aboutMe
    }
    ```

- Object实例方法
    - valueOf()     返回对象值，默认返回本身，Date实例返回毫秒时间
    
    - toString() 返回当前对象对应的字符串形式，常用作为字符串转换。`除了null和undefined，都存在toString()`
    - hasOwnProperty() 判断某属性是否为当前对象的自有属性
    - isPrototypeOf() 判断一个对象是否是另一个对象的原型
    ```
        function Animal(){
    　　　　this.species = "动物";
    　  };
        var eh = new Animal();
        Animal.prototype.isPrototypeOf(eh)//=>true
    ```

- Object静态属性
     - getOwnPropertyDescriptor() 和 getOwnPropertyDescriptors()【es6新增】
        > 属性的描述对象

        ```
        //打印出对象p的属性age对应的属性描述符对象
        console.log(Object.getOwnPropertyDescriptor(p,'age'));
        {value: 1, writable: true, enumerable: true, configurable: true}
        //打印出对象p的所有自有属性描述符对象
        console.log(Object.getOwnPropertyDescriptors(p));
        ```
    
    - defineProperty() 和 defineProperties()
        > 用于添加/修改对象属性的描述，vue对象拦截重要原理
        
        ```
        var p={
          firstName:'Lily',
          age:18,
          lastName:'Li',
        }
        Object.defineProperty(p,'age',{
          enumerable:false
        });
        ```
        ```
        Object.defineProperties(p,{
            age:{
              writable: false  //不可修改
            },
            lastName:{
              configurable:false //不可配置
            }
        })
        ```
    - keys() 和 getOwnPropertyNames()
        > keys返回对象可枚举的自有属性数组，getOwnPropertyNames返回的是对象所有自有属性的数组
    
    - values()
        > values返回对象可枚举的自有属性值数组
        
    - entries()（ES6新增）
        > 返回对象可枚举的属性键值对组成的数组
        
    - 对象状态方法
    ```
        Object.preventExtensions()：防止对象扩展。
        Object.isExtensible()：判断对象是否可扩展。
        Object.seal()：禁止对象配置。
        Object.isSealed()：判断一个对象是否可配置。
        Object.freeze()：冻结一个对象。
        Object.isFrozen()：判断一个对象是否被冻结。
    ```
     
##### 2. Array [&](https://www.runoob.com/jsref/jsref-obj-array.html)

###### 数组创建
- Array构造函数
- 数组字面量表示
 
###### 数组使用
- 中括号+索引下标
- length属性设置或返回数组个数
- `Array.isArray()` 进行数组检测 
 
###### 对象方法
- concat()	连接两个或更多的数组，并返回结果。
- copyWithin()	从数组的指定位置拷贝元素到数组的另一个指定位置中。
    ```
    var fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits.copyWithin(2, 0);
    ```
- entries()	返回数组的可迭代对象。
    ```
    var fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits.entries();
    ```
- every()	检测数值元素的每个元素是否都符合条件。
- fill()	使用一个固定值来填充数组。
    ```
    var fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits.fill("Runoob");
    ```
- filter()	检测数值元素，并返回符合条件所有元素的数组。
- find()	返回符合传入测试（函数）条件的数组元素。
- findIndex()	返回符合传入测试（函数）条件的数组元素索引。
- forEach()	数组每个元素都执行一次回调函数。
- from()	通过给定的对象中创建一个数组。
    ```
    var myArr = Array.from("RUNOOB");
    ```
- includes()	判断一个数组是否包含一个指定的值。
- indexOf()	搜索数组中的元素，并返回它所在的位置。
- isArray()	判断对象是否为数组。
- join()	把数组的所有元素放入一个字符串。
- keys()	返回数组的可迭代对象，包含原始数组的键(key)。
- lastIndexOf()	搜索数组中的元素，并返回它最后出现的位置。
- map()	通过指定函数处理数组的每个元素，并返回处理后的数组。
- pop()	删除数组的最后一个元素并返回删除的元素。
- push()	向数组的末尾添加一个或更多元素，并返回新的长度。
- reduce()	将数组元素计算为一个值（从左到右）。
- reduceRight()	将数组元素计算为一个值（从右到左）。
- reverse()	反转数组的元素顺序。
- shift()	删除并返回数组的第一个元素。
- slice()	选取数组的的一部分，并返回一个新数组。
- some()	检测数组元素中是否有元素符合指定条件。
- sort()	对数组的元素进行排序。
- splice()	从数组中添加或删除元素。
- toString()	把数组转换为字符串，并返回结果。
- unshift()	向数组的开头添加一个或更多元素，并返回新的长度。
- valueOf()	返回数组对象的原始值

##### 3. Date [&](https://www.runoob.com/jsref/jsref-obj-date.html)
> 用于处理日期和时间，通过 new Date() 创建对象，结合对象方法获取需要的时间格式

###### 常用方法
- getDate()	从 Date 对象返回一个月中的某一天 (1 ~ 31)。
- getDay()	从 Date 对象返回一周中的某一天 (0 ~ 6)。
- getFullYear()	从 Date 对象以四位数字返回年份。
- getHours()	返回 Date 对象的小时 (0 ~ 23)。
- getMilliseconds()	返回 Date 对象的毫秒(0 ~ 999)。
- getMinutes()	返回 Date 对象的分钟 (0 ~ 59)。
- getMonth()	从 Date 对象返回月份 (0 ~ 11)。
- getSeconds()	返回 Date 对象的秒数 (0 ~ 59)。
- getTime()	返回 1970 年 1 月 1 日至今的毫秒数。
- setDate()	设置 Date 对象中月的某一天 (1 ~ 31)。
- setFullYear()	设置 Date 对象中的年份（四位数字）。
- setHours()	设置 Date 对象中的小时 (0 ~ 23)。
- setMilliseconds()	设置 Date 对象中的毫秒 (0 ~ 999)。
- setMinutes()	设置 Date 对象中的分钟 (0 ~ 59)。
- setMonth()	设置 Date 对象中月份 (0 ~ 11)。
- setSeconds()	设置 Date 对象中的秒钟 (0 ~ 59)。
- setTime()	方法以毫秒设置 Date 对象。

##### 4. RegExp [&](https://www.w3cschool.cn/zhengzebiaodashi/regexp-tutorial.html)
> 描述了一种字符串匹配的模式（pattern），可以用来检查一个串是否含有某种子串、将匹配的子串替换或者从某个串中取出符合某个条件的子串

###### 基础语法
- 组成部分：1、斜杆  2、模式  3、标志
    ```
    var expression = / pattern / flags
    ```
- 创建方式
    - 字面量表达
    - 构造函数初始化
    ```
    new RegExp("表达式", "标志")
    ```

- 标志
    - g：表示在全局范围内匹配，不在发现第一个匹配符后就停止
    - i：表示不区分大小写
    - m：表示多行范围内匹配，达到文末会继续查找下一行

###### 实例属性
- gloal：是否设置了g标志
- ignoreCase：是否设置了i标志
- multiline：是否设置了m标志
- source：返回表达式的字符串
- lastIndex：返回开始搜索下一个匹配字符位置
 
###### 实例方法
- exec()：返回包含第一个匹配项信息的数组
- test()：测试是否存在匹配信息，存在返回true


##### 5. Function 略

##### 6. 基本包装类型
> ECMAScript提供了3个特殊的引用类型:Boolean、Number、String

> 基本包装类型与引用类型的主要区别是对象的生命周期。使用new操作符创建的引用类型的实例，在执行流离开当前作用域之前都一直保存。而自动创建的基本包装类型的对象则只存在于一行代码。

> 只有对象才有属性和方法，为了方便操作基本数据类型，JavaScript 还提供了三个特殊的引用类型。如s1为字符串，当调用 s1.substring(5) 的时候，会先把 s1 包装成 String类型的临时对象，再调用 substring()方法，最后销毁临时对象。

- Number
    - toFixed
    - toExponential 指数表示法
    - toPrecision

- String
    - 字符方法
        - charAt(arg)：返回对应索引位置字符
        - charCodeAt(arg)：区别是返回字符编码
    
    - 字符串方法
        - concat(arg)：字符串拼接，但是用 + 的情况居多
        - slice(arg1, arg2)：返回子串
        - substr(arg1, arg2)：返回子串，arg2表示返回个数
        - substring(arg1, arg2)：返回子串，负值会被转为0

    - 字符串位置方法
        - indexOf(arg)：返回匹配的索引
        - lastIndexOf(arg)：返回匹配的索引，尾部向前搜索
        
    - 字符串去空格
        - trim()
        
    - 字符串大小写转换
        - toLowerCase()
        - toUpperCase()
    
    - 字符串模式匹配方法
        - match(arg)
        - search(arg)
        - replace(arg1, arg2)
        - split(arg)

##### 7. 单体内置对象
- Global
    - encodeURI()、decodeURI()：不对本身就属于URI的符号进行编码解码
    - encodeURIComponent()、decodeURIComponent()
    - eval()

    `还有很多其他的`
    
- Math
    - 可能用到的常量
        - Math.PI
    - 四舍五入的方法
        - Math.ceil()：向上舍入
        - Math.floor()：向下舍入
        - Math.round()：标准舍入
    - 随机数（介于0~1，不包括0/1）
        - Math.random()
    - 其他方法
    
        