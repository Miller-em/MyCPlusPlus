# 标准库类型vector

标准库类型**vector**表示对象的集合，其中所有对象的类型都相同。集合中的每个对象都有一个与之对应的索引，索引用于访问对象。因为`vector` "容纳着" 其他对象，所以它也常被称作**容器(container)**。

要使用vector那么，需要适当的头文件：

```c++
#include <vector>
using std::vector;
```

C++语言既有**类模板（class template)**，也有函数模板，其中 vector是一个类模板。只有对C++有了相当深入的理解才能写出模板。幸运的是，即使还不会创建模板，我们也可以先试着用用它。

如下：

```c++
vector<int> ivec;			//ivec保存的是int类型对象
vector<Sales_item> Sales_vec; //保存Sales_item类型的对象
vector<vector<string>> file;  //该向量的元素是vector对象
```



**注意**：

> vector是模板而不是类型，又vector生成的类型必须包含vector中元素类型，例如: vector<int>

## 定义和初始化vector对象

初始化vector对象的方法：

```c++
vector<string> svec;        //默认初始化，svec不包含任何元素
vector<int> ivec;
vector<int> ives = ivec;	//把ivec的元素拷贝给ives
vector<int> ivea(ivec);		//把ivec的元素拷贝给ivea

```

### 列表初始化vector对象

C++11新标准还提供了另外一种为vector对象的元素赋初值的方法，即列表初始化：

```c++
vector<string> articles = {"a", "an", "the"};
vector<string> articles{"a", "an", "the"};
vector<string> articles("a", "an", "the"); //错误，不能够放在圆括号内初始化
```



### 创建指定数量的元素：

```c++
vector<int> ivec(10, -1);	//10个int类型的元素，每个都被初始化为-1
vector<string> svec(10, "hi!") //10个string类型的元素，每个都被初始化为hi!
```



## 向vector对象中添加元素

如果想创建一个**vector对象**令其包含从0到9共10个元素，使用**列表初始化**的方法很容易做到这一点;但如果vector对象包含的元素是从0到99或者从0到999呢?这时通过列表初始化把所有元素都一一罗列出来就不太合适了。对于此例来说，更好的处理方法是先创建一个空vector，然后在运行时再利用vector 的成员函数**push_back**向其中添加元素。**push_back负责把一个值当成vector对象的尾元素“压到( push)" vector对象的“尾端( back)”。**例如:

```c++
vector<int> v2;			//空vector对象
for (int i = 0; i != 100; i++){
    v2.push_back(i);
}
```



## 其他vector操作

vector支持的操作：

| **v.empty()**            | **如果v不含有任何元素，返回真；否则返回假**                  |
| ------------------------ | ------------------------------------------------------------ |
| **v.size()**             | **返回v中元素的个数**                                        |
| **v.push_back(t)**       | **向v的尾端添加一个值为t的元素**                             |
| **v[n]**                 | **返回第n个元素位置上的引用**                                |
| **v1 = v2**              | **用v2中元素的拷贝替换v1中的元素**                           |
| **v1 = {a, b, c, ....}** | **用列表中元素的拷贝替换v1中的元素**                         |
| **v1 == v2, v1 != v2**   | **v1和v2相等当且仅当它们的元素数量相同且对应位置的元素值都相同** |
| **<, >, <=, >=**         | **顾名思义，以字典顺序进行比较**                             |
|                          |                                                              |
|                          |                                                              |

