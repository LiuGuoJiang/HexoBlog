---
title: Go语言学习之旅（3）基础语法
tags: Go语言基础
categories:
  - go
top: 3
abbrlink: f0734f3c
date: 2018-10-25 19:50:24
---

## Go标记

Go 程序可以由多个标记组成，可以是关键字，标识符，常量，字符串，符号。如以下 GO 语句由 6 个标记组成：
<!--more-->
```go
mt.Println("Hello, World!")
```

6 个标记是(每行一个)：

```go
1. fmt	#标识符
2. .	#符号
3. Println	#关键字
4. (	#符号
5. "Hello, World!"	#字符串/常量
6. )	#符号
```

## 行分隔符

在 Go 程序中，一行代表一个语句结束。每个语句不需要像 C 家族中的其它语言一样以分号 ; 结尾，因为这些工作都将由 Go 编译器自动完成。

如果你打算将多个语句写在同一行，它们则必须使用 ; 人为区分，但在实际开发中我们并不鼓励这种做法。

以下为两个语句：

```go
fmt.Println("Hello, World!")
fmt.Println("Go语言学习之旅：liuguojiang.github.io")
```

## 注释

注释不会被编译，每一个包应该有相关注释。

单行注释是最常见的注释形式，你可以在任何地方使用以 // 开头的单行注释。多行注释也叫块注释，均已以 /* 开头，并以 */ 结尾。如：

```go
// 单行注释
/*
 Martin Blogs
 我是多行注释
 */
```

## 标识符

标识符用来命名变量、类型等程序实体。一个标识符实际上就是一个或是多个字母(A~Z和a~z)数字(0~9)、下划线_组成的序列，但是第一个字符必须是字母或下划线而不能是数字。

以下是有效的标识符：

```go
mahesh   kumar   abc   move_name   a_123
myname50   _temp   j   a23b9   retVal
```

以下是无效的标识符：

- 1ab（以数字开头）
- case（Go 语言的关键字）
- a+b（运算符是不允许的）

## Go语言的空格

Go 语言中变量的声明必须使用空格隔开，如：

```go
var name string;
```

空格的作用可以使用编辑器来达到目的，比如vscode

## Go语言程序的一般结构：

```go
// 当前程序的包名
package main

// 导入其他包
import . "fmt"

// 常量定义
const myMoney = 3.14

// 全局变量的声明和赋值
var name = "Martin"

// 一般类型声明
type intType int

// 结构的声明
type structType struct{}

// 接口的声明
type interfaceFunc interface{}

// 由main函数作为程序入口点启动
func main() {
    Println("This is my Martin Blogs!")
}
```

通过 **const** 关键字来进行常量的定义。

通过在函数体外部使用 **var** 关键字来进行全局变量的声明和赋值。

通过 **type** 关键字来进行结构(struct)和接口(interface)以及一般类型的声明。

通过 **func** 关键字来进行函数的声明。

Go 程序是通过 **package** 来组织的，只有 **package** 名称为 **main** 的包可以包含 **main** 函数。

一个可执行程序有且仅有一个 **main** 包。

通过 **import** 关键字来导入其他非 **main** 包。

可以通过 **import** 关键字单个导入:

```go
import "fmt"
import "io"
```

也可以通过 **import** 关键字多个导入:

```go
import {
    "fmt",
    "io"
}
```

### 可见性规则

Go语言中，使用大小写来决定该常量、变量、类型、接口、结构或函数是否可以被外部包所调用。

- 函数名首字母小写即为 **private** ，变量同理
- 函数名首字母大写即为 **public** ，变量同理