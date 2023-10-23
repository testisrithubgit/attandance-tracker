In many colleges, we have an attendance system for each subject, and the lack of the same leads to problems. It is difficult for students to remember the number of leaves taken for a particular subject. If every time paperwork has to be done to track the number of leaves taken by staff and check whether it is a lack of attendance or not, it involves a lot of time and is inefficient too. 

This article will bring a simple tracker & reminder system for attendance. The input to this system is an excel sheet containing the students’ mail-id and their number of leaves in each class subject. For say, if a student will not be allowed to write the exam for a particular subject if he takes more than 3 leaves. This tracker will send out an email to the student when he takes the second leave as a reminder that only 1 more left with him on that subject. If he takes further leave, both the student and the corresponding staff receive emails regarding the lack of attendance. The only thing to do is just enter the subject code and roll number of the student absent from the class and the rest will be taken care of by this tracker system.
Python Modules Used
Install the following modules using pip or conda commands.

openpyxl – To update and read from the excel sheet.
smtplib & email   – To send out emails.
Dataset in Use:
The Excel sheet should contain the following data:
Roll number
Student mail ID
Subject {1,2,……..N}
For this article, consider three subjects and their codes as numbers for input: 

Computer Intelligence (CI)—-> 1
Python —-> 2
Data Mining (DM) —-> 3
Initially, the Excel sheet should look like this:
Stepwise Implementation
Import required modules
Initialize required variables and import the data file in use.
Create a function to save excel on every update
def savefile(): 
  
    book.save(r'<your-path>\attendance.xlsx') 
    print("saved!")
    Create a function to track attendance: A function for checking the list of absentees against the threshold condition is required. The updates must take place to the variables declared outside the function as global variables. Thus, the following lines are written.
def check(no_of_days, row_num, b): 
  
  # to use the globally declared lists and strings 
    global staff_mails 
    global l2 
    global l3
    This check() function takes three arguments:
no_of_days : A-List containing total.no.of. leaves of the students in the row_num parameter.
row_num : A List of roll numbers of today’s absentees
b : Subject code
