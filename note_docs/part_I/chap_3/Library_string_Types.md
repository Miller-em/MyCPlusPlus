# 标准库类型string

标准库类型string表示可变长的字符序列，使用string 类型必须首先包含`string头文件`。作为标准库的一部分，string定义在命名空间std中。接下来的示例都假定已包含了下述代码:

```c++
#include <string>
using std::string
```



## 定义和初始化string对象

下面是几个定义和初始化`string`对象的例子：

```c++
string s1;
string s2 = s1;
string s3 = "hello";
string s4(10, 'c');
```

