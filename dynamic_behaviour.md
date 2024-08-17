# Dynamic Behavior in C++

Dynamic behavior in programming refers to actions or decisions that occur during the execution of a program, based on conditions that are only known or determined at runtime. In C++, there are several ways to implement dynamic behavior.

## 1. Dynamic Memory Allocation

C++ allows for memory to be allocated and deallocated during program execution.

```cpp
int main() {
    int size;
    cout << "Enter array size: ";
    cin >> size;
    
    int* arr = new int[size];  // Dynamic allocation
    
    // Use the array...
    
    delete[] arr;  // Deallocate memory
    return 0;
}
```

## 2. Polymorphism and Virtual Functions

```cp
class Animal {
public:
    virtual void makeSound() = 0;
};

class Dog : public Animal {
public:
    void makeSound() override { cout << "Woof!" << endl; }
};

class Cat : public Animal {
public:
    void makeSound() override { cout << "Meow!" << endl; }
};

int main() {
    Animal* pet;
    int choice;
    cout << "Choose pet (1 for Dog, 2 for Cat): ";
    cin >> choice;
    
    if (choice == 1)
        pet = new Dog();
    else
        pet = new Cat();
    
    pet->makeSound();  // Dynamic dispatch
    
    delete pet;
    return 0;
}
```

The actual function called by pet->makeSound() is determined at runtime.

## 3. Function Pointers and Callbacks

```cpp
void add(int a, int b) { cout << "Sum: " << a + b << endl; }
void subtract(int a, int b) { cout << "Difference: " << a - b << endl; }

int main() {
    void (*operation)(int, int);  // Function pointer
    int choice;
    cout << "Enter 1 for addition, 2 for subtraction: ";
    cin >> choice;
    
    if (choice == 1)
        operation = add;
    else
        operation = subtract;
    
    operation(10, 5);  // Dynamic function call
    return 0;
}
```
The function to be called is decided at runtime based on user input.

## 4. Exception Handling
```cpp
int divide(int a, int b) {
    if (b == 0)
        throw runtime_error("Division by zero!");
    return a / b;
}

int main() {
    int a = 10, b;
    cout << "Enter a number: ";
    cin >> b;
    
    try {
        int result = divide(a, b);
        cout << "Result: " << result << endl;
    } catch (const exception& e) {
        cout << "Error: " << e.what() << endl;
    }
    
    return 0;
}
```
The program's behavior changes dynamically based on whether an exception is thrown.

## 5. Dynamic Casting
```cpp
class Base { public: virtual ~Base() {} };
class Derived : public Base { public: void specialFunction() {} };

void processObject(Base* obj) {
    Derived* derivedPtr = dynamic_cast<Derived*>(obj);
    if (derivedPtr)
        derivedPtr->specialFunction();
    else
        cout << "Object is not of Derived type" << endl;
}
```

dynamic_cast checks the object type at runtime and casts only if it's safe.
