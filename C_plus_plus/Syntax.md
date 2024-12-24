# C++ Syntax Reference Guide

## Basic Program Structure
```cpp
#include <iostream>
using namespace std;

int main() {
    // Your code here
    return 0;
}
```

## Data Types & Variables
```cpp
// Integer types
int a = 10;                    // -2147483648 to 2147483647
short b = 5;                   // -32768 to 32767
long c = 100000L;             // At least 32 bits
long long d = 1000000000LL;   // At least 64 bits

// Floating point types
float f = 3.14f;              // 7 decimal digits
double d = 3.14159;           // 15 decimal digits
long double ld = 3.14159L;    // 19 decimal digits

// Character types
char ch = 'A';                // Single character
char str[] = "Hello";         // C-style string
string s = "Hello";           // C++ string

// Boolean type
bool flag = true;             // true or false

// Constants
const int MAX_SIZE = 100;
#define PI 3.14159
```

## Input/Output
```cpp
// Output
cout << "Hello World" << endl;
cout << "Value: " << variable << endl;

// Input
int num;
cin >> num;

string name;
getline(cin, name);  // For strings with spaces

// File I/O
#include <fstream>
ofstream outFile("file.txt");
outFile << "Writing to file" << endl;
outFile.close();

ifstream inFile("file.txt");
string line;
getline(inFile, line);
inFile.close();
```

## Operators
```cpp
// Arithmetic
int sum = a + b;      // Addition
int diff = a - b;     // Subtraction
int prod = a * b;     // Multiplication
int quot = a / b;     // Division
int rem = a % b;      // Modulus

// Increment/Decrement
int x = 5;
x++;                  // Post-increment
++x;                  // Pre-increment
x--;                  // Post-decrement
--x;                  // Pre-decrement

// Comparison
bool isEqual = (a == b);
bool isNotEqual = (a != b);
bool isGreater = (a > b);
bool isLess = (a < b);
bool isGreaterEqual = (a >= b);
bool isLessEqual = (a <= b);

// Logical
bool andResult = (a && b);
bool orResult = (a || b);
bool notResult = !a;

// Assignment
int x = 5;
x += 3;              // x = x + 3
x -= 3;              // x = x - 3
x *= 3;              // x = x * 3
x /= 3;              // x = x / 3
x %= 3;              // x = x % 3
```

## Control Structures
```cpp
// If-else
if (condition) {
    // code
} else if (condition2) {
    // code
} else {
    // code
}

// Switch
switch (variable) {
    case 1:
        // code
        break;
    case 2:
        // code
        break;
    default:
        // code
}

// For loop
for (int i = 0; i < 10; i++) {
    // code
}

// While loop
while (condition) {
    // code
}

// Do-while loop
do {
    // code
} while (condition);

// Range-based for loop
for (auto item : container) {
    // code
}
```

## Arrays
```cpp
// Array declaration
int arr[5];                      // Uninitialized
int arr[5] = {1, 2, 3, 4, 5};   // Initialized
int arr[] = {1, 2, 3, 4, 5};    // Size inferred

// 2D array
int matrix[3][3] = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};

// Vector (dynamic array)
#include <vector>
vector<int> vec;                 // Empty vector
vector<int> vec = {1, 2, 3};    // Initialized vector
vec.push_back(4);               // Add element
vec.pop_back();                 // Remove last element
```

## Functions
```cpp
// Basic function
returnType functionName(paramType param) {
    // code
    return value;
}

// Function with default parameters
void greet(string name = "Guest") {
    cout << "Hello " << name << endl;
}

// Pass by reference
void modify(int& x) {
    x = x * 2;
}

// Function overloading
int add(int a, int b) { return a + b; }
double add(double a, double b) { return a + b; }

// Lambda function
auto lambda = [](int x) { return x * 2; };
```

## Classes
```cpp
class ClassName {
private:
    // Private members
    int privateVar;

protected:
    // Protected members
    int protectedVar;

public:
    // Constructor
    ClassName(int var) {
        privateVar = var;
    }

    // Destructor
    ~ClassName() {
        // cleanup code
    }

    // Member function
    void memberFunction() {
        // code
    }

    // Getter
    int getVar() { return privateVar; }

    // Setter
    void setVar(int var) { privateVar = var; }
};

// Using a class
ClassName obj(10);
obj.memberFunction();
```

## Pointers & References
```cpp
// Pointers
int* ptr;                // Declaration
int x = 5;
ptr = &x;               // Assignment
cout << *ptr;           // Dereferencing

// Dynamic allocation
int* arr = new int[5];  // Allocate
delete[] arr;           // Deallocate

// References
int& ref = x;           // Reference declaration
ref = 10;               // Modifies x
```

## Exception Handling
```cpp
try {
    // Code that might throw exception
    if (error_condition) {
        throw exception_object;
    }
}
catch (exception_type& e) {
    // Handle exception
    cout << e.what() << endl;
}
catch (...) {
    // Handle any other exceptions
}
```