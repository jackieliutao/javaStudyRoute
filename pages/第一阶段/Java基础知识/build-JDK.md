---
layout: post
title:  "Java基本语法"
date:   2017-10-19
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

### 二：标识符

* 标识符概述
* * 标识符是用来给类、对象、方法、变量、接口和自定义数据类型命名的字符序列。


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


* 注释的作用
* * 解释说明程序，提高了代码的阅读性
* * 可以帮助我们调试程序

### 四：常量
* 常量概述
* * 在程序执行过程中其值不会发生改变的量。


* 常量的分类
* * 字面值常量
* * * 字符串常量(用双引号扩起来的内容)，如"hello","hello world"
* * * 整数常量（所有的整数）
* * * 小数常量（所有的小数）
* * * 字符常量（用单引号扩起来的内容），如'a','A'
* * * 布尔常量（boolean）<font color="red">有true和false两个值</font>
* * * 空常量（null）


* 在Java中针对整数常量提供了四种表现形式
* * 二进制
* * * 由0、1组成，以0b开头
* * 八进制
* * * 由0、1、2..7组成，以0开头
* * 十进制
* * * 由0、1、2、3...9组成，整数默认为十进制
* * 十六进制
* * * 由0、1...9，a/b/c/d/e/f(大小写均可)，以0x（0X）开头

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


* 进制间的相互转换
* * 其他进制转换成十进制
* * * 系数：每一位上的数值
* * * 基数：x进制的基数就是x
* * * 权：每一位上的数据，从右开始，从0开始编号，对应的编号就是该数据的权
* * * 结果：系数*基数<sup>权</sup>


* ![image](../../assets/img/JAVASE/java-04.png)

* * 十进制转换成其他进制
* * * 除基取余，直到商为零，余数反转


* ![image](../../assets/img/JAVASE/java-05.png)

* * 进制的快速转换法
* * * 十进制和二进制的快速转换
* * * * 8421码
* * * * 8421码是中国大陆的叫法，8421码是BCD代码中最常用的一种。在这种编码方式中每一位二值代码的1都是代表一个固定数值，把每一位的1代表的十进制数加起来，得到的结果就是它所代表的十进制数码。由于代码中从左到右每一位的1分别表示8，4，2，1，所以把这种代码叫做8421代码。每一位的1代表的十进制数称为这一位的权。8421码中的每一位的权是固定不变的，它属于恒权代码。


* ![image](../../assets/img/JAVASE/java-06.png)

* * * * 二进制到八进制、十六进制的转换


* ![image](../../assets/img/JAVASE/java-07.png)

* * 有符号数据的表示法
* * * 在计算机内，有符号的数据有三种表示方法：原码、反码和补码。所有数据的运算都是采用补码进行的。
* * * * 原码：
* * * * 反码：
* * * * 补码：

<font size="5">(2)</font>[<font color="blue" size="5">原码、反码、补码详解</font>](http://www.cnblogs.com/zhangziqiu/archive/2011/03/30/ComputerCode.html)


![image](../../assets/img/JAVASE/java-08.png)

### 六：变量及数据类型
* 变量
* * 在程序的执行过程中，其值在某个范围内可以发生变化的量
* 变量的定义格式
* * 数据类型 变量名 = 初始化值
* * 数据类型 变量名; 变量名 = 初始化值


* 数据类型
* * 基本数据类型（四类八种）
* * * 整数
* * * * byte
* * * * short
* * * * int
* * * * long
* * * 浮点数
* * * * float
* * * * double
* * * 字符
* * * * char
* * * 布尔
* * * * boolean
* * 引用数据类型

<table>
  <tr align="center">
    <td colspan="4">数据类型——整数</td>
  </tr>
  <tr align="center">
    <td>类型</td>
    <td>占用存储空间</td>
    <td>表数范围</td>
    <td>默认值</td>
  </tr>
  <tr align="center">
    <td>byte</td>
    <td>1字节</td>
    <td>-128 - 127</td>
    <td rowspan="4">int</td>
  </tr>
  <tr align="center">
    <td>short</td>
    <td>2字节</td>
    <td>-2<sup>15</sup> - 2<sup>15</sup> - 1</td>
  </tr>
  <tr align="center">
    <td>int</td>
    <td>4字节</td>
    <td>-2<sup>31</sup> - 2<sup>31</sup> - 1</td>
  </tr>
  <tr align="center">
    <td>long</td>
    <td>8字节</td>
    <td>-2<sup>63</sup> - 2<sup>63</sup> - 1</td>

  </tr>
  <tr align="center">
    <td colspan="4">数据类型——浮点数</td>
  </tr>
  <tr align="center">
    <td>类型</td>
    <td>占用存储空间</td>
    <td>表数范围</td>
    <td>默认值</td>
  </tr>
  <tr align="center">
    <td>float</td>
    <td>4字节</td>
    <td>-3.402823E38 - 3.402823E38</td>
    <td rowspan="2">double</td>
  </tr>
  <tr align="center">
    <td>double</td>
    <td>8字节</td>
    <td>-1.797,693,134,862,32E308 - 1.797,693,134,862,32E308</td>
  </tr>
  <tr align="center">
    <td colspan="4">数据类型——字符型</td>
  </tr>
  <tr align="center">
    <td>类型</td>
    <td>占用存储空间</td>
    <td>表数范围</td>
    <td>默认值</td>
  </tr>
  <tr align="center">
    <td>char</td>
    <td>2字节</td>
    <td></td>
      <td></td>
  </tr>
  <tr align="center">
    <td colspan="4">数据类型——布尔型</td>
  </tr>
  <tr align="center">
    <td>类型</td>
    <td>占用存储空间</td>
    <td>表数范围</td>
    <td>默认值</td>
  </tr>
  <tr align="center">
    <td>boolean</td>
    <td>1字节</td>
    <td>false,true</td>
    <td>false</td>
  </tr>
</table>

* 数据类型转换
* * boolean类型不参与转换
* * 默认转换
* * * 从小到大
* * * byte/short/char-->int-->float-->long
* * * byte/short/char相互间不进行转换，直接转换成int类型参与运算。


* * 强制转换
* * * 从大到小
* * * 可能会有精度的损失，一般不建议使用
* * * 格式
* * * * 目标数据类型 变量名 = （目标数据类型）（被转换的数据）


* **<font color="red">知识补充</font>**

* 1：在定义Long或者Float类型变量的时候，要加L或f。
* * 整数默认是int类型，浮点数默认是double类型。
* 2： byte、short在定义的时候接收的其实是一个int类型的值。当定义的数据在byte的范围内时，程序会正常运行，否在在编译过程中会报错。
* * byte b1 = 127;
* * byte b2 = (byte)128;  //-128
* * byte b3 = (byte)129;  //-127
* * byte b4 = (byte)130;  //-126
* * byte的范围：-128 ~ 127
* * 128：10000000
* * -128：10000000（这里的1既是符号位，也是数值位）
* 3：数据类型转换之默认转换
* * byte/short/char-->int-->long-->float-->double
* * long：8 字节
* * float：4字节
* * **<font color="red">它们的底层存储结构不相同</font>**
* * **<font color="red">flaot表示的数据范围比long的范围要大</font>**
* 4：Java语言的字符char可以存储一个中文汉字吗？为什么呢？
* * 可以。因为java语言中的字符占用两个字节。
* * Java语言采用的是Unicode编码。


* Unicode编码表

* ![image](../../assets/img/JAVASE/java-10.jpg)


* ASC码表

![image](../../assets/img/JAVASE/java-09.jpg)

### 七：运算符
