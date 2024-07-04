# Tutorial 1

## Commands in pgsql

```postgres=> \l```

```postgres=> CREATE DATABASE students;```

```postgres=> \l```

```postgres=> \c students```

```students=> CREATE TABLE students();```

```students=> CREATE TABLE majors();```

```students=> CREATE TABLE courses();```

```students=> CREATE TABLE majors_courses();```

```students=> \d```

```students=> ALTER TABLE students ADD COLUMN student_id SERIAL PRIMARY KEY;```

```students=> ALTER TABLE students ADD COLUMN first_name VARCHAR(50) NOT NULL;```

```students=> ALTER TABLE students ADD COLUMN last_name VARCHAR(50) NOT NULL;```

```students=> ALTER TABLE students ADD COLUMN major_id INT;```

```students=> ALTER TABLE students ADD COLUMN gpa NUMERIC(2,1);```

```students=> \d students```

```students=> ALTER TABLE majors ADD COLUMN major_id SERIAL PRIMARY KEY;```

```students=> ALTER TABLE majors ADD COLUMN major VARCHAR(50) NOT NULL;```

```students=> \d majors```

```students=> ALTER TABLE students ADD FOREIGN KEY(major_id) REFERENCES majors(major_id);```

```students=> \d students```

```students=> ALTER TABLE courses ADD COLUMN course_id SERIAL PRIMARY KEY;```

```students=> ALTER TABLE courses ADD COLUMN course VARCHAR(100) NOT NULL;```

```students=> \d courses```

```students=> ALTER TABLE majors_courses ADD COLUMN major_id INT;```

```students=> ALTER TABLE majors_courses ADD FOREIGN KEY(major_id) REFERENCES majors(major_id);```

```students=> ALTER TABLE majors_courses ADD COLUMN course_id INT;```

```students=> ALTER TABLE majors_courses ADD FOREIGN KEY(course_id) REFERENCES courses(course_id);```

```students=> \d majors_courses```

```students=> ALTER TABLE majors_courses ADD PRIMARY KEY(major_id, course_id);```

```students=> \d majors_courses```

```students=> \d```

```students=> \d majors```

```students=>INSERT INTO majors(major) VALUES ('Database Administration');```

```students=> SELECT * FROM majors;```

```students=> INSERT INTO courses(course) VALUES('Data Structures and Algorithms');```

```students=> SELECT * FROM courses;```

```students=> \d majors_courses```

```students=> INSERT INTO majors_courses(major_id, course_id)```

```students=> SELECT * FROM majors_courses;```

```students=> \d students```

```students=> INSERT INTO students(first_name, last_name, major_id, gpa) VALUES ('Rhea', 'Kellems', 1, 2.5);```

```students=> SELECT * FROM students;```

```students=> SELECT * FROM majors;```

```students=> TRUNCATE majors;```

```students=> TRUNCATE majors,students,majors_courses;```

```students=> SELECT * FROM majors;```

```students=> SELECT * FROM majors_courses;```

```students=> SELECT * FROM students;```

```students=> SELECT * FROM courses;```

```students=> TRUNCATE courses,majors_courses;```

```students=> SELECT * FROM courses;```

```students=> SELECT * FROM majors;```

```students=> TRUNCATE majors,students,majors_courses;```

```students=> SELECT * FROM majors;```

## Commands in terminal

```/project$ echo hello SQL```

```/project$ psql --username=freecodecamp --dbname=postgres```

```/project$ touch insert_data.sh```

```/project$ chmod +x insert_data.sh ```

```/project$ ./insert_data.sh```

```/project$ ./insert_data.sh```

```/project$ declare -p IFS```

```/project$ cp courses.csv courses_test.csv```

```/project$ cp students.csv students_test.csv```

```/project$ ls```

```/project$ rm students_test.csv``` 

```/project$ rm courses_test.csv```

```/project$ ls```

```/project$ pg_dump --help```

```/project$ pg_dump --clean --create --inserts --username=freecodecamp students > students.sql```
