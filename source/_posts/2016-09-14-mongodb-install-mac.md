---
title: MongoDB--Mac环境安装
category: Technology
tags:
- Database
- MongoDB
---

## MongoDB安装

### 安装环境介绍

> 系统：OS X El Capitan 
> 
> 时间：2016-09-14
> 
> MongoDB 版本：3.2.9

<!-- more -->

### 通过``brew``命令安装

> 有的人喜欢图形界面

```shell
brew cask install mongodb
```
	
> 我还是喜欢命令行

```shell
brew install mongodb
```

> 安装后有提示，如果需要开机自启，则输入命令

```shell
brew services start mongodb
```

> 如果不想用后台服务，可以手动启动

```shell
mongod --config /usr/local/etc/mongod.conf
```

### 进入交互模式

> 启动后，执行命令

```shell
mongo
```

> __注意__，此时是无需用户登录即可进入的，如果要开发使用，记得设置成必须用户登录。

> 退出命令

```
> exit
```

### 客户端

> 推荐``Robomongo``

```shell
brew cask install robomongo
```
