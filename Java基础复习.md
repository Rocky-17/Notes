---
title: Java基础复习
tags: [Java,学习笔记]
---
《Java核心技术 卷一》（第十版）读书笔记
<!--more-->

# 第一章 Java程序设计概述

## Java的特性

### 简单性
&emsp;&emsp;Java没有诸如C++一样的头文件、指针、结构、联合、虚基类、操作符重载一类的东西，但是C++的许多特性在Java中仍有应用。

### 面向对象
&emsp;&emsp;面向对象设计是一种程序设计技术。它将重点放在对象与对象的接口上。Java与C++的主要不同点就在于多重继承，在Java中，取而代之的是更为简单的接口概念。

### 分布式
&emsp;&emsp;Java有一个丰富的例程库，用于处理想HTTP和FTP之类的TCP/IP协议。Java程序能够通过URL打开和访问网络上的对象。

### 健壮性
&emsp;&emsp;Java投入了大量的精力进行早期的问题检测，后期动态的（运行时）检测，并消除了容易出错的情况······Java和C++最大的不同在于Java采用的指针模型可以消除重写和损坏数据的可能性。

### 安全性
&emsp;&emsp;Java适用于网络/分布式环境，在安全方面投入了很大精力，使用Java可以构建防病毒，防篡改的系统。它能够防范诸如运行时堆栈溢出、破坏自己的进程空间之外的内存、未经授权读写文件等攻击。

### 体系结构中立
&emsp;&emsp;编译器编译源码生成与特定的计算机体系结构无关的字节码，字节码又可通过任意计算机上的解释器来执行，其还可以动态的翻译为本地机器代码。

### 可移植性
&emsp;&emsp;在Java中，数据类型具有固定大小，这消除了代码移植时的主要问题。二进制数据以固定的格式进行存储和传输，消除了字节顺序的困扰。字符串是标准的Unicode格式存储的。除了与用户界面有关的部分外，所有其他Java库都能很好的支持平台独立性。

### 解释型
&emsp;&emsp;Jaca解释器可以在任何移植了解释器的机器上执行Java字节码。

### 高性能
&emsp;&emsp;字节码可以（在运行时刻）动态地翻译成对应运行这个应用的特定CPU的机器码。

### 多线程
&emsp;&emsp;多线程可以带来更好的交互响应和实时行为，Java是第一个支持并发程序设计的主流语言。

### 动态性
&emsp;&emsp;它能够适应不断发展的环境。库中可以自由地添加新方法和实例变量，而对客户端没有任何影响。

## Java applet 与 Internet
&emsp;&emsp;在网页中运行的Java程序称为applet。要使用applet，需要启动Java的Web浏览器执行字节码，而不需要安装任何软件。由于兼容性问题以及安全问题，applet的使用渐渐减少。

## Java发展史
版本|年份|语言新特性|类与接口数量
:-: |:-: |:-: |:-: |
1.0|1996|语言本身|211
1.1|1997|内部类|477
1.2|1998|strictfp修饰符|1524
1.3|2000|无|1840
1.4|2002|断言|2723
5.0|2004|泛型类、"for each"循环、可变元参数。自动装箱、元数据、枚举、静态导入|3279
6|2006|无|3793
7|2011|基于字符串的switch、钻石操作符、二进制字面量、异常处理改进|4024
8|2014|lambda表达式、包含默认方法的接口、流和日期/时间库|4240

# 第二章 Java程序设计环境  
术语名|缩写|解释
:-: |:-: |:-: 
Java Development Kit|JDK|编写Java程序使用的软件
Java Runtime Environment|JRE|运行Java程序的软件
Server JRE|-|在服务器上运行Java程序的软件
Standard Edition|SE|用于桌面或简单服务器应用的Java平台
Enterprise Edition|EE|用于复杂服务器应用的Java平台
Micro Edition|ME|用于手机或其他小型设备的Java平台
Java FX|-|用于图形化用户界面的一个替代工具包，在Oracle的Java SE的发布版本中提供
OpenJDK|-|Java SE的一个免费开源实现，不包含浏览器集成或Java FX
Java 2|J2|一个过时术语，用于描述1998 ~ 2006年间的Java版本
Software Development Kit|SDK|一个过时的术语，用于描述1998 ~ 2006年间的JDK
Update|u|Oracle术语，表示bug修正版本
Netbeans|-|Oracle的集成开发环境


# 第三章 Java的基本程序结构

一个简单的Java应用程序：
```
public class HelloWorld{
    public static void main(String[] args){
        System.out.println("HelloWorld");
    }
}
```
逐行来看一下这段代码的结构
```
public class HelloWorld{···}
```
&emsp;&emsp;关键字public 称为访问修饰符，访问修饰符用于控制程序的其他部分对这段代码的访问级别。  
&emsp;&emsp;关键字class表明这是一个类。  
&emsp;&emsp;Helloworld是类名 类名的命名规则很宽松，可以任意命名，但必须用字母作为开头，且不能使用Java保留字
```
public static void main(String[] args){···}
```
&emsp;&emsp;main方法，Java程序的入口。根据Java语言规范，main方法必须申明为public类型
```
System.out.println("HelloWorld");
```
&emsp;&emsp;程序语句。

## 注释
```
// 单行注释

/*
多
行
注
释
*/
```

## 数据类型
Java是一种强类型语言，意味着必须为每一个变量声明一种类型。在Java中有8种基本类型：

### 4种整型
类型|存储需求|取值范围
:-: |:-: |:-: 
byte|1 byte|-128 ~ 127
short|2 bytes|-32,768 ~ 32,767
int|4 bytes|-2,147,483,648 ~ 2,147,483,647
long|8 bytes|-9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807

&emsp;&emsp;长整型数值有一个后缀L或l；  
&emsp;&emsp;十六进制数值有一个前缀0x或0X  
&emsp;&emsp;八进制有一个前缀0  
&emsp;&emsp;从Java7开始，加上前缀0b或0B表示二进制数

### 2种浮点型
类型|存储需求|取值范围
:-: |:-: |:-: 
float|4 bytes|大约 ±3.402,823,47E+38F（有效位数为6~7位）
double|8 bytes|大约 ±1.797,693,134,862,315,70E+308（有效位数为15位）

&emsp;&emsp;float类型的数值有一个后缀f或F，没有这个后缀的浮点型数值默认为double类型。
&emsp;&emsp;浮点型不适用于无法接受舍入误差的计算（如金融系统）中，应该使用BigDecimal类。  
  
<table>
    <tr>
        <th colspan="3">用于表示溢出和出错情况的三个特殊的浮点数值</th>
    </tr>
    <tr>
        <td>正无穷大</td>
        <td>负无穷大</td>
        <td>NaN（不是一个数字）</td>
    </tr>
</table>

>常量Double.POSITIVE_INFINITY、Double.NEGATIVE_INFINITY和Double.NaN（以及相应类型的Float类型的常量分别表示这三个特殊的值）

注意：不能这样检测一个特定值是否等于Double.NaN：
```
if(x == Double.NaN)    // is never true
```
所有的“非数值”都认为是不相同的，但可以使用Double.isNaN方法检测
```
if(Double.isNaN(x))    // check whether x is "not a number"
```
### 1种字符类型
&emsp;&emsp;char类型的字面常量要用单引号括起来。  
&emsp;&emsp;char类型的值可以表示为十六进制，其范围从\u0000到\Uffff。 
&emsp;&emsp;Unicode转义序列会在解析代码前得到处理。如：
```
"\u0022+\u0022"
```
&emsp;&emsp;并不是一个由""引起来的字符串，而会转义为
```
""+""   //一个空串
```
&emsp;&emsp;特别的，要小心注释中的\u。如：
```
// \u00A0 is a newline
```
&emsp;&emsp;其中\u00A0会被认为是一个换行符，而不是单纯的注释文字。

一些特殊的转义序列：
<table>
    <tr>
        <td>转义序列</td>
        <td>名称</td>
        <td>Unicode值</td>
    </tr>
    <tr>
        <td>\b</td>
        <td>退格</td>
        <td>\u0008</td>
    </tr>
    <tr>
        <td>\t</td>
        <td>制表</td>
        <td>\u0009</td>
    </tr>
    <tr>
        <td>\n</td>
        <td>换行</td>
        <td>\u000a</td>
    </tr>
    <tr>
        <td>\r</td>
        <td>回车</td>
        <td>\u000d</td>
    </tr>
    <tr>
        <td>\"</td>
        <td>双引号</td>
        <td>\u0022</td>
    </tr>
    <tr>
        <td>\'</td>
        <td>单引号</td>
        <td>\u0027</td>
    </tr>
    <tr>
        <td>\\</td>
        <td>反斜杠</td>
        <td>\u005c</td>
    </tr>
</table>


### 1种布尔类型
&emsp;&emsp;boolean类型有两个值，false和true，用来判断逻辑条件。整型和布尔值之间不能进行相互转换。

## 变量
### 变量声明
&emsp;&emsp;变量名大小写敏感。  
&emsp;&emsp;不可使用Java保留字作为变量名。   
&emsp;&emsp;变量的声明应尽可能靠近第一次使用该变量的地方。  
&emsp;&emsp;变量声明有许多的约定俗成的规范，相关资料可以参考[《阿里巴巴Java开发手册》](https://yq.aliyun.com/download/2720?utm_content=m_1000019584)一类的资料，不再赘述。 

### 常量
&emsp;&emsp;在Java中，使用关键字final指示常量。关键字final表示这个变量只能被赋值一次，一旦被赋值，便不能再被更改。  
&emsp;&emsp;习惯上常量名使用全大写。  
&emsp;&emsp;如果希望某个常量能在一个类中被多个方法使用，那么可以使用static final设置一个类常量。

## 运算符
运算符|操作
:-: |:-:
+|加
-|减
*|乘
/|除
%|取模

### 数值类型之间的转换
![数据类型之间的合法转换](https://github.com/Rocky-17/Blog_illustration/blob/master/Java%E5%9F%BA%E7%A1%80%E5%A4%8D%E4%B9%A0/%E5%90%88%E6%B3%95%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B%E8%BD%AC%E6%8D%A2.png?raw=true)
&emsp;&emsp;实箭头：无信息丢失的转换。  
&emsp;&emsp;虚箭头：可能有精度损失的转换。

### 强制类型转换
&emsp;&emsp;