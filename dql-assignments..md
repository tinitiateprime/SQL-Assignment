# DQL Assignments Solutions

## Select

```sql
1. Select all columns from students table

2. Select specific columns (first_name and last_name) from students

3. Select unique majors (DISTINCT) from Students table

4. Select the total number of students 

5. Select students with a calculated/concatenated column (Full Name) 

6. Select students with a formatted dob(date(yyyy-mm-dd)) 

7. Select students and alias columns

8. Select courses and calculate credit weight( * 2)
 
9. Select students and return lowercase email
 
10. Select students and show their age

11. Get the students from 'Computer Science' major

12. Get the COUNT of students in each major
 
13. Get all the courses for engineering department
 
14. Get Count for courses per department from courses 
 
15. Get All the recods from Enrollments for student_id = 101

16. Get Count for enrollments per course_id from enrollments 

17. Get student_id and course_id who got grade 'A'

18. Get COUNT grade per course from the grades table

19. Get all instructors from 'Computer Science' department

20. Get COUNT instructors per department from instructors

21. Get all courses taught by a specific instructor instructor_id = 501 (course_instructor,courses,instructors)

22. Get  COUNT courses per instructor from course_instructors 

```

## Where

```sql

1. Select students where major is 'Computer Science'

2. Select students born after 2002

3. Select courses where credits are greater than or equal to 4

4. Select students where last name starts with 'J'

5. Select students with a NULL email

6. Select students enrolled in Mathematics or Physics

7. Select students not in the Biology department

8. Select students with ID between 100 and 200

9. Select students whose email ends with 'university.edu'

10. Select enrollments made in the last 30 days

```
## Group by

```sql

1. Count students per major

2. Count students by year of birth

3. Sum of credits per department

4. Average student age per major

5. Count enrollments per course

6. Find the earliest enrollment date per course

7. Find highest and lowest grades per course

8. Count students per year of enrollment

9. Count instructors per department

10. Calculate average course credits per department

```
## Having

```sql

1. Count students per major and filter those with more than 5 students

2. Find courses with more than 3 enrollments

3. Find majors where the average student age is greater than 22

4. Find departments with more than 10 courses

5. Find courses with an average grade below 'B'

6. Find departments with total credit hours exceeding 50

7. Find instructors teaching more than 2 courses

8. Find students enrolled in more than 3 courses

9. Find courses with at least one student who received an 'A'

10. Find birth years where more than 5 students were born
```

## Order by 
```sql
1. Order students by last name alphabetically

2. Order students by birthdate, oldest first

3. Order courses by credits in descending order

4. Order students by major, then by first name

5. Order enrollments by enrollment date, newest first

6. Order students by age (oldest first)

7. Order instructors by department, then by last name

8. Order courses by department, then by number of credits

9. Order grades by student_id and grade (A first)

10. Order students by email in descending order
```
