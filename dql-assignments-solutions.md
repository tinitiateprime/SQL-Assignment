# DQL Assignments Solutions

## Select
```sql
-- 1. Select all columns from students table
SELECT * FROM students;

-- 2. Select specific columns (first_name and last_name)
SELECT first_name, last_name FROM students;

-- 3. Select unique majors (DISTINCT)
SELECT DISTINCT major FROM students;

-- 4. Select the total number of students (COUNT)
SELECT COUNT(*) AS total_students FROM students;

-- 5. Select students with a calculated column (Full Name)
SELECT first_name + ' ' + last_name AS full_name FROM students;

-- 6. Select students with a formatted date
SELECT first_name, last_name, FORMAT(dob, 'yyyy-MM-dd') AS birth_date FROM students;

-- 7. Select students and alias columns
SELECT student_id AS ID, first_name AS "First Name", last_name AS "Last Name" FROM students;

-- 8. Select courses and calculate credit weight
SELECT course_name, credits * 2 AS total_weight FROM courses;

-- 9. Select students and return lowercase email
SELECT first_name, LOWER(email) AS email FROM students;

-- 10. Select students and show their age
SELECT first_name, last_name, DATEDIFF(YEAR, dob, GETDATE()) AS age FROM students;

-- SELECT students from 'Computer Science' major
SELECT * FROM students 
WHERE major = 'Computer Science';

-- COUNT students in each major
SELECT major, COUNT(*) AS num_students 
FROM students 
GROUP BY major;

-- SELECT all courses in the 'Engineering' department
SELECT * FROM courses 
WHERE department = 'Engineering';

-- COUNT courses per department
SELECT department, COUNT(*) AS num_courses 
FROM courses 
GROUP BY department;

-- SELECT enrollments for a specific student
SELECT * FROM enrollments 
WHERE student_id = 101;

-- COUNT enrollments per course
SELECT course_id, COUNT(*) AS num_students 
FROM enrollments 
GROUP BY course_id;


-- SELECT students who got 'A'
SELECT student_id, course_id FROM grades 
WHERE grade = 'A';

-- COUNT grades per course
SELECT course_id, grade, COUNT(*) AS num_students 
FROM grades 
GROUP BY course_id, grade;

-- SELECT all instructors from 'Computer Science' department
SELECT * FROM instructors 
WHERE department = 'Computer Science';

-- COUNT instructors per department
SELECT department, COUNT(*) AS num_instructors 
FROM instructors 
GROUP BY department;

-- SELECT all courses taught by a specific instructor
SELECT c.course_name, i.first_name, i.last_name
FROM course_instructors ci
JOIN courses c ON ci.course_id = c.course_id
JOIN instructors i ON ci.instructor_id = i.instructor_id
WHERE i.instructor_id = 501;

-- COUNT courses per instructor
SELECT instructor_id, COUNT(course_id) AS num_courses 
FROM course_instructors 
GROUP BY instructor_id;

```
## Where
```sql
-- 1. Select students where major is 'Computer Science'
SELECT * FROM students WHERE major = 'Computer Science';

-- 2. Select students born after 2002
SELECT * FROM students WHERE dob > '2002-01-01';

-- 3. Select courses where credits are greater than or equal to 4
SELECT * FROM courses WHERE credits >= 4;

-- 4. Select students where last name starts with 'J'
SELECT * FROM students WHERE last_name LIKE 'J%';

-- 5. Select students with a NULL email
SELECT * FROM students WHERE email IS NULL;

-- 6. Select students enrolled in Mathematics or Physics
SELECT * FROM students WHERE major IN ('Mathematics', 'Physics');

-- 7. Select students not in the Biology department
SELECT * FROM students WHERE major NOT IN ('Biology');

-- 8. Select students with ID between 100 and 200
SELECT * FROM students WHERE student_id BETWEEN 100 AND 200;

-- 9. Select students whose email ends with 'university.edu'
SELECT * FROM students WHERE email LIKE '%university.edu';

-- 10. Select enrollments made in the last 30 days
SELECT * FROM enrollments WHERE enrollment_date >= DATEADD(DAY, -30, GETDATE());
```

## Group by
```sql
-- 1. Count students per major
SELECT major, COUNT(*) AS student_count 
FROM students 
GROUP BY major;

-- 2. Count students by year of birth
SELECT YEAR(dob) AS birth_year, COUNT(*) AS num_students 
FROM students 
GROUP BY YEAR(dob);

-- 3. Sum of credits per department
SELECT department, SUM(credits) AS total_credits 
FROM courses 
GROUP BY department;

-- 4. Average student age per major
SELECT major, AVG(DATEDIFF(YEAR, dob, GETDATE())) AS avg_age 
FROM students 
GROUP BY major;

-- 5. Count enrollments per course
SELECT course_id, COUNT(student_id) AS total_enrollments 
FROM enrollments 
GROUP BY course_id;

-- 6. Find the earliest enrollment date per course
SELECT course_id, MIN(enrollment_date) AS first_enrollment 
FROM enrollments 
GROUP BY course_id;

-- 7. Find highest and lowest grades per course
SELECT course_id, MAX(grade) AS highest_grade, MIN(grade) AS lowest_grade 
FROM grades 
GROUP BY course_id;

-- 8. Count students per year of enrollment
SELECT YEAR(enrollment_date) AS enroll_year, COUNT(*) AS num_students 
FROM enrollments 
GROUP BY YEAR(enrollment_date);

-- 9. Count instructors per department
SELECT department, COUNT(*) AS num_instructors 
FROM instructors 
GROUP BY department;

-- 10. Calculate average course credits per department
SELECT department, AVG(credits) AS avg_credits 
FROM courses 
GROUP BY department;

```
## Having

```sql
-- 1. Count students per major and filter those with more than 5 students
SELECT major, COUNT(*) AS student_count 
FROM students 
GROUP BY major 
HAVING COUNT(*) > 5;

-- 2. Find courses with more than 3 enrollments
SELECT course_id, COUNT(*) AS total_enrollments 
FROM enrollments 
GROUP BY course_id 
HAVING COUNT(*) > 3;

-- 3. Find majors where the average student age is greater than 22
SELECT major, AVG(DATEDIFF(YEAR, dob, GETDATE())) AS avg_age 
FROM students 
GROUP BY major 
HAVING AVG(DATEDIFF(YEAR, dob, GETDATE())) > 22;

-- 4. Find departments with more than 10 courses
SELECT department, COUNT(*) AS total_courses 
FROM courses 
GROUP BY department 
HAVING COUNT(*) > 10;

-- 5. Find courses with an average grade below 'B'
SELECT course_id, AVG(CASE 
    WHEN grade = 'A' THEN 4.0
    WHEN grade = 'B' THEN 3.0
    WHEN grade = 'C' THEN 2.0
    WHEN grade = 'D' THEN 1.0
    ELSE 0 END) AS avg_gpa 
FROM grades 
GROUP BY course_id 
HAVING AVG(CASE 
    WHEN grade = 'A' THEN 4.0
    WHEN grade = 'B' THEN 3.0
    WHEN grade = 'C' THEN 2.0
    WHEN grade = 'D' THEN 1.0
    ELSE 0 END) < 3.0;

-- 6. Find departments with total credit hours exceeding 50
SELECT department, SUM(credits) AS total_credits 
FROM courses 
GROUP BY department 
HAVING SUM(credits) > 50;

-- 7. Find instructors teaching more than 2 courses
SELECT instructor_id, COUNT(course_id) AS num_courses 
FROM course_instructors 
GROUP BY instructor_id 
HAVING COUNT(course_id) > 2;

-- 8. Find students enrolled in more than 3 courses
SELECT student_id, COUNT(course_id) AS num_courses 
FROM enrollments 
GROUP BY student_id 
HAVING COUNT(course_id) > 3;

-- 9. Find courses with at least one student who received an 'A'
SELECT course_id 
FROM grades 
GROUP BY course_id 
HAVING MAX(grade) = 'A';

-- 10. Find birth years where more than 5 students were born
SELECT YEAR(dob) AS birth_year, COUNT(*) AS num_students 
FROM students 
GROUP BY YEAR(dob) 
HAVING COUNT(*) > 5;

```

## Order by 

```sql
-- 1. Order students by last name alphabetically
SELECT * FROM students ORDER BY last_name ASC;

-- 2. Order students by birthdate, oldest first
SELECT * FROM students ORDER BY dob ASC;

-- 3. Order courses by credits in descending order
SELECT * FROM courses ORDER BY credits DESC;

-- 4. Order students by major, then by first name
SELECT * FROM students ORDER BY major ASC, first_name ASC;

-- 5. Order enrollments by enrollment date, newest first
SELECT * FROM enrollments ORDER BY enrollment_date DESC;

-- 6. Order students by age (oldest first)
SELECT first_name, last_name, DATEDIFF(YEAR, dob, GETDATE()) AS age 
FROM students 
ORDER BY age DESC;

-- 7. Order instructors by department, then by last name
SELECT * FROM instructors ORDER BY department ASC, last_name ASC;

-- 8. Order courses by department, then by number of credits
SELECT * FROM courses ORDER BY department ASC, credits DESC;

-- 9. Order grades by student_id and grade (A first)
SELECT * FROM grades ORDER BY student_id ASC, grade ASC;

-- 10. Order students by email in descending order
SELECT * FROM students ORDER BY email DESC;
```