# Day 4

4th day of focused Postgresql learning

### [Learn PostgreSQL Tutorial - Full Course for Beginners](https://www.youtube.com/watch?v=qw--VYLpxG4)




```bash
sudo -u postgres psql
```

```SQL

SELECT id, make, model, price, ROUND(price * .10,2) AS "10% Discount", ROUND(price - (price * .10),2) AS
"Discounted Price" FROM car LIMIT 5;

 id |  make   |     model     |  price  | 10% Discount | Discounted Price
----+---------+---------------+---------+--------------+------------------
  1 | Pontiac | Grand Am      | 7146.72 |       714.67 |          6432.05
  2 | Dodge   | Ram 1500 Club | 6498.32 |       649.83 |          5848.49
  3 | Hyundai | Accent        | 6992.11 |       699.21 |          6292.90
  4 | Suzuki  | Esteem        | 1461.30 |       146.13 |          1315.17
  5 | Lincoln | Town Car      | 1190.14 |       119.01 |          1071.13
(5 rows)


COALESCE --finds first non-null value in an array. Can add characters to null rows?

SELECT COALESCE(email, 'Email not provided') FROM person3;

      coalesce
-----------------------
 Email not provided
 tom@email.com
 michael@email.com
 hphilpotts0@cdc.gov
 hsolleme1@soup.io
 pfransoni2@nsw.gov.au
 Email not provided
 adreye5@netscape.com
 Email not provided
 gbradbeer8@weibo.com


 NULLIF --keyword

 "Dividing by 0"

 SELECT 10 / NULLIF(0,0);

 ?column?
----------

(1 row)

SELECT COALESCE(10 / NULLIF(0,0), 0);

 coalesce
----------
        0


SELECT NOW(); --get current year and time

--
SELECT NOW() - INTERVAL '1 YEAR';

           last_year
-------------------------------
 2022-08-30 05:54:14.255928-07

SELECT EXTRACT(YEAR FROM NOW());

 extract
---------
    2023


ALTER TABLE person ADD PRIMARY KEY(id); --add primary key constraint. Has to be unique

SELECT email, COUNT(*) FROM person3 GROUP BY email HAVING COUNT(*) > 1; --find non-unique emails

UNIQUE CONSTRAINT --unique value per column

ALTER TABLE person3 ADD CONSTRAINT unique_email UNIQUE(email);

CHECK CONSTRAINT

ALTER TABLE person3 ADD CONSTRAINT constraint_name CHECK(gender = 'Female');

UPDATE table_name SET column_name = update_value, column_name_2 = update_value_2 WHERE id = id_number;

```