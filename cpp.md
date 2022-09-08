# C++

```cpp
#include <iostream>

int main()
{
    std::cout << "Hello, World!" << std::endl;
    return 0;
}
```

## Data Types

```cpp
std::string name = "Saracen"; //string
char gender = 'm'; //char
int age = 20; //int
bool older18 = true; //bool
float averageGrade = 4.0f; //float
double balance = 3535664675.757; //double
int arrname[10] = {0,1,2,3,4,5,6,7,8,9}; //array
```

## In and Output

```cpp
std::string username;
std::cin >> username; //write user input as string in variable
std::cout << "my name is " << username << std::endl; //print variable
```

## Namespaces

```cpp
#include <iostream>
using namespace std; //"import" std namespace (not recommended)
string name = "Saracen"; //string

//import only string, cout, endl, cin
using std::string; using std::cout; using std::endl; using std::cin; 

```

## Casting

change the data type of a variable

```cpp
x = 3.14; //double
y = (int)x; //int
```

## Arrays

```cpp
int array[] = {1, 2, 3, 4, 5, 6};
int arraySize = sizeof(array) / sizeof(array[0]); //get size of array

for (auto item : items) {  // iterate array or list
    std::cout << item << std::endl;
}
```

### Flow Control

```cpp
int n;
cout << "enter number ";
cin >> n;
if (n%2 == 0) {
    cout << "the mumber is even" << endl;
} else {
    cout << "the mumber is odd" << endl;
}
```
