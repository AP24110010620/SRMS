# SRMS

This repository contains a complete Student Management System implemented in the C programming language. The program uses file handling to store and manage student records and includes a secure login system with role-based access control.

🔐 Login System

The system authenticates users from a credentials file (credentials.txt).
Each user has:

Username

Password

Role (admin / staff / guest)

The login system includes:

Case-insensitive username matching

3-attempt password limit

Automatic logout and exit after failed attempts

👤 User Roles & Permissions
Admin

✔ Add Student
✔ Display Students
✔ Search Student
✔ Update Student
✔ Delete Student
✔ Logout

Staff

✔ Display Students
✔ Search Student
✔ Update Student
✘ Cannot add/delete records
✔ Logout

Guest

✔ Display Students
✔ Search Student
✘ Cannot add/update/delete
✔ Logout

📚 Student Data Handling

Student records are stored in students.txt using the format:

roll,name,marks


Each record is represented by the following structure:

struct Student {
    int roll;
    char name[50];
    float marks;
};

✨ Features Included
1. Add Student (Admin Only)

Validates roll number

Checks for duplicates

Accepts student name and marks

Appends to student file

2. Display Students

Lists all stored student records in a formatted output.

3. Search Student

Search by:

Roll Number

Name (case-insensitive)

4. Update Student

Modify name and marks for a given roll

Uses a temporary file for safe update

5. Delete Student

Deletes a record matching a roll number

Safely rewrites file

🧹 Input Validation

The program includes:

Safe buffer clearing

Validation for numeric input (roll & marks)

Case-insensitive comparison for name search

Sanitized string input using fgets()

🏗 File Structure
students.txt        → stores student details
credentials.txt     → stores login credentials
main.c              → core program logic

🚀 How It Works

Program starts → displays welcome screen

User logs in → credentials verified

Role is determined → corresponding menu displayed

User performs allowed actions

Program exits after logout
# How to run and compile
compile :
gcc -o sms main.c

run:
./sms or srms.exe
