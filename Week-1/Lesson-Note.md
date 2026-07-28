
---

Week 1: C++ Foundations – Syntax, Variables, I/O & Operators

Duration Audience Goal
2.5 hours (with 10-min break) 17-year-old university student (absolute beginner) Write first program, master data types, user input, and build a simple calculator.

---

🎯 Learning Objectives

By the end of this session, the student will be able to:

· Set up a C++ compiler/IDE and run a "Hello World" program.
· Understand core C++ syntax: #include, main(), return 0, and semicolons.
· Declare and use variables of types: int, double, char, bool, and string.
· Take user input with cin and display output with cout.
· Use arithmetic (+, -, *, /, %) and logical (&&, ||, !) operators.
· Build a functional console calculator that handles basic math and division by zero.

---

⏱️ Session Flow & Timetable

Time Activity Key Focus
0:00 – 0:15 Introduction & Environment Setup Installing VS Code / g++, online compilers
0:15 – 0:40 First Program & Basic Syntax iostream, main(), cout, comments
0:40 – 1:10 Variables & Data Types int, double, char, bool, string
1:10 – 1:35 Input (cin) & Output (cout) Reading keyboard input, formatting output
1:35 – 1:45 ☕ Break (10 minutes)
1:45 – 2:10 Arithmetic & Logical Operators Integer division vs floating-point, operator precedence
2:10 – 2:30 Capstone Activity: Simple Calculator Combine everything into a working program
2:30 – 2:45 Q&A + Homework Assignment Review, discuss homework, share references

---

📚 Detailed Instructor Script & Live Code Demos

0:00 – 0:15 | Introduction & Setup

· What is C++? A fast, powerful language used for games, operating systems, and finance. It's an extension of C with object-oriented features.
· Your tools for today: We will use OnlineGDB (no install required) so we can start coding immediately. Later we will install VS Code + MinGW or Code::Blocks.
· How it works: Write code → Compiler translates to machine code → Run the executable.
· Command line basics (optional): g++ myprogram.cpp -o myprogram then ./myprogram.

---

0:15 – 0:40 | First Program & Basic Syntax

Code Example 1 – Hello World:

```cpp
// This is a single-line comment – compiler ignores it
#include <iostream>   // Include the standard input/output library
using namespace std;   // So we can type 'cout' instead of 'std::cout'

int main() {           // Every C++ program starts here
    cout << "Hello, World!" << endl;  // Print text to the console
    return 0;          // Return 0 to indicate successful execution
}
```

Key Syntax Rules:

· #include <iostream> – tells the compiler to add the I/O library.
· using namespace std; – saves typing std:: before cout and cin (good for small programs).
· int main() – the entry point. Every program must have exactly one main.
· cout << "text" – the << operator pushes text to the output stream.
· endl – moves to a new line (like pressing Enter).
· Every statement must end with a semicolon ;. Forgetting it is the #1 beginner mistake.

Exercise: Change the message to your name and run it again.

---

0:40 – 1:10 | Variables & Data Types

Data Type Cheat Sheet:

Type Description Example Size (approx)
int Whole numbers (no decimals) int age = 17; 4 bytes
double Decimal numbers double price = 19.99; 8 bytes
char Single character (single quotes) char grade = 'A'; 1 byte
bool True or false (1 or 0) bool isStudent = true; 1 byte
string Text (must include <string>) string name = "Alice"; Variable

Code Example 2 – Declaring and Printing Variables:

```cpp
#include <iostream>
#include <string>   // Required for the 'string' type
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
    cout << "Initial: " << initial << endl;
    cout << "Passed? " << passed << endl;  // prints 1 for true, 0 for false
    return 0;
}
```

Important Notes:

· string requires #include <string> (even though some compilers auto-include it, always add it).
· bool prints 1 for true and 0 for false. To print "true" or "false", add cout << boolalpha; later.
· Variable names must start with a letter or underscore, cannot contain spaces, and are case-sensitive (age ≠ Age).

Exercise: Create your own variables for your age, favorite number, and first initial. Print them in a sentence.

---

1:10 – 1:35 | Input (cin) & Output (cout)

· cout uses << (insertion operator) to send data to the screen.
· cin uses >> (extraction operator) to read data from the keyboard.

Code Example 3 – Taking User Input:

```cpp
#include <iostream>
using namespace std;

int main() {
    int number;
    cout << "Enter a whole number: ";
    cin >> number;                      // Wait for user to type a number and press Enter
    cout << "You entered: " << number << endl;
    return 0;
}
```

Pro Tip: cin stops reading at whitespace (space, tab, newline). For full names with spaces, we will use getline(cin, fullName) in Week 2.

Exercise: Write a program that asks for the user's name and age, then prints a greeting like:
"Hello John! You are 17 years old."

---

1:35 – 1:45 | ☕ Break

(10 minutes – stretch, grab water)

---

1:45 – 2:10 | Arithmetic & Logical Operators

Arithmetic Operators:

Operator Operation Example Result
+ Addition 10 + 3 13
- Subtraction 10 - 3 7
* Multiplication 10 * 3 30
/ Division 10 / 3 3 (integer division!)
% Modulus (remainder) 10 % 3 1

Critical Warning about Division:
In C++, 10 / 3 gives 3 because both are integers (truncates the decimal). To get 3.333, use 10.0 / 3 or 10 / 3.0.

Code Example 4 – Math Operators:

```cpp
int a = 10, b = 3;
cout << "a + b = " << a + b << endl;   // 13
cout << "a - b = " << a - b << endl;   // 7
cout << "a * b = " << a * b << endl;   // 30
cout << "a / b = " << a / b << endl;   // 3 (integer division)
cout << "a % b = " << a % b << endl;   // 1 (remainder)

double c = 10.0, d = 3.0;
cout << "c / d = " << c / d << endl;   // 3.33333 (floating division)
```

Logical Operators:

Operator Name Example Result
&& AND (age > 13 && age < 20) true if both are true
`  ` OR
! NOT !(passed) true if passed is false

Code Example 5 – Logical Checks:

```cpp
bool isTeen = (age >= 13 && age <= 19);
bool canVote = (age >= 18);
cout << "Is teen? " << isTeen << endl;
cout << "Can vote? " << canVote << endl;
```

Exercise: Write a small program that declares two numbers and prints the result of +, -, *, /, and %.

---

2:10 – 2:30 | Capstone Activity: Simple Calculator

Combine everything to build a menu-driven calculator that takes two numbers and an operator.

Code Example 6 – Full Calculator (Live Demo):

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
            cout << "Error: Division by zero is not allowed!" << endl;
            return 1;  // Exit with error code
        }
        result = num1 / num2;
    } else {
        cout << "Invalid operator! Please use +, -, *, or /." << endl;
        return 1;
    }
    
    cout << num1 << " " << op << " " << num2 << " = " << result << endl;
    return 0;
}
```

Walkthrough:

· We use double so the calculator works with decimals.
· The if / else if chain checks which operator was entered.
· We handle division by zero gracefully with a specific error message.
· Invalid operators are caught and reported.

---

2:30 – 2:45 | Q&A & Homework

Review Questions:

· What does #include <iostream> do?
· Why does 10 / 3 give 3 and not 3.333?
· How do you read a number from the user?

Homework (submit .cpp files next session):

1. Modify the calculator to also support modulus (%). Hint: % only works on integers, so cast your inputs to int or use int variables.
2. Area of a circle: Write a program that asks the user for the radius (as a double) and prints the area using area = 3.14159 * radius * radius.
3. Bonus challenge: Write a program that converts Celsius to Fahrenheit: F = (C * 9/5) + 32. Test with 0°C → 32°F.

---

📖 References & Further Learning

Resource Type Link
W3Schools C++ Tutorial Best for quick syntax reference https://www.w3schools.com/cpp/
Programming with Mosh (YouTube) Excellent beginner walkthrough https://youtu.be/vLnPwxZdW4Y
freeCodeCamp C++ Course (YouTube) Full 4-hour free course https://youtu.be/vLnPwxZdW4Y (search for updated)
cppreference.com Official C++ documentation https://en.cppreference.com/
OnlineGDB Compiler Write & run C++ in your browser https://www.onlinegdb.com/online_c++_compiler

---

🧠 Instructor Notes

· Teaching style: W3Schools-inspired – show code first, explain line-by-line, then let the student modify it.
· Common pitfalls to watch for: Missing semicolons, forgetting #include <string>, and integer division surprises.
· Engagement: Ask the student to predict the output before running every code block.

---

Next week: We will dive into Control Flow – if/else statements, switch, and loops (for, while) to make our programs think and repeat.

---
