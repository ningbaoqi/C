### 动态分配函数`<alloc.h>`

|函数|说明|
|-------|-------|
|`void* calloc(unsigned n , unsigned size)`|分配n个大小为size字节的内存区并返回首地址|
|`void free(void* ptr)`|释放ptr所指的内存区|
|`void* malloc(unsigned size)`|分配大小为size字节的内存区并返回首地址|
|`void realloc(void* ptr , unsigned newsize)`|将ptr所指的内存区大小改为newsize字节并返回首地址|
