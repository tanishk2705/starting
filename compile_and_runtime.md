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

## Runtime

Runtime refers to the phase when the compiled program is actually executed on a computer.

During runtime:
- The program is loaded into memory
- Instructions are executed sequentially
- Dynamic behaviors of the program occur

### Example of a RunTime Error

```py
def divide(x, y):
    return x / y

a = 10
b = int(input("Enter a number: "))
result = divide(a, b)
print(result)
```

## Key Differences Between Compile Time and Runtime

1. **Error Occurrence and Detection**:
   - Compile-time errors prevent the program from running at all.
   - Runtime errors occur during program execution.

2. **Speed and Efficiency**:
   - Compile-time checks are generally faster and can catch many errors before the program runs.
   - Runtime checks occur during execution, which can impact performance.

3. **Types of Issues Detected**:
   - Compile-time checks can detect syntax errors, type mismatches, and other static issues.
   - Some issues, especially those involving user input or dynamic behavior, can only be detected at runtime.

These differences highlight the importance of both compile-time and runtime checks in developing robust and efficient C++ programs.
