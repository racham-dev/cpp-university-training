
# Week 1: C++ Foundations – Syntax, Variables, I/O & Operators

| **Duration** | **Audience** | **Goal** |
| :--- | :--- | :--- |
| 2.5 hours (with 10-min break) | 17-year-old university student (absolute beginner) | Write first program, master data types, user input, and build a simple calculator. |

---

## 🎯 Learning Objectives

- Set up a C++ compiler/IDE and run a "Hello World" program.
- Understand core syntax: `#include`, `main()`, `return 0`, semicolons, and comments.
- Declare variables using `int`, `double`, `char`, `bool`, and `string`.
- Read keyboard input with `cin` and display output with `cout`.
- Use arithmetic (`+`, `-`, `*`, `/`, `%`) and logical (`&&`, `||`, `!`) operators.
- Build a functional console calculator with error handling.

---

## ⏱️ Session Flow & Timetable

| Time | Activity | Key Focus |
| :--- | :--- | :--- |
| 0:00 – 0:15 | Introduction & Setup | Online compiler / VS Code + g++ setup |
| 0:15 – 0:40 | First Program & Basic Syntax | `iostream`, `main()`, `cout`, comments |
| 0:40 – 1:10 | Variables & Data Types | `int`, `double`, `char`, `bool`, `string` |
| 1:10 – 1:35 | Input (`cin`) & Output (`cout`) | Reading user input, formatting strings |
| 1:35 – 1:45 | **☕ Break** | (10 minutes) |
| 1:45 – 2:10 | Arithmetic & Logical Operators | Integer vs floating division, operator precedence |
| 2:10 – 2:30 | Capstone: Simple Calculator | Combine everything into one working program |
| 2:30 – 2:45 | Q&A & Homework | Review concepts and assign tasks |

---

## 📚 Detailed Lesson Script

### 0:15 – 0:40 | First Program & Syntax

**Code:**
```cpp
// Single-line comment
#include <iostream>
using namespace std;

int main() {
    cout << "Hello, World!" << endl;
    return 0;
}
```

Key Points:

· #include <iostream> – adds input/output library.
· using namespace std; – allows cout instead of std::cout.
· int main() – program entry point. Must return an integer.
· cout << – prints to screen. endl inserts a new line.
· Every line ends with ; – missing it causes errors.

Exercise: Modify the message to print your name.

---

0:40 – 1:10 | Variables & Data Types

Data Type Quick Reference:

Type Example Notes
int int age = 17; Whole numbers
double double price = 19.99; Decimal numbers
char char grade = 'A'; Single character (single quotes)
bool bool isStudent = true; true (1) or false (0)
string string name = "Alice"; Requires #include <string>

Code:

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    int age = 17;
    double price = 29.95;
    char initial = 'J';
    bool passed = true;
    string name = "John";

    cout << "Name: " << name << endl;
    cout << "Age: " << age << endl;
    cout << "Price: $" << price << endl;
    cout << "Passed? " << passed << endl; // prints 1 for true
    return 0;
}
```

Rules:

· Variables must be declared before use.
· string requires #include <string>.
· bool prints 1 or 0 (we'll learn boolalpha later).

Exercise: Declare variables for your age, favorite number, and initial. Print them in one sentence.

---

1:10 – 1:35 | Input (cin) & Output (cout)

· cin >> reads user input from the keyboard.
· cout << displays output to the screen.

Code:

```cpp
#include <iostream>
using namespace std;

int main() {
    int number;
    cout << "Enter a number: ";
    cin >> number;
    cout << "You entered: " << number << endl;
    return 0;
}
```

Note: cin stops reading at spaces. For full names, we will use getline() in Week 2.

Exercise: Ask for the user's name and age, then print: "Hello [Name]! You are [Age] years old."

---

1:45 – 2:10 | Arithmetic & Logical Operators

Arithmetic Operators:

Operator Operation Example Result
+ Addition 10 + 3 13
- Subtraction 10 - 3 7
* Multiplication 10 * 3 30
/ Division 10 / 3 3 (integer truncation!)
% Modulus (remainder) 10 % 3 1

Critical Note: 10 / 3 returns 3 because both are int. Use 10.0 / 3 for 3.333.

Code:

```cpp
int a = 10, b = 3;
cout << "a / b = " << a / b << endl;   // 3
double c = 10.0, d = 3.0;
cout << "c / d = " << c / d << endl;   // 3.33333
```

Logical Operators:

Operator Name Example
&& AND (age > 13 && age < 20)
`  `
! NOT !(passed)

Exercise: Write a program to check if a given number is even (use % 2 == 0).

---

2:10 – 2:30 | Capstone Project: Simple Calculator

Code (Live Demo):

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

Key Logic:

· Use double to support decimals.
· if/else if chain checks the operator.
· Division by zero is handled with an explicit error message.

---

📝 Homework (Submit .cpp files next session)

1. Extend the calculator – add support for modulus (%). Hint: cast inputs to int or use int variables.
2. Circle area program – ask for radius (double) and print Area = 3.14159 * radius * radius.
3. Bonus: Temperature converter – convert Celsius to Fahrenheit: F = (C * 9/5) + 32. Test with 0°C → 32°F.

---

📖 References & Further Learning

Resource Type Link
W3Schools C++ Tutorial Quick reference https://www.w3schools.com/cpp/
Programming with Mosh (YouTube) Beginner walkthrough https://youtu.be/vLnPwxZdW4Y
freeCodeCamp C++ Course (YouTube) Full 4-hour course https://youtu.be/vLnPwxZdW4Y
cppreference.com Official documentation https://en.cppreference.com/
OnlineGDB Run C++ in browser https://www.onlinegdb.com/online_c++_compiler

---

🧠 Instructor Notes

· Style: Show code first, explain line-by-line, then let the student modify it.
· Common pitfalls: Missing ;, forgetting #include <string>, and integer division surprises.
· Engagement: Ask the student to predict output before running each block.

---

Next Week: Control Flow – if/else, switch, and loops (for, while).

```

---