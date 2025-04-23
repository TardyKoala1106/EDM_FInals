## Lab Task 3-1 - Using MYSQL Clauses

# Task 1 

SELECT course_name
FROM courses
WHERE students_enrolled < enrollment_limit;

# OUTPUT:

<img src="Task3-1Task1.png">

# Task 2

SELECT course_name, sum(students_enrolled)
FROM courses
GROUP BY (category);

# OUTPUT:

<img src="Task3-1Task2.png">

# Task 3

SELECT course_name 
FROM courses
WHERE students_enrolled = enrollment_limit;

# OUTPUT:

<img src="Task3-1Task3.png">

# Task 4

SELECT SUM(students_enrolled) FROM courses; 
   
# OUTPUT:

<img src="Task3-1Task4.png">

# Task 5

SELECT course_name, students_enrolled 
FROM courses
ORDER BY students_enrolled ASC;
   
# OUTPUT:

<img src="Task3-1Task5.png">
   


