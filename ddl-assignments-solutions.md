# DDL Assignments for University
## Create a table for Students 

```sql
CREATE TABLE students (
    student_id INT PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    dob DATE,
    email VARCHAR(100),
    major VARCHAR(50)
);
```

## Create a table for Courses 

```sql
CREATE TABLE courses (
    course_id INT PRIMARY KEY,
    course_name VARCHAR(100),
    department VARCHAR(50),
    credits INT
);
```

## Create a table for Enrollments
```sql
CREATE TABLE enrollments (
    enrollment_id INT PRIMARY KEY,
    student_id INT,
    course_id INT,
    enrollment_date DATE,
    FOREIGN KEY (student_id) REFERENCES students(student_id),
    FOREIGN KEY (course_id) REFERENCES courses(course_id)
);
```


## Create a table for Grades
```sql
CREATE TABLE grades (
    grade_id INT PRIMARY KEY,
    student_id INT,
    course_id INT,
    FOREIGN KEY (student_id) REFERENCES students(student_id),
    FOREIGN KEY (course_id) REFERENCES courses(course_id)
);
```
```sql
ALTER TABLE grades
ADD COLUMN grade VARCHAR(10);

ALTER TABLE grades
ADD CONSTRAINT pk_grade PRIMARY KEY (grade_id);

ALTER TABLE grades
ADD CONSTRAINT fk_student FOREIGN KEY (student_id) REFERENCES students(student_id);

ALTER TABLE grades
ADD CONSTRAINT fk_course FOREIGN KEY (course_id) REFERENCES courses(course_id);

```
## Create a table for Instructors
```sql

CREATE TABLE instructors (
    instructor_id INT PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    department VARCHAR(50),
    email VARCHAR(100)
);
```


## Create a table for course_instructors
```sql
CREATE TABLE course_instructors (
    course_id INT,
    instructor_id INT,
    PRIMARY KEY (course_id, instructor_id),
    FOREIGN KEY (course_id) REFERENCES courses(course_id),
    FOREIGN KEY (instructor_id) REFERENCES instructors(instructor_id)
);
```