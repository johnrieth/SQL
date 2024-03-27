# Day 1

1st day of learning Postgresql

### [PostgreSQL CRASH COURSE - Learn PostgreSQL in 2022](https://www.youtube.com/watch?v=zw4s3Ey8ayo)

Structured Query Language
- columns and rows make up a table
- there can be constraints on columns
- schema is the layout
- uppercase all keywords
- lowecase snakecase for all other
- convention to not pluralize table names. Singular (profile instead of profiles)
- 3 types of basic relationships
  - one to one
  - one to many
  - many to many

```SQL
/* Create a table */
CREATE TABLE profile1(
    id SERIAL PRIMARY KEY, --SERIAL is a special type. integer that is auto incrementing. Primary Key is unique identifier
    name VARCHAR(100), --VARCHAR is text column with a constarint on size. Max is 100 characters
    email VARCHAR(255),
    password TEXT, 
    age INT -- a number
);

CREATE TABLE "user"( -- wrapping keyword in quotes ensures there is no error. Without quotes there would be an error
    id SERIAL PRIMARY KEY,
    name VARCHAR(50)
);

DROP TABLE profile1; --removes table profile1 from the database


INSERT INTO profile1 (name, email, password, age) VALUES ('John', 'john@email.com', 27, 'asfasdfaljaksdlfjl'),
('Chris', 'chris@email.com', 78, 'afssdfsdf'); --single quotes for inserting data. String value


SELECT * FROM profile1; -- select all columns

-- Output
 id | name |     email      | password | age
----+------+----------------+----------+-----
  1 | John | john@email.com | asdfasdf |  27
--

SELECT name, email FROM profile1;

--Output
 name |     email
------+----------------
 John | john@email.com
--

SELECT * FROM profile1
WHERE age < 50;

--Output
 id | name |     email      |   password    | age
----+------+----------------+---------------+-----
  1 | John | john@email.com | asdfasdf      |  27
  2 | Fred | fred@email.com | asdfasasdfdaf |  30
--

UPDATE profile1 SET age = 30
WHERE id = 1; -- updates table with age 30 for user with id of 1

--Output
id | name |     email      | password | age
----+------+----------------+----------+-----
  1 | John | john@email.com | asdfasdf |  30
--

DELETE FROM profile1 WHERE id = 2;

--Output
 id | name |     email      |     password      | age
----+------+----------------+-------------------+-----
  3 | Mary | mary@email.com | asdfasasdasdffdaf |  55
  1 | John | john@email.com | asdfasdf          |  30
--
```

### [Learn PostgreSQL Tutorial - Full Course for Beginners](https://www.youtube.com/watch?v=qw--VYLpxG4)

- place to store, retrieve, manipulate date
- attributes are columns. stuff is rows

```SQL

CREATE DATABASE test1; -- create databse

DROP DATABASE test1; -- delete database

\l -- to show list of all databases

\c database_name -- connect to database

\d --describe. list tables

\d table_name --describe. set up of table

ALTER TABLE table_name ADD column_name data_type;

CREATE TABLE table_name (
    column_name + data_type + constraints
);

    CREATE TABLE person (
        id BIGSERIAL NOT NULL PRIMARY KEY,
        first_name VARCHAR(50) NOT NULL,
        last_name VARCHAR(50) NOT NULL,
        gender VARCHAR(6) NOT NULL,
        date_of_birth DATE NOT NULL
    );

```

### [Postgres Tutorial - Beginners to Advanced](https://www.youtube.com/playlist?list=PL0hSJrxggIQrz5OKtnaFuPiyMDTXUF5J1)

- store and organize data with large amounts of data
- SQL is how we communicate with our database


```SQL
SELECT customer_id, first_name, last_name
FROM sales
ORDER BY first_name;


SELECT column_name FROM table_name; -- syntax for SELECT statement

```