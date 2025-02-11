# Assignment for Set Operators

## UNION removes duplicate records and merges results from two queries.
```sql
1. Get all student IDs from enrollments and grades (no duplicates)
SELECT student_id FROM enrollments
UNION
SELECT student_id FROM grades;

2. Get all instructor and student names
SELECT first_name, last_name FROM students
UNION
SELECT first_name, last_name FROM instructors;

3. Get all distinct majors from students and departments
SELECT major AS department_name FROM students
UNION
SELECT department FROM instructors;

4. Get all student and instructor emails
SELECT email FROM students
UNION
SELECT email FROM instructors;

5. Get all enrolled course IDs and graded course IDs
SELECT course_id FROM enrollments
UNION
SELECT course_id FROM grades;

6. Get all department names from courses and instructors
SELECT department FROM courses
UNION
SELECT department FROM instructors;

7. Get distinct course names from courses and enrollments
SELECT course_name FROM courses
UNION
SELECT DISTINCT c.course_name FROM enrollments e
JOIN courses c ON e.course_id = c.course_id;

8. Get all student IDs and instructor IDs (avoiding duplicates)
SELECT student_id FROM students
UNION
SELECT instructor_id FROM instructors;

9. Get all course names assigned to instructors or enrolled by students
SELECT course_name FROM courses
UNION
SELECT DISTINCT c.course_name FROM enrollments e
JOIN courses c ON e.course_id = c.course_id;

10. Get all first names from students and instructors (no duplicates)
SELECT first_name FROM students
UNION
SELECT first_name FROM instructors;
```

## UNION ALL keeps duplicate records while merging results.

```sql

1. Get all student IDs from enrollments and grades (including duplicates)
SELECT student_id FROM enrollments
UNION ALL
SELECT student_id FROM grades;

2. Get all instructor and student names (with duplicates)
SELECT first_name, last_name FROM students
UNION ALL
SELECT first_name, last_name FROM instructors;

3. Get all student and instructor emails (with duplicates)
SELECT email FROM students
UNION ALL
SELECT email FROM instructors;

4. Get all course IDs from enrollments and grades (including duplicates)
SELECT course_id FROM enrollments
UNION ALL
SELECT course_id FROM grades;

5. Get all department names from courses and instructors (with duplicates)
SELECT department FROM courses
UNION ALL
SELECT department FROM instructors;

6. Get all first names from students and instructors (including duplicates)
SELECT first_name FROM students
UNION ALL
SELECT first_name FROM instructors;

7. Get all course names from courses and enrollments (including duplicates)
SELECT course_name FROM courses
UNION ALL
SELECT c.course_name FROM enrollments e
JOIN courses c ON e.course_id = c.course_id;

8. Get all student IDs and instructor IDs (with duplicates)
SELECT student_id FROM students
UNION ALL
SELECT instructor_id FROM instructors;

9. Get all students and instructors from a specific department
SELECT first_name, department FROM students WHERE major = 'Computer Science'
UNION ALL
SELECT first_name, department FROM instructors WHERE department = 'Computer Science';

10. Get all instructors and students in descending order
SELECT first_name FROM instructors
UNION ALL
SELECT first_name FROM students
ORDER BY first_name DESC;


```

## INTERSECT returns only the common records between two queries.

```sql

1. Find student IDs that exist in both enrollments and grades
SELECT student_id FROM enrollments
INTERSECT
SELECT student_id FROM grades;

2. Find common first names between students and instructors
SELECT first_name FROM students
INTERSECT
SELECT first_name FROM instructors;

3. Find common course IDs between enrollments and grades
SELECT course_id FROM enrollments
INTERSECT
SELECT course_id FROM grades;

4. Find students who are also instructors
SELECT student_id FROM students
INTERSECT
SELECT instructor_id FROM instructors;

5. Find common emails between students and instructors
SELECT email FROM students
INTERSECT
SELECT email FROM instructors;

6. Find courses that are both assigned to instructors and have enrollments
SELECT course_id FROM course_instructors
INTERSECT
SELECT course_id FROM enrollments;

7. Find students enrolled in the same courses they received grades for
SELECT student_id, course_id FROM enrollments
INTERSECT
SELECT student_id, course_id FROM grades;

8. Find instructors who are also students
SELECT first_name FROM students
INTERSECT
SELECT first_name FROM instructors;

9. Find courses with the same name in both the courses table and enrollments
SELECT course_name FROM courses
INTERSECT
SELECT DISTINCT c.course_name FROM enrollments e
JOIN courses c ON e.course_id = c.course_id;

10. Find students who have the same last name as instructors
SELECT last_name FROM students
INTERSECT
SELECT last_name FROM instructors;


```


## EXCEPT returns records from the first query that do not exist in the second query.

```sql

1. Find students who are enrolled but don’t have grades
SELECT student_id FROM enrollments
EXCEPT
SELECT student_id FROM grades;

2. Find students who are not also instructors
SELECT student_id FROM students
EXCEPT
SELECT instructor_id FROM instructors;

3. Find instructors who have not been assigned to any courses
SELECT instructor_id FROM instructors
EXCEPT
SELECT instructor_id FROM course_instructors;

4. Find courses that have enrollments but no grades
SELECT course_id FROM enrollments
EXCEPT
SELECT course_id FROM grades;

5. Find emails that belong only to students, not instructors
SELECT email FROM students
EXCEPT
SELECT email FROM instructors;

6. Find courses that are offered but have no enrollments
SELECT course_id FROM courses
EXCEPT
SELECT course_id FROM enrollments;

7. Find students who have never taken a course
SELECT student_id FROM students
EXCEPT
SELECT student_id FROM enrollments;

8. Find instructors who have never taught a course
SELECT instructor_id FROM instructors
EXCEPT
SELECT instructor_id FROM course_instructors;

9. Find students who have never received a grade
SELECT student_id FROM students
EXCEPT
SELECT student_id FROM grades;

10. Find departments that have instructors but no courses
SELECT department FROM instructors
EXCEPT
SELECT department FROM courses;


```