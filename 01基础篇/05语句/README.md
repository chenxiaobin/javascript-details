#### 语句
- if、else if、else
- do-while
    > 后测试循环语句，即只有在循环体中的代码执行之后，才测试出口
    ```
    var i = 0;
    do {
        i += 2
    } while (i < 10)
    ```
- while
    > 前测试循环语句
    ```
    var i = 0
    while (i < 10) {
        i += 2
    }
    ```
- for
    ```
    for (statement 1; statement 2; statement 3) {
        code block to be executed
    }
    ```
- for-in
    > 精准的迭代语句，可以用来枚举对象的属性
    ```
    for (var propName in window) {
        document.write(propName)
    }
    ```
- label
    > 可以精确的返回到你想要的程序的位置

    > 举一个比较典型的例子，看完后即明白 Label 的应用：（未添加 Label）
    
    ```
    var num = 0;
    for (var i = 0 ; i < 10 ; i++){
        for (var j = 0 ; j < 10 ; j++){
            if( i == 5 && j == 5 ){
                break;
            }
            num++;
        }
    }
    alert(num); 
    // 循环在 i 为5，j 为5的时候跳出 j循环，但会继续执行 i 循环，输出 95
    ```
    > 对比使用了 Label 之后的程序：（添加 Label 后）
    
    ```
    var num = 0;
    outPoint:
    for (var i = 0 ; i < 10 ; i++){
        for (var j = 0 ; j < 10 ; j++){
            if( i == 5 && j == 5 ){
                break outPoint;
            }
            num++;
        }
    }
    alert(num); 
    // 循环在 i 为5,j为5的时候跳出双循环，返回到outPoint层继续执行，输出 55
    ```
- break、continue
    - break: 立即退出循环，强制执行循环后面的语句
    - continue: 立即退出循环，但是退出循环后从循环顶部继续执行
- with
    > 不去使用就对了

    - 性能低
    - 不可预测
    - 无法优化
    
- switch

    ```
    switch(表达式) {
     case n:
        代码块
        break;
     case n:
        代码块
        break;
     default:
        默认代码块
    }
    ```
