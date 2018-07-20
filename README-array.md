### 字符数组
```
#include<stdio.h>
#define MAXLINE 1000
int getline(char line[] , int maxline);
void copy(char to[] , char from[]);
main(){
       int len;
       int max;
       char line[MAXLINE];
       char longest[MAXLINE];
       max = 0;
       while((len = getline(line , MAXLINE)) > 0){
              if(len > max){
                     max = len;
                     copy(longest , line);
              }
       }
       if(max > 0){
              printf("%s" , longest);
       }
       return 0;
}

int getline(char s[] , int lim){
       int c , i ;
       for(i = 0 ; i < lim - 1 && (c = getChar() != EOF && c != '\n' , ++i)){
              s[i] = c;
       }
       if(c == '\n'){
              s[i] = c;
              ++i;
       }
       s[i] = '\0';
       return i;
}

void copy(char to[] , char from[]){
       int i;
       i = 0;
       while((to[i] = from[i] != '\0')){
              ++i;
       }
}
```
+ 在C语言程序中出现类似于`hello\n`的字符串常量时，它将以字符数组的形式存储，数组的各元素分别存储字符串的各个字符，并以`’\0‘`标志字符串的结束；如`hello\n\0`；
### 多维数组
+ 在C语言中，二维数组实际上是一种特殊的一维数组，它的每个元素也是一个一维数组，因此，数组下标应该写成`daytab[i][j]`；如`static char daytab[2][13] = {{0,31,28,31,30,31,30,31,31,30,31,30,31},{0,31,29,31,30,31,30,31,31,30,31,30,31}}`；在函数中参数可以写成`f(int daytab[2][13]){......}`也可以写成`f(int daytab[][13]){......}`因为数组的行数无关紧要，还可以写成`f(int (*daytab)[13]){.......}`这种声明形式表明参数是一个指针，它指向13个整型元素的一维数组；
### 指针数组的初始化
```
char* name[] = {"illegal month" , "jan" , "feb" , "mar" , "apr" , "may" , "jun" , "jul" , "aug" , "sep" , "oct" , "nov" , "dec"}; //声明中没有指明数组name的长度，因此，编译器编译时将对初值个数进行统计，并将这一准确数字填入数组的长度
```
### 命令行参数
+ 在支持C语言的环境中，可以在程序开始执行时将命令参数传递给程序，调用主函数`main`时，它将带有两个参数，第一个参数（习惯上称为argc，用于参数计数）的值表示运行程序时命令行中参数的数目，第二个参数（称为argv，用于参数向量）是一个指向字符串数组的指针，其中每个字符串对应一个参数，我们通常用多极指针处理这些字符串；按照C语言的约定，`argv[0]`的值是启动该程序的程序名，因此argc的值至少为1，如果argc的值为1，则说明程序名后面没有命令行参数；
