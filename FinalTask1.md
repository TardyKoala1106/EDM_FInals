## Lab Task 2 - MySQL Basics
# Task 1 - Employee Table
employee id: Unique INT, Auto Increment, PK.
employee name: VARCHAR(255), not null
manager id: INT, FK referencing employee id.

# Code: 
<img src="Task1-1.png">
# Table:
<img src="Task1-T1.png">

# Task 2 - Departments Table
department id: Unique INT, Auto Increment, PK.
department name: VARCHAR(255), not null.

# Code:
<img src="Task1-2.png">
# Table:
<img src="Task1-T2.png">

# Task 3 - Employee Departments
employee id: INT, FK referencing employee id.
department id: INT, FK referencing department id

# Code:
<img src="Task1-3.png">
# Table:
<img src="Task1-T3.png">

# Task 4 - Employee Projects
employee id: INT, FK referencing employee id.
project name: VARCHAR(255), not null.

# Code:
<img src="Task1-4.png">
# Table:
<img src="Task1-T4.png">

# Task 5 - Managers
manager id: Unique INT, Auto Increment, PK.
employee id: INT, FK referencing employee id.

# Code:
<img src="Task1-5.png">
# Table:
<img src="Task1-T5.png">
