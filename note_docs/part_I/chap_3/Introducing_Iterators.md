# 迭代器

## 使用迭代器

和指针不同的是，获取迭代器可以不用取地址符，有迭代器的类型同时拥有返回迭代器的成员。比如，这些类型都拥有名为begin和end的成员。其begin成员负责指向第一个元素的迭代器。end负责指向最后一个元素的迭代器。

定义方法：

1. 正向迭代器：

   > 容器类名::iterator 迭代器名；

2. 常量正向迭代器：

   > 容器类名::const_iterator 迭代器名；

3. 反向迭代器：

   > 容器类名::reverse_iterator 迭代器名；

4. 常量反向迭代器：

   > 容器类名::const_reverse_iterator 迭代器名；

举个迭代器的例子：

```c++
string s("some string");
if (s.begin() != s.end()){ //确保s非空
	auto it = s.begin();  //it表示第一个字符
	*it = toupper(*it); 
}
```



### 迭代器类型

我们通常不知道迭代器的类型，一般都是使用的 iterator 和 const_iterator 来表示迭代器的类型：

```c++
vector<int>::iterator it;	// it能够读写vector的元素
string::iterator it2;	//能读写
vector<int>::const_iterator it3; //只能读不能够写
string::const_iterator it4; //只能读不能够写

```

## 迭代器用法

通过迭代器可以读取他指向的元素，迭代器名就是迭代器指向的元素。

迭代器可以进行++操作。反向迭代器和正向迭代器的区别在于：

- 对正向迭代器进行++操作。迭代器会指向后一个元素
- 对反向迭代器进行++操作时，迭代器会指向容器的前一个元素

下面一个例子表示通过迭代器遍历一个vector容器的所有元素：

```c++
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> v; //存放int类型的可变长数组，开始没有元素
    for (int n=0; n<5; ++n)
        v.push_back(n);
    
    vector<int>::iterator i;
    for (i = v.begin(); i!=v.end(); ++i){
        cout << *i << " "; //*i 就是迭代器指向的元素
        *i *= 2;
    }
    cout << endl;
}
```

