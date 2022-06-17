
# 19.1 制作一个简易公告板

## 19.1.1 简易公告板的结构

- 公告板只会连接到数据库执行显示记录、写入姓名和消息、删除记录、查询记录这4个简单的处理

## 19.1.2 创建数据库和表

- 创建用于 Web 程序中进行操作的表
- `CREATE TABLE tbk (empid INT AUTO_INCREMENT PRIMARY KEY, name VARCHAR(10), mess VARCHAR(100));`

## 19.1.3 简易公告板的文件结构

- 本章示例
  - 创建以下 PHP 脚本文件 MAMP/htdocs 文件夹中
    - simple_select.php 显示记录
    - simple_insert.php 插入记录
    - simple_delete.php 删除记录
    - simple+search.php 查询记录
    - simple.html 执行上面的4个脚本

# 19.2 创建首页

## 19.2.1 调用消息显示脚本的表单

- 创建一个表单，用于调用显示表 tbk 中所有记录
- 发送数据方式均为 POST
- 具有提交按钮

```PHP
<form method="POST" action="simple_select.php">
<div> 显示消息 </div>
<input type="submit" value="显示消息">
</form>
```

## 19.2.2 调用插入脚本的表单

- 针对 form 标签，只修改相应 PHP 文件的指定部分
- 对用于输入信息的文本框，可以设置 size 属性来规定其大小

```php
<form method="POST" action="simple_insert.php">
<div>
输入姓名<input type="text" name="xingming">
</div>
<div>输入消息<input type="text" name="xiaoxi" size=150></div>
<input type="submit" value="发送消息">
</form>
```

## 19.2.3 调用删除脚本的表单

```php
<form method="POST" action="simple_delete.php">
<div>输入要删除的编号<input type="text" name="shanshu"></div>
<input type="submit" value="发送删除编号">
```

## 19.2.4 调用查询脚本的表单

```php
<from method="POST" action="simple_search.php">
<div>输入查询的关键字<input type="text" name="chaxun"></div>
<input type="submit" value="查询">
</form>
```

## 19.2.5 创建首页

- simple.html

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
    </head>

    <body>
        <p>
            <form method="POST" action="simple_select.php">
            <div> 显示消息 </div>
            <input type="submit" value="显示消息">
            </form>
        </p>

        <p>
            <form method="POST" action="simple_insert.php">
            <div>输入姓名<input type="text" name="xingming"></div>
            <div>输入消息<input type="text" name="xiaoxi" size=150></div>
            <input type="submit" value="发送消息">
            </form>
        </p>

        <p>
            <form method="POST" action="simple_delete.php">
            <div>输入要删除的编号<input type="text" name="shanshu"></div>
            <input type="submit" value="发送删除编号">
        </p>

        <p>
            <from method="POST" action="simple_search.php">
            <div>输入查询的关键字<input type="text" name="chaxun"></div>
            <input type="submit" value="查询">
            </form>
        </p>
    </body>
</html>
```

# 19.3 创建分别具有显示、插入、删除和查询功能的 PHP 脚本

## 19.3.1 4个脚本的共通之处

- 这 4 个 PHP 脚本中都包含连接数据库和显示当前所有记录的处理

## 19.3.2 用于显示记录的 PHP 脚本

## 19.3.3 用于插入记录的 PHP 脚本

## 19.3.4 用于删除记录的 PHP 脚本

## 19.3.5 用于查询记录的 PHP 脚本

## 19.3.6 确认 4 个文件的运行结果

[[专栏]] 在公告板上输入标签的技巧

# 19.4 总结
