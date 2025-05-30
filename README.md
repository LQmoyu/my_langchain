# my_langchain

union 成员共享一块地址空间，共用体大小 = 成员中占内存最大的成员的大小
struct 不同的成员放在不同的地址中， 结构体大小 = 所有成员大小之和（注意字节对齐）
#include <stdio.h>

typedef union {
    int i;
    int k[5];
    char c;
} Data;

typedef struct {
    int a;
    Data cow;
    short b;
} DataStruct;

int main(void){
    printf("Size of Data: %d bytes\n", sizeof(Data)); //20 bytes
    printf("Size of DataStruct: %d bytes\n", sizeof(DataStruct)); //28 bytes
}
