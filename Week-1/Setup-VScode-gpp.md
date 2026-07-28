
# 🛠️ Setup Guide: VS Code + g++ Compiler for C++ Development

| **Target** | **Platforms** | **Goal** |
| :--- | :--- | :--- |
| 17-year-old beginner (and any new learner) | Windows, macOS, Linux | Install VS Code, set up the g++ compiler, and run your first C++ program locally. |

---

## ✅ Prerequisites

- A computer with an internet connection.
- Basic familiarity with file navigation and installing software.

---

## 📥 Step 1: Install Visual Studio Code

Go to [https://code.visualstudio.com/](https://code.visualstudio.com/) and download the installer for your operating system.

- **Windows:** Run the `.exe` installer. **Important:** During installation, **check the box** "Add to PATH" – this makes it easier to open VS Code from the terminal.
- **macOS:** Download the `.zip`, open it, and drag `Visual Studio Code.app` to the `Applications` folder.
- **Linux:** Use your package manager (e.g., `sudo apt install code` on Ubuntu) or download the `.deb`/`.rpm` from the website.

After installation, launch VS Code.

---

## 🧩 Step 2: Install the C++ Extension

1. Open VS Code.
2. Click the **Extensions** icon on the left sidebar (or press `Ctrl+Shift+X` / `Cmd+Shift+X` on Mac).
3. Search for **"C++"**.
4. Install the official **C/C++** extension by Microsoft (it has the blue badge).

This extension provides syntax highlighting, IntelliSense, debugging, and integration with the compiler.

---

## ⚙️ Step 3: Install the g++ Compiler

### Windows (MinGW-w64)

The easiest way is to install **MinGW-w64** via the **MSYS2** package manager.

1. Download MSYS2 from [https://www.msys2.org/](https://www.msys2.org/) (choose the 64-bit installer).
2. Run the installer. Keep the default installation path (e.g., `C:\msys64`).
3. When the installation finishes, **launch the MSYS2 UCRT64 terminal** (search "MSYS2 UCRT64" in Start).
4. In the terminal, run:
```

pacman -S mingw-w64-ucrt-x86_64-gcc

```
   Press `Y` to confirm.
5. After installation, you need to add the compiler to your system PATH:
   - Open **System Properties** → **Advanced** → **Environment Variables**.
   - Under **System variables**, find `Path`, click **Edit**.
   - Add a new entry: `C:\msys64\ucrt64\bin` (or the actual path where `g++.exe` is located – check inside `C:\msys64\ucrt64\bin`).
   - Click OK, OK, OK.
6. **Restart** VS Code (and any terminal) to apply the new PATH.

**Verify:** Open a new terminal in VS Code (`Ctrl+``) and type:
```

g++ --version

```
You should see something like `g++ (Rev10, Built by MSYS2 project) ...` – if so, it's working.

> **Alternative (simpler for beginners):** Download the **MinGW-w64** standalone from [SourceForge](https://sourceforge.net/projects/mingw-w64/) (search for "MinGW-W64 GCC-8.1.0" or newer). Extract to `C:\mingw64` and add `C:\mingw64\bin` to PATH. However, MSYS2 is the recommended modern approach.

### macOS

The g++ compiler is part of the **Xcode Command Line Tools**. Install it by opening the Terminal and running:
```

xcode-select --install

```
A pop‑up will ask you to install the tools – click **Install**.

After installation, verify:
```

g++ --version

```
You should see `Apple clang version...` (which is a drop‑in replacement for g++).

### Linux (Ubuntu/Debian)

Open a terminal and run:
```

sudo apt update
sudo apt install g++ build-essential

```
Verify with:
```

g++ --version

```

---

## 🚀 Step 4: Configure VS Code to Use g++

1. Create a new folder for your C++ projects, e.g., `cpp-training`.
2. Open that folder in VS Code: **File → Open Folder**.
3. Create a new file: `hello.cpp` and paste the classic code:

```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Hello, World!" << endl;
    return 0;
}
```

4. Save the file (Ctrl+S / Cmd+S).
5. Now we need a tasks.json file to compile and run easily.
   · Press Ctrl+Shift+P (or Cmd+Shift+P on Mac) to open the command palette.
   · Type "Tasks: Configure Task" and select it.
   · Choose "C/C++: g++.exe build active file" (or clang++ on Mac) – this will create a .vscode/tasks.json file automatically.
   · If asked to select a template, pick "Others" and then modify the JSON.
   Alternatively, create the .vscode folder manually and put this tasks.json inside:

```json
{
    "version": "2.0.0",
    "tasks": [
        {
            "label": "build C++",
            "type": "shell",
            "command": "g++",
            "args": [
                "-g",
                "${file}",
                "-o",
                "${fileDirname}/${fileBasenameNoExtension}.exe"
            ],
            "group": {
                "kind": "build",
                "isDefault": true
            },
            "problemMatcher": ["$gcc"],
            "detail": "Compiles the active C++ file."
        }
    ]
}
```

6. Run the program:
   · Open hello.cpp.
   · Press Ctrl+Shift+B (or Cmd+Shift+B on Mac) to build.
   · If successful, the terminal will show the compilation command and no errors.
   · Now run the executable:
     · In the VS Code integrated terminal ( Ctrl+` ), type:
       ```
       ./hello.exe          (Windows)
       ./hello              (Mac/Linux)
       ```
     · You should see Hello, World! printed.

Tip: You can also install the Code Runner extension for a one‑click run button, but the above method gives you full control.

---

🧪 Step 5: Test with a More Complex Program

Create a new file calc.cpp and paste the calculator code from Week 1. Build and run it to ensure everything works.

---

📖 Troubleshooting Common Issues

Problem Solution
g++ not recognized Check PATH: restart VS Code and terminal. On Windows, ensure the bin folder of MinGW is in the PATH.
iostream not found You are using an old compiler or not including the correct library. Ensure you installed g++ properly.
Permission denied (Mac/Linux) Make the executable executable: chmod +x hello before running.
Build fails with errors Check your code for missing semicolons or typos. The terminal will show line numbers.

---

🌐 Alternative: Use an Online Compiler (No Setup)

If you're stuck, you can start coding immediately using an online compiler:

· OnlineGDB: https://www.onlinegdb.com/online_c++_compiler
· Replit: https://replit.com/ (create a C++ repl)
· Programiz: https://www.programiz.com/cpp-programming/online-compiler/

These are great for quick practice, but you'll want a local setup for larger projects.

---

✅ Checklist – You're Ready!

· VS Code installed.
· C++ extension installed.
· g++ installed and verified (g++ --version works).
· A hello.cpp compiled and run successfully.

Now you're all set to follow the 6‑week training – let's code! 🚀

```

---

**Where to put it?**  
Add this as a separate file in your repo (e.g., `setup-vscode-gpp.md`). You can also link to it from your `README.md` under a "Setup" section.

This guide is clean, step‑by‑step, beginner‑friendly, and follows the same formatting style as your other documents. Your student will be up and running in no time. Good luck with the training! 🎯