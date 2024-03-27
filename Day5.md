# Day 5

5th day of focused Postgresql learning



[FULL SQL DATABASE COURSE | Beginner to Intermediate in 1 Hour](https://www.youtube.com/watch?v=MvcDM2nLdzI)


```SQL
INSERT INTO car(make, model, price) VALUES ('Mazda', 'B-Series', 1000.20) ON CONFLICT (id) DO UPDATE SET price = EXCLUDED.price;


SELECT p3.first_name, c.make, c.model, c.price FROM person3 p3 LEFT JOIN car c ON p3.car_id = c.id LIMIT 3;

 first_name |  make   |  model   |  price
------------+---------+----------+---------
 Annie      | Pontiac | Grand Am | 7146.72
 Kati       | Pontiac | Grand Am | 7146.72
 Clyde      |         |          |


SELECT p3.first_name, p3.email, c.make, c.model, c.price FROM person3 p3 RIGHT JOIN car c ON p3.car_id = c.id LIMIT 3;

 first_name |         email         |  make   |     model     |  price
------------+-----------------------+---------+---------------+---------
 Annie      |                       | Pontiac | Grand Am      | 7146.72
 Kati       |                       | Pontiac | Grand Am      | 7146.72
 Derril     | dwillmont31@alexa.com | Dodge   | Ram 1500 Club | 6498.32

```

Foreign key represents a connection to another table

INNER JOINS

- combining two tables. Takes what is common in both tables

LEFT JOIN
