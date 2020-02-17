# PHP简介

### PHP是什么？

- PHP（全称：PHP：Hypertext Preprocessor，即"PHP：超文本预处理器"）是一种通用开源脚本语言。
- PHP 脚本在服务器上执行。

即服务器脚本语言。

### PHP 文件是什么？

- PHP 文件可包含文本、HTML、JavaScript代码和 PHP 代码
- PHP 代码在服务器上执行，**结果以纯 HTML 形式**返回给浏览器
- PHP 文件的默认文件扩展名是 ".php"

# PHP语法

### 基本的 PHP 语法

PHP 脚本可以放在文档中的任何位置。

PHP 脚本以 ** 开始，以 **?>** 结束：

```php
<?php
// PHP 代码
?>
```

PHP 文件的默认文件扩展名是 ".php"。

PHP 文件通常包含 **HTML 标签和一些 PHP 脚本代码**。

PHP 中的每个代码行都必须以分号结束。分号是一种分隔符，用于把指令集区分开来。

通过 PHP，有两种在浏览器输出文本的基础指令：**echo** 和 **print**。

### PHP 中的注释

```php
<?php
// 这是单行注释

# 这也是单行注释
/*
这是多行注释
多行注释
多行注释
*/
?>
```

### PHP 变量

PHP 变量规则：

- 变量以 $ 符号开始，后面跟着变量的名称$x=5;
- 变量名必须以字母或者下划线字符开始
- 变量名只能包含字母数字字符以及下划线（A-z、0-9 和 _ ）
- 变量名不能包含空格
- **变量名是区分大小写的**（$y 和 $Y 是两个不同的变量）

```php
<?php
$txt="Hello world!";
$x=5;
$y=10.5;
?>
```

### PHP 是一门弱类型语言

在上面的实例中，我们注意到，不必向 PHP 声明该变量的数据类型。

PHP 会根据变量的值，自动把变量转换为正确的数据类型。

在强类型的编程语言中，我们必须在使用变量前先声明（定义）变量的类型和名称。

|        | 弱类型语言                                | 强类型语言       |
| ------ | ----------------------------------------- | ---------------- |
| 典型   | PHP/Ruby/Python/Perl/SQL/JavaScript/Shell | C/C++/Java/C#    |
| 利弊   | 运行速度快                                | 严谨，能避免错误 |
| 安全性 | 不安全                                    | 安全             |

### PHP 变量作用域

变量的作用域是脚本中变量可被引用/使用的部分。

PHP 有四种不同的变量作用域：

- local

- global：global 关键字用于函数内访问全局变量。在函数内调用函数外定义的全局变量，我们需要在函数中的变量前加上 global 关键字。

  ```php
  <?php
  $x=5;
  $y=10;
   
  function myTest()
  {
      global $x,$y;
      $y=$x+$y;
  }
   
  myTest();
  echo $y; // 输出 15
  ?>
  ```

  

- static:当一个函数完成时，它的所有变量通常都会被删除。然而，有时候您希望某个局部变量不要被删除。

  ```php
  <?php
  
  function myTest()
  {
      static $x=0;
      echo $x;
      $x++;
  }
  
  myTest();
  myTest();
  myTest();
  ?>
  
  输出：
  0 1 2
  ```

  

- parameter：参数是通过调用代码将值传递给函数的局部变量。

### PHP 5 echo 和 print 语句

```php
<?php
$txt1="学习 PHP";
$txt2="RUNOOB.COM";
$cars=array("Volvo","BMW","Toyota");
 
echo $txt1;
echo "<br>";
echo "在 $txt2 学习 PHP ";
echo "<br>";
echo "我车的品牌是 {$cars[0]}";
?>
  
<?php
print "<h2>PHP 很有趣!</h2>";
print "Hello world!<br>";
print "我要学习 PHP!";
?>
```

### PHP EOF(heredoc) 使用说明

PHP EOF(heredoc)是定义一个字符串的方法。

```php
<?php
echo <<<EOF
        <h1>我的第一个标题</h1>
        <p>我的第一个段落。</p>
EOF;
// 结束需要独立一行且前后不能空格
?>
```

### PHP 数组

数组可以在一个变量中存储多个值。

在以下实例中创建了一个数组， 然后使用 PHP var_dump() 函数返回数组的数据类型和值：

```php
<?php 
$cars=array("Volvo","BMW","Toyota");
var_dump($cars);
?>
```

### PHP 对象

对象数据类型也可以用于存储数据。

在 PHP 中，对象必须声明。

首先，你必须使用class关键字声明类对象。类是可以包含属性和方法的结构。

然后我们在类中定义数据类型，然后在实例化的类中使用数据类型：

```php
<?php
class Car
{
  var $color;
  function __construct($color="green") {
    $this->color = $color;
  }
  function what_color() {
    return $this->color;
  }
}
?>
```

### PHP 类型比较

- 松散比较：使用两个等号 **==** 比较，只比较值，不比较类型。
- 严格比较：用三个等号 **===** 比较，除了比较值，也比较类型。



### 设置 PHP 常量

设置常量，使用 define() 函数，函数语法如下：

```php
bool define ( string $name , mixed $value [, bool $case_insensitive = false ] )
例子：
<?php
// 不区分大小写的常量名
define("GREETING", "欢迎访问 Runoob.com", true);
echo greeting;  // 输出 "欢迎访问 Runoob.com"
?>
```

该函数有三个参数:

- **name：**必选参数，常量名称，即标志符。
- **value：**必选参数，常量的值。
- **case_insensitive** ：可选参数，如果设置为 TRUE，该常量则大小写不敏感。默认是大小写敏感的。

### PHP 并置运算符

在 PHP 中，只有一个字符串运算符。

并置运算符 (.) 用于把两个字符串值连接起来。

```php
<?php
$txt1="Hello world!";
$txt2="What a nice day!";
echo $txt1 . " " . $txt2;
?>
```

输出Hello world! What a nice day!

### PHP strlen() 函数

```php
<?php
echo strlen("Hello world!");
?>
```

### PHP strpos() 函数

strpos() 函数用于在字符串内查找一个字符或一段指定的文本。

如果在字符串中找到匹配，该函数会返回第一个匹配的字符位置。如果未找到匹配，则返回 FALSE。

```php
<?php
echo strpos("Hello world!","world");
?>
输出 6
```

### PHP - if...else 语句

```php
<?php
$t=date("H");
if ($t<"20")
{
		echo "Have a good day!";
}
else
{
		echo "Have a good night!";
}
?>
```

### PHP 数组

在 PHP 中，array() 函数用于创建数组：

##### 获取数组的长度 - count() 函数

```php
<?php
$cars=array("Volvo","BMW","Toyota");
echo "I like " . $cars[0] . ", " . $cars[1] . " and " . $cars[2] . ".";//.并置运算符
echo count($cars);
//遍历数值数组
for($i=0;$i<count($cars);$i++)
{
  echo $cars[$i];
  echo "<br>";
}
?>
```

### PHP 关联数组

```php
这里有两种创建关联数组的方法：
$age=array("Peter"=>"35","Ben"=>"37","Joe"=>"43");
或者：
$age['Peter']="35";
$age['Ben']="37";
$age['Joe']="43";
```

### 遍历关联数组

遍历并打印关联数组中的所有值，您可以使用 foreach 循环，如下所示：

```php
<?php
$age=array("Peter"=>"35","Ben"=>"37","Joe"=>"43");
 
foreach($age as $x=>$x_value)
{
    echo "Key=" . $x . ", Value=" . $x_value;
    echo "<br>";
}
?>
```

### PHP 数组排序

- sort() - 对数组进行升序排列
- rsort() - 对数组进行降序排列

### PHP 超级全局变量

PHP中预定义了几个超级全局变量（superglobals） ，这意味着它们在一个脚本的全部作用域中都可用。 你不需要特别说明，就可以在函数及类中使用。

PHP 超级全局变量列表:

- ```php
  - $GLOBALS
  - $_SERVER
  - $_REQUEST
  - $_POST
  - $_GET
  - $_FILES
  - $_ENV
  - $_COOKIE
  - $_SESSION
  ```

  

## PHP 魔术常量

PHP 向它运行的任何脚本提供了大量的预定义常量。

不过很多常量都是由不同的扩展库定义的，只有在加载了这些扩展库时才会出现，或者动态加载后，或者在编译时已经包括进去了。

有**八个魔术常量**它们的值随着它们在代码中的位置改变而改变。

### __LINE__

文件中的当前行号。

```php
<?php
echo '这是第 " '  . __LINE__ . ' " 行';
?>
```

### __FILE__

文件的完整路径和文件名。如果用在被包含文件中，则返回被包含的文件名

```php
<?php
echo '该文件位于 " '  . __FILE__ . ' " ';
?>
```

### __DIR__

文件所在的目录。如果用在被包括文件中，则返回被包括的文件所在的目录。

```php
<?php
echo '该文件位于 " '  . __DIR__ . ' " ';
?>
```

### __FUNCTION__

函数名称（PHP 4.3.0 新加）。自 PHP 5 起本常量返回该函数被定义时的名字（区分大小写）。

```php
<?php
function test() {
    echo  '函数名为：' . __FUNCTION__ ;
}
test();
?>
```

### __CLASS__

类的名称（PHP 4.3.0 新加）。

### __TRAIT__

Trait 名包括其被声明的作用区域（例如 Foo\Bar）。

### __METHOD__

类的方法名（PHP 5.0.0 新加）。返回该方法被定义时的名字（区分大小写）。

### __NAMESPACE__

当前命名空间的名称（区分大小写）。此常量是在编译时定义的（PHP 5.3.0 新增）。

