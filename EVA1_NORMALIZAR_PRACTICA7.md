**EVA1\_NORMALIZAR\_PRACTICA7**



MySQL Shell 8.0.46



Copyright (c) 2016, 2026, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its affiliates.

Other names may be trademarks of their respective owners.



Type '\\help' or '\\?' for help; '\\quit' to exit.

&#x20;MySQL  JS > \\connect root@localhost

Creating a session to 'root@localhost'

Please provide the password for 'root@localhost':

Save password for 'root@localhost'? \[Y]es/\[N]o/Ne\[v]er (default No):

Fetching schema names for auto-completion... Press ^C to stop.

Your MySQL connection id is 10

Server version: 8.4.7 MySQL Community Server - GPL

No default schema selected; type \\use <schema> to set one.

&#x20;MySQL  localhost:3306 ssl  JS > \\sql

Switching to SQL mode... Commands end with ;

Fetching global names for auto-completion... Press ^C to stop.

&#x20;MySQL  localhost:3306 ssl  SQL > show tables;

ERROR: 1046 (3D000): No database selected

&#x20;MySQL  localhost:3306 ssl  SQL > show databases;

+--------------------+

| Database           |

+--------------------+

| employees          |

| eva1               |

| eva1\_copia         |

| hospital           |

| information\_schema |

| mysql              |

| performance\_schema |

| sakila             |

| sys                |

| world\_x            |

| wrpracti\_northwind |

+--------------------+

11 rows in set (0.0010 sec)

&#x20;MySQL  localhost:3306 ssl  SQL > use eva1

Default schema set to `eva1`.

Fetching global names, object names from `eva1` for auto-completion... Press ^C to stop.

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show tables;

+--------------------+

| Tables\_in\_eva1     |

+--------------------+

| actor2             |

| copia\_persona      |

| customer2          |

| empleado           |

| estudiante         |

| persona            |

| persona\_modificada |

| playera            |

| vehiculo           |

| vehiculo2          |

+--------------------+

10 rows in set (0.0023 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > CREATE TABLE customers (

&#x20;                                    ->     cust\_code VARCHAR(10) PRIMARY KEY,

&#x20;                                    ->     cust\_name VARCHAR(100) NOT NULL

&#x20;                                    -> );C^C

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table custumer (

&#x20;                                    -> cust\_code varchar(10) key,

&#x20;                                    -> ^C

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table custumer (

&#x20;                                    -> id\_cust int not null key auto\_increment,

&#x20;                                    -> cust\_code varchar(10) not null,

&#x20;                                    -> cust\_name varchar(50) not null);

Query OK, 0 rows affected (0.0195 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show tables;

+--------------------+

| Tables\_in\_eva1     |

+--------------------+

| actor2             |

| copia\_persona      |

| customer2          |

| custumer           |

| empleado           |

| estudiante         |

| persona            |

| persona\_modificada |

| playera            |

| vehiculo           |

| vehiculo2          |

+--------------------+

11 rows in set (0.0013 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc customers;

ERROR: 1146 (42S02): Table 'eva1.customers' doesn't exist

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc customer;

ERROR: 1146 (42S02): Table 'eva1.customer' doesn't exist

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc custumer;

+-----------+-------------+------+-----+---------+----------------+

| Field     | Type        | Null | Key | Default | Extra          |

+-----------+-------------+------+-----+---------+----------------+

| id\_cust   | int         | NO   | PRI | NULL    | auto\_increment |

| cust\_code | varchar(10) | NO   |     | NULL    |                |

| cust\_name | varchar(50) | NO   |     | NULL    |                |

+-----------+-------------+------+-----+---------+----------------+

3 rows in set (0.0016 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table items (

&#x20;                                    -> id\_items int not null key auto\_increment,

&#x20;                                    -> item\_num varchar(50) not null,

&#x20;                                    -> item\_name varchar(50) not null);

Query OK, 0 rows affected (0.0175 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table orders (

&#x20;                                    -> id\_order int not null key not null,

&#x20;                                    -> so\_number^C

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > drop custumerñ

&#x20;                                    -> ^C

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > drop custumer

&#x20;                                    -> ;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'custumer' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > drop custumer table;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'custumer table' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table orders (

&#x20;                                    -> id\_orders int not null key auto\_increment,

&#x20;                                    -> so\_number int not null,

&#x20;                                    -> cust\_code varchar(10));

Query OK, 0 rows affected (0.0117 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table order\_details (

&#x20;                                    -> ^C

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table order\_details (

&#x20;                                    ->     id\_detail int not null key auto\_increment,

&#x20;                                    ->     so\_number int not null,

&#x20;                                    ->     item\_num varchar(50) not null,

&#x20;                                    ->     qty\_ordered int not null

&#x20;                                    -> );

Query OK, 0 rows affected (0.0177 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > insert into custumer (cust\_code, cust\_name) values

&#x20;                                    -> ('WHEEL', 'Wheelaway Cycle Center'),

&#x20;                                    -> ('ETC', 'Bikes Et Cetera'),

&#x20;                                    -> ('IBS', 'Inter. Bicycle Sales');

Query OK, 3 rows affected (0.0125 sec)



Records: 3  Duplicates: 0  Warnings: 0

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > insert into items (item\_num, item\_name) values

&#x20;                                    -> ('2010-0050', 'Formed Handlebar'),

&#x20;                                    -> ('1000-1', '20 in. Bicycle'),

&#x20;                                    -> ('1002-1', '24 in. Bicycle'),

&#x20;                                    -> ('1001-1', '26 in. Bicycle'),

&#x20;                                    -> ('1003-1', '20 in. Bicycle'),

&#x20;                                    -> ('3961-1041', 'Tire Tube, 26 in.'),

&#x20;                                    -> ('3965-1050', 'Spoke Reflector');

Query OK, 7 rows affected (0.0030 sec)



Records: 7  Duplicates: 0  Warnings: 0

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > insert into orders (so\_number, cust\_code) values

&#x20;                                    -> (1010, 'WHEEL'),

&#x20;                                    -> (1011, 'ETC'),

&#x20;                                    -> (1012, 'WHEEL'),

&#x20;                                    -> (1013, 'IBS'),

&#x20;                                    -> (1014, 'ETC'),

&#x20;                                    -> (1015, 'WHEEL'),

&#x20;                                    -> (1016, 'ETC');

Query OK, 7 rows affected (0.0021 sec)



Records: 7  Duplicates: 0  Warnings: 0

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > insert into order\_details (so\_number, item\_num, qty\_ordered) values

&#x20;                                    -> (1010, '2010-0050', 2),

&#x20;                                    -> (1010, '1000-1', 5),

&#x20;                                    -> (1011, '1002-1', 5),

&#x20;                                    -> (1011, '1001-1', 10),

&#x20;                                    -> (1012, '1003-1', 5),

&#x20;                                    -> (1012, '1001-1', 10),

&#x20;                                    -> (1013, '1001-1', 50),

&#x20;                                    -> (1014, '1003-1', 25),

&#x20;                                    -> (1015, '1003-1', 25),

&#x20;                                    -> (1016, '3961-1041', 5),

&#x20;                                    -> (1016, '3965-1050', 50),

&#x20;                                    -> (1016, '1003-1', 5),

&#x20;                                    -> (1016, '1000-1', 4);

Query OK, 13 rows affected (0.0025 sec)



Records: 13  Duplicates: 0  Warnings: 0

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc custumer;

+-----------+-------------+------+-----+---------+----------------+

| Field     | Type        | Null | Key | Default | Extra          |

+-----------+-------------+------+-----+---------+----------------+

| id\_cust   | int         | NO   | PRI | NULL    | auto\_increment |

| cust\_code | varchar(10) | NO   |     | NULL    |                |

| cust\_name | varchar(50) | NO   |     | NULL    |                |

+-----------+-------------+------+-----+---------+----------------+

3 rows in set (0.0028 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc items;

+-----------+-------------+------+-----+---------+----------------+

| Field     | Type        | Null | Key | Default | Extra          |

+-----------+-------------+------+-----+---------+----------------+

| id\_items  | int         | NO   | PRI | NULL    | auto\_increment |

| item\_num  | varchar(50) | NO   |     | NULL    |                |

| item\_name | varchar(50) | NO   |     | NULL    |                |

+-----------+-------------+------+-----+---------+----------------+

3 rows in set (0.0007 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc orders;

+-----------+-------------+------+-----+---------+----------------+

| Field     | Type        | Null | Key | Default | Extra          |

+-----------+-------------+------+-----+---------+----------------+

| id\_orders | int         | NO   | PRI | NULL    | auto\_increment |

| so\_number | int         | NO   |     | NULL    |                |

| cust\_code | varchar(10) | YES  |     | NULL    |                |

+-----------+-------------+------+-----+---------+----------------+

3 rows in set (0.0006 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc order\_details;

+-------------+-------------+------+-----+---------+----------------+

| Field       | Type        | Null | Key | Default | Extra          |

+-------------+-------------+------+-----+---------+----------------+

| id\_detail   | int         | NO   | PRI | NULL    | auto\_increment |

| so\_number   | int         | NO   |     | NULL    |                |

| item\_num    | varchar(50) | NO   |     | NULL    |                |

| qty\_ordered | int         | NO   |     | NULL    |                |

+-------------+-------------+------+-----+---------+----------------+

4 rows in set (0.0013 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL >

