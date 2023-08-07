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








// use of structure tag (struct employee) >> is a structure tag
/* i/p >> Enter The Salary Of the Employee1: 20000,Enter The Salary Of the Employee2: 30000
o/p  >>  employee 1 salary is : 20000
 employee 2 salary is : 30000
 manager salary is : 55000*/
 
 
#include <stdio.h>
struct employee {
    char *name;
    int age ;
    int salary ;
    } ;
    int manager()
    {
        struct employee manager ;
        
        manager.age = 27 ;
        if (manager.age >30 )
        manager.salary = 65000 ;
        else 
        manager.salary = 55000 ;
        return manager.salary ;
    }
int main() {
    struct employee emp1 ;
    struct employee emp2 ;
    printf("Enter The Salary Of the Employee1: ");
    scanf("%d" , &emp1.salary) ;
    printf("Enter The Salary Of the Employee2: ");
    scanf("%d" , &emp2.salary) ;
    printf("employee 1 salary is : %d\n ", emp1.salary);
    printf("employee 2 salary is : %d\n ", emp2.salary);
    printf("manager salary is : %d\n ", manager());
    return 0;
}






// use of typedef is change the old dtatype to new datatype
//o/p >> 100
 
 
#include <stdio.h>
typedef int INTEGER ;
int main() {
    INTEGER var = 100 ;
    printf("%d\n ", var);
    return 0;
}






// how to initialize structure and accessing members of structure this code for initialize

 
 
#include <stdio.h>
struct car {
 char engine[50] ;
 char fuel_type[10] ;
 int fuel_tank_cap ;
 int seating_cap ;
 float city_mileage ;
};
int main() {
   struct car c1 = { "DDis 190 Engine" , "Diesel" , 37 , 5 , 19.74} ;
   struct car c2 = { "kappa" , "petrol" , 22 , 8 , 14.5} ;
    
    return 0;
}








// how to  accessing members of structure this code for accesssing we use (.) operator   o/p  >> 45 30 


#include <stdio.h>
struct car {

 int fuel_tank_cap ;
 
}c1,c2;
int main() {
   c1.fuel_tank_cap= 45 ;
   c2.fuel_tank_cap= 30 ;
    printf("%d %d", c1.fuel_tank_cap , c2.fuel_tank_cap) ;
    return 0;
}







/* how to  accessing members of structure this code for accesssing we use (.) operator   o/p  
    10 20 30
    10 20 30*/
 
 
#include <stdio.h>
struct abc {

 int x ;
 int y ;
 int z ;
};


int main() {
   struct abc a ={ .x = 10, .y =20 , .z = 30} ;
    printf("%d %d %d\n", a.x , a.y ,  a.z) ;
     struct abc b ={ .x = 10, .y =20 , .z = 30} ;
    printf("%d %d %d", b.x , b.y ,  b.z) ;
    return 0;
}








// declare an array of structure
/*
i/p >>  Enter the car 1 fuel tank capacity : 23
        Enter the car 1 seating capacity : 5
        Enter the car 1 city mileage : 17.89
        Enter the car 2 fuel tank capacity : 22
        Enter the car 2 seating capacity : 7
        Enter the car 2 city mileage : 14.65
o/p>> car 1 details :
      fuel tank capacity :23
        seating capacity :5
         city mileage :17.889999
 
 car 2 details :
 fuel tank capacity :22
 seating capacity :7
 city mileage :14.650000*/
#include <stdio.h>

struct car{
    int fuel_tank_cap ;
    int seating_cap ;
    float city_mileage ;
};
int main() {
    struct car c[2] ;
    int i ;
    for(i = 0 ; i < 2 ; i++)
    {
        printf("Enter the car %d fuel tank capacity : ",i+1) ;
        scanf("%d",&c[i].fuel_tank_cap) ;
        printf("Enter the car %d seating capacity : ",i+1) ;
        scanf("%d",&c[i].seating_cap) ;
        printf("Enter the car %d city mileage : ",i+1) ;
        scanf("%f",&c[i].city_mileage) ;
        
    }
    printf("\n");
    for(i = 0 ; i < 2 ; i++)
    {
       printf("\n car %d details :\n ",i+1) ; 
       printf("fuel tank capacity :%d\n ",c[i].fuel_tank_cap) ; 
       printf("seating capacity :%d\n ",c[i].seating_cap) ;
       printf("city mileage :%f\n ",c[i].city_mileage) ;
    }

    return 0;
}








//access members of structure using structure pointer  o/pp >> 0 1 \n 23
#include <stdio.h>

struct abc{
    int x ;
    int y ;
    
};
int main() {
    struct abc a = {0, 1} ;
    struct abc *ptr = &a ;
    printf("%d %d\n" ,ptr ->x,ptr ->y);
    struct abc b = {2, 3} ;
    struct abc *pt = &b ;
    printf("%d %d ", pt ->x,pt ->y) ;
    return 0;
}









