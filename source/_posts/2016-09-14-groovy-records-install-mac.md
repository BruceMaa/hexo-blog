---
title: Groovy使用记录－－Mac环境安装
category: Technology
tags:
- Groovy
---

## Mac环境安装Groovy

> 最近想学习一下Spring源码，下载下来需要使用``Gradle``来构建，没用过，要去学一下，结果``Gradle``又说它是基于``Groovy``的，好吧，正好一直想看看``Groovy``长什么样子。

### 安装环境介绍

> 系统：OS X El Capitan 10.11.6
> 
> Groovy版本：2.4.7

<!-- more -->

### 使用``brew``安装

```shell
brew install groovy
```

> 也可以直接下载压缩包，类似于Maven。

### 配置

> ``brew``安装后，会自动添加到环境变量中，不过还是提示添加``GROOVY_HOME``

```
export GROOVY_HOME=/usr/local/opt/groovy/libexec
```