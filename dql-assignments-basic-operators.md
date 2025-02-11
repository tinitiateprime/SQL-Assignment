# Assignments for Basic Operators
## Equality Operator (=)

```sql
1️⃣ Find students majoring in 'Computer Science'.
2️⃣ Find courses in the 'Engineering' department.
3️⃣ Find students with student ID 101.
4️⃣ Find instructors from the 'Mathematics' department.
5️⃣ Find enrollments for course ID 202.
6️⃣ Find students whose first name is 'Alice'.
7️⃣ Find students whose email is 'alice@email.com'.
8️⃣ Find courses with exactly 3 credits.
9️⃣ Find students who have received a grade of 'A'.
🔟 Find instructors whose last name is 'Smith'.
```

## Inequality Operator (<> or !=)

```sql

1️⃣ Find students who are not majoring in 'Computer Science'.
2️⃣ Find courses not in the 'Engineering' department.
3️⃣ Find students whose ID is not 101.
4️⃣ Find instructors not from the 'Mathematics' department.
5️⃣ Find students whose first name is not 'Alice'.
6️⃣ Find students whose email is not 'alice@email.com'.
7️⃣ Find courses that do not have 3 credits.
8️⃣ Find students who have not received a grade of 'A'.
9️⃣ Find instructors whose last name is not 'Smith'.
🔟 Find enrollments that are not for course ID 202.
```

## IN Operator

```sql

1️⃣ Find students majoring in 'Computer Science' or 'Mathematics'.
2️⃣ Find courses from the 'Engineering' or 'Biology' departments.
3️⃣ Find students with IDs 101, 102, or 103.
4️⃣ Find instructors in the 'Mathematics' or 'Physics' department.
5️⃣ Find students whose first name is either 'Alice' or 'Bob'.
6️⃣ Find students with email addresses from a given list.
7️⃣ Find courses that have 3 or 4 credits.
8️⃣ Find students who received either 'A' or 'B' in grades.
9️⃣ Find instructors whose last name is either 'Smith' or 'Johnson'.
🔟 Find enrollments for course IDs 202, 203, or 204.
```

## LIKE Operator

```sql


1️⃣ Find students whose first name starts with 'A'.
2️⃣ Find students whose last name ends with 'son'.
3️⃣ Find emails containing 'gmail'.
4️⃣ Find students with a last name containing 'John'.
5️⃣ Find students whose first name is exactly 5 letters long.
6️⃣ Find students whose first name has 'a' in the second position.
7️⃣ Find courses whose name contains 'Data'.
8️⃣ Find instructors with emails ending in '.edu'.
9️⃣ Find students whose email starts with 'alice'.
🔟 Find students whose last name starts with 'J' and ends with 'n'.
```

## NOT LIKE Operator

```sql

1️⃣ Find students whose first name does not start with 'A'.
2️⃣ Find students whose last name does not end with 'son'.
3️⃣ Find emails that do not contain 'gmail'.
4️⃣ Find students whose first name is not exactly 5 letters long.
5️⃣ Find students whose email does not start with 'alice'.
6️⃣ Find instructors with emails not ending in '.edu'.
7️⃣ Find courses whose name does not contain 'Data'.
8️⃣ Find students whose first name does not have 'a' in the second position.
9️⃣ Find students whose last name does not start with 'J' and end with 'n'.
🔟 Find courses that do not have 'AI' in their name.
```

## BETWEEN Operator

```sql

1️⃣ Find students born between 2000 and 2005.
2️⃣ Find courses with credits between 3 and 5.
3️⃣ Find students with IDs between 100 and 200.
4️⃣ Find enrollments made between two specific dates.
5️⃣ Find students whose last names fall alphabetically between 'A' and 'M'.
6️⃣ Find courses whose names fall alphabetically between 'Data Science' and 'Machine Learning'.
7️⃣ Find students whose email addresses start alphabetically between 'a' and 'm'.
8️⃣ Find courses with budgets between $50,000 and $100,000.
9️⃣ Find grades given between 'B' and 'D'.
🔟 Find instructors whose department names are alphabetically between 'Engineering' and 'Physics'.
```


## Greater Than (>) Operator

```sql

1️⃣ Find students born after 2002.
2️⃣ Find courses with more than 3 credits.
3️⃣ Find students with IDs greater than 150.
4️⃣ Find enrollments made after a specific date.
5️⃣ Find instructors with more than 5 assigned courses.
6️⃣ Find students older than 22 years.
7️⃣ Find courses whose names start alphabetically after 'Machine Learning'.
8️⃣ Find students whose last name is alphabetically greater than 'M'.
9️⃣ Find grades greater than 'C'.
🔟 Find enrollments where students enrolled after a specific date.
```
## Greater Than or Equal To (>=) Operator

```sql

1️⃣ Find students born before 2000.
2️⃣ Find courses with at least 3 credits.
3️⃣ Find students with IDs 100 or greater.
4️⃣ Find enrollments made on or after a specific date.
5️⃣ Find instructors teaching at least 3 courses.
6️⃣ Find students aged 18 or older.
7️⃣ Find courses with names alphabetically from 'Machine Learning' onwards.
8️⃣ Find students whose last name is alphabetically greater than or equal to 'M'.
9️⃣ Find grades 'C' and above.
🔟 Find enrollments made on or after a specific date.
```

## EXISTS Operator

```sql
1️⃣ Find students who are enrolled in at least one course.
2️⃣ Find courses that have at least one enrollment.
3️⃣ Find instructors who are assigned to at least one course.
4️⃣ Find students who have received at least one grade.
5️⃣ Find students who have taken courses from the 'Computer Science' department.
6️⃣ Find students who have received an 'A' grade in at least one course.
7️⃣ Find instructors who are teaching 'Data Science' courses.
8️⃣ Find students who have taken at least one course in the last 6 months.
9️⃣ Find students who have received at least one grade below 'C'.
🔟 Find courses that are being taught by at least one instructor.
```

## NOT EXISTS Operator

```sql
1️⃣ Find students who are NOT enrolled in any course.
2️⃣ Find courses that have never been enrolled in.
3️⃣ Find instructors who are NOT assigned to any course.
4️⃣ Find students who have never received a grade.
5️⃣ Find students who have NOT taken any 'Computer Science' courses.
6️⃣ Find students who have NEVER received an 'A' grade.
7️⃣ Find instructors who are NOT teaching 'Data Science' courses.
8️⃣ Find students who have NOT taken any course in the last 6 months.
9️⃣ Find students who have NEVER received a grade below 'C'.
🔟 Find courses that are NOT assigned to any instructor.
```