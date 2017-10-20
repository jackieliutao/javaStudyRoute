---
layout: post
title:  "Java基础语法"
date:   2017-10-19
comments: true
---

* [1、JDK环境搭建](#buildJDK)
* [2、Java语法基础](#basicGrammer)
* * [2.1、关键字](#keyWords)
* * [2.2、标识符](#symbol)
* * [2.3、注释](#annotation)
* * [2.4、常量](#constant)
* * [2.5、变量](#variable)
* * [2.6、运算符](#operator)
* * [2.7、进制](#scale)
* [3、程序流程控制](#flowControl)
* [4、方法及应用](#methodApplication)
* [5、数组及应用](#arrayApplication)
* [6、经典问题](#problems)

<h2 id="buildJDK">一：JDK环境搭建</h2>

- <h2 id="basicGrammer">二：Java语法基础</h2>
- - <h3 id="keyWords">（一）关键字</h3>
* 关键字概述
* * 被Java语言赋予特定含义的单词
* 关键字特点
* * 组成关键字的字母全部小写
* 关键字注意事项
* * goto和const作为保留子存在，目前并不使用

<table>
  <tr>
  <td colspan="6" align="center">访问控制</td>
  </tr>
  <tr>
    <td colspan="2"  align="center">private</td>
    <td colspan="2"  align="center">protected</td>
    <td colspan="2"  align="center">public</td>
  </tr>
  <tr >
  <td colspan="6" align="center">类、方法和变量修饰符</td>
  </tr>
  <tr>
    <td  align="center">abstract</td>
    <td  align="center">class</td>
    <td  align="center">extends</td>
    <td  align="center">final</td>
    <td  align="center">implements</td>
    <td  align="center">interface</td>
  </tr>
  <tr>
    <td  align="center">native</td>
    <td  align="center">new</td>
    <td  align="center">static</td>
    <td  align="center">strictfp</td>
    <td  align="center">synchronized</td>
    <td  align="center">transient</td>
  </tr>
  <tr align="center">
    <td colspan="6">volatile</td>
  </tr>
  <tr>
    <td  align="center" colspan="6">程序控制</td>
  </tr>
  <tr>
    <td align="center">break</td>
    <td align="center">continue</td>
    <td align="center">return</td>
    <td align="center">do</td>
    <td align="center">while</td>
    <td align="center">if</td>
  </tr>
  <tr>
    <td align="center">else</td>
    <td align="center">for</td>
    <td align="center">instanceof</td>
    <td align="center">switch</td>
    <td align="center">case</td>
    <td align="center">default</td>
  </tr>
  <tr>
    <td  align="center" colspan="6">异常处理</td>
  </tr>
  <tr>
    <td align="center">try</td>
    <td align="center">catch</td>
    <td align="center">throw</td>
    <td align="center">throws</td>
    <td align="center">finally</td>
    <td align="center"></td>
  </tr>
  <tr>
    <td  align="center" colspan="6">包相关</td>
  </tr>
  <tr>
    <td align="center">import</td>
    <td align="center">package</td>
    <td align="center"></td>
    <td align="center"></td>
    <td align="center"></td>
    <td align="center"></td>
  </tr>
  <tr>
    <td  align="center" colspan="6">基本类型</td>
  </tr>
  <tr>
    <td align="center">boolean</td>
    <td align="center">tyte</td>
    <td align="center">char</td>
    <td align="center">double</td>
    <td align="center">float</td>
    <td align="center">int</td>
  </tr>
  <tr>
    <td align="center">long</td>
    <td align="center">short</td>
    <td align="center">null</td>
    <td align="center">true</td>
    <td align="center">false</td>
    <td align="center"></td>
  </tr>
  <tr>
    <td  align="center" colspan="6">变量引用</td>
  </tr>
  <tr>
    <td align="center">super</td>
    <td align="center">this</td>
    <td align="center">void</td>
    <td align="center"></td>
    <td align="center"></td>
    <td align="center"></td>
  </tr>
  <tr>
    <td  align="center" colspan="6">保留字</td>
  </tr>
  <tr>
    <td align="center">goto</td>
    <td align="center">const</td>
    <td align="center"></td>
    <td align="center"></td>
    <td align="center"></td>
    <td align="center"></td>
  </tr>
  <tr>
    <td  align="center" colspan="6">其他</td>
  </tr>
  <tr>
    <td align="center">enum</td>
    <td align="center">assert</td>
    <td align="center"></td>
    <td align="center"></td>
    <td align="center"></td>
    <td align="center"></td>
  </tr>
</table>

(1)[<font color="blue">关键字的详细解释</font>](http://www.cnblogs.com/AloneZ/p/java1.html)[详解来源于Alone章鱼的博客]

- - <h3 id="symbol">（二）标识符</h3>
<h2 id="flowControl">三：程序流程控制</h2>
<h2 id="methodApplication">四：方法及应用</h2>
<h2 id="arrayApplication">五：数组及应用</h2>
<h2 id="problems">六：经典问题</h2>
