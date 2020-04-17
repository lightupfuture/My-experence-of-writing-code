 
# My-experence-of-writing-code
From 2020/4/11 to 2060/4/11
## my c 语言4/11
```
//写一个一元二次方程求解程序，输入三个系数，输出解，当完成一次程序给出解后，询问是否继续
#include <stdio.h>
#include <math.h>
int main (void)
{
    double  a , b , c;
    double x1 , x2 , delta;
    char fu;
    do{printf("欢迎来到一元二次方程求解程序!\n");
    printf("请输入三个系数：");
    scanf("%f %f %f",&a , &b ,&c);
    delta = sqrt(b*b-4*a*c);
    x1 = (-b+delta)/(2*a);
    x2 = (-b-delta)/(2*a);
    if(delta<0)
    {
        printf("小可爱，你输入的方程没有解呦！");
    }
    else if(delta==0)
    {
        printf("该方程有两个相等的实数解为%.2f",x1);
    }

    else
    {
        printf("该方程的第一个解为%.2f",x1);
        printf("该方程的第二个解为%.2f",x2);
    }
    }while(fu=='Y'||fu=='y');
    return 0;
}

```
Today's code has little problem, tommorrow I will go on.

## 4.12  
```
//写一个一元二次方程求解的小程序，输入a，b，c三个系数，输出他的解，随后询问是否继续输入。
//可以先写一个求解程序，再考虑循环，但是需要注意的是，在这里没有说到底要进行多少次计算，所以循环语句使用do...while
//清屏：引入windows，输入cls
//本章重点内容：①根号--引入math库，使用sqrt；②do...while的使用；③清屏的使用--引用Windows库，使用system（“cls”）；
#include <stdio.h>
#include <math.h>
#include <windows.h>
int main (void)
{
    //因为需要考虑输入的三个系数可能是小数，所以应该使用double
    double a ,b , c;
    double delta;
    double x , x1 , x2;
    char flag;
    do
    {
        delta = b*b-4*a*c;
    printf("亲爱的用户：你好！欢迎来到一元二次方程求解小程序。\n");
    printf("请依次输入二次项系数、一次项系数和常数项，中间请用空格隔开：");
    scanf("%f %f %f",&a ,&b ,&c);
    //接下来我就需要判断（b*b-4-a-c)的大小，所以需要引入一个量delta
    //而后根据delta使用if语句分情况进行讨论
    if(delta<0)
    {
        printf("小可爱，您输入的方程没有实数解呦！\n");
    }
    else if(delta==0)
    {
        //考虑到要输出解x，所以需要在开头定义x，但是需要出现根号，所以要引入数据库math
        x = (-b)/(2*a);
        printf("该方程有两个相等的实数解：%.2f\n",x);
    }
    else
    {
        x1 = (-b+sqrt(delta)/(2*a));
        x2 = (-b-sqrt(delta)/(2*a));
        printf("该方程的第一个解为：%.2f\n",x1);
        printf("该方程的第一个解为：%.2f\n",x2);
    }
    //现在我已经写好了只计算一次的程序，进行计算看能否成功
    //运行成功后我要进行下一个项目，即尝试运用do、、、while来进行循环运算
    //所以下面需要引入下一个字符型变量char类型
    //询问是否需要继续运算，如果继续输入Y或者y，否则输入N
    printf("是否需要继续运算？");
    fflush(stdin);
    scanf("%c",&flag);
    system("cls");
    }while(flag=='Y'||flag=='y');
    printf("多谢您的使用，欢迎您下次使用！");

    return 0;
}
```
## 4.13 我的网络原理  
1.数据链路层的三个基本问题：封装成帧、透明传输和差错检测。对应的解决方法依次是用控制字符进行帧定界；字节填充或者字符填充；循环冗余检验CRC、帧检验序列FCS。
2.现在全世界使用最广泛的数据链路层协议是点对点协议PPP。
3.局域网的数据链路层：逻辑链路控制LLC和媒体接入控制MAC。现今LLC协议已经不太适用。
4.以太网提供的服务不可靠！！是尽最大努力的交付。
5.以太网采用星形拓扑，在星形的中心则增加了一种可靠性非常高的设备，叫做集线器(hub)。使用集线器的以太网在逻辑上仍是一个总线网，各工作站使用的还是 CSMA/CD 协议，并共享逻辑上的总线。集线器工作在物理层上。
6.在局域网中，硬件地址又称为物理地址，或 MAC 地址。 
7.出错原因：delta的计算应该在输入数据之后进行计算
```
//写一个一元二次方程求解的小程序，输入a，b，c三个系数，输出他的解，随后询问是否继续输入。
//可以先写一个求解程序，再考虑循环，但是需要注意的是，在这里没有说到底要进行多少次计算，所以循环语句使用do...while
//清屏：引入windows，输入cls
#include <stdio.h>
#include <math.h>
#include <windows.h>
int main (void)
{
    //因为需要考虑输入的三个系数可能是小数，所以应该使用double
    double a ,b , c;
    double delta;
    double x , x1 , x2;
    char flag;
    do
    {
    printf("亲爱的用户：你好！欢迎来到一元二次方程求解小程序。\n");
    printf("请依次输入二次项系数、一次项系数和常数项，中间请用空格隔开：");
    scanf("%f %f %f",&a ,&b ,&c);
    delta = b*b-4*a*c;
    x = (-b)/(2*a);
    x1 = (-b+sqrt(delta)/(2*a));
    x2 = (-b-sqrt(delta)/(2*a));
    //接下来我就需要判断（b*b-4-a-c)的大小，所以需要引入一个量delta
    //而后根据delta使用if语句分情况进行讨论
    if(delta<0)
    {
        printf("小可爱，您输入的方程没有实数解呦！\n");
    }
    else if(delta==0)
    {
        //考虑到要输出解x，所以需要在开头定义x，但是需要出现根号，所以要引入数据库math
        printf("该方程有两个相等的实数解：%.2f\n",x);
    }
    else
    {
        printf("该方程的第一个解为：%.2f\n",x1);
        printf("该方程的第一个解为：%.2f\n",x2);
    }
    //现在我已经写好了只计算一次的程序，进行计算看能否成功
    //运行成功后我要进行下一个项目，即尝试运用do、、、while来进行循环运算
    //所以下面需要引入下一个字符型变量char类型
    //询问是否需要继续运算，如果继续输入Y或者y，否则输入N
    printf("是否需要继续运算？");
    fflush(stdin);
    scanf("%c",&flag);
    system("cls");
    }while(flag=='Y'||flag=='y');
    printf("多谢您的使用，欢迎您下次使用！");
    return 0;
}

```
God!Also have little problem!
## 4.14--4.16  
```
#include <stdio.h>
int main(void)
{
    int n , i;
    double sum=0 , sum1 , sum2;
    printf("请输入n值：");
    scanf("%d",&n);
    for(;n>=1;n--)
    {
        for(;n>=1;n--)
        {
            sum1+=n;
        }
        sum2=1.0/sum1;
        sum+=sum2;
    }
    printf("%f",sum);
    return 0;
}
/*
#include <stdio.h>
int main (void)
{

    int n , num , k , i;
    printf("请输入行数\n");
    scanf("%d",&n);
    i = n;
    for(;i>0;i--)
    {
        num=2*i-1;
        for(k=0;k<n-i;k++)
        {
            printf(" ");
        }
        for(;num>0;num--)
        {
            printf("*");
        }
            printf("\n");
    }
    return 0;
}
*/
/*
#include <stdio.h>
int main (void)
{
    int n , i ,j ;
    int sum=0;
    printf("请输入n值：");
    scanf("%d",&n);
    for(i= 2;i<=n;i++)
    {
        int t = 1;
        for(j=2;j<i;j++)
        {
            if(i%j==0)
            {
                t=0;
                break;
            }
        }
        if(t==1)
        {
            sum+=i;
        }
    }
    printf("素数和为%d\n",sum);
    return 0;
}
*/
```
## 4.16  
```
#include <stdio.h>
int main(void)
{
    int n , i;
    double sum=0 , sum1 , sum2=0;
    printf("请输入n值：");
    scanf("%d",&n);

    for(;n>=1;n--)
    {
        i=n;
        for(;i>=1;i--)
        {
            sum1+=i;
        }
        printf("%f\n",sum1);
        sum2=1.0/sum1;
        printf("%f\n",sum2);
        sum+=sum2;
        printf("%f\n",sum);
        sum1=0;

    }
    printf("%f\n",sum);
    return 0;
}
```
## 4.17 
[TOC]

## 数组的使用

### 1 数组的基本概念

- 数组：类型相同的数据元素的集合，是C语言中的一种构造数据类型
  - 元素的类型可以是基本数据类型，也可以是构造数据类型
    - 构造数据类型：C语言中根据用户实际需求自定的类型，称之为构造数据类型，常见构造数据类型有：数组、结构体、枚举体、联合体。
- 这些元素会顺序的存储在内存的某段区域
  
### 2 数组定义语法

``` c
数据类型 数组名[数组大小];
```

- 数据类型：决定了数组中存放元素的类型
- 数组名：决定了数组的名称
	- 必须满足C语言变量名（合法标识符）的要求
	  1. 由数字、字母、下划线组成
	  2. 数字不能打头，不能作为第一个字符
	  3. 不能与关键字冲突
	  4. 在同一作用域不允许重名
- 数组大小：决定了数组中最大能够存放的元素数量
	- 数组大小不能是变量，只能是字面值或字面值表达式
	  - C语言编译器要求在编译期间就需要确定数组的内存大小
	- 数组大小必须是大于0的正整数
	
### 3 数组的使用

``` c
int arr[6];
```


- 例如上面例子，定义了一个长度为6的整型数组，对于这个数组，可以认为它就是定义了6个变量。

- 这6个变量是什么？

``` c
arr[0], arr[1],arr[2], arr[3],arr[4], arr[5]
```

- 访问数组中的元素，都是通过`数组名`+`下标`的形式来完成的。

- 下标从`0`开始，最大下标为`数组长度-1`。
- 下标为什么从0开始？需要等到学完数组与指针的关系后再解答。

### 4 一维数组的初始化

- 初始化：定义变量的同时赋初值，称为初始化

#### 4.1 方法一：全部初始化

``` c
int arr[5] = {1, 2, 3, 4, 5};
// arr[0]:1
// arr[1]:2
// arr[2]:3
// arr[3]:4
// arr[4]:5
```

- 初始化列表：用大括号括起来的，用于对数组进行初始化的一个值的列表，每个值之间通过逗号隔开
- 会根据初始化列表中元素顺序，依次对数组每一个元素初始化。
- 初始化列表只能在定义数组的时候使用，数组定义完成之后不能再使用初始化列表！
- 全部初始化要求初始化列表中元素个数必须与数组大小相同

#### 4.2 部分元素赋初值

``` c
int arr[5] = {1, 2, 3};
// arr[0]:1
// arr[1]:2
// arr[2]:3
// arr[3]:0
// arr[4]:0
```

- 首先会依次将初始化列表中的每一个元素值按照顺序对数组每一个元素赋初值

- 如果发现数组中仍有元素没有被初始化，则默认初始化为0

- 实际开发中，通常采用部分元素赋初值的方法对数组元素进行初始化，例如：int arr[100] = {0}; 

#### 4.3 省略长度赋初值

``` c
int a[] = {1, 2, 3, 4, 5};
// 等同于 int a[5] = {1, 2, 3, 4, 5};
```

- 在定义数组时，如果后面跟有初始化列表，并且初始化列表元素值的个数就是预期的数组大小，那么可以省率中括号中的数组大小
- 定义数组时，如果后面没有进行初始化的初始化列表，那么数组长度不能省略
- 定义数组时，时刻铭记要通过某一个途径，准确的告诉编译器数组的大小才可以

### 5 一维数组的使用示例

#### 5.1 求平均值、最大值、最小值

``` c
#include <stdio.h>

int main(void) 
{
    int arr[10];
    int i, sum, max, min;

    // 命令行读取10个整数
    for (i=0; i<10; i++) 
    {    
        scanf("%d", &arr[i]);    
    }

    // 按顺序打印
    for (i=0; i<10; i++) 
    {    
        printf("%d ", arr[i]);   
    }
    printf("\n");

    sum = 0;
    max = arr[0];
    min = arr[0];
    // 求10个数之和、最大值
    for (i=0; i<10; i++)
    {
        sum += arr[i];
        if (max < arr[i]) 
        {    max = arr[i];   } 
        if (min > arr[i])
        {    min = arr[i];   }
    }
    printf("和为：%.2f\n", sum / 10.0);
    printf("最大值为：%d\n", max);
    printf("最小值为：%d\n", min);

    // 倒序输出
    for (i=9; i>=0; i--) 
    {
        printf("%d ", arr[i]);
    }
    printf("\n");

    return 0;
} 
```

#### 5.2 数组逆置

``` c
#include <stdio.h>

int main(void) 
{
    int arr[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
    int i, temp;

    for (i=0; i<10/2; i++) 
    {
        temp = arr[i];
        arr[i] = arr[10-1-i];
        arr[10-1-i] = temp;
    }

    for (i=0; i<10; i++) 
    {    
        printf("%d ", arr[i]);   
    }
    printf("\n");

    return 0;
} 
```

#### 5.3 数组排序

- 冒泡排序

``` c
#include <stdio.h>

int main(void) 
{
    int arr[10] = {5, 7, 1, 4, 9, 2, 10, 3, 8, 6};
    int i, j, temp;
    int n = 10;

    // 控制冒泡次数
    for (i=0; i<n-1; i++)
    {
        // 控制两两比较次数
        for (j=0; j<9; j++)
        {
            // 预期存放顺序从小到大，实际存储与预期不相符时交换
            if (arr[j] > arr[j+1]) 
            {
                temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
            }
        }
    }

    for (i=0; i<10; i++) 
    {    
        printf("%d ", arr[i]);   
    }
    printf("\n");

    return 0;
} 
```

- 选择排序

``` c
#include <stdio.h>

int main(void) 
{
    int arr[10] = {5, 7, 1, 4, 9, 2, 10, 3, 8, 6};
    int i, j, temp, min;
    int n = 10;

    for (i=0; i<n-1; i++)
    {
        min = i;
        // 求当前无序序列中最小值
        for (j=i+1; j<n; j++)
        {
            if (arr[min] > arr[j])
            {
                min = j;
            }
        }
        temp = arr[i];
        arr[i] = arr[min];
        arr[min] = temp;
    }

    for (i=0; i<10; i++) 
    {    
        printf("%d ", arr[i]);   
    }
    printf("\n");

    return 0;
} 
```

- 直接插入排序

``` c
#include <stdio.h>

int main(void) 
{
    int arr[10] = {5, 7, 1, 4, 9, 2, 10, 3, 8, 6};
    int i, j, temp;
    int n = 10;

    // i代表着无序序列中第一个元素
    for (i=1; i<n; i++)
    {
        // 通过temp保存无序序列第一个元素
        temp = arr[i];
        // 寻找要插入的位置
        for (j=i-1; j>=0 && arr[j] > temp; --j)
        {
            arr[j+1] = arr[j];
        }
        arr[j+1] = temp;
    }

    for (i=0; i<10; i++) 
    {    
        printf("%d ", arr[i]);   
    }
    printf("\n");

    return 0;
} 
```
