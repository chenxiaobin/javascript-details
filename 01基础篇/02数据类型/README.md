> 本章包含：基本数据类型、引用类型等相关内容

### 数据类型
> 值类型：Undefined、Null、Boolean、Number、String、Symbol（ES6新增） \
> 引用类型：Object、Array、Function、Date、RegExp、基本包装类型、单体内置对象

`注：Symbol是ES6引入了一种新的原始数据类型，表示独一无二的值`

##### typeof操作符
> 用来检测给定变量的数据类型 `typeof 变量名`

可能返回一下类型结果：
- undefined
- boolean
- string
- number
- object
- function
 
#### 值类型

##### 1. Undefined
> 未定义的变量或者定义了未初始化变量，会得到一个undefined值

##### 2. Null
> 代表什么都没有，null和undefined最大区别是如果变量为null，说明变量存在，只是值为空值null

##### 3. Number
> 包括浮点数和整数

`注意：永远不要测试某个特定浮点数值`


特殊数值类型：
- NaN
    - 表示不是数字
    - NaN参与的任何运算，结果都为NaN
    - 与任何值都不相等
- Infinity
    - 数据超过了js可以表示的范围
    - Infinity参与的任何运算，结果都是Infinity
    - 数值除以0得到Infinity
- 数值判断函数
    - isNaN()：判断是否为NaN的唯一方式
    - isFinite()：如果为NaN或Infinity返回true


##### 4. Boolean
> 包括true和false两个值，区分大小写，True和Flase只是标识符

false值的几个情况：
- 数值0
- NaN
- 空字符串
- false
- undefined
- null


##### 5. String
> 多个字符的有序序列，单双引号引起来的都是字符串

- 转义字符
    - \n \t \b \r \\ ...

- 字符串特点
    - 字符串相加，等于拼接
    - 字符串加数值，首先将数值转化为响应的字符串然后参与运算
    - 不支持- * / 等运算
    - 除了null和undefined，都存在toString()
    - 若不知道数值类型，可以通过String()转换


##### 6. Symbol（es6新增）


#### 引用类型

##### 1. Object
