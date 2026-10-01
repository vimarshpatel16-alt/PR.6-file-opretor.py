# 📔 Personal Journal Manager

## 📌 Project Overview

The **Personal Journal Manager** is a simple Python-based console application that allows users to maintain and manage their personal journal entries.

The application provides an easy-to-use menu-driven interface where users can:

- Add new journal entries
- View all saved entries
- Search entries using a keyword or date
- Delete all journal entries
- Exit the application safely

Each journal entry is automatically stored in a text file along with the **date and time** at which it was created.

---

## 🎯 Project Objective

The main objective of this project is to develop a simple and practical **Personal Journal Management System** using Python.

This project demonstrates important Python programming concepts such as:

- Object-Oriented Programming
- Classes and Objects
- Methods
- File Handling
- Exception Handling
- Date and Time Handling
- Conditional Statements
- Loops
- User Input
- String Searching
- File and Operating System Operations

---

## 🛠️ Technologies Used

| Technology | Purpose |
|-----------|---------|
| Python | Main programming language |
| `datetime` | To record date and time of journal entries |
| `os` | To delete the journal file |
| Text File | To permanently store journal entries |

---

## 💻 Requirements

To run this project, you need:

- Python 3.x
- Any Python IDE or code editor

Examples:

- IDLE
- Visual Studio Code
- PyCharm
- Jupyter Notebook
- Command Prompt / Terminal

No external Python libraries are required.

---

## 📂 Project Structure

```text
Personal-Journal-Manager/
│
├── journal_manager.py
├── journal.txt
└── README.md
````

### File Description

**`journal_manager.py`**
Contains the complete Python source code of the Personal Journal Manager.

**`journal.txt`**
Stores all journal entries created by the user. This file is automatically created when the first entry is added.

**`README.md`**
Contains project documentation, features, installation instructions, usage instructions, and technical details.

---

# ⭐ Features

## 1. Add a New Entry

The user can enter a personal journal entry.

The program automatically adds the current date and time to the entry.

### Example:

```text
Enter your journal entry:
Today I completed my Python project.

Entry added successfully.
```

The entry is stored in the following format:

```text
[2026-10-01 11:20:15] Today I completed my Python project.
```

---

## 2. View All Entries

This option displays all previously saved journal entries.

### Example:

```text
Your Journal Entries:
-------------------------------------
[2026-10-01 10:30:15] Today I learned Python.
[2026-10-01 11:20:15] Today I completed my project.
```

If the journal file does not exist, the program displays an appropriate message.

---

## 3. Search for an Entry

The search feature allows users to find journal entries using:

* Keywords
* Dates
* Words or phrases

The search is **case-insensitive**, meaning that uppercase and lowercase letters are treated equally.

### Example:

```text
Enter keyword or date to search: Python

[2026-10-01 10:30:15] Today I learned Python.
```

If no matching entry is found:

```text
No matching entries found.
```

---

## 4. Delete All Entries

This option allows the user to delete all stored journal entries.

For safety, the program asks for confirmation before deleting the file.

### Example:

```text
Are you sure you want to delete all entries? (yes/no): yes

All journal entries have been deleted.
```

If the user enters anything other than `yes`:

```text
Deletion cancelled.
```

---

## 5. Exit

The Exit option safely terminates the program.

```text
Thank you for using Personal Journal Manager. Goodbye!
```

---

# 🔄 Program Workflow

The basic workflow of the application is:

```text
Start
  ↓
Display Welcome Message
  ↓
Display Main Menu
  ↓
User Selects an Option
  ↓
 ┌───────────────────────────────┐
 │ 1. Add New Entry              │
 │ 2. View All Entries           │
 │ 3. Search for an Entry        │
 │ 4. Delete All Entries        │
 │ 5. Exit                       │
 └───────────────────────────────┘
  ↓
Perform Selected Operation
  ↓
Return to Main Menu
  ↓
If Option 5 → Exit
```

---

# 🧱 Object-Oriented Programming

This project uses **Object-Oriented Programming (OOP)**.

A class named:

```python
class journalmanager:
```

is created to manage all journal-related operations.

An object of the class is created using:

```python
j = journalmanager()
```

The class contains the following methods:

```text
__init__()
add_entry()
view_entry()
search_entry()
delete_entries()
```

---

## 🔹 Constructor

The constructor initializes the journal file name.

```python
def __init__(self):
    self.filename = "journal.txt"
```

The variable `self.filename` stores the name of the file used for saving journal entries.

---

## 🔹 Add Entry Method

```python
def add_entry(self):
```

This method:

1. Takes journal text from the user.
2. Gets the current date and time.
3. Opens the journal file in append mode.
4. Saves the entry.
5. Displays a success message.

The date and time are generated using:

```python
datetime.now().strftime("[%Y-%m-%d %H:%M:%S]")
```

---

## 🔹 View Entry Method

```python
def view_entry(self):
```

This method opens the journal file in read mode and displays all saved entries.

It also handles the situation where the file does not exist.

---

## 🔹 Search Entry Method

```python
def search_entry(self):
```

This method asks the user for a keyword or date and checks every line in the journal file.

The search uses:

```python
keyword.lower() in line.lower()
```

Therefore, the search is not affected by uppercase or lowercase letters.

---

## 🔹 Delete Entries Method

```python
def delete_entries(self):
```

This method deletes the journal file using:

```python
os.remove(self.filename)
```

Before deleting the file, the program asks the user for confirmation.

---

# 📁 File Handling

File handling is one of the major concepts demonstrated in this project.

The program uses different file modes:

### Append Mode

```python
open(self.filename, "a")
```

Used to add new entries without deleting existing entries.

### Read Mode

```python
open(self.filename, "r")
```

Used to read and display existing journal entries.

---

# 🛡️ Exception Handling

The project uses `try` and `except` blocks to prevent the program from crashing when an error occurs.

For example:

```python
try:
    file = open(self.filename, "r")
except FileNotFoundError:
    print("The journal file does not exist.")
```

The program handles situations such as:

* Journal file not found
* Invalid menu input
* Error while adding an entry
* Error while reading the file
* Error while deleting the file

This makes the application more reliable and user-friendly.

---

# ⌚ Date and Time

The Python `datetime` module is used to automatically record when an entry was created.

```python
from datetime import datetime
```

The current date and time are obtained using:

```python
datetime.now()
```

The timestamp is formatted as:

```text
[YYYY-MM-DD HH:MM:SS]
```

Example:

```text
[2026-10-01 11:20:15]
```

---

# 🔁 Menu-Driven Program

The program uses an infinite `while` loop to continuously display the menu.

```python
while True:
```

The loop continues until the user selects option `5`.

The `break` statement is used to terminate the loop:

```python
elif user == 5:
    print("Thank you for using Personal Journal Manager. Goodbye!")
    break
```

---

# ▶️ How to Run the Project

## Step 1: Install Python

Make sure Python 3.x is installed on your computer.

Check the installation using:

```bash
python --version
```

---

## Step 2: Save the Python File

Save the source code as:

```text
journal_manager.py
```

---

## Step 3: Open Terminal

Navigate to the folder containing the Python file.

Example:

```bash
cd Personal-Journal-Manager
```

---

## Step 4: Run the Program

Execute:

```bash
python journal_manager.py
```

The program will display:

```text
Welcome to Personal Journal Manager!
Please select an option.
```

---

# 🧪 Sample Output

```text
Welcome to Personal Journal Manager!
Please select an option.

1. Add a New Entry
2. View all Entries
3. Search for an Entry
4. Delete all Entries
5. Exit

user Input: 1

Enter your journal entry:
Today I learned about Python file handling.

Entry added successfully.
```

### Viewing Entries

```text
1. Add a New Entry
2. View all Entries
3. Search for an Entry
4. Delete all Entries
5. Exit

user Input: 2

Your Journal Entries:
-------------------------------------
[2026-10-01 11:10:20] Today I learned about Python file handling.
```

### Searching Entries

```text
user Input: 3

Enter keyword or date to search: Python

[2026-10-01 11:10:20] Today I learned about Python file handling.
```

### Exiting

```text
user Input: 5

Thank you for using Personal Journal Manager. Goodbye!
```

---

# ⚠️ Error Handling

The program provides error messages for invalid situations.

### Invalid Menu Input

If the user enters:

```text
abc
```

The program displays:

```text
Invalid input. Please enter a number.
```

### Invalid Menu Option

If the user enters:

```text
10
```

The program displays:

```text
Invalid option. Please select a valid option from the menu.
```

### Missing Journal File

If the user tries to view entries before creating a journal:

```text
The journal file does not exist. Please add a new entry first.
```

---

# 📊 Advantages

* Simple and easy to use
* Menu-driven interface
* Automatically records date and time
* Stores data permanently in a text file
* Supports keyword searching
* Includes delete confirmation
* Uses Object-Oriented Programming
* Uses exception handling
* Requires no external packages
* Suitable for beginners learning Python

---

# 🔮 Future Enhancements

The project can be improved in the future by adding:

1. Edit an existing journal entry
2. Delete a single selected entry
3. Password protection
4. User login system
5. Categories for journal entries
6. Export entries to PDF
7. Graphical User Interface (GUI)
8. Database storage using SQLite
9. Mood tracking
10. Backup and restore functionality
11. Sorting entries by date
12. Multiple user accounts

---

# 🎓 Learning Outcomes

After completing this project, the following Python concepts are demonstrated:

* Python fundamentals
* Variables and data types
* Input and output
* Conditional statements
* Loops
* Functions and methods
* Classes and objects
* File handling
* Exception handling
* String manipulation
* Date and time operations
* Operating system file operations

---

# 🔐 Data Storage

All journal entries are stored locally in:

```text
journal.txt
```

The application does not require an internet connection or an external database.

The journal data is therefore stored on the computer where the program is executed.

---

# 📝 Limitations

The current version has some limitations:

* It uses a text file instead of a database.
* All users share the same journal file.
* There is no password protection.
* Users cannot edit individual entries.
* Users can delete all entries at once, but cannot delete a single entry.
* The application currently works through the command line.

These limitations can be addressed in future versions.

---

# 👨‍💻 Project Information

**Project Name:** Personal Journal Manager

**Programming Language:** Python

**Project Type:** Console-Based Application

**Programming Concept:** Object-Oriented Programming

**Storage:** Text File

**File Name:** `journal.txt`

---

# ✅ Conclusion

The **Personal Journal Manager** is a practical Python application designed to help users create, store, view, and search personal journal entries.

The project demonstrates how Python can be used to build a real-world console application by combining **Object-Oriented Programming, file handling, exception handling, date and time functions, loops, and conditional statements**.

This project provides a strong foundation for developing more advanced journal management applications with databases, graphical interfaces, authentication, and additional features in the future.

---

## ⭐ Project Summary

```text
Personal Journal Manager
        │
        ├── Add Journal Entry
        │
        ├── View All Entries
        │
        ├── Search Entries
        │
        ├── Delete All Entries
        │
        ├── Automatic Date & Time
        │
        ├── File Handling
        │
        ├── Exception Handling
        │
        └── Object-Oriented Programming
```

**Thank You!**





