# Assignments for Analytical Functions

## ROW_NUMBER() Function - The ROW_NUMBER() function assigns a unique row number to each row based on the specified order.

```sql

Assign a row number to each student based on their enrollment date.

Assign row numbers to courses ordered by course name.

Rank students based on their total credits.

Number students within each department.

Assign row numbers to instructors by salary (highest to lowest).

Number students who received a grade in each course.

Assign row numbers to enrollments per course.

Assign a unique number to instructors based on years of experience.

Rank students within each department by name.

Assign row numbers to students based on tuition fee (highest to lowest).
```

## RANK() Function - The RANK() function assigns a rank to each row with gaps in case of ties.

```sql
Rank students based on tuition fee (ties allowed).

Rank instructors by salary (ties allowed).

Rank students based on GPA.

Rank courses by the number of enrollments.

Rank students by credits earned in each department.

Rank students by the number of courses taken.

Rank instructors by the number of courses they teach.

Rank students based on fees paid within each department.

Rank students based on attendance.

Rank courses by difficulty level.
```

## DENSE_RANK() Function - The DENSE_RANK() function assigns a rank to each row without skipping any numbers for ties.

```sql
Rank students based on GPA without gaps.

Rank instructors by salary without gaps.

Rank students based on tuition fee.

Rank courses by number of enrollments without gaps.

Rank students based on credits earned per department.

Rank students by the number of courses taken.

Rank instructors by number of courses taught without gaps.

Rank students based on fees paid within each department.

Rank students by attendance without gaps.

Rank courses by difficulty level without gaps.

```

## NTILE(n) Function  - The NTILE(n) function distributes rows into n equal-sized groups.

```sql
Divide students into 4 groups based on tuition fee.

Divide courses into 3 difficulty levels based on enrollments.

Distribute students into 5 equal-sized groups based on GPA.

Divide instructors into 4 salary bands.

Split students into 3 groups based on the number of courses taken.

Group students into 4 attendance performance levels.

Rank students into 2 categories based on tuition fee.

Divide courses into 6 groups based on credits.

Group students into 4 financial aid brackets.

Divide students into 3 participation level groups.

```


## LAG() Function - The LAG() function returns the previous row's value within an ordered partition.

```sql
Compare a students GPA with the previous students GPA.

Compare an instructors salary with the previous instructors salary.

Compare each course’s number of enrollments with the previous course.

Compare student tuition fees with the previous student’s tuition fee.

Track previous course grades of a student.

Compare the previous semesters attendance.

Compare a course’s credit count with the previous one.

Compare students’ financial aid amounts with the previous one.

Compare student participation scores with the previous student.

Compare instructor experience with the previous instructor.
```

## LEAD() Function - The LEAD() function returns the next row's value within an ordered partition.

```sql
Compare a students GPA with the next students GPA.

Compare an instructors salary with the next instructors salary.

Compare each course’s enrollments with the next course.

Compare student tuition fees with the next student’s tuition fee.

Track next course grades of a student.

Compare the next semesters attendance.

Compare a course’s credit count with the next one.

Compare students’ financial aid amounts with the next one.

Compare student participation scores with the next student.

Compare instructor experience with the next instructor.
```

## FIRST_VALUE() Function - The FIRST_VALUE() function returns the first row's value in an ordered partition.

```sql
Get the first student who enrolled.

Get the first instructor hired.

Get the first course created.

Get the first student who paid tuition.

Get the first student in each department based on enrollment.

Get the student with the highest GPA in each department.

Get the first instructor assigned to each course.

Get the first exam taken by each student.

Get the first grade received by each student.

Get the first department created.
```

## LAST_VALUE() Function - The LAST_VALUE() function returns the last row's value in an ordered partition.

```sql
Get the last student who enrolled.

Get the last instructor hired.

Get the last course added.

Get the last student who paid tuition.

Get the last student enrolled in each department.

Get the student with the lowest GPA in each department.

Get the last instructor assigned to each course.

Get the last exam taken by each student.

Get the last grade received by each student.

Get the last department created.

```