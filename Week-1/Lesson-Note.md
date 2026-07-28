
---

# Week 1: C++ Foundations – Syntax, Variables, I/O & Operators

Duration: 2.5 hours (10‑min break halfway)
Target: Absolute beginner – no prior coding experience required.
Goal: Write your first C++ program, understand data types, take user input, and build a simple calculator.

---

🎯 Learning Objectives

By the end of this session, the student will be able to:

1. Set up a C++ development environment (IDE or compiler).
2. Write, compile, and run a “Hello World” program.
3. Understand C++ syntax: #include, main(), return 0, semicolons.
4. Declare and use variables of basic data types (int, double, char, bool, string).
5. Read input from the keyboard using cin and output to the screen using cout.
6. Perform arithmetic (+, -, *, /, %) and logical (&&, ||, !) operations.
7. Build a simple calculator that adds, subtracts, multiplies, or divides two numbers.

---

📚 Topic Breakdown & Instructor Script

0:00 – 0:15 | Introduction & Setup (15 mins)

· What is C++? A powerful, general‑purpose language used in game engines, operating systems, and high‑performance applications.
· Your tools: We’ll use VS Code + MinGW (Windows) or built‑in g++ (macOS/Linux). Alternatively, use Code::Blocks or an online compiler like OnlineGDB to start immediately.
· Compilation: Write code → compile (g++ myprogram.cpp -o myprogram) → run (./myprogram or myprogram.exe).

---

0:15 – 0:40 | First Program & Basic Syntax (25 mins)

Code:

```cpp
// This is a comment – ignored by the compiler
#include <iostream>   // Input/output library
using namespace std;   // So we can write cout instead of std::cout

int main() {           // Program starts here
    cout << "Hello, World!" << endl;  // Print to screen
    return 0;          // Tell OS the program ended successfully
}
```

Key concepts:

· #include <iostream> – includes the standard I/O library.
· using namespace std; – avoids typing std:: every time (explain later that it's okay for small programs).
· int main() – every C++ program needs a main function. The int means it returns an integer to the OS.
· cout (character output) prints text. endl adds a new line.
· Statements end with a semicolon ;.
· Comments: // for single‑line, /* ... */ for multi‑line.

Exercise: Change the message and run again.

---

0:40 – 1:10 | Variables & Data Types (30 mins)

Data types:

Type Description Example
int Whole numbers (no decimals) int age = 17;
double Decimal numbers double price = 19.99;
char Single character (in single quotes) char grade = 'A';
bool True/false (1 or 0) bool isStudent = true;
string Text (must include <string>) string name = "Alice";

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
    cout << "Initial: " << initial << endl;
    cout << "Passed? " << passed << endl;  // prints 1 for true
    return 0;
}
```

Important:

· Variables must be declared before use.
· string requires #include <string>.
· bool outputs 1 (true) or 0 (false). To print “true”/“false”, use boolalpha – we’ll cover later.

Exercise: Declare your own variables for your age, favourite number, and a character, then print them.

---

1:10 – 1:35 | Input & Output – cin & cout (25 mins)

· cout (character output) uses << (insertion operator).
· cin (character input) uses >> (extraction operator).
· Example:

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

Note: cin automatically handles whitespace for numbers and strings (but for strings with spaces, you need getline – we’ll cover later).

Exercise: Ask the user for their name and age, then print a greeting.

---

1:35 – 1:45 | ☕ Break (10 mins)

---

1:45 – 2:10 | Arithmetic & Logical Operators (25 mins)

Arithmetic operators:

Operator Meaning Example
+ Addition a + b
- Subtraction a - b
* Multiplication a * b
/ Division a / b (integer division for ints!)
% Modulus (remainder) a % b

Code:

```cpp
int a = 10, b = 3;
cout << "a + b = " << a + b << endl;   // 13
cout << "a - b = " << a - b << endl;   // 7
cout << "a * b = " << a * b << endl;   // 30
cout << "a / b = " << a / b << endl;   // 3 (integer division)
cout << "a % b = " << a % b << endl;   // 1 (remainder)
```

Important:

· Integer division truncates decimals. To get a decimal result, use double for at least one operand.
· Example: 10 / 3 = 3, but 10.0 / 3 = 3.333...

Logical operators:

Operator Meaning Example
&& AND (both true) (age > 18 && age < 30)
`  `
! NOT (inverts) !(passed)

Code:

```cpp
bool isTeen = (age >= 13 && age <= 19);
bool isAdult = (age >= 18);
cout << "Is teen? " << isTeen << endl;
cout << "Is adult? " << isAdult << endl;
```

---

2:10 – 2:30 | Capstone Activity: Simple Calculator (20 mins)

Now we combine everything into a calculator that asks the user for two numbers and an operator, then outputs the result.

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

Walkthrough:

· We use double to handle decimals.
· The if/else if chain checks the operator.
· Division by zero is handled gracefully.
· The result is printed.

Try it: Run the calculator with different numbers and operators.

---

2:30 – 2:45 | Q&A & Homework (15 mins)

Homework:

1. Modify the calculator to support modulus (%) – remember that % works only with integers, so you’ll need to cast or use int.
2. Write a program that asks the user for the radius of a circle and prints the area (area = 3.14159 * radius * radius). Use double.
3. Extra challenge: Write a program that converts Celsius to Fahrenheit: F = (C * 9/5) + 32.

Submission: Share your .cpp files via email or push to your own GitHub repo.

---

📖 References & Further Learning

· W3Schools C++ Tutorial – https://www.w3schools.com/cpp/ (excellent for quick reference)
· YouTube – Programming with Mosh – “C++ Tutorial for Beginners” (very clear) – https://youtu.be/vLnPwxZdW4Y
· YouTube – freeCodeCamp – “C++ Full Course for Beginners” – https://youtu.be/vLnPwxZdW4Y (or search for updated ones)
· cppreference.com – official C++ documentation – https://en.cppreference.com/
· Online Compiler – https://www.onlinegdb.com/online_c++_compiler – to test code without local setup.

---

🧠 Instructor Notes

· Keep it interactive: Ask the student to predict what each line does before you run it.
· Common pitfalls: Forgetting semicolons, missing #include <string> for strings, mixing integer division.
· Grading: The calculator homework is the main deliverable – check for correct logic and error handling.

---