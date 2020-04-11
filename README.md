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
