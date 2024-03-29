# 第一章 概述

作者：李昕

单位：中国石油大学（华东）

## 1. 数据科学简介

## 2. Python简介

   python是一种面向对象的解释型计算机程序设计语言，由荷兰人Guido van Rossum于1989年发明，第一个公开发行版发行于1991年。python具有丰富和强大的库。它常被昵称为胶水语言，能够把用其他语言制作的各种模块（尤其是C/C++）很轻松地联结在一起。

   python是一种脚本语言，写好了就可以直接运行，省去了编译链接的麻烦，对于需要多动手实践的初学者而言，也就是少了出错的机会。而且python还有一种交互的方式，如果是一段简单的小程序，连编辑器都可以省了，直接敲进去就能运行。

   python是一种清晰的语言，用缩进来表示程序的嵌套关系可谓是一种创举，把过去软性的编程风格升级为硬性的语法规定。再不需要在不同的风格间选择、再不需要为不同的风格争执。python中没有各种隐晦的缩写，不需要去强记各种奇怪的符号的含义。python写的程序很容易懂，这是不少人的共识。

   python是一种面向对象的语言，但它的面向对象却不像C++那样强调概念，而是更注重实用。它用最简单的方法让编程者能够享受到面向对象带来的好处，这正是python能像Java、C#那样吸引众多支持者的原因之一。

   python是一种功能丰富的语言，它拥有一个强大的基本类库和数量众多的第三方扩展。python为程序员提供了丰富的基本功能使得人们写程序时，用不着一切从最底层做起。

   人们通常会有一种担心：脚本语言通常很慢。但python的速度却比人们想象得快很多。虽然python是一种脚本语言，但实际上也可以对它进行编译，省去了对程序文本的分析解释，速度自然提升很多。

   python的优势：

   1）python的定位是“优雅”、“明确”、“简单”，所以python程序看上去总是简单易懂，初学者学python，不但入门容易，而且将来深入下去，可以编写那些非常非常复杂的程序。

   2）开发效率非常高，python有非常强大的第三方库，基本上你想通过计算机实现任何功能，python官方库里都有相应的模块进行支持，直接下载调用后，在基础库的基础上再进行开发，大大降低开发周期，避免重复造轮子。

   3）高级语言——当你用python语言编写程序的时候，你无需考虑诸如如何管理你的程序使用的内存一类的底层细节

   4）可移植性——由于它的开源本质，python已经被移植在许多平台上（经过改动使它能够工 作在不同平台上）。如果你小心地避免使用依赖于系统的特性，那么你的所有python程序无需修改就几乎可以在市场上所有的系统平台上运行

   5）可扩展性——如果你需要你的一段关键代码运行得更快或者希望某些算法不公开，你可以把你的部分程序用C或C++编写，然后在你的python程序中使用它们。

   6）可嵌入性——你可以把python嵌入你的C/C++程序，从而向你的程序用户提供脚本功能。

## 3. 环境介绍

 Python的语法比较简单，采用缩进方式，写出来的代码如下： 

~~~ python
# print absolute value of an integer:
a = int(input())	#e.g. input 100
if a >= 0:
    print(a)
else:
    print(-a)
~~~

 以`#`开头的语句是注释，注释是给人看的，可以是任意内容，解释器会忽略掉注释。其他每一行都是一个语句，当语句以冒号`:`结尾时，缩进的语句视为代码块。  按照约定俗成的惯例，应该始终坚持使用*4个空格*的缩进。 

本书中的所有介绍基于python3.x，在Jupyter中进行运行。因为jupyter支持ipython，并有一些特殊的设置，因此书中的实例代码并不保障在idle等简单的编辑器下能够成功运行。特此说明。

##  4. 适用范围

本书重点在于适用Python语言进行数据分析，假定您已经学习过一门程序设计语言（例如C语言），对程序设计的基本用法已经掌握。在基础语法部分，重点强调Python语言与其他的语言的不同之处，而不会对基础语法进行详细介绍。

## 练习题

1. 运行以下代码，体会Python中对“大数”的支持。Python中通过内部功能增强，打破了存储对数据的限制，可以实现任意大小数据的运算。

   ~~~ python
   342534253432453425+3453452323423   # => 342537706884776848
   ~~~
   
2. 运行以下代码，观察出现的图形，体会for的使用

   ~~~ python
   from turtle import*
   pensize(5)	#set the size of the pen
   speed("fastest")	#set the speed of the animation
   for i in range(1,37):	#loop 36 times
       pencolor(0.018,0.015*i,0.012)	#set the color with (Red,Green,Blue)
       circle(100,360)		#draw a circle
       right(10)		#turn right 10 degree
   done()
   ~~~

   ![](.\figure\overlapped circle.png)

3. 运行以下代码，观察出现的图形，体会while的使用

~~~ python
from turtle import *
color("green")	#set the color
pensize(3)	#set the pen size
speed("fastest")	#set the speed of the animation
i=0	
while i<12:	#loop 12 times to draw 12 stars
    right(150)	#turn right 150 degree
    forward(150)	#move foreward 150 steps
    #the above two statement will repeat 5 times to make a star
    if abs(pos())<1:	#if pen come back to the original
        left(150)	#turn left 150 degree, being ready for the next star
        i+=1	#i increment 1
done()
~~~

![](.\figure\turtle while loop.png)