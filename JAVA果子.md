# Java入门

**使用软件**： IntelliJ IDEA Community Edition 2024.2 

**JDK版本**：jdk-17.0.2



## 常见的CMD命令



### 切换盘符

```
E: + 回车
```



### 查看当前路径下的内容

```
dir
```



### 进入单级目录

```
cd
```



### 回退上级目录

```
cd..
```

具体使用方式与虚拟机终端中的一致



### 清屏

```
cls
```



### 退出命令提示符窗口

```
exit
```



### 使用cmd打开应用软件

```
可以到具体的文件下找到.exe文件自己打开，也可以直接将此应用程序配置到环境变量的path中，之后无论在哪个目录下都可以直接输入打开此应用
```

***例：***

![image-20250104200142610](C:/Users/ziyix/Desktop/JAVA/JAVA%E6%9E%9C%E5%AD%90.assets/image-20250104200142610.png)

![image-20250104200130479](C:/Users/ziyix/Desktop/JAVA/JAVA%E6%9E%9C%E5%AD%90.assets/image-20250104200130479.png)

配置完成后切记重新打开cmd，类似更新当前环境。



## JDK各个目录存放的东西



### bin

该路径下存放了各种工具命令。其中比较重要的有：**javac **和 **java**。



### conf

该路径下存放了相关配置文件。



### include

该路径下存放了一些平台特定的头文件。



### jmods

该路径下存放了各种模块。



### legal

该路径下存放了各模块的授权文档



### lib

该路径下存放了工具的一些补充JAR包。



## 使用记事本编写代码并用cmd运行

先在创建一个记事本，将扩展名修改为.java文件。并向内部编写以下内容

```
public class test{
	public static void main(String[] args){
		System.out.println("haohao");
	}
}
```

然后使用cmd命令窗口，使用jdk的bin目录下的 **javac.exe**（JDK提供的编译工具，将文件编译成.class文件） 程序对其进行编译成 **.class文件**。然后使用 **java.exe** 程序启动该文件（此时启动文件不需要带扩展名）

***例：***

![image-20250104225313686](C:/Users/ziyix/Desktop/JAVA/JAVA%E6%9E%9C%E5%AD%90.assets/image-20250104225313686.png)



## 配置环境变量

虽然安装时会自动配置，但是只支持最基本的四个组件。需要使用其他组件的时候需要自己配置环境变量。如下所示

![image-20250105194842642](C:/Users/ziyix/Desktop/JAVA/JAVA%E6%9E%9C%E5%AD%90.assets/image-20250105194842642.png)



![image-20250105194928979](C:/Users/ziyix/Desktop/JAVA/JAVA%E6%9E%9C%E5%AD%90.assets/image-20250105194928979.png)





## JDK 和 JRE

**JDK** 是 java 的开发工具包

- jvm虚拟机：java程序运行的地方

- 核心类库：java已经写好的东西，我们可以直接用

- 开发工具：javac，java，jdb，jhat...



**JRE** 是 java的运行环境

- 其中包含JVM，核心类库，运行工具



JDK，JRE，JVM 三者的包含关系

- JDK 包含了 JRE
- JRE 包含了 JVM



# Java基础概念



## 关键字

含义：被 Java 赋予了特定涵义的英文单词

关键字的字母 ***全部小写***

常用的代码编译器，针对关键字会有特殊的颜色标记。



### class

用于（创建 / 定义）一个类，后面跟随类名。类是 Java 中最基本的组成单元





## 字面量

数据在程序中的书写格式。

| 字面量类型 |               说明               |          举例           |
| :--------: | :------------------------------: | :---------------------: |
|  整数类型  |         不带小数点的数字         |        666，-88         |
|  小数类型  |          带小数点的数字          |      13.14，-5.20       |
| 字符串类型 |      用双引号包括起来的内容      |  "HelloWorld"，"好好"   |
|  字符类型  | 用单引号括起来的，内容只能有一个 |     'A'，'0'，'好'      |
|  布尔类型  |         布尔值，表示真假         | 只有两个值：true，false |
|   空类型   |        一个特殊的值，空值        |       值为：null        |

```java
public class ValueDemo1 {
    public static void main(String[] args) {
        // 整数
        System.out.println(445);
        System.out.println(-313);

        // 小数
        System.out.println(1.93);
        System.out.println(-2.2);

        // 字符串类型
        System.out.println("好好");
        System.out.println("haohao");

        // 字符类型
        System.out.println('A');
        System.out.println('好');

        // 布尔类型
        System.out.println(true);
        System.out.println(false);

        // 空类型
        // 无法直接印出来，数据为空时显示null
        System.out.println("null");

    }
}
```



## 特殊字符

### \t  制表符

在打印的时候，把前面的字符串的长度补齐到8，或者8的整数倍。最少补1个空格，最多补8个空格。

```java
public class test{
	public static void main(String[] args){
	System.out.println("name" + '\t' + "haohao");
        	System.out.println("age" + '\t' + "23");
	}
}
```

使用CMD的输出效果

![image-20250109190829892](C:/Users/ziyix/Desktop/JAVA/JAVA%E6%9E%9C%E5%AD%90.assets/image-20250109190829892.png)



使用Idea的输出效果

![image-20250109190856255](C:/Users/ziyix/Desktop/JAVA/JAVA%E6%9E%9C%E5%AD%90.assets/image-20250109190856255.png)

原因：在 **IDE 中**，制表符的效果受到 **编辑器设置和字体** 的影响。制表符的跳跃不一定是 8 字符的倍数，而是基于当前的显示设置（比如字体的宽度和行距）。这意味着如果你在字符串中使用制表符，制表符会根据当前的光标位置跳到下一个显示的制表位，而这个跳跃的间隔可能不是固定的。制表符（`\t`）并非所有环境都能完美地显示对齐。在 IDEA 或其他开发工具的控制台中，它可能并不会完全按照每 8 个字符的规则进行跳转，而是根据当前光标位置选择一个合适的对齐方式，这可能导致像 `haohao` 和 `23` 之间的位置看起来不一致。





## 变量

数据类型  变量名  =  数据值;

```java
public class test{
	public static void main(String[] args){
		int a = 10;
		System.out.println(a);
        
        int a = 10;
        int b = 20;
		System.out.println(a+b);
	}
}
```

注：

- 变量名不能重复

- 变量只能存储一个值

- 使用前一定要赋值



## 计算机中的数据存储

### 各进制的转换方法

![image-20250109194921469](C:/Users/ziyix/Desktop/JAVA/JAVA%E6%9E%9C%E5%AD%90.assets/image-20250109194921469.png)



![image-20250109195328498](C:/Users/ziyix/Desktop/JAVA/JAVA%E6%9E%9C%E5%AD%90.assets/image-20250109195328498.png)



## 数据类型

### 数据类型和字面量的区别

| **区别**       | **字面量**                                   | **数据类型**                                   |
| -------------- | -------------------------------------------- | ---------------------------------------------- |
| **定义**       | 字面量是代码中直接表示常量值的具体值。       | 数据类型是定义变量值结构和行为的规则。         |
| **作用**       | 字面量用于给变量赋值，作为常量出现在程序中。 | 数据类型确定变量或常量的值的类型及其操作方式。 |
| **例子**       | `42` (整数字面量), `"Hello"` (字符串字面量)  | `int`（整数类型），`String`（字符串类型）      |
| **存在的方式** | 字面量是程序中的常量直接值。                 | 数据类型是程序中变量声明的一部分。             |
| **类型关联**   | 字面量必须匹配所使用的变量的数据类型。       | 数据类型规定了可以接受的字面量的范围和类型。   |

​          

### 基本数据类型

| **数据类型** | **关键字** | **取值范围**                                            | **备注**                      |
| ------------ | ---------- | ------------------------------------------------------- | ----------------------------- |
| **整数类型** | `byte`     | -128 到 127                                             | 8 位有符号整数                |
| **整数类型** | `short`    | -32,768 到 32,767                                       | 16 位有符号整数               |
| **整数类型** | `int`      | -2,147,483,648 到 2,147,483,647                         | 32 位有符号整数               |
| **整数类型** | `long`     | -9,223,372,036,854,775,808 到 9,223,372,036,854,775,807 | 64 位有符号整数               |
|              |            |                                                         |                               |
| **浮点类型** | `float`    | ±1.4 × 10^-45 到 ±3.4 × 10^38 (有效位数：6-7 位)        | 单精度浮点数，32 位           |
| **浮点类型** | `double`   | ±4.9 × 10^-324 到 ±1.8 × 10^308 (有效位数：15-16 位)    | 双精度浮点数，64 位           |
|              |            |                                                         |                               |
| **字符类型** | `char`     | 0 到 65,535（Unicode字符）                              | 16 位无符号整数，表示一个字符 |
| **布尔类型** | `boolean`  | `true` 或 `false`                                       | 1 位，表示布尔值              |



### 整数和小数取值范围的大小关系

double > float > long > int > short > byte



**注：**

**long** 类型变量需要加入 L 标识 (大小写都可以)；

```
long num1 = 123L;
```

**float** 类型变量需要加入 F 标识 (大小写都可以)

```
float num2 = 12.3F;
```





## 定义变量的三个练习                

```JAVA
package JAVA_accident;

public class VariableTest {
    public static void main(String[] args) {
        /*TEXT1*/
        // 输入出老师信息
        String name = "小徐";

        int age = 18;

        char gender = '男';

        double height = 180.1;

        // 判断是否单身，使用ture or false 来判断
        boolean flag = true;

        System.out.println("姓名: " + name + '\n' + "年龄: " + age + '\n' + "性别: " + gender + '\n' + "身高: " + height + '\n' + "是否单身: " + flag + '\n');

        /*TEXT2*/
        //输入电影信息
        String MovieName = "送初恋回家";

        String people = "刘鑫 张雨提 高媛";

        String director = "刘国彤";

        String area = "中国";

        int year = 2020;

        double score = 9.0;

        System.out.println("电影名: " + MovieName + '\n' + "主演: " + people + '\n' + "导演: " + director + '\n' + "地区: " + area + '\n' + "年份: " + year + '\n' + "评分: " + score + '\n');

        /*TEXT3*/
        //输入手机信息
        double price = 5299.00;

        String PhoneName = "华为";

        System.out.println("手机名: " + PhoneName + '\n' + "价格: " + price);

    }
}
```

![image-20250217114216082](C:/Users/ziyix/Desktop/JAVA/JAVA%E6%9E%9C%E5%AD%90.assets/image-20250217114216082.png)

### 存在的问题

![image-20250217110535029](C:/Users/ziyix/Desktop/JAVA/JAVA%E6%9E%9C%E5%AD%90.assets/image-20250217110535029.png)

这个问题的根本原因是 **文件编码不匹配**。Java文件可能是以 **UTF-8** 编码保存的，但 `javac` 编译器默认使用的是 **GBK** 编码，导致无法正确解析文件中的中文字符。

**解决方法1：**

在cmd编译的时候指定文件编码类型为UTF-8即可

```
javac -encoding UTF-8 test2.java
```



**解决方法2：**

打开代码编辑器（如 Notepad++、VS Code 等）

将文件编码改为 **GBK**：

- 在 Notepad++ 中：点击菜单栏的“编码” -> “转为 ANSI”（ANSI 在中文 Windows 下就是 GBK）。
- 在 VS Code 中：点击右下角的编码（如 UTF-8），选择“通过编码保存”，然后选择 **GBK**。

![image-20250217111754702](C:/Users/ziyix/Desktop/JAVA/JAVA%E6%9E%9C%E5%AD%90.assets/image-20250217111754702.png)



## 标识符

### 标识符命名规则

- 由数字，字母，下划线和美元符组成
- 不能以数字开头
- 不能是关键字
- 区分大小写



## Scanner自定义输入方法

java 帮忙我们写好了一个Scanner类，这个类可以用来接收键盘输入的数字

```JAVA
package JAVA_accident;

import java.util.Scanner;

public class ScannerDemo {
    public static void main(String[] args) {
        // 创建对象
        Scanner sc = new Scanner(System.in);

        System.out.println("请输入数据");
        // 接收数据
        int i = sc.nextInt();

        System.out.println(i);
    }
}
```



### 缺陷

只能够接收整数，其他格式数据都会报错



### 练习

输入两个数据并求和输出

```JAVA
package JAVA_accident;

import java.util.Scanner;

public class ScannerDemo {
    public static void main(String[] args) {
        // 创建对象
        Scanner sc = new Scanner(System.in);

        System.out.println("请输入整数1");

        // 接收数据1
        int i = sc.nextInt();

        System.out.println("请输入整数2");

        // 接收数据2
        int a = sc.nextInt();

        int c = a + i;

        System.out.println("两个数据的和为: " + c);
    }
}
```

![image-20250217144015563](C:/Users/ziyix/Desktop/JAVA/JAVA%E6%9E%9C%E5%AD%90.assets/image-20250217144015563.png)



## 算数运算符

```JAVA
package Java_Concept;

public class ArithmeticoperatorDemo {
    public static void main(String[] args) {

        System.out.println(3 + 2); // 5

        System.out.println(5 - 1); // 4

        System.out.println(3 * 2); // 6

        // 如果计算的时候有小数参与,结果有可能不准确。后续会单独讲解，涉及到小数在计算机中的存储模式
        System.out.println(1.1 + 1.1);  // 2.2
        System.out.println(1.1 + 1.01); // 2.1100000000000003
        System.out.println(1.1 - 1.01); // 0.09000000000000008
        System.out.println(1.1 * 1.01); // 1.1110000000000002
    }
}
```

```JAVA
package JAVA_accident;

public class ArithmeticoperatorDemo2 {
    public static void main(String[] args) {

        // 除法
        System.out.println(10 / 2); // 5
        System.out.println(10 / 3); // 3
        System.out.println(10.0 / 3); // 3.3333333333333335


        // 取模, 取余。实际上也是做除法运算，只不过得到的是余数罢了
        System.out.println(10 % 2); // 0
        System.out.println(10 % 3); // 1
        System.out.println(10 % 4); // 2

        // 应用场景
        // 1. 可以用模来判断A是否能被B整除
        System.out.println(10 % 2 == 0); // true
        System.out.println(10 % 3 == 0); // false

        // 2. 可以用模来判断一个数的奇偶性
        System.out.println(10 % 2 == 0); // false
        System.out.println(11 % 2 == 0); // true

        // 斗地主发牌
        // 将序号 %3 如果得到的结果是1，那么就发给第一个玩家
        // 如果得到的结果是2，那么就发给第二个玩家
        // 如果得到的结果是0，那么就发给第三个玩家
        for (int i = 1; i <= 54; i++) {
            int player = i % 3;
            // 如果player是0，那么就将其修改为3
            if(player == 0){
                player = 3;
            }
            System.out.println("第" + i + "张牌发给了第" + player + "个玩家");
        }

    }
}
```

```JAVA
    package JAVA_accident;

    import java.util.Scanner;

    public class ArithmeticoperatorDemo3 {
    public static void main(String[] args) {
        // 键盘输入一个三位数，将其拆分为个位，十位，百位，打印输出
        // 123
        Scanner sc = new Scanner(System.in);

        System.out.println("请输入一个三位数");

        int num = sc.nextInt();

        // 1. 获取个位
        int ge = num % 10;
        // 2. 获取十位
        int shi = num / 10 % 10;
        // 3. 获取百位
        int bai = num / 100;
        System.out.println("个位为: " + ge);
        System.out.println("十位为: " + shi);
        System.out.println("百位为: " + bai);
    }
}
```



### 隐式转换和强制转换

### 隐式转换的两种提升规则

![image-20250221103033942](C:/Users/ziyix/Desktop/JAVA/JAVA%E6%9E%9C%E5%AD%90.assets/image-20250221103033942.png)

数据类型不一样不能进行计算，需要转换成相同的数据才能进行计算



### 强制转换

![image-20250221105226896](C:/Users/ziyix/Desktop/JAVA/JAVA%E6%9E%9C%E5%AD%90.assets/image-20250221105226896.png)

![image-20250221105238924](C:/Users/ziyix/Desktop/JAVA/JAVA%E6%9E%9C%E5%AD%90.assets/image-20250221105238924.png)

```Java
byte b1 = 10;
byte b2 = 20;
byte b3 = (byte) (b1 + b2);
```



### 字符串和字符加的操作

%表示取模/取余

整数操作只能得到整数，想要得到小数必须要有浮点数参与运算

当字符＋字符 或 字符＋数字的时候，会把字符通过ASCII码表查询到对应的数字后进行计算





### 自增自减运算符

++ 和 -- 既可以放在变量前，也可以放在变量后面

a++先用后加，++a先加后用

```JAVA
int a = 10;
a++;
System.out.println(a); // 11
++a;
System.out.println(a); // 12
a--;
System.out.println(a); // 11
--a;
System.out.println(a); // 10
```

```java
int x = 10;
        // 先把x的值赋值给y，然后再把x的值加1
        // 赋值给y的是自增之前的，x++，先用后加
        // y = 10 ，x = 11
        int y = x++;
        
        // 先把x的值加1，然后再把x的值赋值给z
        // 赋值给z的是自增之后的，++x，先加后用
        // x = 12 ，z = 12
        int z = ++x;
        System.out.println("x = " + x); // 12
        System.out.println("y = " + y); // 10
        System.out.println("z = " + z); // 12
```



### **赋值运算符**

![image-20250224111259589](C:/Users/ziyix/Desktop/JAVA/JAVA%E6%9E%9C%E5%AD%90.assets/image-20250224111259589.png)

```JAVA
	    //+=
        //规则：将左边和右边的数据做加法操作，结果赋值给左边
        //左边的变量会发生变化
        int a = 10;
        int b = 20;
        // 把a+b的结果赋值给a
        a += b;
        // 相当于 a = a + b;
        System.out.println(a);
        System.out.println(b);

        // 细节
        // 扩展的赋值运算符底层隐含了强制类型转换
        short s = 1;
        // 把左边和右边的数据进行相加再赋值给左边
        // 等同于 s = (short)(s + 1);
        s += 1;
        System.out.println(s);//+=
        //规则：将左边和右边的数据做加法操作，结果赋值给左边
        //左边的变量会发生变化
        int a = 10;
        int b = 20;
        // 把a+b的结果赋值给a
        a += b;
        // 相当于 a = a + b;
        System.out.println(a);
        System.out.println(b);

        // 细节
        // 扩展的赋值运算符底层隐含了强制类型转换
        short s = 1;
        // 把左边和右边的数据进行相加再赋值给左边
        // 等同于 s = (short)(s + 1);
        s += 1;
        System.out.println(s);
```



### **关系运算符**

![image-20250224112346466](C:/Users/ziyix/Desktop/JAVA/JAVA%E6%9E%9C%E5%AD%90.assets/image-20250224112346466.png)

```JAVA
//  == 判断左右两边是否相等
int a = 10;
int b = 10;
int c = 20;
System.out.println(a == b); // true
System.out.println(a == c); // false
```

Test

```JAVA
package Test;

import java.util.Scanner;

public class OperatorTest {
    public static void main(String[] args) {
        /*
          您和您的约会对象正试图在餐厅获得一张桌子。
          键盘录入两个整数，表示你和你约会对象衣服的时髦度。（手动录入0~10之间的整数，不能录其他）
          如果你的时髦程度大于或等于你对象的时髦程度，相亲就成功，输出true。
          否则输出false。
         */
        Scanner sc = new Scanner(System.in);

        System.out.println("请输入一个0~10的整数：");
        int num1;
        while(true){
            num1 = sc.nextInt();
            if(num1 >= 0 && num1 <= 10){
                break;
            }
            System.out.println("输入的数字不在0~10之间，请重新输入！");
        }

        System.out.println("再次输入一个0~10的整数：");
        int num2;
        while(true){
            num2 = sc.nextInt();
            if(num2 >= 0 && num2 <= 10){
                break;
            }
            System.out.println("输入的数字不在0~10之间，请重新输入！");
        }

        System.out.println(num1 >= num2);

//        if(num1>=num2){
//            System.out.println(true);
//        }else{
//            System.out.println(false);
//        }

    }
}
```



### 逻辑运算符

![image-20250226102226558](C:/Users/ziyix/Desktop/JAVA/JAVA%E6%9E%9C%E5%AD%90.assets/image-20250226102226558.png)

```JAVA
package Java_Concept;

public class LogicOperationDemo {
    public static void main(String[] args) {
         // & 并且
         // 两边都为真，结果才是真
         System.out.println(true & true); // true
         System.out.println(false & false); // false
         System.out.println(true & false); // false
         System.out.println(false & true); // false

        // | 或者
        // 两边只要有一个为真，结果就是真
        System.out.println(true | true); // true
        System.out.println(false | false); // false
        System.out.println(true | false); // true
        System.out.println(false | true); // true

        // ^ 异或
        // 两边相同，结果为假
        // 两边不相同，结果为真
        System.out.println(true ^ true); // false
        System.out.println(false ^ false); // false
        System.out.println(true ^ false); // true
        System.out.println(false ^ true); // true

        // ! 非
        // 真变假，假变真
        // 取反的感叹号不要多次使用，要么不写，要么就写一次
        System.out.println(!true); // false
        System.out.println(!false); // true
    }
}
```



###  短路逻辑运算符

![image-20250226110241489](C:/Users/ziyix/Desktop/JAVA/JAVA%E6%9E%9C%E5%AD%90.assets/image-20250226110241489.png)

```java
package Java_Concept;

public class LogicOperationDemo2 {
    public static void main(String[] args) {
        // 1. &&
        // 运行结果跟单个&是一样的
        // 表示两边都为真，结果才是真
        System.out.println(true && true); // true
        System.out.println(false && false); // false
        System.out.println(true && false); // false
        System.out.println(false && true); // false

        // 2. ||
        // 运行结果跟单个|是一样的
        // 表示两边只要有一个为真，结果就是真
        System.out.println(true || true); // true
        System.out.println(false || false); // false
        System.out.println(true || false); // true
        System.out.println(false || true); // true

        // 3.短路逻辑运算符具有短路效果
        // 简单理解:当左边的表达式能确定最终的结果，那么右边就不会参与运行了
        int a = 10;
        int b = 10;
        boolean result = ++a < 5 && ++b < 5; // 因为左边判断已经是错的 所以右边就不会再判断了，也不会运行了
        System.out.println(result);
        System.out.println(a); // 11
        System.out.println(b); // 10

    }
}
```

![image-20250226112305720](C:/Users/ziyix/Desktop/JAVA/JAVA%E6%9E%9C%E5%AD%90.assets/image-20250226112305720.png)

**Test**

```java
package Test;

import java.util.Scanner;

public class LogicOperationTest {
    public static void main(String[] args) {
        // 键盘输入两个整数，如果一个数字为6，最终结果输出true，如果它们的和为6的倍数，最终结果也输出true，其他情况均输出false.
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入一个整数：");

        int a = sc.nextInt();

        System.out.println("再输入一个整数：");

        int b = sc.nextInt();

//        if(a == 6 || b == 6){
//            System.out.println(true);
//        }else System.out.println((a + b) % 6 == 0);

        boolean result = a == 6 || b == 6 || (a+b) % 6 == 0;
        System.out.println(result);

    }
}
```



### 三元运算符





