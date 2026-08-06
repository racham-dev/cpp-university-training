# 📝 Assignment: Collect and Display User Data (Using `cin` and `>>`)

**Task:** Write a C++ program that asks the user for the following details, stores them in variables, and then displays them back neatly.

| **Data Field** | **Data Type to Use** | **Why?** |
| :--- | :--- | :--- |
| 1. Full Name | `string` | Contains spaces (e.g., "Victor James") |
| 2. Phone Number | `string` | To preserve leading zeros (e.g., "08012345678") |
| 3. BVN | `string` | 11 digits – storing as a string prevents rounding errors |
| 4. Salary Payment | `double` | Can contain decimals (e.g., 45000.50) |
| 5. Gender | `string` | Text input (e.g., "Male" / "Female") |

---

## ⚠️ The Critical Trap: The "Full Name" Problem

As we learned earlier, `cin >>` **stops reading** when it sees a space. 
If Victor types `Victor James`, `cin >> fullName;` will only store `Victor`. 

**Solution:** To read a full name, we must use **`getline(cin, fullName);`** instead of `cin >>`. This special command reads everything until the user presses **Enter**, including spaces.

---

## 💻 The Complete C++ Code (Copy and Run This)

```cpp
#include <iostream>
#include <string>  // Required for using 'string'
using namespace std;

int main() {
    // 1. Declare variables to hold the user data
    string fullName, phoneNumber, bvn, gender;
    double salary;

    // 2. Collect each piece of data from the user
    // NOTE: We use getline for Full Name because it has spaces.
    cout << "Enter your Full Name: ";
    getline(cin, fullName);  // Reads the ENTIRE line, including spaces

    cout << "Enter your Phone Number: ";
    cin >> phoneNumber;

    cout << "Enter your BVN: ";
    cin >> bvn;

    cout << "Enter your Salary payment: ";
    cin >> salary;

    cout << "Enter your Gender (Male/Female): ";
    cin >> gender;

    // 3. Display the collected data back to the user
    cout << "\n==========================================\n";
    cout << "        USER DATA CONFIRMATION            \n";
    cout << "==========================================\n";
    cout << "Full Name      : " << fullName << endl;
    cout << "Phone Number   : " << phoneNumber << endl;
    cout << "BVN            : " << bvn << endl;
    cout << "Salary Payment : $" << salary << endl;
    cout << "Gender         : " << gender << endl;
    cout << "==========================================\n";

    return 0;
}