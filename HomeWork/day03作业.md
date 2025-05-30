# 知识点

运算符

## 题目1(训练)

身高是具有遗传性的，子女的身高和父母的身高有一定的关系。假定，父母和子女的身高遗传关系如下：

​	儿子身高（厘米）＝(父亲身高＋母亲身高) ×1.08÷2

​	女儿身高（厘米）＝(父亲身高×0.923＋母亲身高) ÷2

现有父亲身高177CM,母亲身高165CM。求子女身高分别预计为多少？

### 训练提示

1. 已知的父母身高如何用代码体现？ int

2. 题目中的公式如何转化为代码？ 

### 解题方案

1. 使用变量的定义和算术运算符完成本题

### 操作步骤

1. 定义小数变量代表父亲身高

2. 定义小数变量代表母亲身高

3. 通过儿子身高计算方式计算儿子身高

4. 通过女儿身高计算方式计算女人身高

### 参考答案

```java
package JavaHomeWork;

public class Day3 {
    public static void main(String[] args) {
        int father = 177;
        int mother = 165;

        double son = (father + mother) * 1.08 / 2;
        System.out.println("儿子的升高为："+son);

        double daughter = (father * 0.923 + mother) / 2;
        System.out.println("女儿的升高为："+ daughter);
    }
}
```

## 题目2（训练）

红茶妹妹有21元钱，她攒了几天钱之后自己的钱比原来的两倍还多三块。绿茶妹妹有24元钱，她攒了几天钱之后自己的钱正好是原来的两倍。那么红茶和绿茶现在的钱一样多，请问对么？

### 训练提示

1. 用什么知识点来计算她们现在的钱有多少？
2. 如何对比两个人的钱数？

### 解题方案

1. 使用赋值运算符和算术运算符计算各自的钱，使用比较运算符对比大小

### 操作步骤

1. 定义红茶妹妹原来的钱为整数变量
2. 定义绿茶妹妹原来的钱为整数变量
3. 使用赋值运算符和算术运算符计算其现有的钱
4. 使用比较运算符对数值做出比较

### 参考答案

```java
package JavaHomeWork;

public class Day3_2 {
    public static void main(String[] args) {
        int red = 21;
        int green = 24;

        int NRed = red * 2 + 3;
        int NGreen = green * 2;

        System.out.println(NRed == NGreen);
    }
}
```

## 题目3（综合）

某小伙想定一份外卖，商家的优惠方式如下：鱼香肉丝单点24元，油炸花生米单点8元，米饭单点3元。订单满30元8折优惠。鱼香肉丝优惠价16元，但是优惠价和折扣不能同时使用。那么这个小伙要点这三样东西，最少要花多少钱？

### 训练提示

1. 有两种购买方式，一种是不使用优惠价，另一种是使用优惠价。分别计算花费后，对两种方式的花费作对比。

### 解题方案

1. 使用算术运算符、赋值运算符和三元运算符联合完成本题

### 操作步骤

1. 使用算术运算符求出不使用优惠时的总价
2. 使用三元运算符判断总价是否满足打折条件，并求出折后总价
3. 使用算术运算符求出使用优惠价时的总价
4. 使用三元运算符判断最终更合算的购买方式和花费

### 参考答案

```java
package JavaHomeWork;

public class Day3_3 {
    public static void main(String[] args) {
        int fish = 24;
        int fishN = 16;
        int peanut = 8;
        int rice = 3;
        int sum = fish + peanut + rice;
        int sum2 = fishN + peanut + rice;

        int favourable = sum > 30 ? sum-8 : sum;

        System.out.println("原价" + sum + "元");

        System.out.println("第一种优惠方式" + favourable + "元");

        System.out.println("第二种优惠方式" + sum2 + "元");

        System.out.println(favourable > sum2 ? sum : sum2);
    }
}
```
## 题目4

看代码说结果，不要去运行。

System.out.println(2.0*(5/2));  4

1. 4
2. 4.0
3. 5
4. 5.0
5. 以上答案都不对



## 题目5：

看代码说结果，不要去运行。

```java
String firstName = "Tomas";
String familyName = "Zhang";
打印firstName + familyName 之后是什么结果？TomasZhang
```

## 题目6：

需求：

  	数字6是一个真正伟大的数字，键盘录入两个整数。
  	
  	如果其中一个为6，最终结果输出true。
  	
  	如果它们的和为6的倍数。最终结果输出true。
  	
  	其他情况都是false。

答案：

```JAVA
package JavaHomeWork;

import java.util.Scanner;

public class Day3_4 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入一个整数");
        int num1 = sc.nextInt();
        System.out.println("请输入再输入一个整数");
        int num2 = sc.nextInt();

        if(num1 == 6 || num2 == 6) {
            System.out.println("true");
        } else if((num1 + num2) % 6 == 0) {
            System.out.println("true");
        }else {
            System.out.println("false");
        }
    }
}
```



## 题目7：

需求：

​	键盘录入一个三位数，求这个三位数每一位的数字和。

​	举例：

​		键盘录入123。那么每一位数字相加为：1 + 2 + 3，和为：6。

答案：

```java
package JavaHomeWork;

import java.util.Scanner;

public class Day3_5 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入一个三位整数");
        int num = sc.nextInt();

        int ge = num % 10;
        int shi = num / 10 % 10;
        int bai = num / 100;

        int sum1 = ge + shi + bai;
        System.out.println(sum1);
    }
}
```









