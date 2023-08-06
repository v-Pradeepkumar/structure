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








// use of function pointer >> user can decide which function is call in which time using switch case
//Enter the choice: 0 for sum , 1 for sub , 2 for mul , 3 for div: 
// i/p >> 0
//print enter the two numbers:
//i/p >> 134 345
//o/p >> 479.000000


#include <stdio.h>
float sum(float a , float b){return (a+b);}
float sub(float a , float b){return (a-b);}
float mul(float a , float b){return (a*b);}
float div(float a , float b){return (a/b);}
int main() {
    int choice ;
    float a , b , result ;
    printf("Enter the choice: 0 for sum , 1 for sub , 2 for mul , 3 for div: \n");
    scanf("%d", &choice) ;
    printf("print enter the two numbers:\n");
    scanf("%f %f", &a , &b) ;
    
    switch(choice)
    {
        case 0: result = sum(a,b) ; break ;
        case 1: result = sub(a,b) ; break ;
        case 2: result = mul(a,b) ; break ;
        case 3: result = div(a,b) ; break ;
    }
    printf("%f",result) ;
    return 0;
}









// use of function pointer >> user can decide which function is call in which time without switch case
/*Enter the choice: 0 for sum , 1 for sub , 2 for mul , 3 for div: 
0
print enter the two numbers:
i/p >> 345 879
o/p >> 1224.000000*/


#include <stdio.h>
#define ops 4
float sum(float a , float b){return (a+b);}
float sub(float a , float b){return (a-b);}
float mul(float a , float b){return (a*b);}
float div(float a , float b){return (a/b);}
int main() {
    float (*ptr2func[ops])(float , float) = {sum ,sub ,mul ,div} ;
    int choice ;
    float a , b ;
    printf("Enter the choice: 0 for sum , 1 for sub , 2 for mul , 3 for div: \n");
    scanf("%d", &choice) ;
    printf("print enter the two numbers:\n");
    scanf("%f %f", &a , &b) ;
    
    printf("%f",ptr2func[choice](a , b)) ;
    return 0;
}






//basic example of  structure
/* o/p
DDis 190 Engine
1.2 L Kapppa dual VTVT*/




#include <stdio.h>
struct{
    char *engine;
}car1 ,car2 ;
int main() {
    car1.engine = "DDis 190 Engine" ;
    car2.engine = "1.2 L Kapppa dual VTVT" ;

    printf("%s\n", car1.engine);
    printf("%s", car2.engine);
    return 0;
}






