---
title: Go语言学习之旅（8）条件语句
tags: Go语言基础
categories:
  - go
top: 8
abbrlink: 123d03eb
date: 2018-10-25 19:51:52
---

## Go语言条件语句

条件语句需要开发者通过指定一个或多个条件，并通过测试条件是否为 true 来决定是否执行指定语句，并在条件为 false 的情况在执行另外的语句。
<!--more-->
Go 语言提供了以下几种条件判断语句：

| 语句                                                         | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [if 语句](http://www.runoob.com/go/go-if-statement.html)     | **if 语句** 由一个布尔表达式后紧跟一个或多个语句组成。       |
| [if...else 语句](http://www.runoob.com/go/go-if-else-statement.html) | **if 语句** 后可以使用可选的 **else 语句**, else 语句中的表达式在布尔表达式为 false 时执行。 |
| [if 嵌套语句](http://www.runoob.com/go/go-nested-if-statements.html) | 你可以在 **if** 或 **else if** 语句中嵌入一个或多个 **if** 或 **else if** 语句。 |
| [switch 语句](http://www.runoob.com/go/go-switch-statement.html) | **switch** 语句用于基于不同条件执行不同动作。                |
| [select 语句](http://www.runoob.com/go/go-select-statement.html) | **select** 语句类似于 **switch** 语句，但是select会随机执行一个可运行的case。如果没有case可运行，它将阻塞，直到有case可运行。 |

## If语法

```go
if 布尔表达式 {
   /* 在布尔表达式为 true 时执行 */
}
```

## 实例

```go
package main

import "fmt"

func main() {
   /* 定义局部变量 */
   var a int = 10
 
   /* 使用 if 语句判断布尔表达式 */
   if a < 20 {
       /* 如果条件为 true 则执行以下语句 */
       fmt.Printf("a 小于 20\n" )
   }
   fmt.Printf("a 的值为 : %d\n", a)
}
```

以上代码执行结果为：

```go
a 小于 20
a 的值为 : 10
```

## if...else语法

if 语句 后可以使用可选的 else 语句, else 语句中的表达式在布尔表达式为 false 时执行。

```go
if 布尔表达式 {
   /* 在布尔表达式为 true 时执行 */
} else {
  /* 在布尔表达式为 false 时执行 */
}
```

## 实例

```go
package main

import "fmt"

func main() {
   /* 局部变量定义 */
   var a int = 100;
 
   /* 判断布尔表达式 */
   if a < 20 {
       /* 如果条件为 true 则执行以下语句 */
       fmt.Printf("a 小于 20\n" );
   } else {
       /* 如果条件为 false 则执行以下语句 */
       fmt.Printf("a 不小于 20\n" );
   }
   fmt.Printf("a 的值为 : %d\n", a);

}
```

以上代码执行结果为：

```go
a 不小于 20
a 的值为 : 100
```

## if 语句嵌套

你可以在 if 或 else if 语句中嵌入一个或多个 if 或 else if 语句

```go
if 布尔表达式 1 {
   /* 在布尔表达式 1 为 true 时执行 */
   if 布尔表达式 2 {
      /* 在布尔表达式 2 为 true 时执行 */
   }
}
```

## 实例

```go
package main

import "fmt"

func main() {
   /* 定义局部变量 */
   var a int = 100
   var b int = 200
 
   /* 判断条件 */
   if a == 100 {
       /* if 条件语句为 true 执行 */
       if b == 200 {
          /* if 条件语句为 true 执行 */
          fmt.Printf("a 的值为 100 ， b 的值为 200\n" );
       }
   }
   fmt.Printf("a 值为 : %d\n", a );
   fmt.Printf("b 值为 : %d\n", b );
}
```

以上代码执行结果为：

```go
a 的值为 100 ， b 的值为 200
a 值为 : 100
b 值为 : 200
```

## switch 语句

switch 语句用于基于不同条件执行不同动作，每一个 case 分支都是唯一的，从上直下逐一测试，直到匹配为止。。

switch 语句执行的过程从上至下，直到找到匹配项，匹配项后面也不需要再加break

```go
switch var1 {
    case val1:
        ...
    case val2:
        ...
    default:
        ...
}
```

变量 var1 可以是任何类型，而 val1 和 val2 则可以是同类型的任意值。类型不被局限于常量或整数，但必须是相同的类型；或者最终结果为相同类型的表达式。

您可以同时测试多个可能符合条件的值，使用逗号分割它们，例如：case val1, val2, val3。

## 实例

```go
package main

import "fmt"

func main() {
   /* 定义局部变量 */
   var grade string = "B"
   var marks int = 90

   switch marks {
      case 90: grade = "A"
      case 80: grade = "B"
      case 50,60,70 : grade = "C"
      default: grade = "D"  
   }

   switch {
      case grade == "A" :
         fmt.Printf("优秀!\n" )     
      case grade == "B", grade == "C" :
         fmt.Printf("良好\n" )      
      case grade == "D" :
         fmt.Printf("及格\n" )      
      case grade == "F":
         fmt.Printf("不及格\n" )
      default:
         fmt.Printf("差\n" );
   }
   fmt.Printf("你的等级是 %s\n", grade );      
}
```

以上代码执行结果为：

```go
优秀!
你的等级是 A
```

## Type Switch

switch 语句还可以被用于 type-switch 来判断某个 interface 变量中实际存储的变量类型

```go
switch x.(type){
    case type:
       statement(s);      
    case type:
       statement(s); 
    /* 你可以定义任意个数的case */
    default: /* 可选 */
       statement(s);
}
```

## 实例

```go
package main

import "fmt"

func main()  {
	var x interface{}

	switch i :=x.(type){
	case nil:
		fmt.Printf("x 的类型是：%T",i)
	case int:
		fmt.Printf("x 的类型是：%T",i)
	case float64:
		fmt.Printf("x 的类型是：%T",i)
	case func(int) float64:
		fmt.Printf("x 的类型是：%T",i)
	case bool,string:
		fmt.Printf("x 的类型是：%T",i)
	default:
		fmt.Printf("未知型")
	}
}
```

以上代码执行结果为：

```go
x 的类型 :<nil>
```

## Select语句

select是Go中的一个控制结构，类似于用于通信的switch语句。每个case必须是一个通信操作，要么是发送要么是接收。

select随机执行一个可运行的case。如果没有case可运行，它将阻塞，直到有case可运行。一个默认的子句应该总是可运行的

```go
select {
    case communication clause  :
       statement(s);      
    case communication clause  :
       statement(s); 
    /* 你可以定义任意数量的 case */
    default : /* 可选 */
       statement(s);
}
```

以下描述了 select 语句的语法：

- 每个case都必须是一个通信

- 所有channel表达式都会被求值

- 所有被发送的表达式都会被求值

- 如果任意某个通信可以进行，它就执行；其他被忽略。

- 如果有多个case都可以运行，Select会随机公平地选出一个执行。其他不会执行。

   

  否则：

  1. 如果有default子句，则执行该语句。
  2. 如果没有default字句，select将阻塞，直到某个通信可以运行；Go不会重新对channel或值进行求值。

## 实例

```go
package main

import "fmt"

func main()  {
	var a1,a2,a3 chan int
	var k1,k2 int
	select{
		case k1=<-a1:
			fmt.Printf("received ",k1," from a1\n")
		case a2<-k2:
			fmt.Printf("sent ",k2," to a2\n")
		case a3,ok:=(<-a3):
			if ok{
				fmt.Printf("received ",a3," from a3\n")
			} else{
				fmt.Printf("a3 is closed\n")
			}
		default:
			fmt.Printf("no communication\n")
	}
}
```

以上代码执行结果为：

```go
no communication
```

