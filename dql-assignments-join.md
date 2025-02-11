
## Inner Join
```sql
1. Get student details along with their enrolled courses(Enrollments & Courses)

2. Get students and their grades(grades & courses

3. Get all enrollments with student and course details(Students & Courses)

4. List instructors and the courses they teach(Course_Instructors & Courses)

5. Find students who have received a grade in a course(Grades & Courses)

6. Find courses that have enrollments(enrollments)

7. Find instructors assigned to a specific department(Computer science) (course_instructors & Courses)

8. Get students who have taken courses from more than one department(ENrollments & Courses) 

9. Find students who scored an 'A' in any course(Grades & Courses)

10. Find the total number of enrollments per instructor(Course_instructors & Enrollments)
```

## Full Outer Join

```sql

 1. Get all students and their enrollments (even if they havent enrolled)
 
 2. Get all courses and their enrollments (even if they have no enrollments)

 3. Get all instructors and their courses (even if they are not teaching)

 4. Get all students and their grades (including those without grades)

 5. List all courses and instructors (even if they are not assigned)

 6. Find students who have never taken a course

 7. Find courses that have never been taken

 8. Find students and courses they may have taken (including those with no enrollments)

 9. Find all instructors and students (regardless of whether they are teaching or enrolled)

 10. Get all students and grades (even if they don’t have a grade)
```

## LEFT Outer Join

```sql
1. Get all students and their enrollments (include those without enrollments)

2. Get all courses and their enrollments (include courses with no students)

3. Get all instructors and the courses they teach (include those not assigned)

4. Get all students and their grades (include students with no grades)

5. Find students who havent enrolled in any courses

6. Find courses with no enrollments

```

## RIGHT Outer Join

```sql
1. Get all courses and students who enrolled (include empty courses)

2. Get all enrollments with student details (include enrollments without students)

3. Get all courses and their enrollments (include courses without students)

4. Get all grades along with student details (include grades without student info)

5. Get all courses and the instructors teaching them (include unassigned courses)

6. Get all enrollments with student and course details (include enrollments without students/courses)

7. Get all instructors and their departments (include instructors without a department)

8. Get all students and their enrollments (include enrollments without students)

9. Get all courses and their enrollments (include courses without students)

10. Get all instructors and the number of courses they teach (include instructors without courses)
```
