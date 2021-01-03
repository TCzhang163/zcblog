---
layout: post
title: MySQL的安装与卸载
date: 2021-01-03
Author: TCzhang163
tags: [MySQL]
comments: true
toc: true
---

windows端的MySQL和Linux端的MySQL安装与卸载



<!-- more -->

# Windows上的MySQL

## 安装

1. 下载要用的MySQL版本
  - [点击下载-5.7-x64](https://dev.mysql.com/get/Downloads/MySQL-5.7/mysql-5.7.19-winx64.zip "5.7-x64")
2. 配置环境变量

   ```
   我的电脑——>属性——>高级配置——>环境变量——>系统变量——>找到path添加MySQLbin目录的url
   ```



3. 在MySQL根目录下新建my.ini

```
[mysqld]
#安装目录
basedir=D:\Program Files\mysql-5.7.19\
datadir=D:\Program Files\mysql-5.7.19\data\
port=3306
skip-grant-tables
#basedir表示mysql安装路径
#datadir表示mysql数据文件存储路径
#port表示mysql端口
#skip-grant-tables表示忽略密码
```



4. 打开管理员命令行，进入MySQL的bin目录

- 输入mysqld --install
- 输入mysqld --initialize-insecure --user=mysql初始化
- 输入net start mysql启动mysql服务
- 输入mysql –u root –p然后回车，显示输入密码，直接回车
- 修改密码set password for root@localhost = password('customPassword')
- 刷新权限flush privileges;

## 卸载

1. 免安装版直接删除MySQL文件夹，命令行输入sc delete mysql即可