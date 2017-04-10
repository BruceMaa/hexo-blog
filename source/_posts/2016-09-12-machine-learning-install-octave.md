---
title: 机器学习记录－－安装Octave
category: Technology
tags:
- Machine Learning
- Octave
---

## [Stanford University 机器学习](https://www.coursera.org/learn/machine-learning/home/welcome)

### 安装Octave

> 系统环境 OS X El Capitan 10.11.6

<!-- more -->

#### 使用``Homebrew``进行安装

> 直接用``brew search octave``找不到，需要先添加一个库

```shell
brew tap homebrew/science
```
	
> 这回使用``brew search octave``找到软件了，如果直接执行``brew install octave``，会报错，提示缺少``xquartz``，需要先安装这个，安装过程需要输入密码

```shell
brew cask install xquartz
```

> 现在总算可以安装了吧

```shell
brew install octave
```

> 确实可以正常执行了。不过会看到安装提示，需要先安装大量的依赖包，真的是大量的。
> 
- libmpc
- isl
- gcc
	- 这个有一个提示
	```
	If you need OpenMP support you may want to
  	brew reinstall gcc --without-multilib
	```
- gnu-sed
- texinfo
- veclibfort
- arpack
- little-cms2
- ghostscript
- epstool
- gl2ps
- graphicsmagick
- transfig
- fftw
- fltk
- glpk
- webp
- gd
- lua
- gnuplot
- szip
- hdf5
- plotutils
- pstoedit
- qhull
- qrupdate
- tbb
- metis
- suite-sparse

> 安装过程中的警告暂时没有理会

### 验证安装结果

> 在命令行输入命令

```shell
octave
```

> 进入``octave``的交互模式
> 
> 写一个公式进行验证

```
octave:1> x = linspace(0, 2*pi, 100);
octave:2> y = sin(x);
octave:3> plot(x, y);
```

> 稍等一会，就会出现一个对话框，显示正弦曲线。