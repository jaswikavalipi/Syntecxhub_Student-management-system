simple command-line Student Management System written in Python.
Stores student records (name, student ID, grade) in a local file (JSON or CSV), demonstrates OOP with a Student class and a StudentManager/controller class, and includes basic validation (unique ID) and nicely formatted console output. Great for learning file I/O, classes, and CLI basics.

Features

Add, update, delete, and list student records

Persist data to JSON or CSV

Input validation (unique student ID)

Clean, tabular console output

Simple menu-driven CLI for repeated operations

Easily extensible (add fields, reporting, import/export)

Table of contents

Requirements

Installation

Usage

Data format

Design & Implementation

Example session

Extending the project

Contributing

License

Requirements

Python 3.8+

(Optional) tabulate for nicer table output:

pip install tabulate


If tabulate is not available, the program falls back to simple formatted printing.

Installation

Clone the repository:

git clone https://github.com/<your-username>/student-management-system.git
cd student-management-system


(Optional) Create a virtual environment and install dependencies:

python -m venv venv
source venv/bin/activate    # macOS / Linux
venv\Scripts\activate       # Windows

pip install -r requirements.txt

Usage

Run the CLI application:

python main.py


Typical menu:

Student Management System
1) Add student
2) Update student
3) Delete student
4) List students
5) Search student by ID
6) Export to CSV
7) Exit
Enter choice: _

Common operations

Add student

Enter name, id, and grade.

ID must be unique — the system will warn if a duplicate is entered.

Update student

Provide the student ID to update. You can change name and grade.

Delete student

Provide the ID to remove the student.

List students

Show all records in a table.

Export

Save current data to CSV (useful for sharing).

Data format
JSON (default storage - students.json)

Each student record is a dictionary:

[
  {
    "id": "S001",
    "name": "Asha Kumar",
    "grade": "A"
  },
  {
    "id": "S002",
    "name": "Rahul Singh",
    "grade": "B+"
  }
]

CSV (example)
id,name,grade
S001,Asha Kumar,A
S002,Rahul Singh,B+

Design & Implementation (brief)

Student class

Holds student attributes: id, name, grade.

Implements __str__() / to_dict() helpers.

StudentManager class

Responsible for in-memory list of Student objects.

Methods: add_student(), update_student(), delete_student(), get_student(), list_students(), load(), save().

Performs validation (unique ID).

main.py

CLI loop that uses StudentManager to perform actions.

Handles user input and prints results.

Example session
$ python main.py
Student Management System
1) Add student
2) Update student
3) Delete student
4) List students
5) Search student by ID
6) Export to CSV
7) Exit
Enter choice: 1

Enter student ID: S003
Enter name: Meera Patel
Enter grade: A-
Student added successfully.

Enter choice: 4
+------+-------------+-------+
|  ID  | Name        | Grade |
+------+-------------+-------+
| S001 | Asha Kumar  | A     |
| S003 | Meera Patel | A-    |
+------+-------------+-------+

Extending the project

Ideas to improve:

Add persistent unique ID generation

Add more fields (email, DOB, phone, address)

Add sorting & filtering (by grade, name)

Add import function for bulk records

Add unit tests for manager methods

Add GUI (Tkinter) or a simple web UI (Flask/FastAPI)

Contributing

Contributions welcome! Please:

Fork the repo

Create a feature branch (git checkout -b feature/my-feature)

Commit your changes (git commit -m "Add feature")

Push to the branch (git push origin feature/my-feature)

Open a pull request

Include tests for new functionality where appropriate.
