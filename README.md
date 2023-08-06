# structure

// function pointers it points to a function o/p>> 30 this pointer pointing the add function
#include <stdio.h>
int add(int  a ,int b)
{
    return a+b ;
}

int main() {
    int result ;
    int(*ptr)(int , int) = add ;  // here we can put add or &add both addresss add>> address of the first value
    result = ptr(10 , 20) ;
    printf("%d ", result);

    return 0;
}


