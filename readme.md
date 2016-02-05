# MYSQL I

### Naming Conventions

- Avoid using names like "FirstName" or "All Employees".
- Ex: Use Lowercase: first_name, not "First_Name".
- Ex: Use Underscores separate words: word_count or team_member_id, not wordcount or wordCount.
- Ex: Use Full words, not abbreviations: middle_name, not mid_nm.
- Ex: Avoid using reserved words like user, lock, or table.

### Simple commands
connect

	mysql -u root -p

CREATE database

	CREATE DATABASE shop

SHOW all databases

	SHOW DATABASES;

### Table
simple CREATE TABLE

    CREATE TABLE purchases (
    	id int AUTO_INCREMENT PRIMARY KEY,
        total_value double,
        purchase_date date,
        description varchar(255),
        comments varchar(255),
        bankline tinyint,
	);

or with ENUM, DEFAULT ...

    CREATE TABLE purchases (
        id int AUTO_INCREMENT,
        total_value double,
        purchase_date date,
        description varchar(255) NOT NULL,
        comments varchar(255),
        bankline tinyint DEFAULT 1,
        payment_type ENUM('CARD','CASH','TRANSFER'),
        user_id int,
        PRIMARY KEY (id)
    );

    CREATE TABLE users (
    	id int AUTO_INCREMENT,
        name VARCHAR(100) NOT NULL,
        email VARCHAR(255) NOT NULL,
		phone VARCHAR(20),
        PRIMARY KEY (id)
    );


# TABLE EXAMPLE purchases

| id | total_value | purchase_date | description | comments | bankline | payment_type | user_id |
|----|-------------|---------------|-------------|----------|----------|--------------|---------|
|1 | 200|  2015-01-01 | snack | snack| 1 | TRANSFER| 2 |
|2 | 200|  2015-01-01 | snack | snack| 1 | TRANSFER| 1 |
|3 | 400|  2015-01-02 | lunch | lunch| 1 | TRANSFER| 2 |
|4 | 650|  2015-01-04 | supermarket | supermarket| 0 | TRANSFER| 2 |
|5 | 100|  2015-02-01 | bike repair | bike repair| 0 | TRANSFER| 1 |
|6 | 1200| 2015-02-08 | lunch | lunch| 1 | TRANSFER| 1 |
|7 | 200|  2015-02-07 | dinner | dinner| 1 | TRANSFER| 2 |
|8 | 300|  2015-02-01 | supermarket | supermarket| 0 | TRANSFER| 2 |
|9 | 400|  2015-02-06 | lunch | lunch| 1 | TRANSFER| 1 |
|10| 500|  2015-02-01 | underground passage | underground passage| 1 | TRANSFER| 1 |
|11| 600|  2015-03-08 | bike repair | bike repair| 0 | TRANSFER| 1 |
|12| 700|  2015-03-01 | supermarket | supermarket| 0 | TRANSFER| 2 |
|13| 800|  2015-03-09 | payment power | payment power| 1 | TRANSFER| 2 |
|14| 900|  2015-03-01 | dinner | dinner| 0 | TRANSFER| 2 |
|15| 1000| 2015-03-04 | lunch | lunch| 0 | TRANSFER| 1 |
|16| 1200| 2015-03-06 | bike repair | bike repair| 1 | TRANSFER| 1 |
|17| 1300| 2015-03-05 | snack | snack| 1 | TRANSFER| 2 |
|18| 20|   2015-03-06 | underground passage | underground passage| 0 | TRANSFER| 2 |
|19| 40|   2015-04-07 | supermarket | supermarket| 0 | TRANSFER| 2 |
|20| 60|   2015-04-11 | lunch | lunch| 0 | CARD| 1 |
|21| 70|   2015-04-21 | buy clothes | buy clothes| 0 | CARD| 1 |
|22| 80|   2015-04-11 | dinner | dinner| 0 | CARD| 1 |
|23| 90|   2015-04-02 | payment power | payment power| 0 | CARD| 1 |
|24| 15|   2015-05-03 | supermarket | supermarket| 0 | CARD| 2 |
|25| 25|   2015-05-04 | snack | snack| 1 | CARD| 1 |
|26| 100|  2015-05-25 | lunch | lunch| 1 | CARD| 1 |
|27| 200|  2015-05-12 | underground passage | underground passage| 0 | CARD| 2 |
|28| 300|  2015-05-15 | dinner | dinner| 1 | CARD| 1 |
|29| 400|  2015-05-20 | snack | snack| 0 | CARD| 2 |
|30| 500|  2015-06-30 | supermarket | supermarket| 0 | CARD| 1 |
|31| 600|  2015-06-01 | buy clothes | buy clothes| 0 | CARD| 2 |
|32| 700|  2015-06-11 | lunch | lunch| 0 | CARD| 1 |
|33| 800|  2015-06-21 | snack | snack| 0 | CARD| 2 |
|34| 900|  2015-06-01 | dinner | dinner| 0 | CARD| 1 |
|35| 21|   2015-07-05 | supermarket | supermarket| 0 | CARD| 1 |
|36| 22|   2015-07-09 | underground passage | underground passage| 1 | CARD| 1 |
|37| 23|   2015-07-15 | lunch | lunch| 1 | CARD| 1 |
|38| 24|   2015-07-20 | snack | snack| 0 | CARD| 1 |
|39| 125|  2015-08-30 | bike repair | bike repair| 1 | CARD| 2 |
|40| 226|  2015-08-05 | supermarket | supermarket| 0 | | 1 |
|41| 2000| 2015-08-09 | lunch | lunch| 0 | | 2 |
|42| 201|  2015-08-10 | payment power | payment power| 0 | | 1 |
|43| 320|  2015-08-15 | dinner | dinner| 0 | | 1 |
|44| 10|   2015-08-21 | buy clothes | buy clothes| 0 | | 2 |
|45| 240|  2015-08-10 | bike repair | bike repair| 0 | | 1 |
|46| 520|  2015-09-01 | supermarket | supermarket| 0 | | 1 |
|47| 920|  2015-09-05 | snack | snack| 1 | | 2 |
|48| 1220| 2015-09-02 | underground passage | underground passage| 1 | | 1 |
|49| 220|  2015-09-30 | dinner | dinner| 0 | | 2 |
|50| 20|   2015-10-25 | supermarket | supermarket| 0 | | 1 |
|51| 220|  2015-10-20 | lunch | lunch| 0 | | 1 |
|52| 21|   2015-11-15 | supermarket | supermarket| 0 | | 2 |
|53| 20|   2015-11-10 | snack | snack| 0 | | 1 |
|54| 23|   2015-12-05 | supermarket | supermarket| 1 | | 2 |
|55| 29|   2015-12-04 | buy clothes | buy clothes| 1 | | 1 |

### TABLE users

| id | name | email | phone |
| --- | --- | --- | --- |
| 1 | Mike Sun | mikesun@gmail.com | 5555-9999 |
| 2 | John Wood | mikewood@gmail.com | 5555-1234 |

describe TABLE

	DESC purchases

|Field|Type|Null|Key|Default|Extra|
|--------|--------|--------|--------|--------|--------|
|id				|int(11)		|NO	 |	PRI	|NULL	|auto_increment|
|total_value	|double			|YES	||	NULL	||
|purchase_date	|date			|YES	||	NULL	||
|description	|varchar(255)	|YES	||	NULL	||
|comments		|varchar(255)	|YES		||NULL	||
|bankline		|tinyint(1)		|YES	||	0	||
|payment_type	|enum('CARD','CASH','TRANSFER')	|YES	||	NULL	||
|user_id		|int(11)		|YES	|MUL	|NULL	|||

ALTER TABLE COLUMN

	ALTER TABLE purchases MODIFY COLUMN comments VARCHAR(120);

ALTER COLUMN name

	ALTER TABLE purchases CHANGE comments new_comments varchar(255);

### Select
simple SELECT

	SELECT * FROM purchases WHERE purchase_date >= '2015-10-01';

| id | total_value | purchase_date | description | comments | bankline | payment_type | user_id |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 50 | 20 | 2015-10-25 | supermarket | supermarket | 0 || 1 `[->]` |
| 51 | 220 | 2015-10-20 | lunch | lunch | 0 || 1 `[->]` |
| 52 | 21 | 2015-11-15 | supermarket | supermarket | 0 || 2 `[->]` |
| 53 | 20 | 2015-11-10 | snack | snack | 0 				|| 1 `[->]` |
| 54 | 23 | 2015-12-05 | supermarket | supermarket | 1 || 2 `[->]` |
| 55 | 29 | 2015-12-04 | buy clothes | buy clothes | 1 || 1 `[->]` |

SELECT column

	SELECT description, total_value, purchase_date FROM purchases WHERE purchase_date >= '2015-10-01';

| description | total_value | purchase_date |
| --- | --- | --- |
| supermarket | 20 | 2015-10-25 |
| lunch | 220 | 2015-10-20 |
| supermarket | 21 | 2015-11-15 |
| snack | 20 | 2015-11-10 |
| supermarket | 23 | 2015-12-05 |
| buy clothes | 29 | 2015-12-04 |

AND

	SELECT * FROM purchases WHERE total_value >= 50 AND total_value <= 300 AND description LIKE '%bike%';

| id | total_value | purchase_date | description | comments | bankline | payment_type | user_id |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 5 | 100 | 2015-02-01 | bike repair | bike repair | 0 | TRANSFER | 1 `[->]` |
| 39 | 125 | 2015-08-30 | bike repair | bike repair | 1 | CARD | 2 `[->]` |
| 45 | 240 | 2015-08-10 | bike repair | bike repair | 0 || 1 `[->]` |

LIKE

	SELECT * FROM purchases WHERE total_value >= 10 AND total_value <= 100 AND description LIKE 'supermarket%';

OR

	SELECT * FROM purchases WHERE bankline = 1 OR total_value > 1000;

AS

	SELECT AVG(total_value) AS Avg, SUM(total_value) AS Total FROM purchases

| Avg | Total |
| --- | --- |
| 399.54 | 21975 |

OR group

	SELECT * FROM purchases WHERE (total_value >= 800 AND total_value <= 1000) OR (total_value > 1300);

| id | total_value | purchase_date | description | comments | bankline | payment_type | user_id |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 13 | 800 | 2015-03-09 | payment power | payment power | 1 | TRANSFER | 2 `[->]` |
| 14 | 900 | 2015-03-01 | dinner | dinner | 0 | TRANSFER | 2 `[->]` |
| 15 | 1000 | 2015-03-04 | lunch | lunch | 0 | TRANSFER | 1 `[->]` |
| 33 | 800 | 2015-06-21 | snack | snack | 0 | CARD | 2 `[->]` |
| 34 | 900 | 2015-06-01 | dinner | dinner | 0 | CARD | 1 `[->]` |
| 41 | 2000 | 2015-08-09 | lunch | lunch | 0 || 2 `[->]` |
| 47 | 920 | 2015-09-05 | snack | snack | 1 || 2 `[->]` |

BETWEEN values

	SELECT * FROM purchases WHERE total_value BETWEEN 400 AND 700;

BETWEEN dates

	SELECT * FROM purchases WHERE purchase_date BETWEEN '2015-05-05' AND '2015-06-25';

### Update

UPDATE all entries

	UPDATE purchases SET comments = 'emergency';

UPDATE WHERE BETWEEN

	UPDATE purchases SET comments = 'using savings' WHERE purchase_date BETWEEN '2015-05-05' AND '2015-06-25';

UPDATE WHERE BETWEEN multiple fields

	UPDATE purchases SET comments = 'paid online with bonus during vacation', bankline = 1 WHERE purchase_date BETWEEN '2015-07-01' AND '2015-08-01';

UPDATE IN

	UPDATE purchases SET comments = 'holidays' WHERE purchase_date IN('2015-12-25', '2015-10-12', '2015-06-12');

UPDATE WHERE dates

	UPDATE purchases SET total_value = '10.00' WHERE purchase_date < '2015-09-01';

UPDATE increase value

	UPDATE purchases SET total_value = total_value + 10 WHERE purchase_date < '2015-06-01';

### NOT

UPDATE NOT

	UPDATE purchases SET comments = 'using savings' WHERE purchase_date NOT BETWEEN '2015-05-05' AND '2015-06-25';

SELECT NOT

	SELECT * FROM purchases WHERE NOT total_value = 200;


### ADD COLUMN

	ALTER TABLE purchases ADD COLUMN user_id int;

###ENUM

	ALTER TABLE purchases ADD COLUMN payment_type ENUM('CARD','CASH','TRANSFER');

UPDATE ENUM COLUMN

	UPDATE purchases SET payment_type = 'TRANSFER' WHERE payment_type IS NULL;

CREATE TABLE with ENUM

	CREATE TABLE users (
        name VARCHAR(100) NOT NULL,
        role ENUM('DIRECTOR', 'EMPLOYEE') NOT NULL,
		salary DECIMAL(10,2) DEFAULT '10000'
    )

### ALTER DEFAULT values

	ALTER TABLE purchases MODIFY COLUMN bankline TINYINT(1) DEFAULT '0';

NOT NULL

	ALTER TABLE purchases MODIFY COLUMN description TEXT NOT NULL;

### SUM

	SELECT SUM(total_value) FROM purchases;

| SUM(total_value) |
| --- |
| 21975 |

AS

	SELECT SUM(total_value) AS Value FROM purchases;

| Value |
| --- |
| 21975 |

SUM GROUP BY

	SELECT bankline, SUM(total_value) FROM purchases GROUP BY bankline;

| bankline | SUM(total_value) |
| --- | --- |
| 0 | 12788 |
| 1 | 9187 |

### AVG

	SELECT AVG(total_value) FROM purchases;

| AVG(total_value) |
| --- |
| 399.54 |

AVG WHERE

    SELECT AVG(total_value) FROM purchases WHERE purchase_date < '2015-05-12';

| AVG(total_value) |
| --- |
| 442 |

AVG GROUP BY

	SELECT bankline, AVG(total_value) FROM purchases GROUP BY bankline;

### SUM + GROUP BY

	SELECT 	bankline,
            payment_type,
            SUM(total_value)
    FROM purchases
    GROUP BY payment_type, bankline

| bankline | payment_type | SUM(total_value) |
| --- | --- | --- |
| 0 || 4018 |
| 1 || 2192 |
| 0 | CARD | 4460 |
| 1 | CARD | 595 |
| 0 | TRANSFER | 4310 |
| 1 | TRANSFER | 6400 |

### SUM + GROUP BY

    SELECT 	payment_type,
            SUM(total_value)
    FROM purchases 
    WHERE purchase_date < '2015-10-10'
    GROUP BY payment_type;

| payment_type | SUM(total_value) |
| --- | --- |
|| 5877 |
| CARD | 5055 |
| TRANSFER | 10710 |

### SUM + AVG + GROUP BY + ORDER BY

    SELECT 		MONTH(purchase_date),
                YEAR(purchase_date),
                SUM(total_value),
                AVG(total_value)
    FROM purchases
    GROUP BY 	MONTH(purchase_date),
                YEAR(purchase_date)
    ORDER BY 	MONTH(purchase_date),
                YEAR(purchase_date);

| MONTH(purchase_date) | YEAR(purchase_date) | SUM(total_value) | AVG(total_value) |
| --- | --- | --- | --- |
| 1 | 2015 | 1450 | 362.5 |
| 2 | 2015 | 2700 | 450 |
| 3 | 2015 | 6520 | 815 |
| 4 | 2015 | 340 | 68 |
| 5 | 2015 | 1040 | 173.33 |
| 6 | 2015 | 3500 | 700 |
| 7 | 2015 | 90 | 22.5 |
| 8 | 2015 | 3122 | 446 |
| 9 | 2015 | 2880 | 720 |
| 10 | 2015 | 240 | 120 |
| 11 | 2015 | 41 | 20.5 |
| 12 | 2015 | 52 | 26 |

### COUNT

	SELECT COUNT(id) FROM purchases WHERE purchase_date < '2015-05-12';

### FLOOR + RAND

	UPDATE purchases SET user_id = FLOOR( 1 + RAND( ) *2 );

### FOREIGN KEY

	ALTER TABLE purchases
    ADD FOREIGN KEY (user_id)
    REFERENCES users(id)

### INNER JOIN GROUP BY

	SELECT 	name,
    		SUM(total_value)
    FROM purchases
    INNER JOIN users
    ON purchases.user_id = users.id
    GROUP BY name;

or

	SELECT 	name,
    		SUM(total_value)
    FROM purchases
    INNER JOIN users
    ON purchases.user_id = users.id
    GROUP BY name;

| name | SUM(total_value) |
| --- | --- |
| John Wood | 10844 |
| Mike Sun | 11131 |

SELECT

    SELECT 	name,
    		SUM(total_value),
            description
    FROM purchases
    INNER JOIN users
    ON purchases.user_id = users.id
    WHERE user_id = 1
    GROUP BY description

| name | SUM(total_value) | description |
| --- | --- | --- |
| Mike Sun | 2140 | bike repair |
| Mike Sun | 99 | buy clothes |
| Mike Sun | 1600 | dinner |
| Mike Sun | 3703 | lunch |
| Mike Sun | 291 | payment power |
| Mike Sun | 269 | snack |
| Mike Sun | 1287 | supermarket |
| Mike Sun | 1742 | underground passage |

SELECT LIKE

	SELECT *
    FROM purchases
    INNER JOIN users
    ON purchases.user_id = users.id
    WHERE name like 'Mike%'
    GROUP BY description

| id | total_value | purchase_date | description | comments | bankline | payment_type | user_id | id | name | email | phone |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 5 | 100 | 2015-02-01 | bike repair | bike repair | 0 | TRANSFER | 1 `[->]` | 1 | Mike Sun | mikesun@gmail.com | 5555-9999 |
| 21 | 70 | 2015-04-21 | buy clothes | buy clothes | 0 | CARD | 1 `[->]` | 1 | Mike Sun | mikesun@gmail.com | 5555-9999 |
| 22 | 80 | 2015-04-11 | dinner | dinner | 0 | CARD | 1 `[->]` | 1 | Mike Sun | mikesun@gmail.com | 5555-9999 |
| 6 | 1200 | 2015-02-08 | lunch | lunch | 1 | TRANSFER | 1 `[->]` | 1 | Mike Sun | mikesun@gmail.com | 5555-9999 |
| 23 | 90 | 2015-04-02 | payment power | payment power | 0 | CARD | 1 `[->]` | 1 | Mike Sun | mikesun@gmail.com | 5555-9999 |
| 2 | 200 | 2015-01-01 | snack | snack | 1 | TRANSFER | 1 `[->]` | 1 | Mike Sun | mikesun@gmail.com | 5555-9999 |
| 30 | 500 | 2015-06-30 | supermarket | supermarket | 0 | CARD | 1 `[->]` | 1 | Mike Sun | mikesun@gmail.com | 5555-9999 |
| 10 | 500 | 2015-02-01 | underground passage | underground passage | 1 | TRANSFER | 1 `[->]` | 1 | Mike Sun | mikesun@gmail.com | 5555-9999 |

### NOT LIKE

	SELECT * FROM purchases WHERE description NOT LIKE '%bike%' ORDER BY id ASC

### IS NOT NULL

	SELECT * FROM `purchases` WHERE `description` IS NOT NULL ORDER BY `id` ASC


## Restore dump file

	mysql -u root -p < path\to\file\file-dump.sql
