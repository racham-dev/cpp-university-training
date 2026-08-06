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
}```

---


#🧠 Step‑by‑Step Explanation (What happens at each line)

Line What it does
#include <string> Allows us to use the string data type for text.
string fullName, ... Creates boxes (variables) to hold the data.
getline(cin, fullName); Reads the entire line of text (including spaces) and stores it in fullName.
cin >> phoneNumber; Reads a single word (no spaces) into phoneNumber.
cin >> salary; Reads a number (like 50000.75) into the salary variable.
cout << ... Prints the stored values to the screen in a clean table format.

---

🎯 The "Twist" Victor Needs to Know

Because we used getline() first, this program works perfectly. However, if you ever put getline() after a cin >>, you will run into a sneaky bug called the "leftover newline".

For this assignment, the order above is correct and works flawlessly.

---

🧪 Sample Run (What Victor should see in his terminal)

```
Enter your Full Name: Victor James
Enter your Phone Number: 08012345678
Enter your BVN: 12345678901
Enter your Salary payment: 75000.50
Enter your Gender (Male/Female): Male

==========================================
        USER DATA CONFIRMATION            
==========================================
Full Name      : Victor James
Phone Number   : 08012345678
BVN            : 12345678901
Salary Payment : $75000.5
Gender         : Male
==========================================
```

---

✅ What Victor needs to do right now (Before 3pm)

1. Open VS Code (or OnlineGDB) and create a new file called user_data.cpp.
2. Copy and paste the code above into the file.
3. Compile and run it (g++ user_data.cpp -o user_data then .\user_data.exe).
4. Test it by typing different values (try a name with 3 words, like "John Paul Smith").
5. Observe how getline() perfectly catches the full name, while cin >> correctly catches the other fields.

---

🧠 Bonus Challenge (If he finishes early)

Modify the program so that:

· It asks for Age as well (use int).
· It calculates Yearly Salary (Salary * 12) and displays it under the salary line.

---