# first: uses of const keyword in c++:
const keyword is used in c++ to refer to elements that cannot be changed or modified and, it can be used for:
 
## 1) constant variables:
const keyword can be used to refer to constant variables in c++ so, it can be used in declaration to indicate 
that this variable cannot be changed (modified) also, constant variables should be given initial values
while their declaration.

EXAMPLE 

~~~
int main(){
   const int DaysOfMonth = 30;
   const double weeks = DaysOfMonth/7;     //no error.
   DaysOfMonth = 31;                       //error.
}
~~~

from the previous example we can conclude that constant variables can be used in substitution in another
variables but, they cannot be modified.

## 2) constant pointers;
we can use const keyword for declaring pointers.

In pointers the const keyword can be used in two ways:

***first: pointer to constant variable:
this means that the pointer is pointing to a constant variable 

EXAMPLE

~~~
const int* ptr1;                      //pointer is pointing to a constant variable of integer type.
int const* ptr1;                      //same meaning of the previous one.
~~~

IMPORTANT REMARK
pointers to constant variables is useful for making arrays and strings immutable (cannot be changed).

***second:constant pointer:
pointer can be declared to be constant by using the const keyword to the right of * sign.

EXAMPLE 

~~~
int main(){
    int x =5;
    int* const ptr1 = &x;           //ptr1 is a constant pointer.
}
~~~

in the previous example, for constant pointer ptr1 it will always point to the variable x although, we can 
change the value of variable x itself as x is not a constant variable.

IMPORTANT REMARKS
1- constant pointer is useful if we want to change the value of variable but, to be stored in the same memory
location so, the constant pointer will always point to this location.

2- we can use the constant pointer to point to a constant variable.


## 3) constant function arguments and return types:
we can use const to make function arguments constant.

EXAMPLE

~~~
void function(const int x =1){
     x=4;                       //error.
}
~~~

also, we can make the return type of the function to be constant.

EXAMPLE

~~~
const int function(int x){
      x++;                  //no error.
      return 1;
}
~~~

in the previous example the return value cannot be modified.

IMPORTANT REMARKS
1-the temporary objects that are created during the execution of the program are by default of constant type.
2-we cannot pass a const argument for a function that have a non-const parameter but, for a function with
const parameter we can pass a const or non-const type argument.


## 4) using const keyword for defining class data members:
we can declare constant variables in class but, they are not initialized while declaration, they are 
initialized using the constructor.

EXAMPLE 

~~~
class class1
{
     const int i;
     public:
     class1(int j):i(j);
     {
     cout << "i=" << i;
     }
};

int main(){
    class1 x(10);
    class1 y(20);
}
~~~

in the previous mentioned example "i" is constant data member, it has independent copy in each object created
which is initialized using the constructor and its value cannot be changed after the initialization.


## 5) const keyword can be used in defining the class object:
when object is declared by the const keyword we cannot change its data members during its lifetime.
 
EXAMPLE 

~~~
const class1 object(30);       //declaration of constant object.
~~~


## 6) const keyword can be used for defining class’s member function:
const member functions cannot modify data members in any object.

syntax:

~~~
return_type function_name() const;
~~~

EXAMPLE for const object and const member function

~~~
class birds
{
    public:
    int i;
    birds(int x)            //constructor.
    {
       i=x;
    } 
    
    
    int falcon() const     //constant function.
    {
    cout << "falcon can fly" << endl;
    // constant function so we cannot modify any data members.
    }
    
    
    int bird()
    {
       i++;
    }
};

int main() { 
    birds object1(10);             //non-constant object.
    const birds object2(20);       //constant object.
    
    object1.falcon();              //no error.
    object2.falcon();              //no error.
    
    cout << onject1.i << object2.i;
    
    object1.bird();               //no error.
    object2.bird();               //error (compile time).
}
~~~

in the previous example we can note that:
the const member function never change the data members of the class and, it can be used for constant and
non-constant objects but, we cannot use the const object  with a constant member which tries to modify
its data members.

                       *********************************************************

# second: uses of "&" symbol in c++
the main usage of the "&" in c++ is that its used as an operator either a bitwise and operator or as a pointer
address of operator.

## 1) usage as bitwise and operator:
the & as a bitwise operator compares each bit of the first operand to that bit of the second operand and, 
it gives 1 if both bits are 1 otherwise it gives 0.

IMPORTANT REMARK
the operands of the bitwise and operator should be of integral type.

EXAMPLE 

~~~
#include <iostream>
using namespace std;

int main(){
    unsigned short x = 0x5555;     //0101
    unsigned short y = 0xAAAA;     //1010
    cout << hex << (x&y) << endl;
}
~~~

the output of the following code will be 0 as if we applied the bitwise and operator it will give 0000
which is 0.

## 2) usage as address of operator:
There are two pointer operators provided by c++ which are address operator (&) and indirection
operator (*).

the pointer is considered as a variable that contains address of another variable so, it’s a variable that points to 
another variable so, variable can be any data or pointer.
the address of the (&) operator and its complement (*), it’s a unary operator that returns the address of the variable 
specified by its operand.

EXAMPLE

~~~
#include <iostream>
using namespace std;

int main() {
    int x;
    int *ptr1;
    int y;
    
    x=3000;
    
    ptr1=&x;  //ptr1 takes the address of x.
    
    //taking the value available at ptr1.
    y= *ptr1;
    cout << "value of x =" << x << endl;
    cout << "value of ptr1 =" << ptr1 << endl;
    cout << "value of y =" << y << endl;
    
    return 0;
}
~~~
 the output of this code will be:
 value of X = 3000 
 value of ptr1 = 0xbff64494
 value of y = 3000








   
   
