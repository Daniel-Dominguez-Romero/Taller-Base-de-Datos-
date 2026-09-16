**MySQL Shell 8.0.46 PRACTICA 1** 



Copyright (c) 2016, 2026, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its affiliates.

Other names may be trademarks of their respective owners.



Type '\\help' or '\\?' for help; '\\quit' to exit.

&#x20;MySQL  JS > mysql

<mysql>

&#x20;MySQL  JS > /sql

Expected an operand but found / (SyntaxError)

&#x20;MySQL  JS > /SQL

Expected an operand but found / (SyntaxError)

&#x20;MySQL  JS > \\sql

Switching to SQL mode... Commands end with ;

&#x20;MySQL  SQL > SHOW DATABASES;

ERROR: Not connected.

&#x20;MySQL  SQL > \\connect root@localhost;

Creating a session to 'root@localhost;'

Please provide the password for 'root@localhost;':

MySQL Error 2005: No such host is known 'localhost;'

&#x20;MySQL  SQL > \\connect root@localhost:3306

Creating a session to 'root@localhost:3306'

Please provide the password for 'root@localhost:3306':

Save password for 'root@localhost:3306'? \[Y]es/\[N]o/Ne\[v]er (default No): Y

Fetching global names for auto-completion... Press ^C to stop.

Your MySQL connection id is 42

Server version: 8.4.7 MySQL Community Server - GPL

No default schema selected; type \\use <schema> to set one.

&#x20;MySQL  localhost:3306 ssl  SQL > SHOW DATABASES;

+--------------------+

| Database           |

+--------------------+

| employees          |

| hospital           |

| information\_schema |

| mysql              |

| performance\_schema |

| sakila             |

| sys                |

| world\_x            |

| wrpracti\_northwind |

+--------------------+

9 rows in set (0.0012 sec)

&#x20;MySQL  localhost:3306 ssl  SQL > use sakila;

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

&#x20;MySQL  localhost:3306 ssl  sakila  SQL > show engines;

+--------------------+---------+----------------------------------------------------------------+--------------+------+------------+

| Engine             | Support | Comment                                                        | Transactions | XA   | Savepoints |

+--------------------+---------+----------------------------------------------------------------+--------------+------+------------+

| MEMORY             | YES     | Hash based, stored in memory, useful for temporary tables      | NO           | NO   | NO         |

| MRG\_MYISAM         | YES     | Collection of identical MyISAM tables                          | NO           | NO   | NO         |

| CSV                | YES     | CSV storage engine                                             | NO           | NO   | NO         |

| FEDERATED          | NO      | Federated MySQL storage engine                                 | NULL         | NULL | NULL       |

| PERFORMANCE\_SCHEMA | YES     | Performance Schema                                             | NO           | NO   | NO         |

| MyISAM             | DEFAULT | MyISAM storage engine                                          | NO           | NO   | NO         |

| InnoDB             | YES     | Supports transactions, row-level locking, and foreign keys     | YES          | YES  | YES        |

| ndbinfo            | NO      | MySQL Cluster system information storage engine                | NULL         | NULL | NULL       |

| BLACKHOLE          | YES     | /dev/null storage engine (anything you write to it disappears) | NO           | NO   | NO         |

| ARCHIVE            | YES     | Archive storage engine                                         | NO           | NO   | NO         |

| ndbcluster         | NO      | Clustered, fault-tolerant tables                               | NULL         | NULL | NULL       |

+--------------------+---------+----------------------------------------------------------------+--------------+------+------------+

11 rows in set (0.0008 sec)

&#x20;MySQL  localhost:3306 ssl  sakila  SQL > create database eva1;

Query OK, 1 row affected (0.0213 sec)

&#x20;MySQL  localhost:3306 ssl  sakila  SQL > showdata bases;

ERROR: 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'showdata bases' at line 1

&#x20;MySQL  localhost:3306 ssl  sakila  SQL > SHOW DATABASES;

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

10 rows in set (0.0017 sec)

&#x20;MySQL  localhost:3306 ssl  sakila  SQL > use eva1;

Default schema set to `eva1`.

Fetching global names, object names from `eva1` for auto-completion... Press ^C to stop.

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show tables;

Empty set (0.0015 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show create database eva1;

+----------+--------------------------------------------------------------------------------------------------------------------------------+

| Database | Create Database                                                                                                                |

+----------+--------------------------------------------------------------------------------------------------------------------------------+

| eva1     | CREATE DATABASE `eva1` /\*!40100 DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4\_unicode\_ci \*/ /\*!80016 DEFAULT ENCRYPTION='N' \*/ |

+----------+--------------------------------------------------------------------------------------------------------------------------------+

1 row in set (0.0009 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show character set;

+----------+---------------------------------+---------------------+--------+

| Charset  | Description                     | Default collation   | Maxlen |

+----------+---------------------------------+---------------------+--------+

| armscii8 | ARMSCII-8 Armenian              | armscii8\_general\_ci |      1 |

| ascii    | US ASCII                        | ascii\_general\_ci    |      1 |

| big5     | Big5 Traditional Chinese        | big5\_chinese\_ci     |      2 |

| binary   | Binary pseudo charset           | binary              |      1 |

| cp1250   | Windows Central European        | cp1250\_general\_ci   |      1 |

| cp1251   | Windows Cyrillic                | cp1251\_general\_ci   |      1 |

| cp1256   | Windows Arabic                  | cp1256\_general\_ci   |      1 |

| cp1257   | Windows Baltic                  | cp1257\_general\_ci   |      1 |

| cp850    | DOS West European               | cp850\_general\_ci    |      1 |

| cp852    | DOS Central European            | cp852\_general\_ci    |      1 |

| cp866    | DOS Russian                     | cp866\_general\_ci    |      1 |

| cp932    | SJIS for Windows Japanese       | cp932\_japanese\_ci   |      2 |

| dec8     | DEC West European               | dec8\_swedish\_ci     |      1 |

| eucjpms  | UJIS for Windows Japanese       | eucjpms\_japanese\_ci |      3 |

| euckr    | EUC-KR Korean                   | euckr\_korean\_ci     |      2 |

| gb18030  | China National Standard GB18030 | gb18030\_chinese\_ci  |      4 |

| gb2312   | GB2312 Simplified Chinese       | gb2312\_chinese\_ci   |      2 |

| gbk      | GBK Simplified Chinese          | gbk\_chinese\_ci      |      2 |

| geostd8  | GEOSTD8 Georgian                | geostd8\_general\_ci  |      1 |

| greek    | ISO 8859-7 Greek                | greek\_general\_ci    |      1 |

| hebrew   | ISO 8859-8 Hebrew               | hebrew\_general\_ci   |      1 |

| hp8      | HP West European                | hp8\_english\_ci      |      1 |

| keybcs2  | DOS Kamenicky Czech-Slovak      | keybcs2\_general\_ci  |      1 |

| koi8r    | KOI8-R Relcom Russian           | koi8r\_general\_ci    |      1 |

| koi8u    | KOI8-U Ukrainian                | koi8u\_general\_ci    |      1 |

| latin1   | cp1252 West European            | latin1\_swedish\_ci   |      1 |

| latin2   | ISO 8859-2 Central European     | latin2\_general\_ci   |      1 |

| latin5   | ISO 8859-9 Turkish              | latin5\_turkish\_ci   |      1 |

| latin7   | ISO 8859-13 Baltic              | latin7\_general\_ci   |      1 |

| macce    | Mac Central European            | macce\_general\_ci    |      1 |

| macroman | Mac West European               | macroman\_general\_ci |      1 |

| sjis     | Shift-JIS Japanese              | sjis\_japanese\_ci    |      2 |

| swe7     | 7bit Swedish                    | swe7\_swedish\_ci     |      1 |

| tis620   | TIS620 Thai                     | tis620\_thai\_ci      |      1 |

| ucs2     | UCS-2 Unicode                   | ucs2\_general\_ci     |      2 |

| ujis     | EUC-JP Japanese                 | ujis\_japanese\_ci    |      3 |

| utf16    | UTF-16 Unicode                  | utf16\_general\_ci    |      4 |

| utf16le  | UTF-16LE Unicode                | utf16le\_general\_ci  |      4 |

| utf32    | UTF-32 Unicode                  | utf32\_general\_ci    |      4 |

| utf8mb3  | UTF-8 Unicode                   | utf8mb3\_general\_ci  |      3 |

| utf8mb4  | UTF-8 Unicode                   | utf8mb4\_0900\_ai\_ci  |      4 |

+----------+---------------------------------+---------------------+--------+

41 rows in set (0.0018 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show collation where charset = 'utf16';

+----------------------+---------+-----+---------+----------+---------+---------------+

| Collation            | Charset | Id  | Default | Compiled | Sortlen | Pad\_attribute |

+----------------------+---------+-----+---------+----------+---------+---------------+

| utf16\_bin            | utf16   |  55 |         | Yes      |       1 | PAD SPACE     |

| utf16\_croatian\_ci    | utf16   | 122 |         | Yes      |       8 | PAD SPACE     |

| utf16\_czech\_ci       | utf16   | 111 |         | Yes      |       8 | PAD SPACE     |

| utf16\_danish\_ci      | utf16   | 112 |         | Yes      |       8 | PAD SPACE     |

| utf16\_esperanto\_ci   | utf16   | 118 |         | Yes      |       8 | PAD SPACE     |

| utf16\_estonian\_ci    | utf16   | 107 |         | Yes      |       8 | PAD SPACE     |

| utf16\_general\_ci     | utf16   |  54 | Yes     | Yes      |       1 | PAD SPACE     |

| utf16\_german2\_ci     | utf16   | 121 |         | Yes      |       8 | PAD SPACE     |

| utf16\_hungarian\_ci   | utf16   | 119 |         | Yes      |       8 | PAD SPACE     |

| utf16\_icelandic\_ci   | utf16   | 102 |         | Yes      |       8 | PAD SPACE     |

| utf16\_latvian\_ci     | utf16   | 103 |         | Yes      |       8 | PAD SPACE     |

| utf16\_lithuanian\_ci  | utf16   | 113 |         | Yes      |       8 | PAD SPACE     |

| utf16\_persian\_ci     | utf16   | 117 |         | Yes      |       8 | PAD SPACE     |

| utf16\_polish\_ci      | utf16   | 106 |         | Yes      |       8 | PAD SPACE     |

| utf16\_romanian\_ci    | utf16   | 104 |         | Yes      |       8 | PAD SPACE     |

| utf16\_roman\_ci       | utf16   | 116 |         | Yes      |       8 | PAD SPACE     |

| utf16\_sinhala\_ci     | utf16   | 120 |         | Yes      |       8 | PAD SPACE     |

| utf16\_slovak\_ci      | utf16   | 114 |         | Yes      |       8 | PAD SPACE     |

| utf16\_slovenian\_ci   | utf16   | 105 |         | Yes      |       8 | PAD SPACE     |

| utf16\_spanish2\_ci    | utf16   | 115 |         | Yes      |       8 | PAD SPACE     |

| utf16\_spanish\_ci     | utf16   | 108 |         | Yes      |       8 | PAD SPACE     |

| utf16\_swedish\_ci     | utf16   | 109 |         | Yes      |       8 | PAD SPACE     |

| utf16\_turkish\_ci     | utf16   | 110 |         | Yes      |       8 | PAD SPACE     |

| utf16\_unicode\_520\_ci | utf16   | 123 |         | Yes      |       8 | PAD SPACE     |

| utf16\_unicode\_ci     | utf16   | 101 |         | Yes      |       8 | PAD SPACE     |

| utf16\_vietnamese\_ci  | utf16   | 124 |         | Yes      |       8 | PAD SPACE     |

+----------------------+---------+-----+---------+----------+---------+---------------+

26 rows in set (0.0015 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show create database eva1;

+----------+--------------------------------------------------------------------------------------------------------------------------------+

| Database | Create Database                                                                                                                |

+----------+--------------------------------------------------------------------------------------------------------------------------------+

| eva1     | CREATE DATABASE `eva1` /\*!40100 DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4\_unicode\_ci \*/ /\*!80016 DEFAULT ENCRYPTION='N' \*/ |

+----------+--------------------------------------------------------------------------------------------------------------------------------+

1 row in set (0.0010 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > ^C

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > drop database eva1;

Query OK, 0 rows affected (0.0176 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > show databases;

+--------------------+

| Database           |

+--------------------+

| employees          |

| hospital           |

| information\_schema |

| mysql              |

| performance\_schema |

| sakila             |

| sys                |

| world\_x            |

| wrpracti\_northwind |

+--------------------+

9 rows in set (0.0018 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > create database eva1;

Query OK, 1 row affected (0.0045 sec)

&#x20;MySQL  localhost:3306 ssl  eva1  SQL > use eva1;

Default schema set to `eva1`.

Fetching global names, object names from `eva1` for auto-completion... Press ^C to stop.

&#x20;MySQL  localhost:3306 ssl  eva1  SQL >

