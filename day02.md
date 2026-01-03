## Day2 learning

# How this syntax work? Why we need this?
- insert into
- select
- create view
- innerjoin
- where

# Notes

- insert into use for adding value in the table like INSERT INTO student_info (studentID,Name)
VALUES(001,Abdul);

- SELECT syntax used for slecting from table like SELECT*FROM student_info;

- view its a virtual table created using select query but it does not store data itself.it doesnot waste memory and its reusable .create view is like
CREATE VIEW swe_stud AS
SELECT name, cgpa
FROM IT_students
WHERE dept='swe';

-  INNERJOIN actually return  rows combining from 2 table satisfying the condition like
SELECT students.name,Marks.mark
FROM students
INNER JOIN MARKS
ON students.student_id=MARKS.student_id;

- WHERE is used for adding condition like 
SELECT name FROM students
WHERE roll < 6;