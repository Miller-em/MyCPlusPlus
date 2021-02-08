# 命令空间的using声明

到目前为止，我们用到的库函数基本上都属于**命名空间std**，而程序也是显式地标了出来。例如 `std::cin`， `std::cout`。但是上面的方法这样写，通常显得比较麻烦。但是有一种简单的方式，使用**using**声明**命令空间**。

如果使用using，那么不用专门的前缀也能够使用所需的名字了。using声明具有一下两种形式：

```c++
using namespace::name
```

如下：

```c++
#include <iostream>
using std::in;
using std::cout;
using std::endl;
int main{
    cout << "Enter two numbers:" << endl;
    int v1, v2;
    cin >> v1 >> v2;
    cout << "The sum of " << v1 << " and " << v2
        << " is " << v1 + v2 << endl;
    return 0;
}
```

