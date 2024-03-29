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

## Flow Control

### if else statement

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

### switch statement

```cpp
int day = 4;
switch (day) {
  case 6:
    cout << "Today is Saturday";
    break;
  case 7:
    cout << "Today is Sunday";
    break;
  default:
    cout << "Looking forward to the Weekend";
}
```

if there is no "break" the next case will be executed too

### for loop

```cpp
for (int i = 0; i < 5; i++) {
  cout << i ;
}
```

#### auto for loop

```cpp
for (auto item : items) {  // iterate array or list
    std::cout << item << std::endl;
}
```

### while loop

```cpp
int i = 0;
while (i < 5) {
  cout << i;
  i++;
}
```

#### do while loop

```cpp
int i = 0;
do {
  cout << i;
  i++;
} while (i < 5);
```

gets executed at least once

### break statement

```cpp
for (int i = 0; i < 10; i++) {
  if (i == 4) {
    break;
  }
  cout << i;
}
```

break statement breaks the loop

### continue statement

```cpp
for (int i = 0; i < 10; i++) {
  if (i == 4) {
    continue;
  }
  cout << i;
}
```

continue statement skips the current iteration

## functions

```cpp
int myFunction(int x, int y);

int main () {

    //code

    int myFunction(int x, int y) {
        return x + y;
}

}
```

you can also define the function before the main function
and implement it after the main function. This way you have
an overview of all functions in the beginning of the code.

### default parameters

```cpp
int myFunction(int x, int y = 5);
    return x + y;
```

you can set a default value for a parameter so you don't have to pass it every time <br/>
you can overwrite the default value by passing a value

## Exceptions

```cpp
    
try {
    int age = 21;
    if (age >= 16)
    {
        cout << "Access granted - you are old enough.";
    }
    else
    {
        throw(age);
    }
}
catch (int age)
{
    cout << "Access denied - You must be at least 18 years old.\n";
    cout << "Age is: " << age;
}
```

## Generics

generic datatypes can stand for any datatype to awoid function overloading

```cpp
template <typename T>
                            
void swapValue(T &a, T &b){
    T temp = a;
    a = b;
    b = temp;
}
```

## OOP

### Classes

everything `protected` can only be accessed inside the class and subclasses <br/>
everything `private` can only be accessed inside the class <br/>
you can use getter and setter to access `private` and `protected` variables outside the class <br/>
everything `public` can be accessed everywhere

```cpp
class YouTubeChannel {
protected:
    string Name;
    string OwnerName;
    int SubscribersCount;
    list <string> PublishedVideoTitles;
public:
    YouTubeChannel(string name, string ownerName){
        Name = name;
        OwnerName = ownerName;
        SubscribersCount = 0;
    }
    string getName(){
        return Name;
    }
    string setName(string name){
        Name = name; 
    }
};

int main(){
    // create object of class YouTubeChannel
    YouTubeChannel ytChannel("Saracen", "Saracen");
    ytChannel.setName("Saracen");
    cout << ytChannel.getName();
}
```

<!-- ### Enheritance

```cpp
class CookingYouTubeChannel : public YouTubeChannel {
``` -->
