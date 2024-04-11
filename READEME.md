[TOC]

## 一 Solidity语法
### 1.1 类型
+ boolan
+ int
+ unit 默认256
+ address
+ string
+ bytes 最大32位
+ mapping

+ array
```sol
uint[] public arr = [1,2,3];
```
+ struct
```sol
struct Person {
    string name;
    uint age;
}
// 方式1
Person public p1 = Person("John", 25);
// 方式2
Person public p2 = Person({name:"John", age:25});
// 数组方式创建
Person[] public people; // 动态数组，默认[], Person[3]指定数量
Person[] public people = new Person[](2);
people[0] = Person("John", 25);
people[1] = Person("Alice", 30);
```
+ enum

+ enum
+ fixed
+ dynamic

> 变量声明：public等修饰放到类型后面，对于public修饰的变量，相当于提供了getter方法（默认是public）
+ 有2个关键字用来表示是否需要发生交易：payable和view（防止产生gas，但实际被调用时还是会有gas消耗，因为产生了调用操作）
    + view：表示只从链上读，无需产生交易（禁止更新）
    + payable：表示可以产生交易（也禁止更新，甚至禁止从状态或寄存器中读）

> solidity 6大存储位置
>
> **memeory 内存** 存储在内存，调用结束销毁；形参默认，结构体、map、数组、字符串（字节数组）特殊需要指定；**可修改**
>
> **calldata 调用数据** 存储在内存，调用结束销毁；**无法修改**
>
> **storage 存储器** **永久存储，不可修改，函数之外的变量默认为storage**
>
> stack 栈 、 code 代码 、 logs 日志
### 1.2 函数
+ 函数声明
+ 函数调用
+ 函数重载
+ 函数修饰符

### 1.4 事件
+ 事件声明
+ 事件触发
+ 事件过滤