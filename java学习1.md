## java变量

> ####1.1变量的三个基本要素

* **变量**

* **名称**

* **值**

  关于变量

![image-20211231192412495](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20211231192412495.png)

> 变量的基本原理

![image-20211231195320274](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20211231195320274.png)

####变(变化)量(值)的介绍

> 概念

==**变量相当于内存中一个数据存储空间的表示，可以将变量看做是一个房间的门牌号，通过门牌号可以找到房间，而通过变量名可以访问到变量(值)**==

步骤：

1. 声明变量   				int a;
   1. 赋值					a = 60;
   2. 使用                    System.out.println(a);

> 变量使用注意事项

```
1、变量表示内存中的一个存储区域(不同的变量，类型不同，占用的空间大小不同，eg:int占用4个字节, double占用8字节)
2、该区域有自己的名称(变量名)和类型(数据类型)
3、变量必须先声明，后使用，即有顺序
4、该区域的数据可以在同一类型范围内不断变化
5、变量在同一个作用域内不能重名
6、变量=变量名+值+数据类型(变量三要素)
```



> ####2.1程序中 +号的使用

1. 当左右两边都是数值型时，则做加法运算
2. 当左右两边有==一方为字符串==，则做拼接运算
3. 运算顺序，是从左到右

![image-20211231235719952](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20211231235719952.png)





															## java数据类型

每一种数据都定义了明确的数据类型，在内存中分配了不同大小的内存空间(字节)

![image-20220101000350444](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220101000350444.png)

* 整数类型

  Java中的整数类型就是用于存放整数值的

  byte n1 = 10; //1个字节  short n2 = 10; //2个字节

  但是n1和n2的空间大小不同

  ![image-20220101015631628](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220101015631628.png)

> 整数类型的细节

* 整型的使用细节

  ```
  1. Java各整数类型有固定的范围和字段长度，不受具体OS的影响，以保证java程序的可移植性。
  2. Java的整型常量默认为int型，声明long型常量须后面加'l'或者'L'
  	eg: int n1 = 1;   long n2 = 1L;
  3. java程序中变量常声明为int，除非不足以表示大数，才使用long
  4. bit:计算机中的最小存储单位。byte:计算机中基本存储单元, 1byte=8 bit
  ```

![在内存中](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220101101319108.png)

```
			byte n1 = 3;
```

<img src="C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220101101619045.png" alt="image-20220101101619045" style="zoom: 67%;" />



> 浮点数类型细节

![image-20220101101807914](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220101101807914.png)

​	1、关于浮点数在机器中，==浮点数=符号位+指数位+尾数位==
​	2、尾数部分可能丢失，造成精度损失

```
1、与整数类型类似，java浮点类型也有固定的范围和字段长度，不受具体OS的影响。[float是4个字节，double是8个字节]
2、Java的浮点型常量默认为double型，声明float型，须后面加'f'或者'F'
3、浮点型常量有两种表示形式
	十进制数形式：	5.12   512.0f    .512(必须有小数点)
    科学计数法形式：5.12e2[ 5.12*10的2次方 ]	5.12E-2[ 5.12/10的二次方 ]
4、通常情况下，应该使用double型,应为它比float型更精确。
	double num9 = 2.1323423;
	float  num10 = 2.123431F;
5、浮点数使用陷阱:2.7和8.1/3比较
```

==下面的使用==

````java
	float num1 = 1.1; //这个是错误的,这个是double的
	float num2 = 1.1F;	//这个是对的
	double num3 = 1.1f;	//这个也是对的
	double num4 = .123;	//这个也是对的     0.123
````



> 浮点型细节2

//浮点型使用陷阱:   2.7和	8.1 / 3比较

```java
double num5 = 2.7;
double num6 = 8.1 / 3;	//这个是接近2.7，但不是2.7
```

<img src="C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20210715130903237.png" alt="image-20210715130903237" style="zoom:67%;" />

出现这个的原因是因为计算机认为8.1是==看作==8.1000000001 / 3

==下列不可使用==

```java
//对于上面num11和num12，不能仅仅简单地	num11 == num12
//应该是以两个数地差值地绝对值，在某个精度范围类判断
```



正确的写法	==(ctrl + /是多行注销) 浮点数使用陷阱==

```java
//	System.out.println(Math.abs(num11 - num12));
//下列写法
	if (Math.abs(num11 - num12) < 0.000001)
    {
        System.out.println("差值非常小，到我的规定精度，认为相等...");
    }
```

细节：如果是直接查询得到的小数或者直接赋值，是可以直接判断相等



## Java API文档

是Java提供的基本编程接口，如下是链接

[在线API里面](https://www.matools.com)	

> Java类的组织形式

![image-20220101134626209](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220101134626209.png)

[具体细节](https://www.bilibili.com/video/BV1fh411y7R8?p=46&spm_id_from=pageDriver)



> 字符类型(char)

* 字符类型可以表示==单个字符==，字符类型是char，char是两个字节(可以存放汉字)，多个字符我们用字符串String

* ```java
  代码:
  	char c1 = 'a';
  	char c2 = '\t';
  	char c3 = '韩';
  	char c4 = 97;	//字符类型可以直接存放一个数字
  ```



> 字符类型的本质

```
1、字符型 存储到计算机中，需要将字符对应的码值(整数)找出来，比如'a'
	存储：'a'==>码值97==>二进制(110 0001)==>存储
	读取：二进制(110 0001)==>97==>'a'==>显示
2、字符和码值的对应关系是通过字符编码表决定的(是规定好的)
```

* ASCII 编码表：每个字符由一个字节表示，一共有128个字符，实际上一个字节可以表示256个字符，只用128个

* Unicode：固定大小的编码，使用两个字节来表示字符，字母和汉字统一都是占用两个字节，==浪费空间==
* utf-8：大小可变的编码，字母使用1个字节，汉字使用3个字节
* gbk：可以表示汉字，且范围广，字母使用1个字节，汉字使用2个字节
* gb2312：可以表示汉字，gb2312 < gbk
* big5码：繁体中文，台湾，香港





> 布尔类型：boolean

```java
基本介绍
1、boolean数据只允许取值true和false,无null
2、boolean类型占1个字节
3、boolean类型适用于逻辑运算，一般用于程序流程控制
	(1)if条件控制语句
	(2)while循环控制语句
	(3)do-while循环控制语句
	(4)for循环控制语句

boolean pass = true;
if (pass) {
    cout << "111";
} else {
    cout << "222";
}
```

> boolean使用细节

不可以0或非0的整数替代false和true，这里和C语言不同，只能是false或true



##Java基本数据类型的转换

> 当java程序在进行赋值或者运算时，精度小的类型自动转换为精度大的数据类型，这个就是自动类型转换

![image-20220101150030634](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220101150030634.png)

例如：

```java
int a = 'c';	//√
double d = 80;	//√
```



> 基本数据类型转换的细节

```java
1、有多种类型的数据混合运算时，系统首先自动将所有数据转换成容量最大的那种数据类型，然后再进行计算。
    int n1 = 10;
	float d1 = n1 + 1.1;
上面的代码是错误的，因为在多个类型的数据混合运算时，n1 + 1.1会先变成double，但是double不能变成float,精度损失。
要想接受:
	float d1 = n1 + 1.1F;

2、当我们把精度(容量)大 的数据类型赋值给精度(容量小)的数据类型时，就会报错，反之会进行自动类型转换。
    int n1 = 1.1;	//这个就是错误的	doubel->int
	
3、(byte、short)和char之间不会相互自动转换
	当把数赋给byte时,(1)先判断该数是否在byte范围内，如果是就可以
    一个案例：
    	int n2 = 1;
		byte b2 = n2;//是错误的，n2是在四个字节的，不能放到一个字节的

4、byte,short,char 他们三者可以计算，在计算时首先转为int型
	byte b2 = 1;
	short s1 = 1;
	short s2 = b2 + s1;	//是错误的,b2 + s1 => int，即int变为short有损失
同理：
    byte b3 = 1;
	byte b4 = b2 + b3;	//也是不行的，这个结果也是int的

5、boolean不参与转换
	boolean pass = true;
	int num100 = pass;	//这个是错误的，boolean不参与类型自动转换
    
6、自动提升原则:表达式结果的类型自动提升为操作数中最大类型
    byte b4 = 1;
	short s3 = 100;
	int num200 = 1;
	double num300 = 1.1;
	double num500 =  b4 + s3 + num200 + num300;	//这个会转换为最大类型=>double
	同理:
	float num600 = 1.1F;
	int num = 1;
	num600 + num;	//===>转换为float
```

![image-20220101154732156](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220101154732156.png)



> 基本数据类型的强制转换

```java
定义：
    是自动类型转换的逆过程，将容量大的数据类型转换为容量小的数据类型。使用时要加上强制转换符(),	但可能造成精度降低或溢出，需要格外注意
例如:
	int i = (int)1.9;
	cout << i << endl;	//1

	int j = 100;
	byte i = (byte)j;
例如:
	int n1 = (int)1.9;
	System.out.println("n1 = " + n1);	//1     精度损失
	
	int n2 = 2000;
	byte b1 = (byte)n2;
	System.out.println("b1 = " + b1);	//-48	数据溢出
```



1. 当进行数据的大小从	大——小,就需要用到强制转换

   

2. 强转符号只针对最近的操作数有效，往往会使用小括号提升优先级

```java
int x = (int)10 * 3.5 + 6 * 1.5;	//意思就是10转成10再乘以3.5,所以整个结果的类型是double类型
int x = (int)(10 * 3.5 + 6 * 1.5);	//这个才是对的	
```

3. char类型可以保存int的常量值,但不能保存int的变量值,需要强转

```java
char c1 = 100;
int m = 100;
char c2 = m;	//因为int的精度要高于char,所以错误的
char c3 = (char)m;	//这个是对的
```

4. byte和short, char类型在进行运算时,当作int类型处理

### 基本数据类型和String类型的转换

> 在开发中，经常将基本数据类型转换成String类型，或者将String类型转换成基本数据类型

* 基本类型转String类型	语法:将基本类型的值+""即可
* String 类型转基本数据类型   语法：通过基本类型的包装类调用parseXXX即可

```java
1、基本数据类型转字符串
    int n1 = 100;
	float n2 = 1.1f;
	double n3 = 3.4;
	boolean b1 = true;
	String str1 = n1 + "";
	String str2 = n2 + "";
	String str3 = n3 + "";
	String str4 = b1 + "";

2、String类型转基本数据类型
    Integer.parseInt("123");
	Double.parseDouble("123.1");
	Float.parseFloat("123.45");
	Short.parseShort("12");
	Long.parseLong("1234");
	Boolean.parseBoolean("true");
	Byte.parseByte("123");

3、将字符串转换成char---->得到字符串的第一个字符
    String s5 = "123";
    System.out.println(s5.charAt(0));	//将s5字符串的第一个字符'1'
```

> 一些细节

1. 在将String类型转换成基本数据类型时，要确保String类型能够转换成有效的数据,比如可以把"123",转换成一个整数，但是不能把"hello"转换成一个整数。
2. 如果格式不正确，就会抛出异常，程序就会终止。



##运算符

> 运算符是一种特殊的符号,用以表示数据的运算、赋值和比较等

```
1、算术运算符
2、赋值运算符
3、关系运算符(比较运算符)
4、逻辑运算符
5、位运算符(需要二进制)
6、三元运算符
```

###算术运算符

> 算术运算是对数值类型的变量进行运算的

![image-20220101231432300](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220101231432300.png)

如果有疑问,点击下面链接

[算术运算](https://www.bilibili.com/video/BV1fh411y7R8?p=68)

### 比较运算符（关系运算符）

>1、关系运算符的结果都是boolean型，要么是true，要么是false
>
>2、关系表达式经常用在if结构中或循环结构的条件中

![image-20220101232024669](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220101232024669.png)

```java
	int a = 9;
	int b = 8;
	System.out.println(a > b);	//会输出true
	System.out.println(a >= b);	//会输出true
```



###逻辑运算符

> 用于连接多个条件(多个关系表达式)，最终的结果也是一个boolean值

![image-20220101232539328](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220101232539328.png)

````
1、a & b: &叫逻辑与:		当a和b同时为true,则结果为true,否则为false
2、a && b: &&叫短路与:	当a和b同时为true,则结果为true,否则为false
3、a | b: |叫逻辑或:		当a和b,有一个为true,则结果为true,否则为false
4、a || b: ||叫短路或:   当a和b,有一个为true,则结果为true,否则为false
5、!a: 叫取反,或者非运算:  当a为true,则结果为false
6、a^b: 叫逻辑异或,当a和b不同时,则结果为true,反之为false
````



> &和&&的区别

```
1、&&短路与:如果第一个条件为false,则第二个条件不会判断,最终为false,效率高
2、&逻辑与:不管第一个条件是否为false,第二个条件都要判断,效率低
```

![image-20220101234644935](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220101234644935.png)



> || 和 | 的区别

```
1、||短路或:如果第一个条件为true,则第二个条件不会判断,最终结果为true,效率高
2、| 逻辑或:不管第一个条件是否为true,第二个条件都要判断,效率低
```

![image-20220101235624066](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220101235624066.png)



> 逻辑非和逻辑异或^

![image-20220102000403676](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220102000403676.png)

```java
System.out.println(!(60 > 20));	//T->F, F->T
//a^b: 叫做逻辑异或,当a和b不同时,则结果为true,否则为false
boolean b = (10 > 1) ^ (3 < 5);	//0
```

### 赋值运算符

```java
1、运算顺序是从右往左	int num = a + b + c;
2、赋值运算符的左边只能是变量,但是右边可以是变量、表达式、常量值
    int num = 20;	int num2 = 78 * 34 - 10;   int num3 = a;
3、复合赋值运算符等价于下面效果
    a += 3  ====>  a = a + 3;
4、复合赋值运算符会进行类型转换
    byte b = 2; b += 3; b++;
其中:
	b += 2;	===>b = (byte)(b + 2);
	b++;	===>b = (byte)(b + 1);
```

###

### 三元运算符

![image-20220102005346810](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220102005346810.png)

> 使用细节

```java
1、表达式1和表达式2要可以赋给接收变量的类型(或可以自动转换)
    int a = 3;
	int b = 8;
	int c = a > b ? 1.1 : 3.4;	//这个就是错误的
				 (int)1.1 : (int)3.4;	//这个是可以的    

2、三元运算符可以转换成if--else语句	
```



### 运算符优先级

![image-20220102010514704](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220102010514704.png)



## 标识符的命名规则和规范

> 标识符概念

```java
1、Java对各种变量、方法和类等命名时使用的字符序列称为标识符
2、凡是自己可以起名字的地方都叫标识符	int num1 = 90;

标识符命名规则:
1、由26个英文字母大小写,0~9, _或$组成
2、数字不可以开头	int 3ab = 1;	×
3、不可以使用关键字和保留字,但能包含关键字和保留字
4、Java中严格区分大小写,长度无限制。	int totalNum = 10; int n = 90;
5、标识符不能包含空格		int a b = 90;
```

> 保留字

![image-20220102012325803](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220102012325803.png)

![image-20220102012416979](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220102012416979.png)



> 标识符命名的规范

```
1、包名:多单词组成时所有字母都小写:	aaa.bbb.ccc	//比如com.hsp.crm
2、类名、接口名:多单词组成时，所有单词的首字母大写:	XxxYyyZzz
	TankShotGame[大驼峰]
3、变量名、方法名:多单词组成时,第一单词首字母小写,第二个单词开始每个单词首字母大写:xxxYyyZzz[小驼峰，简称:驼峰法]
	tankShotGame
4、常量名:所有字母都大写。多单词时每个单词用下划线连接:XXX_YYY_ZZZ
	比如定义一个所得税: TAX_RATE
```



> 关键字

```
被Java语言赋予了特殊含义,用做专门用途的字符串(单词)
```

![image-20220102105933119](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220102105933119.png)

![image-20220102110831412](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220102110831412.png)



> 保留字

```
Java保留字:现有Java版本尚未使用,但以后版本可能会作为关键字使用。自己命名标识符时要避免使用这些保留字。
```

![image-20220102111032923](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220102111032923.png)



> 键盘输入语句

```
定义:
	在编程中,需要接收用户输入的数据,就可以使用键盘输入语句来获取。
	Input.java,需要一个扫描器(对象),就是Scanner
使用步骤:
	1、导入该类的所在包,java.util.*
	2、创建该类对象(声明变量)
	3、调用里面的功能
```

```java
1、导入	import java.util.Scanner;
//Scanner类 表示 简单文本扫描器 在java,util包
2、创建 Scanner 对象, new就是创建一个对象
	Scanner myScanner = new Scanner(System.in);
//myScanner就是Scanner类的对象
3、接收用户的输入
    System.out.println("请输入名字");
	String name = myScanner.next();	//这个就是表示要接收用户的输入
	System.out.println("请输入年龄");
	int age = myScanner.nextInt();
	System.out.printin("请输入薪水");
	double sal = myScanner.nextDouble();
	System.out.printin("name = " + name + "age = " + age + "sal = " + 							sal);
```



## 进制转换

> 1、进制

```java
对于整数,有四种表示方式:
	1、二进制: 0,1, 满2进1.以0b或0B开头
    2、十进制: 0-9, 满10进1
    3、八进制: 0-7, 满8进1 以数字0开头表示
    4、十六进制: 0-9及A(10)-F(15),满16进1, 以0x或0X开头表示。此处的A-F不区分大小写
    int n1 = 0b1010;	//这个是二进制
	int n2 = 1010;		//这个是十进制
	int n3 = 01010;		//这个是八进制
	int n4 = 0x10101;	//这个是十六进制
```

![image-20220102113924342](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220102113924342.png)

![image-20220102113947376](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220102113947376.png)



> 二进制转十进制

```
从最低位(右边)开始,将每个位上的数提取出来,乘以2的(位数-1)次方,然后求和
```

![image-20220102114509077](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220102114509077.png)



> 八进制转十进制

```
从最低位开始,将每个位上的数提取出来,乘以8的(位数-1)次方,然后求和
```

![image-20220102115901364](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220102115901364.png)



> 十六进制转十进制

```
从最低位开始,将每个位上的数提取出来,乘以16的(位数-1)次方,然后求和
```

![image-20220102124242347](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220102124242347.png)



> 十进制转二进制

```
将该数不断除以2,直到商为0为止,然后将每步得到得余数倒过来,就是对应的二进制
```

![image-20220102124813274](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220102124813274.png)



> 十进制转成八进制

```
将该数不断除以8,直到商为0为止,然后将每步得到的余数倒过来
```

![image-20220102125802187](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220102125802187.png)



> 十进制转十六进制

```
将该数不断除以16,直到商为0为止,然后将每步得到的余数倒过来
```

![image-20220102135521361](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220102135521361.png)



> 二进制转八进制、十六进制

```
从低位开始,将二进制每三位一组,转成对应的八进制数即可
```

![image-20220102135935392](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220102135935392.png)



> 二进制转十六进制

```
从低位开始,将二进制每四位一组,转成对应的十六进制数
```

![image-20220102140204303](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220102140204303.png)



> 八进制转成二进制

```
将八进制数每1位,转成对应的一个3位的二进制数即可
```

![image-20220102140352884](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220102140352884.png)



> 十六进制转成二进制

```
将十六进制数每1位，转成对应的4位的一个二进制数即可
```

![image-20220102140630879](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220102140630879.png)



### 原码、反码、补码

```java
1、二进制的最高位是符号位：0表示正数,1表示负数
2、正数的原码,反码,补码都一样
3、负数的反码=它的原码符号位不变,其它位取反(0->1, 1->0)
4、负数的补码=它的反码+1, 负数的反码=负数的补码-1
5、0的反码,补码都是0
6、java没有无符号数,即java中的数都是有符号的
7、在计算机运算的时候,都是以“补码的方式”来运算的
8、当我们看运算结果的时候,要看他的原码(!!!)
```



> 位运算符

```java
java中有7个位运算(&、|、^、~、>>、<<和>>>)
```

![image-20220102142327581](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220102142327581.png)

```java
	2 & 3
//1、先得到2的补码	  =>2的原码 00000000 00000000 00000000 00000010	
        		  =>2的补码   00000000 00000000 00000000 00000010	
  2、得到3的补码	   =>3的原码 00000000 00000000 00000000 00000011
        		   =>3的补码 00000000 00000000 00000000 00000011
  3、按位	& 
        		   =>结果	  00000000 00000000 00000000 00000010 这是补码
  4、这里补码和原码一样
        
    ~-2
//1、先得到-2的原码  =>-2的原码 10000000 00000000 00000000 00000010
        		  =>-2的补码 = 负数的补码=它的反码+1
        		  =>-2的反码  11111111 11111111 11111111 11111101
        		  =>-2的补码  11111111 11111111 11111111 11111110
      这个是补码    =>~-2操作   00000000 00000000 00000000 00000001
      因为是正数,所以运算后就是这个
    
   ~2
//1、得到2的补码	 =>2的补码	00000000 00000000 00000000 00000010
        		 =>~2操作 11111111 11111111 11111111 11111101运算后的补码
        	=>补码-1变反码 11111111 11111111 11111111 11111100
        	=>运算后的原码 就是符号位不变,其他位取反
        				  10000000 00000000 00000000 00000011
        结果是-3
```



> 位运算

```java
>>、<<和>>>
1、算术右移>>: 低位溢出,符号位不变,并用"符号位"补溢出的高位
2、算术左移<<: 符号位不变,低位补0
3、>>>逻辑右移也叫无符号右移,低位溢出,高位补0
4、没有<<<符号
    
	int a = 1 >> 2;	//=>00000000 00000000 00000000 00000001
				   变为=>00000000 00000000 00000000 00000000
                       本质是 1 / 2 / 2
    int c = 1 << 2; //=>00000000 00000000 00000000 00000001
				   变为=>00000000 00000000 00000000 00000100	
                       本质是 1 * 2 * 2 = 4
	4 << 3  ====>相当于 4 * 2 * 2 * 2
    15 >> 2 ====>相当于 15 / 2 / 2              
```



## 顺序控制

```java
程序运行的流程控制
    (1)顺序控制
    (2)分支控制
    (3)循环控制
```

![image-20220102152139417](C:\Users\蒋海\AppData\Roaming\Typora\typora-user-images\image-20220102152139417.png)

[详细](https://www.bilibili.com/video/BV1fh411y7R8?p=141)

































​	

