# DML Assignments 

## Insert 

```sql
INSERT INTO students  
101, 'Alice', 'Johnson', '2002-06-15', 'alice.johnson@email.com', 'Computer Science'
102, 'Bob', 'Smith', '2001-09-21', 'bob.smith@email.com', 'Mathematics'
103, 'Charlie', 'Brown', '2003-01-12', 'charlie.brown@email.com', 'Physics'
104, 'David', 'Clark', '2002-05-10', 'david.clark@email.com', 'Engineering' 
105, 'Emma', 'Williams', '2001-11-30', 'emma.williams@email.com', 'Biology' 

INSERT INTO courses 
201, 'Database Systems', 'Computer Science', 4 
202, 'Linear Algebra', 'Mathematics', 3 
203, 'Quantum Mechanics', 'Physics', 4 
204, 'Structural Engineering', 'Engineering', 3 
205, 'Genetics', 'Biology', 3 

INSERT INTO enrollments 
301, 101, 201, '2023-01-10' 
302, 102, 202, '2023-01-15' 
303, 103, 203, '2023-01-20' 
304, 104, 204, '2023-02-01' 
305, 101, 202, '2023-02-05' 

INSERT INTO grades
401, 101, 201, 'A' 
402, 102, 202, 'B' 
403, 103, 203, 'A' 
404, 104, 204, 'C' 
405, 101, 202, 'B' 

INSERT INTO instructors
501, 'Dr. John', 'Doe', 'Computer Science', 'john.doe@university.edu' 
502, 'Dr. Sarah', 'Lee', 'Mathematics', 'sarah.lee@university.edu' 
503, 'Dr. Mike', 'Brown', 'Physics', 'mike.brown@university.edu' 
504, 'Dr. Emily', 'Davis', 'Engineering', 'emily.davis@university.edu' 
505, 'Dr. Robert', 'Taylor', 'Biology', 'robert.taylor@university.edu' 

INSERT INTO course_instructors 
 201, 501 
 202, 502 
 203, 503 
 204, 504 
 205, 501 

```

## Update 

```sql

UPDATE a students  major to 'Data Science'  for student_id = 103

UPDATE credits to 5 for course_id = 201 in courses table

UPDATE enrollment_date = '2023-02-10'   for enrollment_id = 301 in enrollments table 

UPDATE grade = 'A'  for grade_id = 402 in grades table

UPDATE email = 'mike.brown@updated.edu' for instructor_id = 503 in  instructors table

UPDATE instructor_id = 502  for course_id = 205  in course_instructors 
```

## Delete

```sql

DELETE   student who student_id is 105

DELETE course_id = 205 from courses 
 
DELETE enrollment_id = 305 FROM enrollments 

DELETE grade_id = 405 FROM grades 

DELETE course_id = 205 FROM course_instructors 
 
DELETE instructor_id = 505 FROM instructors 

``` 
