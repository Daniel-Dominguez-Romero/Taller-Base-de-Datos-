**CREATE TABLES PRACTICA 3**



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

Your MySQL connection id is 8

Server version: 8.4.7 MySQL Community Server - GPL

No default schema selected; type \\use <schema> to set one.

&#x20;MySQL  localhost:3306 ssl  JS > \\sql

Switching to SQL mode... Commands end with ;

Fetching global names for auto-completion... Press ^C to stop.

&#x20;MySQL  localhost:3306 ssl  SQL > create temporary table prueba (

&#x20;                              -> id int

&#x20;                              -> valor varchar (10));

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'valor varchar (10))' at line 3

&#x20;MySQL  localhost:3306 ssl  SQL > create temporary table prueba ( id int  valor, varchar (10));

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'valor, varchar (10))' at line 1

&#x20;MySQL  localhost:3306 ssl  SQL > create temporary table prueba ( id int,  valor varchar (10));

ERROR: 1046 (3D000): No database selected

&#x20;MySQL  localhost:3306 ssl  SQL > use eva1;

Default schema set to `eva1`.

Fetching global names, object names from `eva1` for auto-completion... Press ^C to stop.

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create temporary table prueba ( id int,  valor varchar (10));

Query OK, 0 rows affected (0.0109 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show tables;

+----------------+

| Tables\_in\_eva1 |

+----------------+

| persona        |

+----------------+

1 row in set (0.0130 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > inser into prueba

&#x20;                                    -> values (1, "jsbia"), (2, "dhqbsjkbdw"), (2, "xkjbs");

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'inser into prueba

values (1, "jsbia"), (2, "dhqbsjkbdw"), (2, "xkjbs")' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > insert into prueba  values (1, "jsbia"), (2, "dhqbsjkbdw"), (2, "xkjbs");

Query OK, 3 rows affected (0.0025 sec)



Records: 3  Duplicates: 0  Warnings: 0

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > select \*from prueba;

+----+------------+

| id | valor      |

+----+------------+

|  1 | jsbia      |

|  2 | dhqbsjkbdw |

|  2 | xkjbs      |

+----+------------+

3 rows in set (0.0095 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > \\disconnect

&#x20;MySQL  SQL > \\connect root@localhost

Creating a session to 'root@localhost'

Please provide the password for 'root@localhost':

Save password for 'root@localhost'? \[Y]es/\[N]o/Ne\[v]er (default No):

Fetching global names for auto-completion... Press ^C to stop.

Your MySQL connection id is 9

Server version: 8.4.7 MySQL Community Server - GPL

No default schema selected; type \\use <schema> to set one.

&#x20;MySQL  localhost:3306 ssl  SQL > use eva1

Default schema set to `eva1`.

Fetching global names, object names from `eva1` for auto-completion... Press ^C to stop.

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > use eva1;

Default schema set to `eva1`.

Fetching global names, object names from `eva1` for auto-completion... Press ^C to stop.

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > select \*from prueba;

ERROR: 1146 (42S02): Table 'eva1.prueba' doesn't exist

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show databases;

+--------------------+

| Database           |

+--------------------+

| employees          |

| eva1               |

| hospital           |

| information\_schema |

| mysql              |

| performance\_schema |

| sakila             |

| sys                |

| world\_x            |

| wrpracti\_northwind |

+--------------------+

10 rows in set (0.0013 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > use sakila;

Default schema set to `sakila`.

Fetching global names, object names from `sakila` for auto-completion... Press ^C to stop.

&#x20;MySQL  localhost:3306 ssl  sakila  SQL > show tables;

+----------------------------+

| Tables\_in\_sakila           |

+----------------------------+

| actor                      |

| actor\_info                 |

| address                    |

| category                   |

| city                       |

| country                    |

| customer                   |

| customer\_list              |

| film                       |

| film\_actor                 |

| film\_category              |

| film\_list                  |

| film\_text                  |

| inventory                  |

| language                   |

| nicer\_but\_slower\_film\_list |

| payment                    |

| rental                     |

| sales\_by\_film\_category     |

| sales\_by\_store             |

| staff                      |

| staff\_list                 |

| store                      |

+----------------------------+

23 rows in set (0.0019 sec)

&#x20;MySQL  localhost:3306 ssl  sakila  SQL > desc customer;

+-------------+-------------------+------+-----+-------------------+-----------------------------------------------+

| Field       | Type              | Null | Key | Default           | Extra                                         |

+-------------+-------------------+------+-----+-------------------+-----------------------------------------------+

| customer\_id | smallint unsigned | NO   | PRI | NULL              | auto\_increment                                |

| store\_id    | tinyint unsigned  | NO   | MUL | NULL              |                                               |

| first\_name  | varchar(45)       | NO   |     | NULL              |                                               |

| last\_name   | varchar(45)       | NO   | MUL | NULL              |                                               |

| email       | varchar(50)       | YES  |     | NULL              |                                               |

| address\_id  | smallint unsigned | NO   | MUL | NULL              |                                               |

| active      | tinyint(1)        | NO   |     | 1                 |                                               |

| create\_date | datetime          | NO   |     | NULL              |                                               |

| last\_update | timestamp         | YES  |     | CURRENT\_TIMESTAMP | DEFAULT\_GENERATED on update CURRENT\_TIMESTAMP |

+-------------+-------------------+------+-----+-------------------+-----------------------------------------------+

9 rows in set (0.0128 sec)

&#x20;MySQL  localhost:3306 ssl  sakila  SQL > use eva1;

Default schema set to `eva1`.

Fetching global names, object names from `eva1` for auto-completion... Press ^C to stop.

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show tables;

+----------------+

| Tables\_in\_eva1 |

+----------------+

| persona        |

+----------------+

1 row in set (0.0019 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > select \*from persona;

+------------+--------+------------+------------+------------+

| id\_persona | nombre | ap\_paterno | ap\_materno | fecha\_nac  |

+------------+--------+------------+------------+------------+

|          1 | Juan   | Perez      | Jolote     | 1970-11-12 |

|          2 | Juan   | Perez      | Jolote     | 1970-11-12 |

|          3 | Pedro  | Paramo     | NULL       | 1920-10-23 |

+------------+--------+------------+------------+------------+

3 rows in set (0.0183 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table copia\_persona like persona;

Query OK, 0 rows affected (0.0213 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show tables;

+----------------+

| Tables\_in\_eva1 |

+----------------+

| copia\_persona  |

| persona        |

+----------------+

2 rows in set (0.0018 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > select \* from copia\_persona;

Empty set (0.0021 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create database eva1\_copia;

Query OK, 1 row affected (0.0057 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > use eva1\_copia;

Default schema set to `eva1\\\_copia`.

Fetching global names, object names from `eva1\\\_copia` for auto-completion... Press ^C to stop.

&#x20;MySQL  localhost:3306 ssl  eva1\_copia  SQL > show tables;

Empty set (0.0014 sec)

&#x20;MySQL  localhost:3306 ssl  eva1\_copia  SQL > create table persona like eva1.persona;

Query OK, 0 rows affected (0.0194 sec)

&#x20;MySQL  localhost:3306 ssl  eva1\_copia  SQL > show tables;

+----------------------+

| Tables\_in\_eva1\_copia |

+----------------------+

| persona              |

+----------------------+

1 row in set (0.0015 sec)

&#x20;MySQL  localhost:3306 ssl  eva1\_copia  SQL > desc persona;

+------------+-------------+------+-----+---------+----------------+

| Field      | Type        | Null | Key | Default | Extra          |

+------------+-------------+------+-----+---------+----------------+

| id\_persona | int         | NO   | PRI | NULL    | auto\_increment |

| nombre     | varchar(50) | NO   |     | NULL    |                |

| ap\_paterno | varchar(50) | NO   |     | NULL    |                |

| ap\_materno | varchar(50) | YES  |     | NULL    |                |

| fecha\_nac  | date        | NO   |     | NULL    |                |

+------------+-------------+------+-----+---------+----------------+

5 rows in set (0.0019 sec)

&#x20;MySQL  localhost:3306 ssl  eva1\_copia  SQL > create table persona\_datos as selecte \* from persona;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'selecte \* from persona' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1\_copia  SQL > create table persona\_datos as select \* from persona;

Query OK, 0 rows affected (0.0218 sec)



Records: 0  Duplicates: 0  Warnings: 0

&#x20;MySQL  localhost:3306 ssl  eva1\_copia  SQL > show tables;

+----------------------+

| Tables\_in\_eva1\_copia |

+----------------------+

| persona              |

| persona\_datos        |

+----------------------+

2 rows in set (0.0012 sec)

&#x20;MySQL  localhost:3306 ssl  eva1\_copia  SQL > delete table persona\_datos;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'table persona\_datos' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1\_copia  SQL > drop table persona\_datos;

Query OK, 0 rows affected (0.0185 sec)

&#x20;MySQL  localhost:3306 ssl  eva1\_copia  SQL > create table persona\_datos as select \* from eva1.persona;

Query OK, 3 rows affected (0.0224 sec)



Records: 3  Duplicates: 0  Warnings: 0

&#x20;MySQL  localhost:3306 ssl  eva1\_copia  SQL > show tables;

+----------------------+

| Tables\_in\_eva1\_copia |

+----------------------+

| persona              |

| persona\_datos        |

+----------------------+

2 rows in set (0.0017 sec)

&#x20;MySQL  localhost:3306 ssl  eva1\_copia  SQL > select \* from personas\_datos;

ERROR: 1146 (42S02): Table 'eva1\_copia.personas\_datos' doesn't exist

&#x20;MySQL  localhost:3306 ssl  eva1\_copia  SQL > select \* from persona\_datos;

+------------+--------+------------+------------+------------+

| id\_persona | nombre | ap\_paterno | ap\_materno | fecha\_nac  |

+------------+--------+------------+------------+------------+

|          1 | Juan   | Perez      | Jolote     | 1970-11-12 |

|          2 | Juan   | Perez      | Jolote     | 1970-11-12 |

|          3 | Pedro  | Paramo     | NULL       | 1920-10-23 |

+------------+--------+------------+------------+------------+

3 rows in set (0.0006 sec)

&#x20;MySQL  localhost:3306 ssl  eva1\_copia  SQL > desc persona\_datos;

+------------+-------------+------+-----+---------+-------+

| Field      | Type        | Null | Key | Default | Extra |

+------------+-------------+------+-----+---------+-------+

| id\_persona | int         | NO   |     | 0       |       |

| nombre     | varchar(50) | NO   |     | NULL    |       |

| ap\_paterno | varchar(50) | NO   |     | NULL    |       |

| ap\_materno | varchar(50) | YES  |     | NULL    |       |

| fecha\_nac  | date        | NO   |     | NULL    |       |

+------------+-------------+------+-----+---------+-------+

5 rows in set (0.0012 sec)

&#x20;MySQL  localhost:3306 ssl  eva1\_copia  SQL > create table persona\_datos2 as select nombre, ap\_paterno

&#x20;                                          -> from eva1.persona;

Query OK, 3 rows affected (0.0104 sec)



Records: 3  Duplicates: 0  Warnings: 0

&#x20;MySQL  localhost:3306 ssl  eva1\_copia  SQL > show tables;

+----------------------+

| Tables\_in\_eva1\_copia |

+----------------------+

| persona              |

| persona\_datos        |

| persona\_datos2       |

+----------------------+

3 rows in set (0.0011 sec)

&#x20;MySQL  localhost:3306 ssl  eva1\_copia  SQL > select \* from persona\_datos2;

+--------+------------+

| nombre | ap\_paterno |

+--------+------------+

| Juan   | Perez      |

| Juan   | Perez      |

| Pedro  | Paramo     |

+--------+------------+

3 rows in set (0.0005 sec)

&#x20;MySQL  localhost:3306 ssl  eva1\_copia  SQL > desc persona\_datos2;

+------------+-------------+------+-----+---------+-------+

| Field      | Type        | Null | Key | Default | Extra |

+------------+-------------+------+-----+---------+-------+

| nombre     | varchar(50) | NO   |     | NULL    |       |

| ap\_paterno | varchar(50) | NO   |     | NULL    |       |

+------------+-------------+------+-----+---------+-------+

2 rows in set (0.0017 sec)

&#x20;MySQL  localhost:3306 ssl  eva1\_copia  SQL > use sakila;

Default schema set to `sakila`.

Fetching global names, object names from `sakila` for auto-completion... Press ^C to stop.

&#x20;MySQL  localhost:3306 ssl  sakila  SQL > show tables;

+----------------------------+

| Tables\_in\_sakila           |

+----------------------------+

| actor                      |

| actor\_info                 |

| address                    |

| category                   |

| city                       |

| country                    |

| customer                   |

| customer\_list              |

| film                       |

| film\_actor                 |

| film\_category              |

| film\_list                  |

| film\_text                  |

| inventory                  |

| language                   |

| nicer\_but\_slower\_film\_list |

| payment                    |

| rental                     |

| sales\_by\_film\_category     |

| sales\_by\_store             |

| staff                      |

| staff\_list                 |

| store                      |

+----------------------------+

23 rows in set (0.0018 sec)

&#x20;MySQL  localhost:3306 ssl  sakila  SQL > select count(\*) from costomer;

ERROR: 1146 (42S02): Table 'sakila.costomer' doesn't exist

&#x20;MySQL  localhost:3306 ssl  sakila  SQL > select count(\*) from customer;

+----------+

| count(\*) |

+----------+

|        0 |

+----------+

1 row in set (0.0227 sec)

&#x20;MySQL  localhost:3306 ssl  sakila  SQL > select count(\*) from country;

+----------+

| count(\*) |

+----------+

|        0 |

+----------+

1 row in set (0.0264 sec)

&#x20;MySQL  localhost:3306 ssl  sakila  SQL > select count(\*) from customer;

+----------+

| count(\*) |

+----------+

|      599 |

+----------+

1 row in set (0.0015 sec)

&#x20;MySQL  localhost:3306 ssl  sakila  SQL > use eva1;

Default schema set to `eva1`.

Fetching global names, object names from `eva1` for auto-completion... Press ^C to stop.

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table customer2 as select \* from customer;

ERROR: 1146 (42S02): Table 'eva1.customer' doesn't exist

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table customer2 as select \* from sakila.customer;

Query OK, 599 rows affected (0.0120 sec)



Records: 599  Duplicates: 0  Warnings: 0

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show tables;

+----------------+

| Tables\_in\_eva1 |

+----------------+

| copia\_persona  |

| customer2      |

| persona        |

+----------------+

3 rows in set (0.0017 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > select count(\*) from customer;

ERROR: 1146 (42S02): Table 'eva1.customer' doesn't exist

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > select count(\*) from customer2;

+----------+

| count(\*) |

+----------+

|      599 |

+----------+

1 row in set (0.0006 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc costumer2;

ERROR: 1146 (42S02): Table 'eva1.costumer2' doesn't exist

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc customer2;

+-------------+-------------------+------+-----+-------------------+-----------------------------------------------+

| Field       | Type              | Null | Key | Default           | Extra                                         |

+-------------+-------------------+------+-----+-------------------+-----------------------------------------------+

| customer\_id | smallint unsigned | NO   |     | 0                 |                                               |

| store\_id    | tinyint unsigned  | NO   |     | NULL              |                                               |

| first\_name  | varchar(45)       | NO   |     | NULL              |                                               |

| last\_name   | varchar(45)       | NO   |     | NULL              |                                               |

| email       | varchar(50)       | YES  |     | NULL              |                                               |

| address\_id  | smallint unsigned | NO   |     | NULL              |                                               |

| active      | tinyint(1)        | NO   |     | 1                 |                                               |

| create\_date | datetime          | NO   |     | NULL              |                                               |

| last\_update | timestamp         | YES  |     | CURRENT\_TIMESTAMP | DEFAULT\_GENERATED on update CURRENT\_TIMESTAMP |

+-------------+-------------------+------+-----+-------------------+-----------------------------------------------+

9 rows in set (0.0019 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table actor2 like sakila.actor;

Query OK, 0 rows affected (0.0624 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show tables;

+----------------+

| Tables\_in\_eva1 |

+----------------+

| actor2         |

| copia\_persona  |

| customer2      |

| persona        |

+----------------+

4 rows in set (0.0016 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc actor2;

+-------------+-------------------+------+-----+-------------------+-----------------------------------------------+

| Field       | Type              | Null | Key | Default           | Extra                                         |

+-------------+-------------------+------+-----+-------------------+-----------------------------------------------+

| actor\_id    | smallint unsigned | NO   | PRI | NULL              | auto\_increment                                |

| first\_name  | varchar(45)       | NO   |     | NULL              |                                               |

| last\_name   | varchar(45)       | NO   | MUL | NULL              |                                               |

| last\_update | timestamp         | NO   |     | CURRENT\_TIMESTAMP | DEFAULT\_GENERATED on update CURRENT\_TIMESTAMP |

+-------------+-------------------+------+-----+-------------------+-----------------------------------------------+

4 rows in set (0.0023 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc persona;

+------------+-------------+------+-----+---------+----------------+

| Field      | Type        | Null | Key | Default | Extra          |

+------------+-------------+------+-----+---------+----------------+

| id\_persona | int         | NO   | PRI | NULL    | auto\_increment |

| nombre     | varchar(50) | NO   |     | NULL    |                |

| ap\_paterno | varchar(50) | NO   |     | NULL    |                |

| ap\_materno | varchar(50) | YES  |     | NULL    |                |

| fecha\_nac  | date        | NO   |     | NULL    |                |

+------------+-------------+------+-----+---------+----------------+

5 rows in set (0.0019 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table vehiculo(

&#x20;                                    -> id\_vehiculo int,

&#x20;                                    ->

&#x20;                                    -> ;;;;;;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '' at line 2

ERROR: 1065 (42000): Query was empty

ERROR: 1065 (42000): Query was empty

ERROR: 1065 (42000): Query was empty

ERROR: 1065 (42000): Query was empty

ERROR: 1065 (42000): Query was empty

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > drop table vehiculo;

ERROR: 1051 (42S02): Unknown table 'eva1.vehiculo'

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table vehiculo int not null key auto\_increment,

&#x20;                                    -> marca varchar (50) not null default "Nissan"

&#x20;                                    -> modelo varchar (50) not null default "Altima"

&#x20;                                    -> year int not null default 2000

&#x20;                                    -> color varchar(50));

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'int not null key auto\_increment,

marca varchar (50) not null default "Nissan"

mo' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table vehiculo int not null key auto\_increment, marca varchar (50) not null default "Nissan", modelo varchar (50) not null default "Altima", year int not null default 2000, color varchar(50));

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'int not null key auto\_increment, marca varchar (50) not null default "Nissan", m' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table vehiculo( id\_vehiculo int not null key auto\_increment, marca varchar (50) not null default "Nissan", modelo varchar (50) not null default "Altima", year int not null default 2000, color varchar(50));

Query OK, 0 rows affected (0.0082 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc vehiculo;

+-------------+-------------+------+-----+---------+----------------+

| Field       | Type        | Null | Key | Default | Extra          |

+-------------+-------------+------+-----+---------+----------------+

| id\_vehiculo | int         | NO   | PRI | NULL    | auto\_increment |

| marca       | varchar(50) | NO   |     | Nissan  |                |

| modelo      | varchar(50) | NO   |     | Altima  |                |

| year        | int         | NO   |     | 2000    |                |

| color       | varchar(50) | YES  |     | NULL    |                |

+-------------+-------------+------+-----+---------+----------------+

5 rows in set (0.0016 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > insert into vehiculo (color)

&#x20;                                    -> values("rojo"),("verde"),("morado");

Query OK, 3 rows affected (0.0131 sec)



Records: 3  Duplicates: 0  Warnings: 0

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show table vehiculos;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'vehiculos' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show table vehiculo;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'vehiculo' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL >

