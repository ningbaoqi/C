### 类型定义typedef
+ C语言提供了一个称为`typedef`的功能，它用来建立新的数据类型名；
```
typedef int Lenght;  //将length定义为与int具有同等含义的名字，类型length可用于类型声明，类型转换等，它和类型int完全相同
Length len , maxlen;
Length* lengths[];

typedef char* String;  //将String定义为与char*或字符指针同义
```
+ `typedef`声明并没有创建一个新类型，它只是为某个已经存在的类型增加了一个新的名字而已；`typedef int (*PFI)(char* , char*)`该语句定义了类型PFI是一个指向函数的指针，该函数具有两个char*类型的参数，返回值类型为int；
