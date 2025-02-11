# DDL Assignments for University

## Create a table for Students 

```sql

Student_id integer
first_name  string
last_name string
dob date
email  string
major string
Add Primary key to student_id

```

## Create a table for Courses 
```sql
    course_id integer  
    course_name String,
    department String,
    credits integer
    Add Primary Key to Course_id
```

## Create a table for Enrollments
```sql
    enrollment_id integer 
    student_id integer 
    course_id integer 
    enrollment_date DATE 
    Add Primary Key to enrollment_id
    Add Foreign Key student_id which is referencing to students table
    Add Foreign Key course_id which is referencing to courses table
```

## Create a table for Grades
```sql
    grade_id integer 
    student_id integer 
    course_id integer 
   
 ```

## Create a table for Grades
```sql
Alter table Grades
to add new column grade String
```

## Alter Table for Grades
```sql
   Alter table to  Add Primary Key to grade_id   
    Add Foreign Key student_id which is referencing to students table
    Add Foreign Key course_id which is referencing to courses table

```
## Create a table for Instructors
```sql

    instructor_id integer,
    first_name String,
    last_name String,
    department String,
    email String
    Add Primary Key to instructor_id   
);
```

## Create a table for course_instructors
```sql
    course_id Integer,
    instructor_id INT,
    Add Primary Key to course_id, instructor_id   
    Add Foreign Key instructor_id which is referencing to instructors table
    Add Foreign Key course_id which is referencing to courses table
    
```