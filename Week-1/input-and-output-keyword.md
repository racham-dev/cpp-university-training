
# Week 1: Input and Output – Using `cin` and `cout` in C++

| **Topic** | **Purpose** | **Key Concept** |
| :--- | :--- | :--- |
| `cout` (Output) | Display text and variable values to the screen | Insertion operator `<<` |
| `cin` (Input) | Read data typed by the user from the keyboard | Extraction operator `>>` |

---

## 🖥️ #What is `cout`?

`cout` stands for **Character Output**. It is the standard output stream in C++ that sends data to the display (usually the terminal or console).

**Basic syntax:**
```cpp
cout << data << endl;
```

· The insertion operator << sends the data to cout.
· endl moves the cursor to the next line (and flushes the output buffer).
· You can chain multiple items with <<.

Examples

```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Hello, world!" << endl;
    cout << "The answer is " << 42 << endl;
    cout << "Pi is approximately " << 3.14159 << endl;
    return 0;
}
```

Output:

```
Hello, world!
The answer is 42
Pi is approximately 3.14159
```

Formatting Tips

· Use \n instead of endl if you don't need to flush (faster for large output).
  ```cpp
  cout << "Line 1\nLine 2\n";
  ```
· To print special characters (like quotes or backslashes), use escape sequences:
  Escape Meaning
  \" Double quote
  \' Single quote
  \\ Backslash
  \n Newline
  \t Tab
  · Example: cout << "She said \"Hello!\" \\n";

---

##⌨️ #What is cin?

cin stands for Character Input. It is the standard input stream that reads data from the keyboard.

Basic syntax:

```cpp
cin >> variable;
```

· The extraction operator >> reads the input and stores it in variable.
· It skips leading whitespace (spaces, tabs, newlines) and stops at the next whitespace.

Reading a Single Value

```cpp
int age;
cout << "Enter your age: ";
cin >> age;
cout << "You are " << age << " years old." << endl;
```

Reading Multiple Values

You can chain >> to read several values in one statement.

```cpp
int a, b;
cout << "Enter two numbers: ";
cin >> a >> b;   // User types "10 20" or "10\n20"
cout << "Sum = " << a + b << endl;
```

---

##⚠️ #The Whitespace Trap (Why cin >> Fails for Full Names)

cin >> stops reading when it encounters a space, tab, or newline. So if you try:

```cpp
string fullName;
cout << "Enter your full name: ";
cin >> fullName;   // User types "Victor James"
cout << fullName;  // Outputs only "Victor"
```

Solution: Use getline(cin, variable) to read an entire line, including spaces.

```cpp
string fullName;
cout << "Enter your full name: ";
getline(cin, fullName);   // Reads everything until Enter
cout << "Hello, " << fullName << endl;
```

Important – Mixing cin >> and getline

If you use cin >> before getline, a leftover newline (\n) remains in the input buffer, causing getline to read an empty line. Always use cin.ignore() after cin >> if you plan to use getline afterwards.

Example:

```cpp
int age;
string name;
cout << "Enter age: ";
cin >> age;
cin.ignore();   // Clear the leftover newline
cout << "Enter full name: ";
getline(cin, name);
```

---

##📥 #Input Type Mismatch

If the user enters a value that doesn't match the variable type (e.g., type "abc" when expecting an int), the input fails. The variable remains unchanged and cin goes into an error state. We'll learn to handle this later.

For now: Always assume the user provides correct input.

---

##💡 #Summary Table

Operator Purpose Example
cout << Output to screen cout << "Hello";
cin >> Input from keyboard cin >> number;
endl Newline + flush cout << "Hi" << endl;
\n Newline only (faster) cout << "Hi\n";
getline(cin, string) Read full line with spaces getline(cin, fullName);

---

##🧪 #In‑Class Exercises

1. Greeting program: Ask the user for their first name (without spaces) and age, then print:
      "Hello [name], you are [age] years old."
2. Sum of two numbers: Ask for two integers, read them with a single cin, and print their sum.
3. Full name with getline: Ask for the user's full name using getline() and print a welcome message.
4. Multiple inputs: Ask for three decimal numbers (price, quantity, discount) and calculate the total after discount. Use a single cin for all three.

---

##🎯 #Assignment (Push to your repo)

1. Simple calculator: Ask the user for two numbers and an operator (+, -, *, /). Perform the operation and print the result. (Use double for numbers.)
2. Rectangle area with getline: Ask the user for their full name, then ask for length and width (double). Calculate the area and print a message like:
      "Victor, the area of your rectangle is 25.5"
3. Temperature converter: Ask the user for a temperature in Celsius (double) and convert it to Fahrenheit using F = (C * 9/5) + 32. Print the result.

---

##📖 #References

· W3Schools – C++ Output
· W3Schools – C++ Input
· Programiz – C++ Basic Input/Output

---

##🧠 #Instructor Notes

· Emphasise that cout uses << and cin uses >> – the arrows point in the direction of data flow.
· Show how endl and \n differ; \n is more efficient but endl is useful for debugging.
· Stress that getline is needed for strings with spaces, and demonstrate the cin.ignore() trick.
· Let students practise typing input and observe the output.

---

