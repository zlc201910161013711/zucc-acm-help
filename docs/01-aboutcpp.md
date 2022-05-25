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

