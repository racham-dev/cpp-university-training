
# Week 1: C++ Foundations – Variables, I/O, and Arithmetic

| **Duration** | **Audience** | **Goal** |
| :--- | :--- | :--- |
| 2.5 hours | University beginner (17yo) | Write first programs, use variables, input/output, and build a simple calculator. |

---

## 🎯 Learning Objectives

By the end of this session, the student will be able to:

- Write, compile, and run a “Hello World” program.
- Understand C++ syntax: `#include`, `main()`, `return 0`, semicolons, and comments.
- Declare and use variables of types `int`, `double`, `char`, and `bool`.
- Read keyboard input with `cin` and print output with `cout`.
- Use arithmetic operators (`+`, `-`, `*`, `/`, `%`).
- Build a simple console calculator.

---

## 📚 Topic Breakdown

### 1. Hello World – Your First Program

**Code:**
```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Hello, World!" << endl;
    return 0;
}
```

#Explanation:

· #include <iostream> – adds the input/output library so you can use cout.
· using namespace std; – allows you to write cout instead of std::cout.
· int main() – the program starts here. It returns an integer to the operating system.
· cout << – prints text to the screen. endl moves to a new line.
· return 0; – signals successful execution.

In‑Class Exercise:
Modify the program to print your name and age (e.g., “My name is Victor, I am 17 years old.”).

---

#2. Variables – Storing Data

Variables are named memory locations that hold values. Each variable has a data type that determines what kind of data it can store and how much memory it uses.

#Data Type Quick Reference

Type Keyword Example Size (approx)
Whole number int int age = 17; 4 bytes
Decimal number double double price = 19.99; 8 bytes
Single character char char grade = 'A'; 1 byte
True/False bool bool isStudent = true; 1 byte

#Rules for naming variables:

· Must start with a letter or underscore (_).
· Can contain letters, digits, and underscores.
· Case‑sensitive (age and Age are different).
· Cannot be a C++ keyword (like int, return).

#Example:

```cpp
int age = 17;
double price = 29.95;
char initial = 'J';
bool passed = true;
```

Important: char uses single quotes ('A'); strings use double quotes ("Hello").

In‑Class Exercise:
Declare variables for your age (int), your height in meters (double), your first initial (char), and whether you are a student (bool). Print them all.

---

#3. Input and Output – cin and cout

· cout << (output) – sends data to the screen.
· cin >> (input) – reads data from the keyboard and stores it in a variable.

Example:

```cpp
int number;
cout << "Enter a number: ";
cin >> number;
cout << "You entered: " << number << endl;
```

#Reading multiple values:

```cpp
int a, b;
cout << "Enter two numbers: ";
cin >> a >> b;   // user types "10 20"
cout << "Sum = " << a + b << endl;
```

Important: cin >> stops reading at spaces. To read a full name with spaces, use getline(cin, fullName); (we will cover this later).

In‑Class Exercise:
Write a program that asks for your first name and age, then prints a greeting like:
"Hello Victor, you are 17 years old."

---

#4. Arithmetic Operators

Operator Name Example Result (a=10, b=3)
+ Addition a + b 13
- Subtraction a - b 7
* Multiplication a * b 30
/ Division a / b 3 (integer division!)
% Modulus (remainder) a % b 1

Critical Trap – Integer Division:
When you divide two integers, C++ throws away the decimal part.
10 / 3 gives 3, not 3.333.
To get a decimal, make at least one operand a double (e.g., 10.0 / 3 or 10 / 3.0).

Example:

```cpp
int a = 10, b = 3;
cout << a / b << endl;        // 3
cout << 10.0 / 3 << endl;     // 3.33333
```

In‑Class Exercise:
Write a program that asks for two integers, then prints their sum, difference, product, quotient (as a decimal), and remainder.

---

#5. Building the Simple Console Calculator

Combine everything you’ve learned to make a calculator that takes two numbers and an operator, then prints the result.

Code:

```cpp
#include <iostream>
using namespace std;

int main() {
    double num1, num2;
    char op;

    cout << "Enter first number: ";
    cin >> num1;
    cout << "Enter operator (+, -, *, /): ";
    cin >> op;
    cout << "Enter second number: ";
    cin >> num2;

    double result;
    if (op == '+') {
        result = num1 + num2;
    } else if (op == '-') {
        result = num1 - num2;
    } else if (op == '*') {
        result = num1 * num2;
    } else if (op == '/') {
        if (num2 == 0) {
            cout << "Error: Division by zero!" << endl;
            return 1;
        }
        result = num1 / num2;
    } else {
        cout << "Invalid operator!" << endl;
        return 1;
    }

    cout << num1 << " " << op << " " << num2 << " = " << result << endl;
    return 0;
}
```

Explanation:

· We use double so the calculator works with decimals.
· The if/else if chain checks which operator was entered.
· We handle division by zero to avoid a crash.
· Invalid operators are reported.

In‑Class Exercise:
Extend the calculator to also support modulus (%). Remember that % works only with integers – you can cast the inputs to int or use integer variables.

---

#🎯 Assignment: Submit to Your Repo

Now it’s time to practise. Complete the following tasks and push your code to the assignment repository (your instructor will share the link).

1. Basic calculator – as shown above, but also include modulus (%).
2. Area of a circle – ask the user for the radius (double) and print the area: area = 3.14159 * radius * radius.
3. Temperature converter – ask for Celsius and print Fahrenheit: F = (C * 9/5) + 32.

Bonus challenge: Write a program that asks for the user’s full name (with spaces), age, and monthly salary, then prints a summary.

Submit your .cpp files – one per task – in your repo by the next session.

---

#📖 References & Further Learning

Resource Type Link
W3Schools C++ Tutorial Quick reference https://www.w3schools.com/cpp/
cppreference.com Official documentation https://en.cppreference.com/
OnlineGDB (run code in browser) Online compiler https://www.onlinegdb.com/online_c++_compiler

---

#🧠 Instructor Notes

· Teaching style: Show each code snippet, explain line‑by‑line, then let the student modify it.
· Common pitfalls: Missing semicolons, forgetting #include <iostream>, integer division surprises.
· Engagement: Ask the student to predict the output before running each example.
· Next week: Control flow – if/else, switch, and loops (for, while).

---

