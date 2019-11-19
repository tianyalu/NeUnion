## NeUnio 共用体
### 一、定义
一种特殊的数据类型，允许在相同的内存位置存储不同的数据类型；共用体可以带有多个成员，但任何时候只能有一个成员带有值；共用体提供了一种使用相同的内存位置的有效方式。 
![image](https://github.com/tianyalu/NeUnion/blob/master/show/union.png)  
### 二、代码
```c
union MyStudent {
    int i;
    float j;
    double d;
};
int main(int argc, const char * argv[]) {
    union MyStudent mystudent;
    mystudent.i = 10;
    printf("之前i %d\n", mystudent.i); //10
    mystudent.j = 11;
//    printf("i的地址 %#x\n", &mystudent.i); //0xefbff608
//    printf("j的地址 %#x\n", &mystudent.j); //0xefbff608
    
    printf("i的地址 %px\n", &mystudent.i); //0x7ffeefbff608x
    printf("j的地址 %px\n", &mystudent.j); //0x7ffeefbff608x
    
    printf("之后i %d\n", mystudent.i); //1093664768
    printf("之后j %f\n", mystudent.j); //11.000000
    
    printf("共用体大小： %ld\n", sizeof(mystudent)); //8
    return 0;
}
```