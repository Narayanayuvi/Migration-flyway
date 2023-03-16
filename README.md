# Migration-flyway
Flyway Migration for REGISTRATION_USERS Table :
-------------------------------------------------------

Objective :
--------------

      To create and update the REGISTRATION_USERS table using Flyway migration tool.

Prerequisites :
-----------------

     1.Flyway installed and configured
     >~INSTALL BY USING THIS LINK  [Google](https://flywaydb.org/documentation.com "Google Search")~
     2.MySQL server running
     3.Database and schema created

Steps
---------
Step 1 : 
>Create Migration Script V1__create_users_table.sql
--------------------------------------------------    
     CREATE TABLE REGISTRATION_USERS (
     id bigint(20) NOT NULL AUTO_INCREMENT,
     username varchar(100) NOT NULL,
     first_name varchar(50) NOT NULL,
     last_name varchar(50) DEFAULT NULL,
     email varchar(50) NOT NULL,
     PRIMARY KEY (id),
     UNIQUE KEY UK_username (username)
     ) ENGINE=InnoDB DEFAULT CHARSET=utf8;


Step 2 :
>Apply Migration
-----------------

      By using flyway migrate command in CMD.


  
Step 3 :
>Create Migration Script V1.1__updatemobile_table.sql
-----------------------------------------------------
        ALTER TABLE REGISTRATION_USERS 
        ADD COLUMN mobile VARCHAR(11) AFTER last_name;

Step 4 : 
>Create Migration Script V1.2__Insertdata_users_table.sql
---------------------------------------------------------
        
        INSERT INTO REGISTRATION_USERS(username,first_name,last_name,email,mobile) VALUES('peravali narayana','peravali','narayana','peravalinarayana@gmail.com','7731052033');
        INSERT INTO REGISTRATION_USERS(username,first_name,last_name,email,mobile) VALUES('Bala sai','Bala','Sai','balasai@gmail.com','8886666973');

Step 5 : 
>Create Migration Script V1.3__Dropcolumn_users_table.sql
----------------------------------------------------------

        ALTER TABLE registration_users DROP COLUMN first_name;

Step 6 : 
>Apply Migration
-----------------

      By using flyway migrate command in CMD.

Step 7 : 
>Apply Info
------------ 
     
       By using flyway info command in CMD.
       we are getting
    
+-----------+---------+------------------------+------+---------------------+---------+----------+
| Category  | Version | Description            | Type | Installed On        | State   | Undoable |
+-----------+---------+------------------------+------+---------------------+---------+----------+
| Versioned | 1       | create users table     | SQL  | 2023-03-13 17:26:01 | Success | No       |
| Versioned | 1.1     | updatemobile table     | SQL  | 2023-03-13 17:46:37 | Success | No       |
| Versioned | 1.2     | Insertdata users table | SQL  | 2023-03-13 18:08:24 | Success | No       |
| Versioned | 1.3     | Dropcolumn users table | SQL  | 2023-03-13 18:25:08 | Success | No       |
+-----------+---------+------------------------+------+---------------------+---------+----------+


Conclusion :
-----------------

  You have successfully update ,created ,insert and delete the REGISTRATION_USERS table using Flyway migration tool. 

     
