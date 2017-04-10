---
title: PostgreSQL--Mac环境安装
category: Technology
tags:
- Database
- PostgreSQL
---

## PostgreSQL安装

### 安装环境介绍

> 系统：OS X El Capitan 10.11.6
> 
> 时间：2016-09-13
> 
> PostgreSQL 版本：9.5.4

<!-- more -->

### 通过``brew``命令安装

```shell
brew install postgresql
```

> 安装后有提示，如果需要开机自启，则输入命令

```shell
brew services start postgresql
```

> 如果不想用后台服务，可以手动启动

```shell
postgres -D /usr/local/var/postgres
```

> 具体的启动参数，可以通过``postgres --help``查看

### 进入交互模式

> 启动后，执行命令

```shell
psql -l
```

> 会看到默认创建了三个库，``postgres``，``template0``，``template1``，Owner都是当前用户。
> 
> 输入命令

```shell
psql postgres
```
	
> 进入到``postgres``数据库的交互模式。
> 
> 输入命令

```
postgres=# \du
```

> 可以看到当前用户拥有的权限``Superuser``, ``Create Role``, ``Create DB``, ``Replication``, ``Bypass RLS``。

> 退出交互式模式命令

```
\q
```

### 安装pgAdmin

> 使用``brew cask``命令安装

```shell
brew cask install pgadmin3
```

> 安装完成后，连接数据库
> 
- 名称－－随便
- 主机－－127.0.0.1
- 端口号－－默认5432
- 服务－－空白
- 维护数据库－－postgres
- 用户名－－当前登陆用户
- 密码－－默认是空的
- 组－－默认是服务器

> 可以连接后，最好是创建一个子角色，用于开发。
