---
layout: post
title:  "Java基本语法"
date:   2017-09-20
comments: true
---

### 一：关键字
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
    <td align="center">instance</td>
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

### 二：标识符
* 标识符概述
* * 标识符是用来给类、对象、方法、变量、接口和自定义数据类型命名的。
* 组成规则
* * 英文大小写字母
* * 数字字符
* * $和_
* 注意事项
* * 不能以数字开头
* * 不能是java中的关键字
* * 区分大小写
* 常见的命名规则<font color="red">（见名知意）</font>
* * 包：其实就是文件夹，用于把相同的类名进行区分
* * * 全部小写
* * * 单级：jackie
* * * 多级：com.jackie
* * 类或者接口
* * * 一个单词：单词的首字母必须大写
* * * 多个单词：每个单词的首字母必须大写
* * 方法或者变量
* * * 一个单词：单词的首字母小写
* * * 多个单词：从第二个单词开始，每个单词的首字母大写
* * 常量
* * * 一个单词：全部大写
* * * 多个单词：每个字母都大写，单词间用_进行隔开

### 三：注释
* 注释概述
* * 用于解释说明程序的文字
* 注释分类及其格式
* * * 单行注释 //
* * * 多行注释 ```/*...*/```<font color="red">(多行注释不能嵌套使用，单行注释可以)</font>
* * * 文档注释```/**...*/```

### 四：常量
* 常量概述
* * 在程序执行过程中其值不会发生改变的量。
* 常量的分类
* * 字面值常量
* * * 字符串常量(用双引号扩起来的内容)，如"hello","hello world"
* * * 整数常量（所有的整数）
* * * 小数常量（所有的小数）
* * * 字符常量（用单引号扩起来的内容），如'a','A'
* * * 布尔常量（boolean）只有true和false两个值
* * * 空常量（null）
* * 自定义常量

### 五：进制
* 进制概述
* * 进制也就是进位制，是人们规定的一种进位方法。 对于任何一种进制---X进制，就表示某一位置上的数运算时是逢X进一位。 十进制是逢十进一，十六进制是逢十六进一，二进制就是逢二进一，以此类推，x进制就是逢x进位。
* 不同进制的数据组成
* * 二进制
* * * 由0、1组成，以0b开头
* * 八进制
* * * 由0、1、2..7组成，以0开头
* * 十进制
* * * 由0、1、2、3...9组成，整数默认为十进制
* * 十六进制
* * * 由0、1...9 a/b/c/d/e/f(大小写均可)，以0x（0X）开头
