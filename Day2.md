# Day 2

2nd day of focused Postgresql learning

### [Learn PostgreSQL Tutorial - Full Course for Beginners](https://www.youtube.com/watch?v=qw--VYLpxG4)

```bash
sudo -u postgres psql
```

```SQL
\c database_name --connect to database


ORDER BY --sorts columns by ascending or descending

SELECT * FROM person3
ORDER BY country_of_origin ASC; 

DISTINCT --

WHERE --allows us to filter the data based on conditions

LIMIT --

FETCH -- similar to LIMIT



/*Comparison operators*/
<> --not equal
SELECT 1 = 1;
--
 ?column?
----------
 t
(1 row)
--

SELECT 1 > 2;
--
 ?column?
----------
 f
(1 row)


SELECT * FROM person3 LIMIT 7;
--

 id | first_name | last_name | gender | date_of_birth |         email         | country_of_origin
----+------------+-----------+--------+---------------+-----------------------+-------------------
  1 | Annie      | Smith     | Female | 1988-01-09    |                       |
  2 | Tom        | Smith     | Male   | 1990-03-03    | tom@email.com         |
  3 | Michael    | Michaels  | Male   | 1970-11-09    | michael@email.com     |
  4 | Humfried   | Philpotts | Male   | 2006-08-27    | hphilpotts0@cdc.gov   | Colombia
  5 | Hurlee     | Solleme   | Male   | 2013-01-10    | hsolleme1@soup.io     | China
  6 | Parker     | Fransoni  | Male   | 1981-06-14    | pfransoni2@nsw.gov.au | Russia
  7 | Isa        | Kimbrough | Male   | 2014-09-29    |                       | Costa Rica


SELECT * FROM person3 OFFSET 4 LIMIT 7;
--

 id | first_name | last_name | gender | date_of_birth |            email            | country_of_origin
----+------------+-----------+--------+---------------+-----------------------------+-------------------
  5 | Hurlee     | Solleme   | Male   | 2013-01-10    | hsolleme1@soup.io           | China
  6 | Parker     | Fransoni  | Male   | 1981-06-14    | pfransoni2@nsw.gov.au       | Russia
  7 | Isa        | Kimbrough | Male   | 2014-09-29    |                             | Costa Rica
  8 | Alanna     | Dreye     | Female | 2005-02-06    | adreye5@netscape.com        | Russia
  9 | Kati       | Shyres    | Female | 2023-07-06    |                             | Germany
 10 | Gussi      | Bradbeer  | Female | 2010-11-21    | gbradbeer8@weibo.com        | Indonesia
 11 | Guss       | Chennells | Male   | 1987-11-17    | gchennellsa@squarespace.com | Canada


SELECT * FROM person3 OFFSET 4 FETCH FIRST 7 ROW ONLY;
--
 id | first_name | last_name | gender | date_of_birth |            email            | country_of_origin
----+------------+-----------+--------+---------------+-----------------------------+-------------------
  5 | Hurlee     | Solleme   | Male   | 2013-01-10    | hsolleme1@soup.io           | China
  6 | Parker     | Fransoni  | Male   | 1981-06-14    | pfransoni2@nsw.gov.au       | Russia
  7 | Isa        | Kimbrough | Male   | 2014-09-29    |                             | Costa Rica
  8 | Alanna     | Dreye     | Female | 2005-02-06    | adreye5@netscape.com        | Russia
  9 | Kati       | Shyres    | Female | 2023-07-06    |                             | Germany
 10 | Gussi      | Bradbeer  | Female | 2010-11-21    | gbradbeer8@weibo.com        | Indonesia
 11 | Guss       | Chennells | Male   | 1987-11-17    | gchennellsa@squarespace.com | Canada


SELECT * FROM person3 WHERE country_of_origin IN ('China', 'France', 'Poland');
--
id | first_name | last_name | gender | date_of_birth |          email           | country_of_origin
----+------------+-----------+--------+---------------+--------------------------+-------------------
  5 | Hurlee     | Solleme   | Male   | 2013-01-10    | hsolleme1@soup.io        | China
 12 | Hilary     | Glossup   | Male   | 1995-02-22    |                          | China
 16 | Tiebout    | Tollit    | Male   | 1985-03-04    | ttollitf@accuweather.com | China
 22 | Doralyn    | Fraschini | Female | 1993-12-18    | dfraschinim@jimdo.com    | China
 23 | Andris     | Evetts    | Male   | 2000-12-02    | aevettsn@jigsy.com       | Poland
 30 | Edik       | Shipp     | Male   | 2004-10-21    | eshippv@hc360.com        | China
 31 | Tabina     | Cotes     | Female | 1994-12-06    | tcotesw@diigo.com        | France

```




