
# Week 1: Variables and Data Types – Storing Values in C++

| **Topic** | **Purpose** | **Key Concept** |
| :--- | :--- | :--- |
| Variables & Data Types | Store and manipulate data in memory | Every variable has a type and a value |

---

## 🧠 What is a Variable?

A **variable** is a named memory location that holds a value. You can think of it as a box with a label, where you can store data and change it later.

**Why use variables?**  
- To store user input.  
- To keep intermediate results of calculations.  
- To reuse data multiple times in your program.

**Syntax to declare a variable:**
```cpp
data_type variable_name;
```

Example:

```cpp
int age;         // declares an integer variable named 'age'
double price;    // declares a double variable named 'price'
```

---

📦 Data Types – What Kinds of Data Can We Store?

C++ provides several basic data types. Each type defines:

· The kind of data it can hold.
· The amount of memory it uses.
· The range of possible values.

Quick Reference Table

Type Keyword Size (approx) Range / Precision Example
Whole number int 4 bytes -2,147,483,648 to 2,147,483,647 int count = 10;
Decimal number (double precision) double 8 bytes ~15–16 decimal digits double pi = 3.14159;
Decimal number (single precision) float 4 bytes ~6–7 decimal digits float rate = 1.25f;
Single character char 1 byte -128 to 127 (ASCII) char grade = 'A';
True / False bool 1 byte true (1) or false (0) bool isPassed = true;
Text string string Variable Dynamic length string name = "Victor";

---

📝 Declaring and Initializing Variables

1. Declaration Only

```cpp
int age;
double salary;
char initial;
bool isStudent;
string name;
```

2. Declaration with Initialization (giving a value immediately)

```cpp
int age = 17;
double salary = 45000.50;
char initial = 'V';
bool isStudent = true;
string name = "Victor James";
```

3. Assignment After Declaration

```cpp
int age;
age = 17;   // assign a value later
```

4. Multiple Declarations on One Line

```cpp
int a = 5, b = 10, c = 15;
double x, y, z;
```

---

🔢 Detailed Explanation of Each Type

1. int – Integer (whole numbers)

· Used for counting, indices, ages, quantities.
· Cannot store decimals.
· Example:
  ```cpp
  int quantity = 3;
  int year = 2026;
  ```

2. double – Double‑precision floating‑point (decimals)

· Used for measurements, money, scientific calculations.
· More precise than float – use this by default for decimals.
· Example:
  ```cpp
  double price = 29.95;
  double radius = 5.25;
  ```

3. float – Single‑precision floating‑point

· Similar to double but uses less memory and less precision.
· Not commonly used in beginner programs – we stick with double.
· Example:
  ```cpp
  float temperature = 36.6f;  // note the 'f' suffix
  ```

4. char – Character

· Stores a single ASCII character.
· Must be enclosed in single quotes.
· Example:
  ```cpp
  char grade = 'A';
  char symbol = '$';
  ```

5. bool – Boolean

· Stores true or false (internally 1 or 0).
· Used for conditions and flags.
· Example:
  ```cpp
  bool isAdult = true;
  bool hasPermission = false;
  ```

6. string – Text

· Stores a sequence of characters (words, sentences).
· Requires #include <string> at the top.
· Must be enclosed in double quotes.
· Example:
  ```cpp
  string firstName = "Victor";
  string fullName = "Victor James";
  ```

---

🧠 Rules for Naming Variables

· Must start with a letter or underscore (_).
· Can contain letters, digits, and underscores.
· Cannot contain spaces or special characters (except _).
· Case‑sensitive (age and Age are different).
· Cannot use C++ keywords (like int, return, if).

Good names: age, totalCost, _temp, studentCount
Bad names: 2ndNumber (starts with digit), total cost (space), int (keyword)

---

💾 Storing Values – How Variables Hold Data

When you assign a value to a variable, C++ stores that value in memory at the variable’s address.
You can later change the value by assigning a new one.

```cpp
int score = 85;   // score holds 85
score = 92;       // now score holds 92 (the old value is overwritten)
```

Reading from the user with cin stores the typed value into the variable:

```cpp
int age;
cout << "Enter your age: ";
cin >> age;       // the typed value goes into age
```

Displaying the value with cout:

```cpp
cout << "Age: " << age << endl;
```

---

📘 Constants – Values That Never Change

If you have a value that should not change (like pi), declare it with const:

```cpp
const double PI = 3.14159;
// PI = 3.14;   // Error! Cannot change a constant
```

---

🧪 In‑Class Exercises (Do these in the session)

1. Declare variables for your age (int), height in meters (double), first initial (char), and whether you are a student (bool). Print them all.
2. Ask the user for their favourite number (integer) and their favourite decimal number (double). Store them and print both.
3. Create a program that asks for the user's full name (use string) and age, then prints a greeting like:
      "Hello Victor, you are 17 years old."
4. Swap two numbers – declare two integer variables, assign them values, then swap their contents using a temporary variable. Print before and after.
5. Find the sum and average – ask the user for three decimal numbers, store them in double variables, and print their sum and average.

---

🎯 Assignment (Submit to your repo)

Complete these tasks and push your .cpp files to the assignment repository.

1. Circle area – ask the user for the radius (double) and print the area using area = 3.14159 * radius * radius.
2. Simple interest calculator – ask for principal (double), rate (double, in percent), and time (double, in years). Calculate and print the interest: interest = principal * (rate / 100) * time.
3. BMI calculator – ask for weight (kg) and height (m). Calculate BMI = weight / (height * height). Print the BMI.
4. Challenge: Ask for a full name, age, and salary. Print a receipt‑style summary.

---

📖 References

· W3Schools – C++ Variables
· W3Schools – C++ Data Types
· Programiz – C++ Variables and Literals

---

🧠 Instructor Notes

· Emphasise that double is preferred over float for beginners.
· Remind students about #include <string> when using string.
· Show that char uses single quotes; string uses double quotes.
· Practice with cin and cout multiple times to build confidence.

---
