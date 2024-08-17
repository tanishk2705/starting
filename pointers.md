## Stack vs. Heap Allocation in C++

### Example Code

```cpp
#include<iostream>
using namespace std;

int main(){
    // Basic Example
    int a = 4;
    int* ptr = &a;
    cout << "The value of a is " << *(ptr) << endl;

    // new keyword
    int *p = new int(40);
    cout << "The value at address p is " << *(p) << endl;

    return 0;
}
```


### Comparison: Stack vs. Heap

#### **Stack Allocation**
- **Performance**: Stack allocation is generally faster because it involves simple operations with the call stack, such as moving the stack pointer.
- **Automatic Memory Management**: Memory is automatically freed when the function or block scope ends.
- **Limited Size**: The stack has a limited size, so it's suitable for smaller, short-lived variables.
- **Thread Safety**: Each thread in a program has its own stack, making stack variables inherently thread-safe.

#### **Heap Allocation**
- **Flexibility**: Heap allocation allows for dynamic memory management, meaning you can allocate memory at runtime based on the program's needs.
- **Larger Memory Pool**: The heap has a much larger memory pool than the stack, making it suitable for large objects or arrays.
- **Manual Memory Management**: You have to manually manage the memory (using `delete` to free memory), which can lead to issues like memory leaks if not handled correctly.
- **Fragmentation**: The heap can become fragmented over time, which might lead to inefficient memory usage and slower allocation times.

### When to Use Which

- **Use Stack Allocation**: 
  - When you need fast allocation and deallocation.
  - For small, short-lived variables (e.g., local variables, small arrays).

- **Use Heap Allocation**: 
  - When you need to allocate a large amount of memory.
  - For memory that needs to persist beyond the scope of a function (e.g., objects that need to be shared across multiple functions or exist for the program's lifetime).

### Conclusion
- **Stack Allocation**: Best for simple, short-lived data due to its simplicity and speed.
- **Heap Allocation**: More suitable for larger, dynamic, or long-lived data, provided the memory is managed correctly.
