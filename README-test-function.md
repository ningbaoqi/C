### 字符类别测试`<ctype.h>`

|函数|说明|
|------|------|
|`isalnum(c)`|函数isalpha(c)或isdigit(c)为真；每个函数的参数均为int类型，参数的值必须是EOF或可用unsigned char类型表示的字符，函数的返回值为int类型，如果参数c满足指定的条件，则函数返回非0值表示为真，否则返回0表示为假|
|`isalpha(c)`|函数isupper(c)或islower(c)为真|
|`int isascii(int c)`|判断c是否为标准ASCII字符|
|`iscntrl(c)`|c为控制字符|
|`isdigit(c)`|c为十进制数字|
|`isgraph(c)`|c是除空格外的可打印字符|
|`islower(c)`|c是小写字母|
|`isprint(c)`|c是包括空格的可打印字符|
|`ispunct(c)`|c是除空格、字母和数字外的可打印字符|
|`isspace(c)`|c是空格、换页符、换行符、回车符、横向制表符或纵向制表符|
|`isupper(c)`|c是大写字母|
|`isxdigit(c)`|c是十六进制数字|
|int tolower(int c)|将c转换为小写字母；如果c是大写字母，则返回相应的小写字母，否则返回c|
|int toupper(int c)|将c转换为大写字母；如果c是小写字母，则返回相应的大写字母，否则返回c|
