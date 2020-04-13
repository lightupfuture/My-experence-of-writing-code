 
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
