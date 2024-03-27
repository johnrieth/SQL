# Day 3

3rd day of focused Postgresql learning

### [Learn PostgreSQL Tutorial - Full Course for Beginners](https://www.youtube.com/watch?v=qw--VYLpxG4)




```bash
sudo -u postgres psql
```

```SQL

HAVING --filtering when using GROUP BY?

SELECT * FROM person3 WHERE email LIKE '%.com';
--
 id | first_name | last_name | gender | date_of_birth |            email            | country_of_origin
----+------------+-----------+--------+---------------+-----------------------------+-------------------
  2 | Tom        | Smith     | Male   | 1990-03-03    | tom@email.com               |
  3 | Michael    | Michaels  | Male   | 1970-11-09    | michael@email.com           |
  8 | Alanna     | Dreye     | Female | 2005-02-06    | adreye5@netscape.com        | Russia
 10 | Gussi      | Bradbeer  | Female | 2010-11-21    | gbradbeer8@weibo.com        | Indonesia
 11 | Guss       | Chennells | Male   | 1987-11-17    | gchennellsa@squarespace.com | Canada
 13 | Marya      | Joysey    | Female | 1984-02-19    | mjoyseyc@salon.com          | Saudi Arabia
 14 | Clay       | Tugman    | Male   | 2017-08-17    | ctugmand@google.com         | Russia
 16 | Tiebout    | Tollit    | Male   | 1985-03-04    | ttollitf@accuweather.com    | China
 18 | Orin       | Ferber    | Male   | 2012-06-17    | oferberi@techcrunch.com     | Venezuela
 19 | Les        | Tomsett   | Male   | 1999-03-08    | ltomsettj@hp.com            | Mexico


SELECT * FROM person3 WHERE email LIKE '%@bloomberg.com';
--
 id  | first_name | last_name | gender | date_of_birth |          email           | country_of_origin
-----+------------+-----------+--------+---------------+--------------------------+-------------------
 395 | Gerrard    | Wellan    | Male   | 2008-09-22    | gwellanc1@bloomberg.com  | Indonesia
 640 | Dari       | Methley   | Female | 2007-03-01    | dmethleyjp@bloomberg.com | Philippines

SELECT * FROM person3 WHERE email LIKE '%google.%';
--
 id  | first_name |   last_name   | gender | date_of_birth |             email              | country_of_origin
-----+------------+---------------+--------+---------------+--------------------------------+-------------------
  14 | Clay       | Tugman        | Male   | 2017-08-17    | ctugmand@google.com            | Russia
  38 | Harald     | Wrigglesworth | Male   | 2006-09-22    | hwrigglesworth15@google.com.hk | China
  41 | Miran      | Cafferty      | Female | 2007-10-02    | mcafferty18@google.es          | Albania
 164 | Eamon      | Zanolli       | Male   | 1983-07-26    | ezanolli52@google.fr           | China
 227 | Joly       | Tulloch       | Female | 1993-07-08    | jtulloch6y@google.es           | Japan
 228 | Lesley     | Abazi         | Female | 1991-07-10    | labazi6z@google.fr             | Portugal
 277 | Gun        | Bremmell      | Male   | 2003-02-17    | gbremmell8g@google.com.hk      | Russia
 324 | Alexandra  | Houtby        | Female | 2015-04-10    | ahoutby9x@google.cn            | Russia
 331 | Tedd       | Bendson       | Male   | 2001-11-09    | tbendsona4@google.es           | Finland
 470 | Gwennie    | Edeler        | Female | 2017-09-08    | gedelered@google.de            | Venezuela

 
SELECT * FROM person3 WHERE country_of_origin ILIKE 'p%';
--
id | first_name | last_name | gender | date_of_birth |         email         | country_of_origin
----+------------+-----------+--------+---------------+-----------------------+-------------------
 21 | Mirelle    | Mougin    | Female | 2003-12-05    |                       | Portugal
 23 | Andris     | Evetts    | Male   | 2000-12-02    | aevettsn@jigsy.com    | Poland
 51 | Gaelan     | Akram     | Male   | 2004-10-04    | gakram1k@hatena.ne.jp | Peru
 57 | Genny      | McGuiney  | Female | 2022-07-17    |                       | Philippines
 60 | Cynde      | Eden      | Female | 1996-08-18    | ceden1u@opera.com     | Peru
 72 | Myca       | MacNish   | Male   | 1987-10-12    | mmacnish27@noaa.gov   | Portugal
 73 | Janaye     | Hugk      | Female | 1997-10-22    |                       | Philippines


SELECT country_of_origin, COUNT(*) FROM person3 GROUP BY country_of_origin ORDER BY COUNT(*);

 country_of_origin | count
-------------------+-------
 China             |   167
 Indonesia         |   100
 Russia            |    55
 Philippines       |    46
 Portugal          |    33
 France            |    29
 Brazil            |    28
 Poland            |    23
 Sweden            |    21
 United States     |    19


SELECT country_of_origin, COUNT(*) FROM person3
GROUP BY country_of_origin
HAVING COUNT(*) > 25
ORDER BY COUNT(*) DESC;

 country_of_origin | count
-------------------+-------
 China             |   167
 Indonesia         |   100
 Russia            |    55
 Philippines       |    46
 Portugal          |    33
 France            |    29
 Brazil            |    28


SELECT make, MAX(price) FROM car GROUP BY make;

  make   |   max
---------+---------
 GMC     | 9902.15
 Maybach | 9413.69
 Lincoln | 8882.63
 Honda   | 9606.22
 Ram     | 7931.24
 Spyker  | 7977.46
 Daewoo  | 4604.04

 --

 SELECT make, MAX(price) FROM car;

ERROR:  column "car.make" must appear in the GROUP BY clause or be used in an aggregate function
LINE 1: SELECT make, MAX(price) FROM car;

SELECT make, ROUND(AVG(price),2) AS "Average Cost" FROM car GROUP BY make;
--
  make   | Average Cost
---------+--------------
 GMC     |      5451.03
 Maybach |      4381.20
 Lincoln |      5245.50
 Honda   |      5561.35
 Ram     |      7931.24
 Spyker  |      4537.38
 Daewoo  |      4604.04

SELECT 10 + 2;

```