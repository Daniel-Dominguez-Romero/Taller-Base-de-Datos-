**EVA1\_PRACTICA6\_ALTERTABLE** 





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

Your MySQL connection id is 9

Server version: 8.4.7 MySQL Community Server - GPL

No default schema selected; type \\use <schema> to set one.

&#x20;MySQL  localhost:3306 ssl  JS > \\sql

Switching to SQL mode... Commands end with ;

Fetching global names for auto-completion... Press ^C to stop.

&#x20;MySQL  localhost:3306 ssl  SQL > use eva1

Default schema set to `eva1`.

Fetching global names, object names from `eva1` for auto-completion... Press ^C to stop.

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show tables

&#x20;                                    -> ;

+----------------+

| Tables\_in\_eva1 |

+----------------+

| actor2         |

| copia\_persona  |

| customer2      |

| empleado       |

| persona        |

| playera        |

| vehiculo       |

| vehiculo2      |

+----------------+

8 rows in set (0.0016 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc persona

&#x20;                                    -> ;

+------------+-------------+------+-----+---------+----------------+

| Field      | Type        | Null | Key | Default | Extra          |

+------------+-------------+------+-----+---------+----------------+

| id\_persona | int         | NO   | PRI | NULL    | auto\_increment |

| nombre     | varchar(50) | NO   |     | NULL    |                |

| ap\_paterno | varchar(50) | NO   |     | NULL    |                |

| ap\_materno | varchar(50) | YES  |     | NULL    |                |

| fecha\_nac  | date        | NO   |     | NULL    |                |

+------------+-------------+------+-----+---------+----------------+

5 rows in set (0.0030 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table persona\_mod(

&#x20;                                    -> id int not null auto\_increment

&#x20;                                    -> ,nom varchar(10),

&#x20;                                    -> apellido varchar(10));

ERROR: 1075 (42000): Incorrect table definition; there can be only one auto column and it must be defined as a key

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table persona\_mod( id int not null auto\_increment, nom varchar(10), apellido varchar(10));

ERROR: 1075 (42000): Incorrect table definition; there can be only one auto column and it must be defined as a key

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table persona\_mod( id int not null key auto\_increment, nom varchar(10), apellido varchar(10));

Query OK, 0 rows affected (0.0177 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc persona\_mod;

+----------+-------------+------+-----+---------+----------------+

| Field    | Type        | Null | Key | Default | Extra          |

+----------+-------------+------+-----+---------+----------------+

| id       | int         | NO   | PRI | NULL    | auto\_increment |

| nom      | varchar(10) | YES  |     | NULL    |                |

| apellido | varchar(10) | YES  |     | NULL    |                |

+----------+-------------+------+-----+---------+----------------+

3 rows in set (0.0012 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table persona\_mod

&#x20;                                    -> add fecha\_nac date not null after id;

Query OK, 0 rows affected (0.0339 sec)



Records: 0  Duplicates: 0  Warnings: 0

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc persona\_mod;

+-----------+-------------+------+-----+---------+----------------+

| Field     | Type        | Null | Key | Default | Extra          |

+-----------+-------------+------+-----+---------+----------------+

| id        | int         | NO   | PRI | NULL    | auto\_increment |

| fecha\_nac | date        | NO   |     | NULL    |                |

| nom       | varchar(10) | YES  |     | NULL    |                |

| apellido  | varchar(10) | YES  |     | NULL    |                |

+-----------+-------------+------+-----+---------+----------------+

4 rows in set (0.0017 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table persona\_mod

&#x20;                                    -> drop fecha\_nac;

Query OK, 0 rows affected (0.0301 sec)



Records: 0  Duplicates: 0  Warnings: 0

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table persona\_mod

&#x20;                                    -> add fecha\_nac date not null;

Query OK, 0 rows affected (0.0334 sec)



Records: 0  Duplicates: 0  Warnings: 0

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc persona\_mod

&#x20;                                    -> ;l

+-----------+-------------+------+-----+---------+----------------+

| Field     | Type        | Null | Key | Default | Extra          |

+-----------+-------------+------+-----+---------+----------------+

| id        | int         | NO   | PRI | NULL    | auto\_increment |

| nom       | varchar(10) | YES  |     | NULL    |                |

| apellido  | varchar(10) | YES  |     | NULL    |                |

| fecha\_nac | date        | NO   |     | NULL    |                |

+-----------+-------------+------+-----+---------+----------------+

4 rows in set (0.0012 sec)

&#x20;                                    -> alter persona\_mod

&#x20;                                    -> rename column id to id\_persona;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'l

alter persona\_mod

rename column id to id\_persona' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc persona\_mod;

+-----------+-------------+------+-----+---------+----------------+

| Field     | Type        | Null | Key | Default | Extra          |

+-----------+-------------+------+-----+---------+----------------+

| id        | int         | NO   | PRI | NULL    | auto\_increment |

| nom       | varchar(10) | YES  |     | NULL    |                |

| apellido  | varchar(10) | YES  |     | NULL    |                |

| fecha\_nac | date        | NO   |     | NULL    |                |

+-----------+-------------+------+-----+---------+----------------+

4 rows in set (0.0017 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table persona\_mod

&#x20;                                    -> rename column id to id\_persona;

Query OK, 0 rows affected (0.0211 sec)



Records: 0  Duplicates: 0  Warnings: 0

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table persona\_mod ;

Query OK, 0 rows affected (0.0015 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table persona\_mod

&#x20;                                    -> change nom nombre varchar(50) no null;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'no null' at line 2

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table persona\_mod

&#x20;                                    -> change apellido apellido\_pat varchar (50) not null;

Query OK, 0 rows affected (0.0323 sec)



Records: 0  Duplicates: 0  Warnings: 0

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table persona\_mod

&#x20;                                    -> add apellido\_mat varchar(50) after apellido\_pat;

Query OK, 0 rows affected (0.0322 sec)



Records: 0  Duplicates: 0  Warnings: 0

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc persona\_mod;

+--------------+-------------+------+-----+---------+----------------+

| Field        | Type        | Null | Key | Default | Extra          |

+--------------+-------------+------+-----+---------+----------------+

| id\_persona   | int         | NO   | PRI | NULL    | auto\_increment |

| nom          | varchar(10) | YES  |     | NULL    |                |

| apellido\_pat | varchar(50) | NO   |     | NULL    |                |

| apellido\_mat | varchar(50) | YES  |     | NULL    |                |

| fecha\_nac    | date        | NO   |     | NULL    |                |

+--------------+-------------+------+-----+---------+----------------+

5 rows in set (0.0012 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table persona\_mod

&#x20;                                    -> change nom nombre varchar (50);

Query OK, 0 rows affected (0.0298 sec)



Records: 0  Duplicates: 0  Warnings: 0

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc persona\_mod;

+--------------+-------------+------+-----+---------+----------------+

| Field        | Type        | Null | Key | Default | Extra          |

+--------------+-------------+------+-----+---------+----------------+

| id\_persona   | int         | NO   | PRI | NULL    | auto\_increment |

| nombre       | varchar(50) | YES  |     | NULL    |                |

| apellido\_pat | varchar(50) | NO   |     | NULL    |                |

| apellido\_mat | varchar(50) | YES  |     | NULL    |                |

| fecha\_nac    | date        | NO   |     | NULL    |                |

+--------------+-------------+------+-----+---------+----------------+

5 rows in set (0.0016 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table persona\_mod rename to persona\_modificada;

Query OK, 0 rows affected (0.0170 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show tables;

+--------------------+

| Tables\_in\_eva1     |

+--------------------+

| actor2             |

| copia\_persona      |

| customer2          |

| empleado           |

| persona            |

| persona\_modificada |

| playera            |

| vehiculo           |

| vehiculo2          |

+--------------------+

9 rows in set (0.0017 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table estudiante(

&#x20;                                    -> id\_es int,

&#x20;                                    -> nombre varchar(10),

&#x20;                                    -> apellidos varchar(50) not null,

&#x20;                                    -> carrera varchar (50));

Query OK, 0 rows affected (0.0162 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table estudiante

&#x20;                                    -> change id\_es id\_estudiante varchar (50) key auto\_increment;

ERROR: 1063 (42000): Incorrect column specifier for column 'id\_estudiante'

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc estudiante;

+-----------+-------------+------+-----+---------+-------+

| Field     | Type        | Null | Key | Default | Extra |

+-----------+-------------+------+-----+---------+-------+

| id\_es     | int         | YES  |     | NULL    |       |

| nombre    | varchar(10) | YES  |     | NULL    |       |

| apellidos | varchar(50) | NO   |     | NULL    |       |

| carrera   | varchar(50) | YES  |     | NULL    |       |

+-----------+-------------+------+-----+---------+-------+

4 rows in set (0.0014 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table estudiante change id\_es to id\_estudiante varchar (50) key auto\_increment;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'to id\_estudiante varchar (50) key auto\_increment' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table estudiante change id\_es id\_estudiante varchar (50) not null key auto\_increment;

ERROR: 1063 (42000): Incorrect column specifier for column 'id\_estudiante'

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table estudiante change id\_es id\_estudiante not null key auto\_increment;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'not null key auto\_increment' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table estudiante change id\_es id\_estudiante not null key auto\_increment;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'not null key auto\_increment' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table estudiante change id\_es id\_estudiante int not null key auto\_increment;

Query OK, 0 rows affected (0.0301 sec)



Records: 0  Duplicates: 0  Warnings: 0

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc estudiante;

+---------------+-------------+------+-----+---------+----------------+

| Field         | Type        | Null | Key | Default | Extra          |

+---------------+-------------+------+-----+---------+----------------+

| id\_estudiante | int         | NO   | PRI | NULL    | auto\_increment |

| nombre        | varchar(10) | YES  |     | NULL    |                |

| apellidos     | varchar(50) | NO   |     | NULL    |                |

| carrera       | varchar(50) | YES  |     | NULL    |                |

+---------------+-------------+------+-----+---------+----------------+

4 rows in set (0.0013 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter tables estudiante

&#x20;                                    -> add fecha\_nac date not null after apellidos;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'tables estudiante

add fecha\_nac date not null after apellidos' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table estudiante  add fecha\_nac date not null after apellidos;

Query OK, 0 rows affected (0.0220 sec)



Records: 0  Duplicates: 0  Warnings: 0

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table estudiante

&#x20;                                    -> rename nombre nombre varchar(50) not null;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'nombre varchar(50) not null' at line 2

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table estudiante  rename nombre nombre varchar(50) not null;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'nombre varchar(50) not null' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table estudiante rename nombre nombre varchar(50) not null

&#x20;                                    -> C^C

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table estudiante

&#x20;                                    -> change name name varchar(50);

ERROR: 1054 (42S22): Unknown column 'name' in 'estudiante'

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table estudiante  change nombre nombre varchar(50);

Query OK, 0 rows affected (0.0285 sec)



Records: 0  Duplicates: 0  Warnings: 0

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc estudiante;

+---------------+-------------+------+-----+---------+----------------+

| Field         | Type        | Null | Key | Default | Extra          |

+---------------+-------------+------+-----+---------+----------------+

| id\_estudiante | int         | NO   | PRI | NULL    | auto\_increment |

| nombre        | varchar(50) | YES  |     | NULL    |                |

| apellidos     | varchar(50) | NO   |     | NULL    |                |

| fecha\_nac     | date        | NO   |     | NULL    |                |

| carrera       | varchar(50) | YES  |     | NULL    |                |

+---------------+-------------+------+-----+---------+----------------+

5 rows in set (0.0014 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table estudiante

&#x20;                                    -> change apellidos apellido\_pat varchar(50) not null;

Query OK, 0 rows affected (0.0128 sec)



Records: 0  Duplicates: 0  Warnings: 0

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc estudiante;

+---------------+-------------+------+-----+---------+----------------+

| Field         | Type        | Null | Key | Default | Extra          |

+---------------+-------------+------+-----+---------+----------------+

| id\_estudiante | int         | NO   | PRI | NULL    | auto\_increment |

| nombre        | varchar(50) | YES  |     | NULL    |                |

| apellido\_pat  | varchar(50) | NO   |     | NULL    |                |

| fecha\_nac     | date        | NO   |     | NULL    |                |

| carrera       | varchar(50) | YES  |     | NULL    |                |

+---------------+-------------+------+-----+---------+----------------+

5 rows in set (0.0011 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table estudiante;

Query OK, 0 rows affected (0.0017 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > alter table estudiante

&#x20;                                    -> add apellido\_mat varchar (50) after apellido\_pat;

Query OK, 0 rows affected (0.0310 sec)



Records: 0  Duplicates: 0  Warnings: 0

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc estudiante;

+---------------+-------------+------+-----+---------+----------------+

| Field         | Type        | Null | Key | Default | Extra          |

+---------------+-------------+------+-----+---------+----------------+

| id\_estudiante | int         | NO   | PRI | NULL    | auto\_increment |

| nombre        | varchar(50) | YES  |     | NULL    |                |

| apellido\_pat  | varchar(50) | NO   |     | NULL    |                |

| apellido\_mat  | varchar(50) | YES  |     | NULL    |                |

| fecha\_nac     | date        | NO   |     | NULL    |                |

| carrera       | varchar(50) | YES  |     | NULL    |                |

+---------------+-------------+------+-----+---------+----------------+

6 rows in set (0.0011 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL >

