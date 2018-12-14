---
title: Go语言学习之旅（1）概述
tags: Go语言基础
categories:
  - go
top: 1
abbrlink: 5397fd79
date: 2018-10-25 19:40:53
---

## Go语言历史

​	Go 是一个开源的编程语言，它能让构造简单、可靠且高效的软件变得容易。

​	Go是从2007年末由Robert Griesemer, Rob Pike, Ken Thompson主持开发，后来还加入了Ian Lance Taylor, Russ Cox等人，并最终于2009年11月开源，在2012年早些时候发布了Go 1稳定版本。<!--more-->现在Go的开发已经是完全开放的，并且拥有一个活跃的社区 。

## Go 语言特色

- 简洁、快速、安全
- 并行、有趣、开源
- 内存管理、数组安全、编译迅速

## Go 语言用途

Go 语言被设计成一门应用于搭载 Web 服务器，存储集群或类似用途的巨型中央服务器的系统编程语言。对于高性能分布式系统领域而言，Go 语言无疑比大多数其它语言有着更高的开发效率。它提供了海量并行的支持，这对于游戏服务端的开发而言是再好不过了。

## Go语言安装

本人使用的是windows系统，所以使用的是msi文件安装，安装很简单，具体安装步骤可参考这篇博客：https://blog.csdn.net/hhtnan/article/details/78562085

## 第一个Go程序

```go
package main

import "fmt"

func main() {
    fmt.Println("Hello, World!")
}
```

```
$ go run hello.go 
Hello, World!
```

## Go 语言最主要的特性：

- 自动垃圾回收
- 更丰富的内置类型
- 函数多返回值
- 错误处理
- 匿名函数和闭包
- 类型和接口
- 并发编程
- 反射
- 语言交互性

## 总结

Go语言接受了函数式编程的一些想法，支持匿名函数与闭包。再如，Go语言接受了以Erlang语言为代表的面向消息编程思想，支持goroutine和通道，并推荐使用消息而不是共享内存来进行并发编程。总体来说，Go语言是一个非常现代化的语言，精小但非常强大。