# Swift新特性介绍（一） 语言基础中的新特性#
---
## 常量和变量的命名 ##

Swift可以使用几乎任何字符来作为常量和变量名，包括Unicode：

    let π = 3.14159
    let 你好 = "你好世界"
    let 星星 = "★"

## 注释可嵌套 ##

Swift中的多行注释`/**/`可以嵌套，这样可以方便地在大段已注释的代码块中继续添加注释：

    /* this is the start of the first multiline comment
    /* this is the second, nested multiline comment */
    this is the end of the first multiline comment */

## 数量表示 ##

浮点数12.1875可以表示为：

    let decimalDouble= 12.1875
    let exponentDouble= 1.21875e1

数字可以包含额外的下划线`_`，增加代码的可读性，但是不影响代码的运行：

    let paddedDouble= 000123.456
    let oneMillion= 1_000_000
    let justOverOneMillion= 1_000_000.000_000_1

## 元组类型 ##

Swift中可以定义元组类型，将一些不同的数据封装成一个元素，并且还可以作为函数值返回：

    let (statusCode, statusMessage) = http404Error
    println("The status code is \(statusCode)")
    // prints "The status code is 404"
    println("The status message is \(statusMessage)")
    // prints "The status message is Not Found"

如果仅需要元组中的个别值，可以使用`_`来忽略其他值：

    let (justTheStatusCode, _) = http404Error
    println("The status code is \(justTheStatusCode)")
    // prints "The status code is 404"

元组的赋值：

    let (x, y) = (1, 2)
    // x等于1, 并且y等于2

## 可选类型(Optional Type) ##

简单来讲这种类型可以是一个特定的值，或者为空。使用`类型+?`的形式来定义：

    let possibleNumber = "123"
    let convertedNumber = possibleNumber.toInt()
    // convertedNumber is inferred to be of type "Int?", or "optional Int"

更多关于可选类型，`?`和`!`的问题，可以参考：[Swift中的问号?和感叹号!](http://letsswift.com/2014/06/swift-questionmark-exclamatorymark/)

## 浮点数的余数运算 ##

Swift中浮点数也可以进行余数运算：

    8 % 2.5 // equals 0.5

## 范围运算符 ##

使用`a...b`定义一个封闭范围，从a到b包括a和b的所有值

    for index in 1...5 {
    println("\(index) times 5 is \(index * 5)")
    }
    // 1 times 5 is 5
    // 2 times 5 is 10
    // 3 times 5 is 15
    // 4 times 5 is 20
    // 5 times 5 is 25

使用`a..b`定义左闭右开区间，从a到b，包括a但是不包括b的所有值

    let names = ["Anna", "Alex", "Brian", "Jack"]
    let count = names.count
    for i in 0..count {
    println("Person \(i + 1) is called \(names[i])")
    }
    // Person 1 is called Anna
    // Person 2 is called Alex
    // Person 3 is called Brian
    // Person 4 is called Jack

## Switch语句 ##

Swift中的`switch`语句不会在`case`语句后面因为没有`break`而自动跳转到下一个`case`。

另外`case`语句还可以完成范围匹配，元组匹配，使用where关键词等。具体使用方法可以参考：[Swift中文教程（五）控制流](http://letsswift.com/2014/06/control-flow/)

---
翻译工作已告一段落，校对工作继续进行中~ 欢迎参与~

校对地址：[https://github.com/letsswift/The-Swift-Programming-Language-in-Chinese](https://github.com/letsswift/The-Swift-Programming-Language-in-Chinese)

Swift新特性学习系列文章更新中

本文由LetsSwift.com原创发布

转载请注明本文原始链接：[http://letsswift.com/2014/06/swift-new-features-one/](http://letsswift.com/2014/06/swift-new-features-one/)