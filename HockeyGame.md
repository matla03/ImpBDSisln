Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 17090268
Server version: 8.0.40 Source distribution

Copyright (c) 2000, 2022, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> use yuki060317$default
Database changed
mysql> show tables;
+------------------------------+
| Tables_in_yuki060317$default |
+------------------------------+
| GameScores                   |
| HockeyGame                   |
| HockeyTeam                   |
| HockeyTeamPlayer             |
| PlayoffRound                 |
| RoundStats                   |
| User                         |
| UserInfo                     |
| UserScorePicks               |
| UserStatsPicks               |
+------------------------------+
10 rows in set (0.00 sec)

mysql> desc GameScores;
+------------+------+------+-----+---------+-------+
| Field      | Type | Null | Key | Default | Extra |
+------------+------+------+-----+---------+-------+
| id         | int  | NO   | PRI | NULL    |       |
| team1Score | int  | NO   |     | NULL    |       |
| team2Score | int  | NO   |     | NULL    |       |
+------------+------+------+-----+---------+-------+
3 rows in set (0.00 sec)

mysql> insert into GameScores(id,team1Score,team2Score);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '' at line 1
mysql> insert into GameScores(id,team1Score,team2Score)
    -> values ('5','6','7');
Query OK, 1 row affected (0.10 sec)

mysql> desc HockeyGame;
+-------------+--------------+------+-----+---------+-------+
| Field       | Type         | Null | Key | Default | Extra |
+-------------+--------------+------+-----+---------+-------+
| id          | int          | NO   | PRI | NULL    |       |
| roundId     | int          | NO   |     | NULL    |       |
| startTime   | date         | NO   | PRI | NULL    |       |
| endTime     | date         | NO   |     | NULL    |       |
| description | varchar(255) | YES  |     | NULL    |       |
| team1Id     | int          | NO   |     | NULL    |       |
| team2Id     | int          | NO   |     | NULL    |       |
+-------------+--------------+------+-----+---------+-------+
7 rows in set (0.00 sec)

mysql> insert into HockeyGame(id,roundId,startTime,endTime,description,team1Id,team2Id)
    -> values('7','9','2025/03/09','Morado_35','5',6');
    '> values('7','9','2025/03/09','Morado_35','5',6');
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '');
values('7','9','2025/03/09','Morado_35','5',6')' at line 2
mysql> values('7','9','2025/03/09','Morado_35','5',6');
    '> 
    '> 
    '> values('7','9','2025/03/09','Morado_35','5',6');
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '('7','9','2025/03/09','Morado_35','5',6');


values('7','9','2025/03/09','Morado' at line 1
mysql> insert into HockeyGame(id,roundId,startTime,endTime,description,team1Id,team2Id)
    -> values('8','10','2025/03/02','2025/03/02','Rojo_34','6','7');
Query OK, 1 row affected, 2 warnings (0.01 sec)

mysql> desc HockeyTeam;
+-------+--------------+------+-----+---------+-------+
| Field | Type         | Null | Key | Default | Extra |
+-------+--------------+------+-----+---------+-------+
| id    | int          | NO   | PRI | NULL    |       |
| name  | varchar(100) | NO   |     | NULL    |       |
| logo  | varchar(100) | YES  |     | NULL    |       |
+-------+--------------+------+-----+---------+-------+
3 rows in set (0.01 sec)

mysql> INSERT INTO HockeyTeam(id,name,logo)                                    
INSERT INTO HockeyTeam(id,name,logo)
^C
mysql> insert into HockeyTeam(id,name,logo)
    -> values('6','56','86');
Query OK, 1 row affected (0.01 sec)

mysql> desc HockeyTeamPlayer;
+--------------+-------------+------+-----+---------+-------+
| Field        | Type        | Null | Key | Default | Extra |
+--------------+-------------+------+-----+---------+-------+
| id           | int         | NO   | PRI | NULL    |       |
| hockeyTeamId | int         | NO   |     | NULL    |       |
| firstName    | varchar(25) | NO   |     | NULL    |       |
| lastName     | varchar(25) | NO   |     | NULL    |       |
| jerseyNum    | int         | YES  |     | NULL    |       |
| position     | varchar(30) | YES  |     | NULL    |       |
+--------------+-------------+------+-----+---------+-------+
6 rows in set (0.00 sec)

mysql> insert into HockeyTeamPlayer(id,hockeyTeamId,firstName,lastName,jerseyNum,position)
    ->  values('11','13','21','24','7','28');
Query OK, 1 row affected (0.00 sec)

mysql> desc RoundStats;
+---------------------+------+------+-----+---------+-------+
| Field               | Type | Null | Key | Default | Extra |
+---------------------+------+------+-----+---------+-------+
| id                  | int  | NO   | PRI | NULL    |       |
| numShutouts         | int  | YES  |     | NULL    |       |
| goalLeaderId        | int  | YES  |     | NULL    |       |
| assistLeaderId      | int  | YES  |     | NULL    |       |
| penaltyLeaderId     | int  | YES  |     | NULL    |       |
| plusMinusLeaderId   | int  | YES  |     | NULL    |       |
| faceoffsWonLeaderId | int  | YES  |     | NULL    |       |
| sogLeaderId         | int  | YES  |     | NULL    |       |
+---------------------+------+------+-----+---------+-------+
8 rows in set (0.00 sec)

mysql> insert into RoundStats(id,numShutouts,goalLeaderId,assistLeaderId,penaltyLeaderId,plusMinusLeaderId,faceoffsWonLeaderId,sogLeaderId)
    -> values('15','17','9','24','25','34','19','23');
Query OK, 1 row affected (0.01 sec)

mysql> desc User;
+----------+-------------+------+-----+---------+-------+
| Field    | Type        | Null | Key | Default | Extra |
+----------+-------------+------+-----+---------+-------+
| id       | int         | NO   | PRI | NULL    |       |
| username | varchar(50) | NO   |     | NULL    |       |
| password | varchar(50) | NO   |     | NULL    |       |
+----------+-------------+------+-----+---------+-------+
3 rows in set (0.00 sec)

mysql> insert into User(id,username,password
    -> )
    -> insert into User(id,username,password)
    ->  values('17','28','39');
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'insert into User(id,username,password)
 values('17','28','39')' at line 3
mysql> insert into User(id,username,password)
    ->  values('17','28','39');
Query OK, 1 row affected (0.01 sec)

mysql> desc UserInfo;
+--------------+-------------+------+-----+---------+-------+
| Field        | Type        | Null | Key | Default | Extra |
+--------------+-------------+------+-----+---------+-------+
| id           | int         | NO   | PRI | NULL    |       |
| firstName    | varchar(25) | NO   |     | NULL    |       |
| lastName     | varchar(25) | NO   |     | NULL    |       |
| email        | varchar(25) | NO   |     | NULL    |       |
| round1Points | int         | YES  |     | NULL    |       |
| round2Points | int         | YES  |     | NULL    |       |
| round3Points | int         | YES  |     | NULL    |       |
| round4Points | int         | YES  |     | NULL    |       |
+--------------+-------------+------+-----+---------+-------+
8 rows in set (0.00 sec)

mysql> insert into UserInfo(id,firstName,lastName,email,round1Points,round2Points,round3Points,round4Points)
    -> values('10','23','21','19','37','32','44','30');
Query OK, 1 row affected (0.00 sec)

mysql> desc UserScorePicks;
+--------------+------+------+-----+---------+-------+
| Field        | Type | Null | Key | Default | Extra |
+--------------+------+------+-----+---------+-------+
| id           | int  | NO   | PRI | NULL    |       |
| hockeyGameId | int  | NO   |     | NULL    |       |
| team1Score   | int  | NO   |     | NULL    |       |
| team2Score   | int  | NO   |     | NULL    |       |
| userId       | int  | NO   |     | NULL    |       |
+--------------+------+------+-----+---------+-------+
5 rows in set (0.00 sec)

mysql> insert into UserScorePicks(id,hockeyGameId,team1Score,team2Score,userId)
    -> values('45','33','55','22','37');
Query OK, 1 row affected (0.01 sec)

mysql> desc UserStatsPiks:;
+---------------------+------+------+-----+---------+-------+
    -> values('45','33','55','22','37');
| Field               | Type | Null | Key | Default | Extra |
+---------------------+------+------+-----+---------+-------+
| id                  | int  | NO   | PRI | NULL    |       |
| roundId             | int  | NO   |     | NULL    |       |
| goalLeaderId        | int  | YES  |     | NULL    |       |
| assistLeaderId      | int  | YES  |     | NULL    |       |
| penaltyLeaderId     | int  | YES  |     | NULL    |       |
| plusMinusLeaderId   | int  | YES  |     | NULL    |       |
| faceoffsWonLeaderId | int  | YES  |     | NULL    |       |
| sogLeaderId         | int  | YES  |     | NULL    |       |
| numShutouts         | int  | YES  |     | NULL    |       |
| userId              | int  | NO   |     | NULL    |       |
+---------------------+------+------+-----+---------+-------+
10 rows in set (0.01 sec)
mysql> insert into UserStatsPicks(id,roundId,goalLeaderId,assistLeaderId,penaltyLeaderId,plusMinusLeaderId,faceoffsWonLeaderId,sogLeaderId,numShutos
,userId)
    -> values('20','43','29','65','46','77','84','49','31','50');
Query OK, 1 row affected (0.00 sec)
mysql> desc UserStatsPicks;
+---------------------+------+------+-----+---------+-------+
| Field               | Type | Null | Key | Default | Extra |
+---------------------+------+------+-----+---------+-------+
| id                  | int  | NO   | PRI | NULL    |       |
| roundId             | int  | NO   |     | NULL    |       |
| goalLeaderId        | int  | YES  |     | NULL    |       |
| assistLeaderId      | int  | YES  |     | NULL    |       |
| penaltyLeaderId     | int  | YES  |     | NULL    |       |
| plusMinusLeaderId   | int  | YES  |     | NULL    |       |
| faceoffsWonLeaderId | int  | YES  |     | NULL    |       |
| sogLeaderId         | int  | YES  |     | NULL    |       |
| numShutouts         | int  | YES  |     | NULL    |       |
| userId              | int  | NO   |     | NULL    |       |
+---------------------+------+------+-----+---------+-------+
10 rows in set (0.00 sec)
