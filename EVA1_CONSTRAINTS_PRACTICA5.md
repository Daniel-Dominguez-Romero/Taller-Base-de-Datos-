**EVA1\_CONSTRAINTS\_PRACTICA5**





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

&#x20;MySQL  localhost:3306 ssl  SQL > use eva1

Default schema set to `eva1`.

Fetching global names, object names from `eva1` for auto-completion... Press ^C to stop.

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show tablesñ

&#x20;                                    ->

&#x20;                                    -> ñ

&#x20;                                    -> ;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'tablesñ



ñ' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show tables;

+----------------+

| Tables\_in\_eva1 |

+----------------+

| actor2         |

| copia\_persona  |

| customer2      |

| persona        |

| vehiculo       |

+----------------+

5 rows in set (0.0030 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table Playera(

&#x20;                                    -> id\_playera int not null key auto\_increment,

&#x20;                                    -> marca varchar (50) not null,

&#x20;                                    -> moderlo varchar (50)  not null,

&#x20;                                    -> material varchar (50) not null,

&#x20;                                    -> talla varchar (50));

Query OK, 0 rows affected (0.0258 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > insert into playera (marca, modelo, material, talla)

&#x20;                                    -> values ("XXX", "xxx", "Algodon", "chica"),("XXX", "xxx", "Algodon", "s"),

&#x20;                                    -> ("XXX", "xxx", "Algodon", "small"))

&#x20;                                    -> ;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ')' at line 3

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > insert into playera (marca, modelo, material, talla)  values ("XXX", "xxx", "Algodon", "chica"),("XXX", "xxx", "Algodon", "s"), ("XXX", "xxx", "Algodon", "small") ;

ERROR: 1054 (42S22): Unknown column 'modelo' in 'field list'

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > insert into playera (marca, moderlo, material, talla)  values ("XXX", "xxx", "Algodon", "chica"),("XXX", "xxx", "Algodon", "s"), ("XXX", "xxx", "Algodon", "small") ;

Query OK, 3 rows affected (0.0122 sec)



Records: 3  Duplicates: 0  Warnings: 0

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > drop table playera;

Query OK, 0 rows affected (0.0188 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table Playera( id\_playera int not null key auto\_increment, marca varchar (50) not null, moderlo varchar (50)  not null,  material varchar (50) not null,

&#x20;                                    -> talla enum("x-small","small","medium","large","x-large","xx-large"));

Query OK, 0 rows affected (0.0184 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc playera;

+------------+---------------------------------------------------------------+------+-----+---------+----------------+

| Field      | Type                                                          | Null | Key | Default | Extra          |

+------------+---------------------------------------------------------------+------+-----+---------+----------------+

| id\_playera | int                                                           | NO   | PRI | NULL    | auto\_increment |

| marca      | varchar(50)                                                   | NO   |     | NULL    |                |

| moderlo    | varchar(50)                                                   | NO   |     | NULL    |                |

| material   | varchar(50)                                                   | NO   |     | NULL    |                |

| talla      | enum('x-small','small','medium','large','x-large','xx-large') | YES  |     | NULL    |                |

+------------+---------------------------------------------------------------+------+-----+---------+----------------+

5 rows in set (0.0118 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > insert into playera (marca, modelo, material, talla)

&#x20;                                    -> value("Adidas", "Algo", "Algodon", "small");

ERROR: 1054 (42S22): Unknown column 'modelo' in 'field list'

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > insert into playera (marca, moderlo, material, talla) value("Adidas", "Algo", "Algodon", "small");

Query OK, 1 row affected (0.0008 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > insert into playera (marca, moderlo, material, talla) value("Adidas", "Algo", "Algodon", "chica");

Query OK, 1 row affected, 1 warning (0.0016 sec)

Warning (code 1265): Data truncated for column 'talla' at row 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > select \* from playera;

+------------+--------+---------+----------+-------+

| id\_playera | marca  | moderlo | material | talla |

+------------+--------+---------+----------+-------+

|          1 | Adidas | Algo    | Algodon  | small |

|          2 | Adidas | Algo    | Algodon  |       |

+------------+--------+---------+----------+-------+

2 rows in set (0.0008 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show tables:

&#x20;                                    -> ;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ':' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show tables;

+----------------+

| Tables\_in\_eva1 |

+----------------+

| actor2         |

| copia\_persona  |

| customer2      |

| persona        |

| playera        |

| vehiculo       |

+----------------+

6 rows in set (0.0018 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create tabla empleado(

&#x20;                                    -> id\_empleado int not null key auto\_increment,

&#x20;                                    -> nombre varchar (50) not null,

&#x20;                                    -> apellidos varchar (50) not null,

&#x20;                                    -> salario decimal (10,2) check (salario > 0));

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'tabla empleado(

id\_empleado int not null key auto\_increment,

nombre varchar (50)' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table empleado( id\_empleado int not null key auto\_increment, nombre varchar (50) not null, apellidos varchar (50) not null, salario decimal (10,2) check (salario > 0));

Query OK, 0 rows affected (0.0202 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show table empleado;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'empleado' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show table;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc empleado;

+-------------+---------------+------+-----+---------+----------------+

| Field       | Type          | Null | Key | Default | Extra          |

+-------------+---------------+------+-----+---------+----------------+

| id\_empleado | int           | NO   | PRI | NULL    | auto\_increment |

| nombre      | varchar(50)   | NO   |     | NULL    |                |

| apellidos   | varchar(50)   | NO   |     | NULL    |                |

| salario     | decimal(10,2) | YES  |     | NULL    |                |

+-------------+---------------+------+-----+---------+----------------+

4 rows in set (0.0022 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > insert into empleado (nombre,apellidos, salario) value ("Juan","Meco", "100.2);

&#x20;                                    "> ;

&#x20;                                    ">

&#x20;                                    ">

&#x20;                                    ">

&#x20;                                    "> ;;);

&#x20;                                    ">

&#x20;                                    ">

&#x20;                                    ">

&#x20;                                    "> ;

&#x20;                                    ">

&#x20;                                    ">

&#x20;                                    ">

&#x20;                                    ">

&#x20;                                    "> ;

&#x20;                                    "> ,

&#x20;                                    "> ))

&#x20;                                    ">

&#x20;                                    ">

&#x20;                                    "> ^C

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > insert into empleado (nombre, apellidos, salario) value("Juan","Meco","100.2");

Query OK, 1 row affected (0.0030 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > desc empleado;

+-------------+---------------+------+-----+---------+----------------+

| Field       | Type          | Null | Key | Default | Extra          |

+-------------+---------------+------+-----+---------+----------------+

| id\_empleado | int           | NO   | PRI | NULL    | auto\_increment |

| nombre      | varchar(50)   | NO   |     | NULL    |                |

| apellidos   | varchar(50)   | NO   |     | NULL    |                |

| salario     | decimal(10,2) | YES  |     | NULL    |                |

+-------------+---------------+------+-----+---------+----------------+

4 rows in set (0.0023 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show table empleado;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'empleado' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show empleado;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'empleado' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > select from \* empleado;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'from \* empleado' at line 1

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > select \* from empleado;

+-------------+--------+-----------+---------+

| id\_empleado | nombre | apellidos | salario |

+-------------+--------+-----------+---------+

|           1 | Juan   | Meco      |  100.20 |

+-------------+--------+-----------+---------+

1 row in set (0.0009 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table vehiculo(

&#x20;                                    -> id\_vehiculo not null key auto\_increment,

&#x20;                                    -> color enum("azul","blanco","rojo"),

&#x20;                                    -> precio int check (precio>0 and precio < 1000000),

&#x20;                                    -> marca varchar(50) not null);

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'not null key auto\_increment,

color enum("azul","blanco","rojo"),

precio int chec' at line 2

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table vehiculo(  id\_vehiculo int not null key auto\_increment, color enum("azul","blanco","rojo"), precio int check (precio>0 and precio < 1000000), marca varchar(50) not null);

ERROR: 1050 (42S01): Table 'vehiculo' already exists

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create table vehiculo2(  id\_vehiculo int not null key auto\_increment, color enum("azul","blanco","rojo"), precio int check (precio>0 and precio < 1000000), marca varchar(50) not null);

Query OK, 0 rows affected (0.0173 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > insert into vehiculo2 (marca, modelo, color, precio)

&#x20;                                    -> value("GMC", "AMG", "rojo", "999999");

ERROR: 1054 (42S22): Unknown column 'modelo' in 'field list'

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > insert into vehiculo2 (color, precio, marca) value("rojo", "999999", "GMC");

Query OK, 1 row affected (0.0008 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > select \* from vehiculo2;

+-------------+-------+--------+-------+

| id\_vehiculo | color | precio | marca |

+-------------+-------+--------+-------+

|           1 | rojo  | 999999 | GMC   |

+-------------+-------+--------+-------+

1 row in set (0.0008 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL >

