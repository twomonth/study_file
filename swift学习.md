# 基础

- 声明常量、变量

`let maximumNumberOfLoginAttempts = 10`

`var currentLoginAttempt = 0`

- 给变量提供类型注释 

`var welcomeMessage: String`

- 常量和变量名称不能包含空格字符，数学符号，箭头，专用的Unicode标量值或线条和框形图字符。它们也不能以数字开头，尽管数字可能包含在名称中的其他位置

- 有符号整数类型 Int、无符号整数类型UInt 会因为操作系统不一样而整数范围不一样
- `Double` 表示64位浮点数。如果您没有为浮点文字指定类型，Swift会推断您要创建一个`Double`
- `Float` 代表32位浮点数。

`所有这些整数文字的十进制值为`17`：

`let decimalInteger = 17`

`let binaryInteger = 0b10001       // 17 in binary notation`

`let octalInteger = 0o21           // 17 in octal notation`

`let hexadecimalInteger = 0x11     // 17 in hexadecimal notation`

- 布尔值

Swift具有一个基本的*布尔*类型，称为`Bool`。布尔值被称为*逻辑*值，因为它们只能是true或false。Swift提供了两个布尔常量值，`true`以及`false`：

`let orangesAreOrange = true`

`let turnipsAreDelicious = false`

- 元组

`let http404Error = (404, "Not Found")`

`let (statusCode, statusMessage) = http404Error`

`print("The status code is \(statusCode)")`

`// Prints "The status code is 404"`

`print("The status message is \(statusMessage)")`

`// Prints "The status message is Not Found"`

`如果只需要一些元组的值，则_在分解元组时，请用下划线（）忽略元组的某些部分：`

`let (justTheStatusCode, _) = http404Error`

`print("The status code is \(justTheStatusCode)")`

`// Prints "The status code is 404"`

`或者，使用从零开始的索引号访问元组中的各个元素值：`

`print("The status code is \(http404Error.0)")`

`// Prints "The status code is 404"`

`print("The status message is \(http404Error.1)")`

`// Prints "The status message is Not Found"`

`定义元组时，可以命名元组中的各个元素：`

`let http200Status = (statusCode: 200, description: "OK")`

`如果在元组中命名元素，则可以使用元素名称来访问这些元素的值：`

`print("The status code is \(http200Status.statusCode)")`

`// Prints "The status code is 200"`

`print("The status message is \(http200Status.description)")`

`// Prints "The status message is OK"`

