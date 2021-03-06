# 计算机进制转换

- 十进制转二进制，除二取余法
- 二进制转十进制，8421法

# 计算机存储单元

- 8 bit（位）= 1Byte（字节），字节是计算机中的基础存储单位

# 常量

- 字符串常量
- 整数常量
- 浮点数常量
- 字符常量
- null 空常量
- 布尔常量 true   false

# 数据类型

| 类型     |              | 关键字      | 大小（内存占用） | 取值范围                     |
| -------- | ------------ | ----------- | ---------------- | ---------------------------- |
| 整数类型 | 字节型       | byte        | 1字节            | -128~127                     |
|          | 短整型       | short       | 2字节            |                              |
|          | 整型         | int（默认） | 4字节            |                              |
|          | 长整型       | long        | 8字节            |                              |
| 浮点型   | 单精度浮点数 | float       | 4字节            |                              |
|          | 双精度浮点数 | long        | 8字节            |                              |
| 字符型   | 字符类型     | char        | 2字节            | 0~65535 （理论上可以存汉字） |
| 布尔型   | 布尔类型     | boolean     | 1字节            | true  false                  |
|          |              |             |                  |                              |

- 数据范围与存储自觉书不一定相关，比如4个字节的float能存的比8位的long多
- 浮点数只能是一个近似值，并非精确的值
- 使用后缀F L 表示这个数不少默认情况下的float 和 int

# 数据类型转换

- 自动类型转换（隐式）
  - 数据范围从小到大，**与字节数不一定相关**

- 强制类型转换（显式）
  - byte short char 和三种数据类型都可以发生数学运算，
  - 一旦char类型在运算的时候会先提升为**int****类型再进行计算**
  - 布尔类型不能发生任何数据类型转换

- ASCII 码表 （美国信息交换标准码） Unicode码表（万国码）
  - ‘0’   48			'A' 65    'a' 97

# 运算符

- 四则运算 取模 自增 自减
- 常量不可以使用 自增和自减
- 常量不能卸载复制运算符的左边
- 符合运算符自动进行强制类型转换

## 注意

- 算术运算符在操作的时候，byte short 会自动提升为 int 之后计算，所以等号左侧接收的类型是int
- 如果编码的时候，等号右边全是常量，编译为class 文件之后，会直接变成结果。例如 

int a = 3 + 4 ，在字节码中会直接是 int a = 7  编译器 javac 的常量优化

# 方法的调用

- 单独调用
- 打印调用
- 赋值调用

找到方法--》传递参数--》执行方法体--》返回结果

# 数组初始化

- 动态初始化，初始化长度
- 静态初始化，指定内容

# java 的内存划分

java内存分为五个部分

|                     |            |                                                              |                                                              |
| ------------------- | ---------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| stack               | 栈         | 存储方法中的局部变量，一旦超出作用域，立刻会从占内存中消失   |                                                              |
| Heap                | 堆         | new 出来的东西都在堆内存中，堆内存中的东西都有一个 16 进制的地址值 | 堆内存中的数据都有默认值<br />整型：0<br />浮点型：0.0<br />布尔型：false<br />字符型：'\u0000'<br />引用数据类型：null |
| Method Aera         | 方法区     | 存储.class 相关信息，包含方法的信息（真正方法运行会在 栈 中） |                                                              |
| Native Method Stack | 本地方法栈 | 与操作系统相关                                               |                                                              |
| pc Register         | 寄存器     | 与CPU相关                                                    |                                                              |

[数组在内存中的创建于改变](https://www.bilibili.com/video/BV1Yb411z7PG?p=85)

[一个对象的创建和使用](https://www.bilibili.com/video/BV1Yb411z7PG?p=102)

# 成员变量和局部变量

- 作用域不同
- 定义位置不同
- 默认值不同，成员变量是有默认值得，局部变量是没有默认值的，需要赋值，才能使用。
- 内存位置不一样，局部变量随着方法走，位于栈内存，成员变量位于堆内存
- 生命周期不一样，局部变量随着方法进栈而产生，方法出栈而销毁，成员变量随着对象创建而创建，随着对象销毁而被回收

形参在方法中调用，必然会赋值



# 封装

- 方法本身就是一种封装
- private 也是一种封装，一旦定义了private 修饰，本类当中可以直接访问，一旦超出范围，就不可以直接访问了。
- 当方法的局部变量和类的成员变量重名的情况下，根据就近原则，优先使用局部变量
- this 通过谁调用的方法，谁就是this ，this 主要起到在重名的情况下，起到区分的效果。

# 字符串String

- 字符串内容，用不可变
- 因为字符串不可变，所以共享使用
- 字符串效果上看上去像是char[] ，但实际上存储的时候是byte[]

- 字符串构造方法3+1
  - public String（）创建的是一个空字符
  - public String（char[]）穿进去一个字符数组
  - public String（byte[]）传递进去一个字节数组
- 直接使用双引号创建字符串，这样创建的字符串都放在 字符串常量池当中
- 调用equals的时候 要把常量放在前面

[字符串在内存中](https://www.bilibili.com/video/BV1Yb411z7PG?p=135)

# static

- 只在类中保存一份，所有的本类对象共享同一份
- 静态不能直接访问非静态，因为在内存当中现有的静态后有的 非静态，静态方法不能使用this，因为静态方法属于类，和对象没关系。

[静态内存图](https://www.bilibili.com/video/BV1Yb411z7PG?p=146)

- 静态代码块: 当第一次用到本类的时候，静态代码块执行唯一的一次。静态代码块用来对静态成员变量进行一次性的赋值。