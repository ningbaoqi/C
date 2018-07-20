### 关键字

|`auto`|`break`|`case`|`char`|`const`|`continue`|`default`|`do`|`double`|
|------|------|------|------|------|------|------|------|------|
|`else`|`enum`|`extern`|`float`|`for`|`goto`|`if`|`int`|`long`|
|`register`|`return`|`short`|`signed`|`sizeof`|`static`|`struct`|`switch`|`typedef`|
|`union`|`unsigned`|`void`|`volatile`|`while`|||||

#### static
+ 在修饰变量的时候，`static`修饰的`静态局部变量`只执行一次，而且延长了局部变量的生命周期，直到程序运行结束以后才释放；`static`修饰`全局变量`的时候，这个全局变量只能`在本文件中访问`，不能在其它文件中访问，即便是`extern`外部声明也不可以；`static`修饰一个函数，则这个函数的`只能在本文件中调用`，不能被其他文件调用，`static`修饰的局部变量存放在全局数据区的静态变量区。初始化的时候自动初始化为0；
