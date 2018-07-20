### 字符串函数`<string.h>`

|函数|说明|
|------|------|
|`char *strcpy(s , ct)`|将字符串ct包括`\0`复制到字符串s中，并返回s|
|`char *strncpy(s , ct , n)`|将字符串ct中最多n个字符复制到字符串s中，并返回s，如果ct中少于n个字符，则用`\0`填充|
|`char *strcat(s , ct)`|将字符串ct连接到s的尾部，并返回s|
|`char *strncat(s , ct , n)`|将字符串ct中最多前n个字符连接到字符串s的尾部，并以`\0`结束，该函数返回s|
|`int strcmp(cs , ct)`|比较字符串cs和ct，当`cs<ct`时，返回一个负值，当`cs==ct`时，返回0，当`cs > ct`返回正数|
|`int strncmp(cs , ct , n)`|将字符串cs中至多前n个字符与字符串ct相比较，当`cs <ct`时，返回一个负数，当`cs== ct`时，返回0，当`cs > ct`时，返回正数|
|`char *strchr(cs , c)`|返回指向字符c在字符串cs中第一次出现的位置的指针，如果cs中不包含c，则该函数返回NULL|
|`char *strrchr(cs , c)`|返回指向字符c在字符串cs中最后一次出现的位置的指针，如果cs中不包含c，则该函数返回NULL|
|`size_t strspn(cs , ct)`|返回字符串cs中包含ct中的字符的前缀的长度|
|`size_t strcspn(cs , ct)`|返回字符串cs中不包含ct中的字符的前缀的长度|
|`char *strpbrk(cs , ct)`|返回一个指针，它指向字符串ct中的任意字符第一次出现在字符串cs中的位置，如果cs中没有与ct相同的字符，则返回NULL|
|`char *strstr(cs , ct)`|返回一个指针，它指向字符串ct第一次出现在字符串cs中的位置，如果cs中不包含字符串ct，则返回NULL|
|`size_t strlen(cs)`|返回字符串cs的长度|
|`char* strerror(n)`|返回一个指针，它指向与错误编号n对应的错误信息字符串（错误信息的具体内容与具体实现有关）|
|`char* strtok(s , ct)`|strtok函数在s中搜索由ct中的字符界定的记号|
|`gets(string)`|从键盘读入字符串，直到读入换行符为止，用`\0`代替换行符并把读入的字符串存入以string为首地址的存储区中|
|`puts(string)`|把首地址为string的字符串显示在屏幕上，输出时用`\n`替换`\0`|
|`strlwr(string)`|把首地址为string的字符串中所有的大写字母转换成小写字母，其他字符不变|
|`strupr(string)`|把首地址为string的字符串中所有的小写字母转换成大写字母，其他字符不变|
|`char* strnset(char* str , char c , unsigned n)`|将串str中的前n个字符都设置为字符c|
|`char* strset(char* str , char c)`|将串str中的所有字符都设置为字符c|
|`char* strrev(char* str)`|将串str中的所有字符倒置|
+ 变量s和t的类型为`char*`；cs和ct的类行为`const char*`；n的类型为size_t；c的类型为int（将被转换为char类型）；

|函数|说明|
|------|------|
|`void* memcpy(s , ct , n)`|将字符串ct中的n个字符拷贝到s中，并返回s|
|`void* memmove(s , ct , n)`|该函数的功能与上函数的功能相似，所不同的是，当对象重叠时，该函数仍然正确执行|
|`int memcmp(cs , ct , n)`|将cs的前n个字符与ct进行比较，其返回值与strcmp的返回值相同|
|`void * memchr(cs , c ,n)`|返回一个指针，它指向c在cs中第一次出现的位置，如果在cs的前n个字符中找不到匹配，则返回NULL|
|`void *memset(s , c, n)`|将s中的前n个字符替换为c，并返回s|
+ s和t的类型均为`void*`，cs和ct的类型均为`const void* `，n的类型为size_t，c的类型为int(将被转换为unsigned char类型)；
