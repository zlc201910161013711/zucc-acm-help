# CPP基础语法

这个模块将介绍关于CPP的语法规则。

不用担心很困难，算法竞赛只会用到它最基础的部分。



如果你的电脑上还没有关于CPP的任何环境和IDE，请先阅读：

[CPP环境配置及常用IDE介绍]()

在一切开始之前，如果你使用的IDE是Dev-cpp，请按照工具->编译选项->编译时加入如下命令->`-std=c++11`的步骤修改Dev-cpp的编译环境。

阅读这段代码，它包含了算法竞赛的CPP代码的最基础组成部分。

`#include<bits/stdc++.h>`是万能头，涵盖了C++的所有库。

`using namespace std;`统一申请命名空间，这里不用·理解它的底层原理，只需记住是必须的。

`int main`是主函数，程序的入口，所有逻辑在main函数里按顺序执行。

```clike
#include<bits/stdc++.h>
using namespace std;
int main () {

    cout << "Hello World!\n";
}
```



## 输入和输出

<a href="https://www.luogu.com.cn/problem/P1001">洛谷P1001 A+B Problem</a>

这道题目非常简单，帮助您熟悉算法竞赛中题目评测的大体模式。

一道题目往往分为三大部分：

1. 题面。题面内会包含这道题目本身的所有必要信息，包括题意、数据范围、时间限制、空间限制等。
2. 输入输出格式。输入格式规定了数据将会以怎样的形式读入，输出格式规定了你必须要以怎样的形式输出答案。
3. 样例。样例会给出1-2组较小的、可以手动推演的（输入数据，标准答案）。这可以帮你在一定程度上测试你代码的正确性。

你的程序提交到后台后，系统会评测10-30组后台数据，这些数据是看不到的，系统最多告诉你错在哪一组，你无法得知数据的具体内容。如果你的程序没有通过这些数据，你就只能在逻辑层面思考是哪里做错了。这也是算法竞赛的魅力所在。

常见的错误类型：

1. `Wrong Answer`。答案错误。你的输出和标准答案不一致。
2. `Time Limit`。超出时间限制。你程序的运行时间超出了题面里要求的时间。
3. `Memory Limit`。超出空间限制。你程序占用的内存超出了题面里要求的内存。
4. `Compile Error`。编译错误。你的程序没有通过系统编译器。
5. 。。。

通常我们将通过一道题目简称为AC。

这里我们给出这道题目的AC代码，帮助您更快的熟悉。

```clike
#include<bits/stdc++.h>
using namespace std;
int main () {
	int a, b;//定义两个整数a，b 
	cin >> a >> b;//输入两个整数a和b
	cout << a + b; //输出a + b 
}
```

?> 模仿上面的代码，试试读入A、B、C三个数，并输出他们的和。

<a href = "https://www.luogu.com.cn/problem/P1421">洛谷P1421 小玉买文具</a>

熟悉CPP的基础运算。这里的思路是1元9角换算成19角，a元b角换算成`a*10+b`角。

`int`型变量之间的除法规则是除不尽自动向下取整。因此`(a*10+b)/19`就是答案。

```cpp
#include<bits/stdc++.h>
using namespace std;
int main () {
	int a, b;
	cin >> a >> b;
	cout << (a * 10 + b) / 19;
}
```

## 变量类型

这里以表格列出最常用的变量类型：

| 变量名称              | 变量声明语法   | 说明                                    |
| --------------------- | -------------- | --------------------------------------- |
| 整型变量`int`         | `int a;`       | 整型变量，范围$-2^{31}$到$2^{31}-1$     |
| 浮点型变量`double`    | `double a;`    | 浮点型变量，主要用于小数运算            |
| 长整型变量`long long` | `long long a;` | 长整型变量，范围$-2^{63}$到$2^{63}-1$   |
| 字符变量`char`        | `char a;`      | 字符，范围0到255，用于存储ASCII码字符。 |

上述所有变量都可以直接用`cin`的句法读入。

## 基础运算

对于两个变量A和B，我们可以用：

```
A + B
A - B
A * B
A / B
```

来表示A和B之间的四则运算。

特殊的，`A % B`表示A / B的余数。

判断两个变量之间的关系，我们用：

```
A > B //如果A大于B返回1，否则返回0
A < B //如果A小于B返回1，否则返回0
A == B //如果A等于B返回1，否则返回0
A != B //如果A不等于B返回1，否则返回0
```



## if else分支语句

举几个例子。

?> 如果`x`等于`1`，则输出`Yes!`

```clike
if (x == 1) {
    cout << "Yes!";
}
```

?> 如果`x`等于`1`，则输出`Yes!`，否则输出`No`。

```cpp
if (x == 1) {
    cout << "Yes!";
}
else {
    cout << "No!\n";
}
```



## for循环

循环的含义是让同一段代码执行多次。

for循环的格式如下：

`for(语句A;语句B;语句C;)`

语句A表示在循环开始之前需要做什么，语句B表示循环的条件（返回一个bool值），语句C表示每一轮循环做什么。

例如，我们要让`printf("Hello World!\n");`这段代码重复执行100次。

```clike
for (int i = 1; i <= 100; i++) {
    printf("Hello World!\n");
} 
```

这里`int i = 1`意思是在循环开始之前，声明一个变量`i`，并赋值为`1`。

`i <= 100`意思是循环的条件是`i <= 100`，当`i > 100`时循环结束。

`i++`意思是`i = i + 1`，每一轮循环`i = i + 1`。

`printf("Hello World!\n")`意思是打印名为`Hello World!`的字符串，`\n`表示换行符，对于这段代码效果是每一行单独一句`Hello World!`，持续100行。

`printf`是C语言特色的输出句法，等价于CPP里的`cout << "Hello World!\n"`。

C语言的句法和CPP的句法是可以混用的。

?> 思考这道题，并尝试解决它。

<a href="https://www.luogu.com.cn/problem/P1035">P1035 [NOIP2022]普及组 级数求和</a>

这里给出参考答案：

```clike
#include<bits/stdc++.h>
using namespace std;
int k;//定义k
int main () {
	cin >> k;//输入k
	double sum = 0;//定义一个double变量sum并赋值为0。
	for (int i = 1; i <= 2000000; i++) {
		sum += 1.0 / i;//更新sum
		if (sum > k) {//如果sum > k
			cout << i;//输出答案
			return 0;//强制终止程序
		}
	}
	//cout << sum << '\n';
}
```

## while循环

`while`循环的格式如下：

`while(语句A)`

语句A表示while循环的执行条件。

比如我们要让一句话执行100次，可以这么写：

```clike
int sum = 100;
while (sum > 0) {
    printf("Hello World!\n");
    sum--;
}
```

在面对一些棘手的情况时，我们不需要纠结于语句A的写法，而是可以直接：

```clike
while (true) {
	if (...) break;
}
```

直接写一个死循环语句，然后在语句块内部用`if`条件分支去判断循环是否终止。

`break`关键字可以直接让循环停止，在`while`和`for`里都适用。

?> 如何获取一个数的数位信息？

<a href = "https://www.luogu.com.cn/problem/P1980">P1980 [NOIP2013 普及组]计数问题</a>

题意：

每组数据给出两个数n和x。

计算区间1到n的所有整数的数位中，数字x出现了多少次。

做法：

我们需要获取一个数字每一位上的数是什么，并把它存到一个数组里。

对于一个整型变量`x`，`x%10`返回的结果是`x`最后一位的数字，`x / 10`返回`x`去掉最后一位数字之后的剩余部分组成的数字。

基于此，我们可以用`while`循环来获取一个数的数位信息。

基于此，我们给出这道题的参考代码：

```clike
#include<bits/stdc++.h>
using namespace std;
int n, x, ans;
int main () {
	cin >> n >> x;
	for (int i = 1; i <= n; i++) {
		int y = i;
		while (y) {
			if (y % 10 == x) ans++;
			y /= 10;
		}
	}
	cout << ans;
}
```





