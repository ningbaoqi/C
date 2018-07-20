### 驱动器_目录函数`<dir.h>`

|函数|说明|
|-------|-------|
|`int chdir(char* pathname)`|将名为pathname的目录当作当前目录|
|`int getcurdir(int drive , char* dir)`|取drive指定的驱动器的当前目录存到dir|
|`int getdisk(void)`|返回当前磁盘驱动器号|
|`int mkdir(char* pathname)`|建立名字为pathname的新目录|
|`int rmdir(char* pathname)`|删除名为pathname的目录|
|`int setdisk(int drive)`|设置drive指定的驱动器为当前驱动器|
