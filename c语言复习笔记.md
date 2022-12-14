# c语言复习笔记

## 一.编程的几个基本思想

1.模块化思想

把实现特定功能的代码单独拿出来，单独作为一个函数，使主函数简短易懂，有许多好处：

（1）可使自己重新来看时，更快的理解代码含义。

（2）可使自己在编程时专心地实现某一功能，使整个编程思路更加清晰。

（3）可使一起工作的同事更快的明白你的代码，并尽快的上手与你协作。

（4）可使学长学姐方便的给你纠错，解惑。

2.过滤的思想

防止程序崩溃，提前结束程序，使用户按照你的思路来走，使你的程序可靠性更强。

3.调试的思想

在程序报错后，我们有许多方式去debug：eg.在不知道的变量后加printf函数，或者是使用编译器自带的调试台，进行一步步的调试，从而得到某个变量的状态，进而与自己的预期相比较，发现问题的源头。

4.注释的思想

注释是注明这个语句的目的，或是这个变量的含义，编程语言的基本要求是让计算机读懂，而更重要的是让人类读懂你所写的内容。

（1）函数的方法注释写在开头，格式:   目的：

​																	参数：						

这可以让你的思路更加清晰，对编程有很大好处。

（2）行注释写在同行，方便理解处理。

## 二.基本数据类型

数据类型分为三种，分别为基本类型，构造类型，指针类型。其中的基本类型又分为整型，字符类型，浮点型，浮点型又分为单精度和双精度型；构造类型分为枚举类型，数组类型，结构体类型，共用体类型。

## 三.基本运算符

#### 1.基本运算符

| 加   | 减   | 乘   | 除   | 余   | 自增 | 自减 |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| +    | -    | *    | /    | %    | ++   | --   |

#### 2.赋值运算符

赋值号：a=b（把b的值赋给a）；

#### 3.关系运算符

| 大于 | 等于 | 小于 | 小于等于 | 大于等于 |
| ---- | ---- | ---- | -------- | -------- |
| >    | ==   | <    | <=       | >=       |

#### 4.逻辑运算符

| 并   | 或   | 非   |
| ---- | ---- | ---- |
| &&   | \|\| | ！   |

#### 5.三目运算符

形式：表达式1  ？ 表达式2  ：表达式3        ，意为如果一为真，实行二，如果一为假，实行三；

## 四.基本语句

### 1.if-else语句

if（条件语句）{

执行语句-1	}；

else

{	执行语句-2	

​				}；

其意义是如果条件语句为真，则执行语句1，如果为假，则执行语句2。if语句可单独使用，但如果后面的语句超过一句，需要加花括号。

else的对应法则为就近原则。

### 2.while循环语句

while（条件语句）

{

循环语句

}；

其意义是一直循环，直到条件语句为假，所以要注意退出循环的条件，否则会进入死循环。

### 3.do-while循环语句

do

{执行代码块

}while（表达式）；

其意义是先执行执行代码块，然后再判断while中表达式是否为真，如果真，继续循环，如果假，退出循环。

### 4.for循环语句

for（表达式1；表达式2；表达式3）

{		执行代码块

}；

其意义是先执行表达式一，初始化循环变量，然后判断表达式二，如果为真，则执行下面的代码块，如果为假，退出循环。然后后执行表达式三，再执行代码块；表达式一只会执行一次。如果三个表达式都不放语句，则会进入无限循环。

### 5.break语句

其意义是在执行到break语句时退出当前循环，如果在多重循环中，则只退出break语句所在的循环，在没有循环的if-else语句中，break语句不能使用。

### 6.continue语句

其意义是结束本次循环开始执行下一次循环，意义为将本次循环结束到

你想结束的位置。

### 7.switch语句

switch（表达式）

​				case 常量表达式1：执行代码块1

​						break；

​				case常量表达式2：执行代码块2

​						break；

​				........ break；

default：执行代码块n+1；

意为选择进行哪一项语句。p.s.case常量的值不能相同，否则会出错。

​													各语句末尾的break不能少，否则跳不出switch语句。

​													switch后面的表达式只能是整型或字符类型。

## 五.基本函数

#### 1.printf函数

printf（”要输入的内容为“）；

sum=1+2；

printf（”1+2=%d“，sum）；

这里int类型对应的是%d

​		char类型对应%c

​		float类型对应%f，m.n，m即域宽，即实型数所占总的位数，包含小数点。n指精度，即小数位数；eg.%4.2表示小数点后两位；

​		字符串对应%s

#### 2.scanf函数

int sum=0；

scanf（”%d“，&sum）；

如果要输入多位数，需要连续输入%x，例如

scanf（”%d%d%d“，&sum，&sum-1，sum-2）；

p.s.

scanf与printf混合使用时，一定要注意在printf结束后敲得回车键会被scanf函数吸收，从而跳过你需要输入的数据，处理办法是在%号前面加一个空格，空格会吸收回车。

## 五.自创函数

#### 定义函数

[数据类型] 函数名称 （参数）

​	{执行代码块

}；。

自定义函数可以实现特定的功能，最好在主函数之前写好，如果放在main函数之后还需要声明函数。

#### 调用函数

形式为：

函数名（参数）；

#### 形参与实参

形参是在定义函数时用到的盒子，徒有其表，目的只是代表这么一个数据，但没有实际意义，出了自创函数就变得无意义。

而实参是全局的有意义的变量，它将主函数里的数据传给了自创函数里的形参，它在整个程序里都有实际意义。

#### 函数的返回值

分两种情况，一种情况是函数为void，一种有数据类型的函数，void函数不需要返回值，因为它内部的函数体都是在程序最底层的数字上进行修改；而其他类型的函数更像是独立出来算一个数值，所以需要一个return去把所得值返回主函数去。

#### 递归函数

即在函数内部再次引用一次函数从而达到循环往复的效果，多次计算，比如阶乘。

## 六.数组

数组的定义是在计算机内部的一块连续的，大小固定并且里面的数据类型一样的内存空间。

#### 声明数组

数据类型  数组名称[长度]；

#### 初始化数组

数据类型 数组名称[长度n]={元素1，元素2，...元素n}；

数据类型  数组名称[]={元素1，元素2，...元素n}；

ps 1.数组的下标均以0开始。  

​      2.数组内元素的个数不能超过声明时的长度。

#### 数组的遍历

用一个循环可以很容易实现数组的遍历

但有几点要注意：

##### 1.避免数组越界，即变量大小别超过数组长度

##### 2.数组的长度一经确认，就不能更改。

## 七.字符串

使用数组来定义我们需要的字符串。

例.1.char  字符串名称[长度]=“字符串值”；

​	  2.char  字符串名称[长度]={”字符1“，”字符2“，...”字符n“、\0};

ps.长度可以省略不写

​		第二种方法时无法输入中文，且结尾必须有\0；

#### 常用的字符串函数

| 函数格式         | 说明                                                 | 举例                           |
| ---------------- | ---------------------------------------------------- | ------------------------------ |
| strlen（s）      | 获得字符串的长度（单位字节）                         | strlen（“abc”），结果为3       |
| strcmp（s1，s2） | 比较字符串，先转化为ascⅡ码，再进行比较，不能比较整型 | strcmp（“ab“，”ac“），结果为-1 |
| strcpy（s1，s2） | 字符串拷贝                                           | strcpy（s1，”abc“）            |
| strcat（s1，s2） | 把字符串s2拼接到s1后面                               | strcat（s1，“abc”）            |
| atoi（s1）       | 字符串转换为整型                                     | atoi（“100”）。结果：100       |



​	强调：strcmp函数时会先把字符串转化成ASCⅡ码进行比较，如果结果为0，则s1与s2长度一样，且不能比较整型吗，因为在它会提前返回值。																									结果为1，则s1比s2长																													结果为-1，则s1比s2短。

## 八.多维数组

数组类型  数组名称 [常量表达式1]		[常量表达式2]{  值1，值2} {值3，值4}；	

ps.1.初始化数组时必须指定列的维数，因为系统会根据数组中元素的总个数来分配空间。

## 九.指针

指针是计算机内存里存储数据的一个地址，指针的作用是指向这个地址。

#### 1.指针的类型

将指针名称去掉后就是指针的类型。eg. 		int *ptr

​																			char*ptr

 指针的类型决定了指针所指区域上的数据是被当作什么来处理的，例如int类型的指针，那么编译器就会将指针所指的地址上的数据当作整数来处理，char类型的指针就会把这些数据当做字符类型的数据来处理。

#### 2.指针的运算

指针的运算不是常规数学意义上的运算，而是再经过编译器编译后的运算，例如，int*ptr；

​																																			ptr++；

这里指的是将ptr指针在原来所指的位置在往后挪动一个单位长度（根据数据类型来决定），以此来遍历整个数组。

#### 3.数组和指针的关系

数组的数组名其实可以看成一个指针，指向这个数组的第一个元素所在的地址。

