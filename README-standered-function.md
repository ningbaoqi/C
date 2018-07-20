### 标准函数`<stdlib.h>`

|函数|说明|
|------|------|
|`double atof(const char *s)`|atof函数将字符串s转换为double类型，该函数等价于`strtod(s , (char##)NULL)`|
|`int atoi(const cahr* s)`|atoi函数将字符串s转换为int类型，该函数等价于`(int)strtol(s , (char**)NULL , 0)`|
|`long atol(const char* s)`|atol函数将字符串s转换为long类型，该函数等价于`strtol(s , (char**)NULL , 10)`|
|`double strtod(const char* s , cahr** endp)`|strtod函数将字符串s的前缀转换为double类型，并在转换时跳过s的前导空白符|
|`long strtol(const char *s , char** endp , int base)`|strtol函数将字符串s的前缀转换为long类型，并在转换时跳过s的前导空白符|
|`unsigned long strtoul(const cahr* s , char** endp , int base)`|该函数的功能与上函数相同，但其结果是unsigned long类型，误值为ULONG_MAX|
|`int rand(void)`|该函数产生一个0~RAND_MAX之间的伪随机整数，RAND_MAX的取值至少为32767|
|`void srand(unsigned int seed)`|srand函数将seed作为生成新的伪随机数序列的种子数，种子数seed的初值为1|
|`int random(int n)`|产生一个0~n之间的伪随机整数|
|`void randomize(void)`|初始化随机数发生器|
|`void* calloc(size_t nobj , size_t size)`|calloc函数为由nobj个长度为size的对象组成的数组分配内存，并返回指向分配区域的指针，若无法满足要求，则返回NULL，该空间的初始长度为0字节|
|`void* malloc(size_t size)`|malloc函数为长度为size的对象分配内存，并返回指向分配区域的指针，若无法满足，则返回NULL，该函数不对分配的内存区域进行初始化|
|`void* realloc(void* p , size_t size)`|该函数将p指向的对象的长度修改为size个字节，如果新分配的内存比原内存大，则原内存的内容保持不变，增加的空间不进行初始化，如果新分配的内存比原内存小，则新分配内存单元不被初始化，该函数返回指向新分配空间的指针，若无法满足要求，则返回NULL，在这种情况下，原指针p指向的单元内容保持不变|
|`void free(void* p)`|该函数释放p指向的内存空间，当p的值为NULL，该函数不执行任何操作，p必须指向先前使用动态分配函数malloc、realloc、calloc分配的空间|
|`void abort(void)`|该函数使程序非正常终止，功能和raise(SIGABRT)类似|
|`void exit(int status)`|exit函数使程序正常终止|
|`int atexit(void(*fnc)(void))`|atexit函数登记函数fcn，该函数将在程序正常终止时被调用，如果登记失败，则返回非0值|
|`int system(const char* s)`|该函数将字符串s传递给环境，如果s的值为NULL，并且有命令处理程序，则该函数返回非0值，如果s的值不是NULL，则返回值与具体的实现有关|
|`char *getenv(const char* name)`|该函数返回与name有关的环境字符串，如果该字符串不存在，则返回NULL|
|`void* bsearch(const void* key , const void* base , size_t n , size_t size , int(*cmp)(const void *keyval , const void* datum))`|bsearch函数在base之间查找*key的匹配的项，bsearch函数返回一个指针，它指向一个匹配项，如果不存在匹配项，则返回NULL|
|`void qsort(void* base , size_t n , size_t size , int(*cmp)(const void*, const void*))`|该函数对base数组中的对象进行升序排列，数组中每个对象的长度为size|
|`int abs(int n )`|返回int类型参数n的绝对值|
|`long abs(long n)`|返回long类型参数n的绝对值|
|`div_t div(int num , int denom)`|该函数计算`num/denom`的商和余数，并把结果分别保存到结构类型div_t的两个int类型的成员qout和rem中|
|`ldiv_t ldiv(long num , long denom)`|ldiv函数计算num/denom的商和余数，并把结果分别保存在结构类型ldiv_t的两个long类型的成员qout和rem中|
|`char* gcvt(double x , int len , char* str)`|将浮点数x转换成长度为len的串并存放在str，返回str|
|`char* itoa(int n , char* str , int radix)`|将整数n转换为radix进制表示的串并存放在str，返回str|
