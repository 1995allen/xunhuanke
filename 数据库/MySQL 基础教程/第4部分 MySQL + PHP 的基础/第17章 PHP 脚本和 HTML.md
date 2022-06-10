
# 17.1 HTML 源代码

- 源代码
  - 是一个 HTML 文件
  - 由 \<html> 或 \<a ~ /a> 等用 “\<>” 括起来的字符组成
  - “\<>” 括起来的对象称为标签（tag），表示在这里显示 XX 内容，在这里显示 XX 的图片等命令
- HTML 文件
  - 是按照 HTML 规则制作的文本文件
  - 浏览器只会按照从 Web 服务器发来的 HTML 文件的命令来配置一起发来的文字和图像

# 17.2 制作 Web 页面的两种方法

- 在编辑器中直接输入标签，或者使用网页制作软件制作标签
- 通过 PHP 脚本等程序编写标签

## 17.2.1 制作静态 Web 页面

- Web 页面只会显示标签指定的内容

## 17.2.2 制作动态 Web 页面

- 通过 PHP 脚本等程序间接地输出显示内容
- 显示的内容会根据条件发生改变的 Web 页面称为动态 Web 页面

## 17.2.3 浏览器不区分静态页面和动态页面

- 目标是将与 MySQL 交互结果制作成 Web 页面并将其发送回客户端
- 交互的结果并不总是一样
- 需要使用 PHP 脚本操作 MySQL，然后通过 PHP 脚本接收 MySQL 发送的结果，动态制作 Web 页面

# 17.3 HTML 的规则

- HTML 文件的扩展名为 .html，如果包含 PHP 脚本则为 .php
- 标签的写法
  - 通过编写 \<html> 之类的标签来制作 Web 页面
  - 大多数标签会包含开始标签和结束标签，加上二者之间夹杂的字符串后，整个部分称为元素
  - `<a href="url地址"> 连接的字符串 </a>`
- HTML 文件的结构

```html
<!DOCTYPE html>             // 文档类型声明
<html>                      // 使用 <html> </html> 将整个文档括起来，并在其中编写 head 元素和 body 元素
    <head>
        编写页面标题和链接的关系等   // 页面标题
    </head>
    <body>
        编写作为 Web 页面显示的主体 // 页面主体
    </body>
</html>
```

- 示例

```html
<!DOCTYPE html>
<html>
    <head>
    <title> SQL 咖啡厅的页面 </title>
    </head>

    <body>
    欢迎光临 SQL 咖啡厅！
    </body>
</html>
```

- 用 "" 和 '' 将属性括起来
  - `<a href="http://www.ituring.com.cn/"> 跳转到图灵社区 </a>`
  - \<a> ~ \</a> 之间编写的是作为链接显示的字符串
  - 链接的地址要在 \<a> 标签的 href 属性中指定
  - a 和 href 之间要加一个半角空格

# 17.4 使用 PHP 脚本输出 HTML 文件

- PHP 中需要使用 print 或 echo 动态编写 HTML 标签时，输出的标签本身也需要用 "" 或 '' 括起来
  - `print "<a href='http://www.ituring.com.cn/'> 跳转到图灵社区 </a>"`
  - 需要注意避免 "" 包裹 "" 的情况，'' 同理
- 本书的示例
  - 基本没有编写标签
  - 但是工作中创建 Web 应用程序，不能省略

# 17.5 需要记住的标签

- \<br>
  - 用于换行
  - 在 HTML 文件中不管键入多少 Enter，浏览器显示的内容都不会改变，要换行，必须使用此标签
- \<hr>
  - 用于分隔段落
  - 现在浏览器一般会生成水平线
- \<img>
  - `<img sec="图片文件的URL" alt="替代的文字">`
  - `print "<img src='pic/father.gif' alt='爸爸的插图'>"`
  - pic 文件夹中的图片会被显示出来
  - alt 属性用于指定当不能显示图片时，显示的文本内容
- \<meta>
  - 用于设置页面信息
  - 如 搜索引擎的关键词、在搜索结果中现实的文章、自动跳转到的页面等，字符编码
  - \<meta> 标签需要记述在 \<head> 和 \</head> 标签之间
  - `<meta charset="字符编码">`

# 17.6 使用 CSS 指定颜色和字体大小

- 在 HTML5 中需要使用 CSS (Cascading Style Sheet 层叠样式表)设置背景和字符的颜色、大小等与样式相关的内容

## 17.6.1 指定背景的颜色

- 需要按照 “属性:值” 的语法来编写 CSS
- `<body style = "background-color:aqua">`
- CSS 中的颜色都是用颜色的全称或 RGB值（16进制值）来指定

|颜色|全称|RGB值|
|黑色|black|#000000|
|海军蓝|navy|#000080|
|蓝色|blue|#0000ff|

## 17.6.2 指定字符的大小和颜色

- 可以通过使用 \<div> 或者 \<p> 标签指定 style 属性来设置整个段落的字符颜色和字体大小
- color 属性用于设置字符颜色， font-size 属性用于设置字体大小
- \<div> 或者 \<p> 都用于将括起来的范围定义为块，不过区别在于 \<p> 可以在块的前后空出一行， \<div> 不行
  - `print "<div style='color:blue; font-size:35pt'>";`
- 可以使用 \<span> 对同一行的一部分字符串进行设置
  - `print "这是SQL咖啡厅的<span style='font-size:50pt'>公告板</span>哦";`

# 17.7 Here Document 和 nl2br 函数

- 使用 PHP 脚本编写 Web 页面意味着要使用 print 或 echo 将 HTML 标签作为文本输出

## 17.7.1 什么是 Here Document

- Here Document
  - 能够将 “<<<表示结束的字符串 到 表示结束的字符;” 之间的内容作为一连串的字符串进行处理
  - 在 `<<<eot` 和 `eot;` 之间输入 HTML 标签的内容即可
- 示例

```php
<?php
$mozi=<<<eot
<!DOCTYPE html>
<html>
<head>
<title> 跳转到图片社区的链接 </title>
</head>
<body>
<a href='http://ituring.com.cn'>跳转到图灵社区</a>
</body>
</html>
eot;
print $mozi;
?>
```

## 17.7.2 什么是 nl2br 函数

- nl2br
  - 在每个新行之前插入换行符

```php
<?php
$str=<<<eot
你好
晚上好
eot;
print nl2br ($str);
?>
```

[[专栏]] \<textarea> 标签

- 用于设置可输入多行字符串的文本区域
- 当输入到改标签内的字符串执行换行处理时
- nl2br 函数就会发挥作用

# 17.8 使用 PHP 从浏览器发送和接收数据

## 17.8.1 浏览器和 PHP 文件之间的数据交换

- 浏览器操作 MySQL 时，数据如何交换
  - 1 用户从浏览器显示的 Web 页面上发送数据
  - 2 Web 服务器上的 PHP 文件接收数据
  - 3 PHP 脚本与 MySQL 数据库进行交互
  - 4 PHP 脚本输出包含结果的 Web 页面，并将其发送回浏览器
  - 5 浏览器接收结果
- HTML 文件与 PHP 脚本之间如何进行数据交换
  - 数据的发送方
    - HTML 文件 send.html
    - 通过点击发送按钮来发送输入到文本框中的字符串
  - 数据的接收方
    - PHP 文件 receive.php
    - 按照原样显示接收的数据
  - 两个文件都保存在 Web 服务器发布的文件夹中

## 17.8.2 制作一个用于发送数据的 Web 页面 send.html

- 点击按钮，文本框中输入的数据就会发送出去
  - 组件有两个
    - 按钮
    - 文本框

```HTML
<form method="POST" action="receive.php">
<input type="text" name="a">
<div>
    <input type="submit" value="发送">
</div>
</form>
```

- \<form>
  - 用于创建表单
  - 使用 \<input> 等标签设置文本框和按钮

```HTML
<form method="发送方法" action="目标地址">
    在这里编写 <input> 等标签，设置按钮和文本框
</form>
```

- \<input>
  - `<input type="种类的按钮" name="用于识别数据的元素名称" size="大小" value="显示的字符" 和 "发送的值" "默认值">`

- input 标签中可以设置的主要属性

|属性|内容|
|:----|:----|
|type|编写用于指定组件种类的字符串|
|name|设置要附加到组件的元素名称，该名称用于识别数据|
|size|设置文本框的宽度|
|value|当字符串显示在按钮等地方时，设置字符串内容|

- type 属性的设置

|描述|可设置的组件种类|
|:----|:----|
|type='submit'|可以发送数据的按钮|
|type='button'|按钮|
|type='text'|文本框|
|type='checkbox'|复选框|
|type='radio'|单选按钮|
|type='hidden'|隐藏（仅发送数据）|

- type='hidden'
  - 主要用于强制发送不需要向用户显示的数据

- 确认创建的表单
  - `<form method='POST' action='receive.php'`
    - 点击发送按钮，会将数据发送给名为 receive.php 的 PHP 脚本
    - 会采用 POST 的方式发送数据
  - `<input type='text' name='a'>`
    - type 属性为 text 会创建一个文本框
    - name 属性为 a
    - 因此接收数据的 PHP 脚本会以 a 这个名字来识别数据
  - `<input type='submit' value='发送'>`
    - type 属性是 submit ，设置的是可以发送数据的按钮
    - value 属性为 “发送”，按钮上会显示这个值

## 17.8.3 创建 receive.php 以接收和显示数据

- 采用 POST 方法发送的数据会被变量 $_POST 接收
  - `$_POST ["用于识别数据的元素名称"]`
  - $_POST 是 PHP 中预定义的变量名，POST 发送的数据会作为数组保存在这个变量中
  - $_POST 可以当做关联数组使用，数组下标指定用于识别数据的元素名称
  - 文本框中附加了 a 这个用于识别数据的元素名称 因此 receive.php 中，如果指定了 “a” 为关联数组的下标，那么只要将变量缩写为 $_POST["a"] 就可以接收发送的数据

[[专栏]] 超级全局变量

- 像 $_POST 这种不需要进行声明，可以用在程序任何的地方的变量，称为 *超级全局变量*
- GET 方法中使用 $_GET，使用 Cookie 时会用到 $_COOKIE 等都属于超级全局变量

## 17.8.4 发送和接收数据

- 略

# 17.9 通过 POST 和 GET 发送数据

## 17.9.1 发送和接收数据

- POST
  - 数据不在 URL 中
  - 可以发送文本或二进制格式的数据
- GET
  - 将数据添加到 URL 中发送（数据可见，可能会发送非法数据）
  - 只可以发送文本格式的数据
  - 如果没有进行任何声明，将使用 GET 方法（默认）

## 17.9.2 使用 GET 方法发送数据

- method 需修改为 GET
- $_POST 需修改为 $_GET
- URL 中会出现 `localhost/get_receive.php?a="输入的字符"`

## 17.9.3 GET 和 POST 的区别

- 当使用 POST 方法发送数据，地址栏上只会显示 `http://localhost/receive.php`
- GET 发送时，数据是作为 URL 的一部分发送的
- 当使用 GET 方法时，地址栏上显示的内容 `URL? 数据名称 = 数据`

## 17.9.4 试着用 GET 方法将值添加在 URL 上发送

- 略

## 17.9.5 在不进行任何声明的情况下发送数据

- 在不进行任何声明的情况下发送数据，会自动使用 GET 方法发送

[[专栏]] Google 是否也可以把数据添加在 URL 上

- 可以
- `http://www.google.com/search?q=abcde`
- 输入此链接，等同于在 google 上进行了 abcde 的搜索

# 17.10 [[总结]]

- 介绍的内容
  - 动态 Web 页面和静态 Web 页面的区别
  - HTML 基础标签的编写方法
  - 从 Web 页面发送数据的方法，以及 PHP 脚本中处理内容及流程
  - 创建表单发送数据的方法
  - 数据的发送方法
- 自我检查
  - 略
- 练习题

```PHP
<form method="POST" action="radio_receive.php">
请选择您的年龄，然后点击“发送”按钮。<br>

<?php
$i=1;
$c=1;
print "<div>";
while($i<=100){
print "<input type='radio' name='r' value='$i'>$i ";
if($c==10){
print "</div><div>";
$c=0;
}
$i++;
$c++;
}
?>

<input type="submit" value="发送">
</div>
</form>
```
