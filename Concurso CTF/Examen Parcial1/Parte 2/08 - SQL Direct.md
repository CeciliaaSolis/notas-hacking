
## Descripción

*Connect to this PostgreSQL server and find the flag!*
 psql -h saturn.picoctf.net -p 61888 -U postgres pico

Password is `postgres`
## Pistas

*What does a SQL database contain?*
## Solución


```
ceciSolis-picoctf@webshell:~$ psql -h saturn.picoctf.net -p 61888 -U postgres pico
Password for user postgres: 
psql (14.17 (Ubuntu 14.17-0ubuntu0.22.04.1), server 15.2 (Debian 15.2-1.pgdg110+1))
WARNING: psql major version 14, server major version 15.
         Some psql features might not work.
Type "help" for help.

pico=# \l
                                 List of databases
   Name    |  Owner   | Encoding |  Collate   |   Ctype    |   Access privileges   
-----------+----------+----------+------------+------------+-----------------------
 pico      | postgres | UTF8     | en_US.utf8 | en_US.utf8 | 
 postgres  | postgres | UTF8     | en_US.utf8 | en_US.utf8 | 
 template0 | postgres | UTF8     | en_US.utf8 | en_US.utf8 | =c/postgres          +
           |          |          |            |            | postgres=CTc/postgres
 template1 | postgres | UTF8     | en_US.utf8 | en_US.utf8 | =c/postgres          +
           |          |          |            |            | postgres=CTc/postgres
(4 rows)

pico=# \dt
         List of relations
 Schema | Name  | Type  |  Owner   
--------+-------+-------+----------
 public | flags | table | postgres
(1 row)

pico=# select * from flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)

pico=# 
```
picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}
## Notas Adicionales 


*Entramos ya que estamos en postgres, usamos \l para que nos liste la base de datos, despiues \dt para ver list tables y vemos las columnas como hay una de flags, la usamos con select *from flags y nos muestra la tabla y en luke esta la bandera.
## Referencias 
