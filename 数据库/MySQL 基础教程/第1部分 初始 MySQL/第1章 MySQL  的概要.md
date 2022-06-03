
# 1.1 数据库的概要

## 1.1.1 数据库是什么

- 只有具备了有效运用这些数据的管理功能，才能称为数据库

## 1.1.2 关系数据库是什么

- 管理关系数据库的系统称为 RDBMS (Realational DataBase Managenment System, 关系数据库管理系统)
- MySQL 也是 RDBMS 的一种- RDBMS 是以 IBM 公司的 埃德加·弗兰克·科德（Edgar F.Cold）于 1970 年发表的关系数据库相关论文为基础发展起来的

## 1.1.3 数据库的特征

> “**只能按照决定好的规则来操作，并且严格地进行管理**”的特征，正是数据库值得信赖的原因

# 1.2 MySQL 是什么样的数据库

## 1.2.1 MySQL 是开源软件

- 主流数据库

|名称|特征|
|:----|:----|
|Oracle|世界上最常用的商用 RDBMS|
|Access|微软公司 Office 系列的 RDBMS|
|Microsoft SQL Server|微软公司的商用 RDBMS|
|PostgreSQL|和 MySQL 一样是开源的 RDBMS,在日本很受欢迎|
|MySQL|世界上最常用的开源 RDBMS|

> Google 正从 MySQL 向 MariaDB 进行切换（2017年6月）

## 1.2.2 MySQL 的历史

- MySQL 是米卡埃尔·维德纽斯（Michael Widenius）在1995年开发的 RDBMS。
- 作为开源数据库世界第一的 MySQL 和作为商用数据库世界第一的 Oracle，现在都由同一家公司管理
- MySQL 源于维德纽斯的大女儿的名字“My”，而 MariaDB 则源于维德纽斯的二女儿的名字“Maria”
  
> 本书介绍的内容 MySQL 和 MariaDB 的基本操作方法并没有什么区别

## 1.2.3 MySQL 的两种版本

- MySQL 社区版（Community Edition）
  - 可免费使用
  - 有参考手册（reference manual）
  - 有论坛（forum）和邮件列表（mailing list），但没有技术支持
&nbsp;

- MySQL 商业版（Commercial Edition）
  - 需要付费
  - 定期更新，并提供服务包（service pack）及技术支持
  - 拥有以下多个版本
    - MySQL 标准版（Standard Edition）
    - MySQL 企业版（Eeterprise Edition）
    - MySQL 集群运营商级版（Cluster Carrier Grade Eidtion）

> 本书介绍的是可免费使用的 MySQL 社区版

## 1.2.4 MySQL 的特征

特征如下：

1. 执行速度快
2. 开放源代码
3. 支持在多种操作系统上运行
4. 支持多种编程语言
5. 拥有免费和付费两个版本

# 1.3 SQL 的概要

## 1.3.1 什么是 SQL

1. 查询和 SQL
   1. 在操作数据库的时候，作为用户的我们会向数据库发出命令（command），并指定需要处理的内容。表示这种命令的语句，就是查询（query）
   2. 编写查询需要遵守 SQL (Structuerd Query Language) 的规则。
   3. SQL 直译过来就是结构化查询语言，用于对数据库进行操作
2. SQL 的方言
   1. 不同的数据库，个别命令语言会有差异，即产生了“方言”，实际操作中，需要特别注意。

## 1.3.2 首先熟悉 SELECT 命令

略

# 1.4 总结

本章内容如下：

1. 什么是数据库，什么是 RDBMS
2. MySQL 的特征
3. 使用 MySQL 的两种版本
4. 数据库的操作方法
