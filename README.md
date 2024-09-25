# College-Management-System
A College Management System using SQL for managing students, courses, faculty, and exams.

This project is a College Management System that helps manage student data, courses, faculty, and exams. The system demonstrates SQL queries for various DBMS operations such as CRUD, joins, aggregate functions, and stored procedures.

## Features:
- Student management (Add, update, delete, view student records)
- Course enrollment for students
- Faculty management
- Exam results management
- Reporting on student performance using aggregate functions                                                                                         

## Database Schema:
The system contains the following tables:
1. **students** – stores student information
2. **courses** – stores course information
3. **faculty** – stores faculty information
4. **enrollments** – stores student enrollment information
5. **results** – stores exam results for students

## Key SQL Queries:
### 1. Add a New Student:
```sql
INSERT INTO students (name, roll_number, course) VALUES ('Naman shroff' , 101, 'B.Tech');

##Join to View Enrolled Courses:
SELECT students.name, courses.course_name 
FROM students
JOIN enrollments ON students.student_id = enrollments.student_id
JOIN courses ON enrollments.course_id = courses.course_id;

##View Top 5 Performing Students:
SELECT students.name, AVG(results.marks) AS average_marks
FROM results
JOIN students ON results.student_id = students.student_id
GROUP BY students.name
ORDER BY average_marks DESC
LIMIT 5;

#### **d. How to Set Up the Project:**
```markdown
## Setup Instructions:
1. Clone the repository:  
```bash
git clone https://github.com/YourUsername/College-Management-System.git
