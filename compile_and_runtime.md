# Compile Time vs Runtime in C++

In C++, program execution involves two distinct phases: compile time and runtime. Understanding the difference between these phases is crucial for effective programming and debugging.

## Compile Time

Compile time refers to the phase when the source code is translated into machine code or an intermediate code by a compiler. This occurs before the program is actually run.

During compile time:
- The compiler checks for syntax errors
- It performs type checking
- It may apply certain optimizations

### Example of a Compile-Time Error

```cpp
int main() {
    int x = 5;
    int y = 0;
    int result = x / y;  // Compile-time error (division by zero)
    return 0;
}
```


