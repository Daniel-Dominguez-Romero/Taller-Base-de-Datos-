**EVA\_1\_CREATE\_TABLE PRACTICA 2**



MySQL Shell 8.0.46



Copyright (c) 2016, 2026, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its affiliates.

Other names may be trademarks of their respective owners.



Type '\\help' or '\\?' for help; '\\quit' to exit.

&#x20;MySQL  JS > \\connect @localhost

Invalid URI: Missing user information

\\connect \[--mx|--mysqlx|--mc|--mysql] \[--ssh <sshuri>] <URI>

&#x20;MySQL  JS >

&#x20;MySQL  JS > \\connect root@localhost

Creating a session to 'root@localhost'

Please provide the password for 'root@localhost':

Save password for 'root@localhost'? \[Y]es/\[N]o/Ne\[v]er (default No):

Fetching schema names for auto-completion... Press ^C to stop.

Your MySQL connection id is 8

Server version: 8.4.7 MySQL Community Server - GPL

No default schema selected; type \\use <schema> to set one.

&#x20;MySQL  localhost:3306 ssl  JS >

&#x20;MySQL  localhost:3306 ssl  JS > \\sql

Switching to SQL mode... Commands end with ;

Fetching global names for auto-completion... Press ^C to stop.

&#x20;MySQL  localhost:3306 ssl  SQL > show databases;

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

10 rows in set (0.0104 sec)

&#x20;MySQL  localhost:3306 ssl  SQL > use eva1

Default schema set to `eva1`.

Fetching global names, object names from `eva1` for auto-completion... Press ^C to stop.

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table Persona (

&#x20;                                    -> id\_persona int not null auto\_increment key,

&#x20;                                    -> nombre varchar (50) not null,

&#x20;                                    -> ap\_paterno varchar(50) not null,

&#x20;                                    -> ap\_materno varchar(50) null,

&#x20;                                    -> fecha\_nac date not null);

Query OK, 0 rows affected (0.0136 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show tables;

+----------------+

| Tables\_in\_eva1 |

+----------------+

| persona        |

+----------------+

1 row in set (0.0017 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show create table persona;

+---------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

| Table   | Create Table                                                                                                                                                                                                                                                                                                                                                                                      |

+---------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

| persona | CREATE TABLE `persona` (

&#x20; `id\\\\\\\_persona` int NOT NULL AUTO\_INCREMENT,

&#x20; `nombre` varchar(50) COLLATE utf8mb4\_unicode\_ci NOT NULL,

&#x20; `ap\\\\\\\_paterno` varchar(50) COLLATE utf8mb4\_unicode\_ci NOT NULL,

&#x20; `ap\\\\\\\_materno` varchar(50) COLLATE utf8mb4\_unicode\_ci DEFAULT NULL,

&#x20; `fecha\\\\\\\_nac` date NOT NULL,

&#x20; PRIMARY KEY (`id\\\\\\\_persona`)

) ENGINE=MyISAM DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4\_unicode\_ci |

+---------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

1 row in set (0.0052 sec)

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

5 rows in set (0.0119 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > drop table persona;

Query OK, 0 rows affected (0.0070 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show table persona;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'persona' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show table;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show tables;

Empty set (0.0012 sec)                   create table Persona (

&#x20;                                    ->                                      -> id\_persona int not null auto\_increment key,

&#x20;                                    ->                                      -> nombre varchar (50) not null,

&#x20;                                    ->                                      -> ap\_paterno varchar(50) not null,

&#x20;                                    ->                                      -> ap\_materno varchar(50) null,

&#x20;                                    ->                                      -> fecha\_nac date not null);

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '-> id\_persona int not null auto\_increment key,

&#x20;                                ' at line 2

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show tables;

Empty set (0.0010 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table persona (

&#x20;                                    -> ^C

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table Persona ( id\_persona int not null auto\_increment key,  nombre varchar (50) not null, ap\_paterno varchar(50) not null, ap\_materno varchar(50) null, fecha\_nac date not null);

Query OK, 0 rows affected (0.0151 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show tables;

+----------------+

| Tables\_in\_eva1 |

+----------------+

| persona        |

+----------------+

1 row in set (0.0011 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > insert into persona

&#x20;                                    -> (value 1, "Juan", "Perez", "Jolote", "1970-11-12")

&#x20;                                    -> ;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '1, "Juan", "Perez", "Jolote", "1970-11-12")' at line 2

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > insert into persona

&#x20;                                    -> value (1, "Juan", "Perez", "Jolote", "1970-11-12");

Query OK, 1 row affected (0.0117 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > select \* from persona;

+------------+--------+------------+------------+------------+

| id\_persona | nombre | ap\_paterno | ap\_materno | fecha\_nac  |

+------------+--------+------------+------------+------------+

|          1 | Juan   | Perez      | Jolote     | 1970-11-12 |

+------------+--------+------------+------------+------------+

1 row in set (0.0006 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > insert into persona  value (1, "Juan", "Perez", "Jolote", "1970-11-12");

ERROR: 1062 (23000): Duplicate entry '1' for key 'persona.PRIMARY'

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > insert into persona  value (2, "Juan", "Perez", "Jolote", "1970-11-12");

Query OK, 1 row affected (0.0009 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > select \* from persona;

+------------+--------+------------+------------+------------+

| id\_persona | nombre | ap\_paterno | ap\_materno | fecha\_nac  |

+------------+--------+------------+------------+------------+

|          1 | Juan   | Perez      | Jolote     | 1970-11-12 |

|          2 | Juan   | Perez      | Jolote     | 1970-11-12 |

+------------+--------+------------+------------+------------+

2 rows in set (0.0006 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > insert into persona (nombre, ap\_paterno,

&#x20;                                    -> fecha\_nac)

&#x20;                                    -> value("Pedro", "Paramo", "1920-10-23");

Query OK, 1 row affected (0.0006 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > select \* from persona;

+------------+--------+------------+------------+------------+

| id\_persona | nombre | ap\_paterno | ap\_materno | fecha\_nac  |

+------------+--------+------------+------------+------------+

|          1 | Juan   | Perez      | Jolote     | 1970-11-12 |

|          2 | Juan   | Perez      | Jolote     | 1970-11-12 |

|          3 | Pedro  | Paramo     | NULL       | 1920-10-23 |

+------------+--------+------------+------------+------------+

3 rows in set (0.0006 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > inser into persona(ap\_paterno, fecha\_nac)

&#x20;                                    -> valu("Paramo", "1962-06-25");

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'inser into persona(ap\_paterno, fecha\_nac)

valu("Paramo", "1962-06-25")' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > inser into persona(ap\_paterno, fecha\_nac) value("Paramo", "1962-06-25");

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'inser into persona(ap\_paterno, fecha\_nac) value("Paramo", "1962-06-25")' at line 1

(reverse-i-search)`':

