### 枚举enum
```
enum Week{Sun , Mon , Tue , Wed , Thu , Fri , Sat};
```
### 联合union
+ 联合是可以在不同时刻保存不同类型和长度的对象的变量，编译器负责跟踪对象的长度和对齐要求，联合提供了一种方式，以在单块存储区中管理不同类型的数据，而不需要在程序中嵌入任何同机器有关的信息；
```
union u_tag{
       int ival;
       float fval;
       char* sval;
} u;
//变量u必须足够大，以保存这三种类型中最大的一种，具体长度同具体的实现有关，访问联合中的成员，联合名.成员   或   联合指针 -> 成员
```
+ 联合可以使用在结构和数组中，反之亦可，访问结构中的联合（或反之）的某一成员的表示法与嵌套结构相同；
```
struct{
       char* name;
       int flags;
       int utype;
       union{
              int ival;
              float fval;
              char* sval;
       } u;
} symtab[NSYM];
//调用成员
symtab[i].u.ival;
*symtab[i].u.sval;
```
### 结构体的基础知识
+ `struct`声明定义了一种数据类型，在标志结构成员表结束的右花括号之后可以跟一个变量表，这与其他基本类型的变量声明是相同的；如果结构声明的后面不带变量表，则不需要为它分配存储空间，它仅仅描述了一个结构的模版或轮廓，但是如果结构声明中带有标记，那么在以后定义结构实例时可以使用该标记定义；`struct point pt`；定义了一个`struct point`类型的变量`pt`，结构的初始化可以在定义的后面使用初值表进行，初值表之间每个成员对应的初值必须是常量表达式；如`struct point maxpt = {320 , 200}`；在表达式中，可以通过下列形式引用特定结构中的成员，`结构名.成员`；`pt.x`；结构可以嵌套；
```
struct point {int x ; int y;};
struct point {int x ; int y;} x , y , z;
struct rect{struct point pt1 ; struct point pt2 ; };
```
### 结构与函数
+ 结构的合法操作只有几种，作为一个整体复制和赋值，通过`&`运算符取地址，访问其成员，其中，复制和赋值包括向函数传递参数以及从函数返回值，结构之间不可以进行比较，可以用一个常量成员值列表初始化结构，自动结构也可以通过赋值进行初始化；结构类型的参数和其他类型的参数一样，都是通过值传递；
```
struct point makepoint(int x , int y){
       struct point temp;
       temp.x = x;
       temp.y = y;
       return temp;
}
```
+ 结构指针：`struct point *pp；`将`pp`定义为一个指向`struct point`型对象的指针，如果`pp`指向一个`point`结构，那么`*pp`即为该结构，而`(*pp).x`和`(*pp).y`则是结构成员；结构指针的使用频率非常高，为了方便使用，C语言提供了另一种简写形式，假定`p`是一个指向结构的指针，可以使用`p->结构成员`方式引用相应的结构成员，如`printf("origin is (%d,%d)\n", pp->x , pp->y)`；
```
struct rect r , *rp = &r;
//以下4个表达式是等价的
r.pt1.x
rp -> pt1.x
(r.pt1).x
(rp -> pt1).x
//下面4个运算符的优先级最高： . -> () []
```
+ 表达式`++p->len`将增加len的值，而不是增加p的值，这是因为，其中的隐含括号关系是`++(p->len)`同样道理，`*p->str`读取的是指针str所指向的对象的值，`*p->str++`先读取指针str指向的对象的值，然后再将str加1；`(*p->str)++`将指针str指向的对象的值加1；`*p++->str`先读取指针str指向的对象的值，然后再将p加1；
### 结构数组
```
struct key{
       char* word;
       int count;
} keytab[NKEYS];
//也可以写成
struct key{
       char* word;
       int count;
};
struct key Keytab[NKEYS];
//在定义后面通过一个用圆括号括起来的初值表进行初始化
struct key{
       char* word;
       int count;
} keytab[] = {
       "auto" , 0 , 
       "break" , 0 ,
       "case" , 0 ,
       "char" , 0 , 
       "const" , 0 ,
       "continue" , 0 ,
       "default" , 0 
};
```
+ C语言提供了一个编译时一元运算符`sizeof`它可用来计算任一对象的长度，表达式`sizeof 对象`或`sizeof(类型名)`将返回一个整形值，它等于指定对象或类型占用的存储空间字节数（严格的说，sizeof的返回值是无符号整形值，其类型是size_t，该类型在头文件`<stddef.h>`中定义）；条件编译语句`#if`中不能使用sizeof，因为预处理器不对类型名进行分析，但预处理器并不计算#define语句中的表达式，因此，在#define中使用sizeof是合法的；
