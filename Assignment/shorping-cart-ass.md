Here’s a real‑life assignment on variables, cin, cout, and arithmetic – designed as a shopping cart calculator.
It includes both whole numbers (quantity) and decimal numbers (price), and guides the student through collecting input, storing it, calculating a total, and displaying the result.

Copy this entire Markdown into a file (e.g., assignment_shopping_cart.md) and push it to your GitHub repo.

---

```markdown
# 🛒 Assignment: Shopping Cart Total Calculator

**Goal:** Write a C++ program that asks the user for the **price** of an item (decimal) and the **quantity** (whole number), then calculates and displays the **total cost**.

This assignment will help you practise:

- Using `double` for decimal numbers (price)
- Using `int` for whole numbers (quantity)
- Using `cin` to read user input
- Storing input in variables
- Performing arithmetic with mixed types
- Displaying results with `cout`

---

## 📖 Scenario – The Shopping Cart

Imagine you are building a simple checkout system for an online store.  
When a customer buys an item, they enter:

- The **price** of one unit (e.g., $19.99)
- The **quantity** they want to buy (e.g., 3)

The system must calculate the **total cost** (price × quantity) and display it to the customer.

---

## 📐 Data Types to Use

| Data | Type | Why? |
| :--- | :--- | :--- |
| **Price** (per item) | `double` | Prices often have cents (e.g., 19.99) |
| **Quantity** | `int` | Quantity is always a whole number (e.g., 1, 2, 3) |
| **Total cost** | `double` | Result of price × quantity – may also have decimals |

---

## 🧠 Step‑by‑Step Logic (Process Before Coding)

1. **Declare** three variables:
   - `double price;`
   - `int quantity;`
   - `double total;`

2. **Prompt** the user for the price:
   - `cout << "Enter the price of one item: ";`

3. **Read** the price using `cin`:
   - `cin >> price;`

4. **Prompt** the user for the quantity:
   - `cout << "Enter the quantity: ";`

5. **Read** the quantity using `cin`:
   - `cin >> quantity;`

6. **Calculate** the total:
   - `total = price * quantity;`

7. **Display** the result in a clear message:
   - `cout << "Total cost: $" << total << endl;`

---

## 💻 Complete Code Example (Copy, Compile, Run)

```cpp
#include <iostream>
using namespace std;

int main() {
    // Step 1: Declare variables
    double price;    // Price per item (can have decimals)
    int quantity;    // Number of items (whole number)
    double total;    // Final total cost

    // Step 2: Get price from user
    cout << "Enter the price of one item: $";
    cin >> price;

    // Step 3: Get quantity from user
    cout << "Enter the quantity: ";
    cin >> quantity;

    // Step 4: Calculate total
    total = price * quantity;

    // Step 5: Display result
    cout << "\n---------------------------\n";
    cout << "Price per item : $" << price << endl;
    cout << "Quantity       : " << quantity << endl;
    cout << "Total cost     : $" << total << endl;
    cout << "---------------------------\n";

    return 0;
}
```

---

🧪 Sample Run (What you should see in the terminal)

```
Enter the price of one item: $19.99
Enter the quantity: 3

---------------------------
Price per item : $19.99
Quantity       : 3
Total cost     : $59.97
---------------------------
```

---

🧩 Important Notes

· The multiplication price * quantity automatically converts quantity to a double because price is a double. So the result is a double with the correct decimal part.
· Always check your data types – if you use int for price, you will lose cents. Always use double for money values.

---

🚀 Challenge Extensions (Optional – Try if you finish early)

1. Discount: Ask the user if they have a discount coupon (yes/no). If yes, ask for the discount percentage (e.g., 10 for 10%) and subtract it from the total.
2. Multiple items: Ask the user how many different items they have, then loop to enter each price and quantity, summing up the grand total (we'll learn loops in Week 2 – but you can try now!).
3. Receipt format: Print the result with exactly two decimal places (e.g., $59.97).
      Hint: Use cout << fixed << setprecision(2); – but you'll need to #include <iomanip>.

---

✅ What to Submit

· Your .cpp file with the working program.
· Screenshot of a test run (optional).

Deadline: Before the next class.

---

📖 Additional Resources

· W3Schools – C++ Variables
· W3Schools – C++ User Input
· Programiz – C++ Variables and Data Types

```

---

This assignment is practical, beginner‑friendly, and perfectly demonstrates the use of variables, input, and output with mixed data types.  
Now Victor can work on it before your 3pm class, and you can discuss his solution together. 🚀