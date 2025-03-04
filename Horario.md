Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 12411042
Server version: 8.0.40 Source distribution

Copyright (c) 2000, 2022, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> use yuki060317$default;
Database changed
mysql> show table;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '' at line 1
mysql> show tables;
+------------------------------+
| Tables_in_yuki060317$default |
+------------------------------+
| detalle_horario              |
| horario                      |
| plantilla_detalle_horario    |
+------------------------------+
3 rows in set (0.01 sec)

mysql> desc detalle_horario;
+--------------------+-------------+------+-----+---------+-------+
| Field              | Type        | Null | Key | Default | Extra |
+--------------------+-------------+------+-----+---------+-------+
| horario_id         | int         | NO   | PRI | NULL    |       |
| hora_salida        | date        | NO   | PRI | NULL    |       |
| hora_entrada       | date        | NO   |     | NULL    |       |
| codigo_incapacidad | varchar(25) | YES  |     | NULL    |       |
+--------------------+-------------+------+-----+---------+-------+
4 rows in set (0.00 sec)

mysql> select * from horario;
+------------+--------------+
| horario_id | plantilla_id |
+------------+--------------+
|          1 |            5 |
|          2 |            1 |
|          3 |            3 |
|          4 |            2 |
|          5 |            4 |
+------------+--------------+
5 rows in set (0.00 sec)

mysql> desc detalle_horario;
+--------------------+-------------+------+-----+---------+-------+
| Field              | Type        | Null | Key | Default | Extra |
+--------------------+-------------+------+-----+---------+-------+
| horario_id         | int         | NO   | PRI | NULL    |       |
| hora_salida        | date        | NO   | PRI | NULL    |       |
| hora_entrada       | date        | NO   |     | NULL    |       |
| codigo_incapacidad | varchar(25) | YES  |     | NULL    |       |
+--------------------+-------------+------+-----+---------+-------+
4 rows in set (0.01 sec)

mysql> insert into detalle_horario(horario_id,hora_entrada,hora_salida,codigo_incapacidad) values (1,'2025/03/01 10:00','2025/03/01 06:00','vacaciones');
Query OK, 1 row affected, 4 warnings (0.01 sec)

mysql> insert into detalle_horario(horario_id,hora_entrada,hora_salida,codigo_incapacidad) values (2,'2025/04/02 11:00','2025/04/02 07:00','vacaciones');
Query OK, 1 row affected, 4 warnings (0.01 sec)

mysql> insert into detalle_horario(horario_id,hora_entrada,hora_salida,codigo_incapacidad) values (3,'2025/05/03 12:00','2025/05/03 08:00','vacaciones');
Query OK, 1 row affected, 4 warnings (0.00 sec)

mysql> insert into detalle_horario(horario_id,hora_entrada,hora_salida,codigo_incapacidad) values (4,'2025/06/04 13:00','2025/06/04 09:00','vacaciones');
Query OK, 1 row affected, 4 warnings (0.00 sec)

mysql> insert into detalle_horario(horario_id,hora_entrada,hora_salida,codigo_incapacidad) values (5,'2025/07/05 14:00','2025/07/05 10:00','vacaciones');
Query OK, 1 row affected, 4 warnings (0.01 sec)

mysql> selec * from detalle_horario;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'selec * from detalle_horario' at line 1
mysql> select * from ddetalle_horario;
ERROR 1146 (42S02): Table 'yuki060317$default.ddetalle_horario' doesn't exist
mysql> select * from detalle_horario;
+------------+-------------+--------------+--------------------+
| horario_id | hora_salida | hora_entrada | codigo_incapacidad |
+------------+-------------+--------------+--------------------+
|          1 | 2025-03-01  | 2025-03-01   | vacaciones         |
|          2 | 2025-04-02  | 2025-04-02   | vacaciones         |
|          3 | 2025-05-03  | 2025-05-03   | vacaciones         |
|          4 | 2025-06-04  | 2025-06-04   | vacaciones         |
|          5 | 2025-07-05  | 2025-07-05   | vacaciones         |
+------------+-------------+--------------+--------------------+
5 rows in set (0.00 sec)

mysql> CREATE TABLE usuarios (idx int(20) NOT NULL,nombre varchar(100) NOT NULL,apellidos varchar(100) NOT NULL,departamento varchar(100) NOT NULL,PRIMARY KEY (nombre, apellidos);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '' at line 1
mysql> CREATE TABLE usuarios (
    -> idx int(20) NOT NULL,
    -> nombre varchar(100) NOT NULL,
    -> apellidos varchar(100) NOT NULL,
    -> departamento varchar(100) NOT NULL,
    -> PRIMARY KEY (nombre, apellidos)
    -> );
Query OK, 0 rows affected, 1 warning (0.03 sec)
mysql> insert into usuarios (idx,nombre,apellidos,departamento) values (11, 'Alondra', 'Mendoza', 'cbtis-246');
Query OK, 1 row affected (0.00 sec)
mysql> insert into usuarios (idx,nombre,apellidos,departamento) values (10, 'Ximena', 'Saldaña', 'cbtis-246');
Query OK, 1 row affected (0.00 sec)
mysql> insert into usuarios (idx,nombre,apellidos,departamento) values (22, 'Emma', 'Sanchez', 'cbtis-246');
Query OK, 1 row affected (0.00 sec)
mysql> insert into usuarios (idx,nombre,apellidos,departamento) values (12, 'Alexa', 'Guerra', 'cbtis-246');
Query OK, 1 row affected (0.00 sec)
mysql> insert into usuarios (idx,nombre,apellidos,departamento) values (15, 'Kevin', 'Gonzales', 'cbtis-246');
Query OK, 1 row affected (0.01 sec)
mysql> insert into usuarios (idx,nombre,apellidos,departamento) values (14, 'Gustavo', 'Perez', 'cbtis-246');
Query OK, 1 row affected (0.01 sec)
mysql> insert into usuarios (idx,nombre,apellidos,departamento) values (16, 'Itzel', 'Matla', 'cbtis-246');
Query OK, 1 row affected (0.00 sec)
mysql> insert into usuarios (idx,nombre,apellidos,departamento) values (16, 'Fernanda', 'Juarez', 'cbtis-246');
Query OK, 1 row affected (0.00 sec)
mysql> insert into usuarios (idx,nombre,apellidos,departamento) values (16, 'Carlos', 'Cruz', 'cbtis-246');
Query OK, 1 row affected (0.00 sec)
mysql> select * from usuarios;
+-----+----------+-----------+--------------+
| idx | nombre   | apellidos | departamento |
+-----+----------+-----------+--------------+
|  12 | Alexa    | Guerra    | cbtis-246    |
|  11 | Alondra  | Mendoza   | cbtis-246    |
|  16 | Carlos   | Cruz      | cbtis-246    |
|  22 | Emma     | Sanchez   | cbtis-246    |
|  16 | Fernanda | Juarez    | cbtis-246    |
|  14 | Gustavo  | Perez     | cbtis-246    |
|  16 | Itzel    | Matla     | cbtis-246    |
|  15 | Kevin    | Gonzales  | cbtis-246    |
|  10 | Ximena   | Saldaña   | cbtis-246    |
+-----+----------+-----------+--------------+
9 rows in set (0.00 sec)
