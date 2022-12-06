# Employee-Management-System
This program was built using Java Swing to build the GUI and sqlite as the database.
After forking/downloading this project. It should be able to be run in a Java IDE such as Eclipse. 
We built the GUI with Eclipse Window Builder. There are two sides to the application, an employee side and a manager side. You will need to run the application twice in order to open 2 separate logins to test each side. 

## Logging In
There are two main sides to the application and logging in to either side is dependent on whether the employee is a manager or not. An account requires a username and password that is linked to an entry in the EmployeeUser table in the database. That username and password is linked to an EmployeeID which is used to find that specific ID in the employee database. When found it checks the position of that employee and if it is a manager, it logs the user into the manager side, otherwise it logs the user into the employee profile side. 

Signing up is done given that the user knows their employee ID. The user can then create an account with their Employee ID given that it exists in the employee database. Then they can proceed with logging in.

## Main Functionality on the Manager Side
On the Employee Database Management System window.

On the right is the database which updates based on what is in the employee.db file. 

On the top left is the input form for using the add and edit buttons. 

On the bottom left is the delete, print, tasks, requests, documents, and performances button. 

## Add button
The user must fill out all input fields and after valid input, the program sends the input data to the database file to be recorded.
Then the table is updated based on the updated database. 

Input Validation:
- All fields must be filled out 
- Email must be in email format (must have @ and .)
- End Date input must be filled OR Current button must be selected
- Salary must be numerical
- Employee ID must be 3 numbers 
- Phone Number must be 10 numbers no dashes

Ex Input:
- First Name: matthew
- Last Name: Pham
- Email: username@domain.com
- Start Date: 02/15/2020
- End Date: 7/12/2021 (or CURR)
- Salary: 70000
- Employee ID: 333
- Phone Number: 1112223333
- Department: Engineering
- Position: Software Developer
- Date of Birth: 05/15/2002

## Edit Button
The Edit button also uses the same input form as the Add button. 
Employee ID MUST match an existing record, and all other fields will be edited depending on what is currently in the input fields.
Input Validation is done the same as for the Add button. However, if the ID doesn't not exist in the database, a "Employee Record not Found" message will pop up. 

## Delete Button 
The Delete button opens up a pop up that asks the user to input an employee ID in order to delete the corresponding record.
Performs input validation on the ID and deletes it if it exists. 

## Print Button
Print button opens up a window with a printing GUI that can print the database shown in the table on the right.

## Tasks Button
Opens a “Tasks” GUI which creates a table using the information in the “tasks” database, using a loadTasks() function. The tasks database has three fields: TaskID, EmpID, and TaskName. Has four buttons: Edit Tasks, Delete Tasks, Add Tasks, and Refresh. 

Edit Tasks:  When the “Edit Tasks” button is pressed, a gui window appears asking the user to enter the Task ID of the task that the manager wishes to edit, along with Task and Emp ID fields if they wish to change it. Once a valid task ID is entered, the task in the Tasks GUI will be edited, once the refresh button is pressed.
Delete Tasks: When the “Delete Tasks” button is pressed, a gui window appears asking the user to enter the Task ID of the task that the manager wishes to delete. Once a valid task ID is entered and the delete button is pressed, the task in the Tasks GUI will be removed, once the refresh button is pressed.
Create Tasks: When the “Create Tasks” button is pressed, a GUI window appears asking the user to enter a Task ID, Emp ID, and Task. Once these fields are entered, and the create button is pressed, a task will be created and will appear in the Tasks GUI, once the update button is pressed.
Refresh: Refreshes the Task database when pressed.

## Requests Button
Opens a requests GUI for the manager that displays all the requests in the database with a corresponding Employee ID and that employee’s request. 
(ex: EmpID: 333, Message: I would like paid time off).

## Documents Button
The document button opens up to another window which allows the user the management of text documents that may be important to the operation of a company (memos, letters, reports, etc.)

### Create/Edit Document
This button allows for the creation or editing of a text file.  Text in the text field labeled "File Name" will be used to determine what file we are working with.  If the file does not exist, it is created automatically and if it does, it will be edited without difficulty.

Input validation requires that the file name not be empty.

### Open Document
The open button is used to open any text file that resides within the working directory.  From there, you may be able to edit the file using the aforementioned create/edit button

Input validation requires that the file name not be empty.

### Delete Document
The delete document button is simple.  If you would like to get rid of a document that you no longer need, you may press this button.

Input validation requires that the file name not be empty.

### Show Files
If you would like to see what files contained in your working directory, simply press this button.

As there is no input needed to work this function, there is no input validation.

## Performances Button

Opens a GUI where the manager can enter a performance review for an employee. The manager enters the Employee ID, rating, and comments. The employee can also get this information when they login into this account. The performance reviews are added into a database that is visible on the right in the GUI. The reset button empties all three of the text boxes to make it easier for a manager to quickly enter in employee performance reviews.

## Employee Side (Non Manager)
The employee has access to tasks, requests, and performance reviews, but only limited to those that correspond to them (have their EmpID with them). On the left the employee can see their specific corresponding information (DOB, Salary, etc), which is displayed based on the EmpID of the account they logged into. Non manager employees will have access to this side. On the right the employee can see the tasks assigned to them by their manager. With the performance button, the employee can see the performance reviews given to them specifically with rating and comments. With the requests button the employee can send a request to the manager side for things like paid time off. 




Disclaimer: When running the code, you may receive the following error:


org.sqlite.SQLiteException: [SQLITE_ERROR] SQL error or missing database (no such table: EmployeeUser)


If you receive this error, open the unzipped demo folder in your file manager. Hover your mouse over the employee database file. It will likely say that the file stores 0 KB of information. To fix this, go to the zip file, and copy the employee database file. Then replace the database file in the unzipped demo folder with the database file that is a direct copy from the zipped folder. Hover the mouse over the database file,  like last time, and it should now state that the data stored is 40.0 KB. Create a new workspace, re-import the project and files, and the code should work properly this time.
