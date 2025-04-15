## Lab Task 2 - TRANSFORMING ER MODEL into Relational Tables

# Task 1 - Student Table

create table student (
username VARCHAR(50) PRIMARY KEY
);

# OUTPUT:
<img src="Task2Task1.png">

# Task 2 - Assignment Table

create table assignment (
shortname VARCHAR(50) PRIMARY KEY,
due_date DATE NOT NULL,
url VARCHAR(255)
);

# OUTPUT:
<img src="Task2Task2.png">

# Task 3 - Submission Table

create table submission (
username VARCHAR(50),
shortname VARCHAR(50),
version INT,
submit_date DATE NOT NULL,
data TEXT,
FOREIGN KEY (username) REFERENCES student (username),
FOREIGN KEY (shortname) REFERENCES assignment (shortname)
);

# OUTPUT:
<img src="Task2Task3.png">

# Task 4 - Relational Table

# OUTPUT:
<img src="Relational Table.png">






