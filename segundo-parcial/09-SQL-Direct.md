# SQL Direct

## Descripcion
Connect to this PostgreSQL server and find the flag! `psql -h saturn.picoctf.net -p 51299 -U postgres pico` Password is `postgres`

## Pistas
- What does a SQL database contain?

## Solución

```
eltetor14-picoctf@webshell:~$ psql -h saturn.picoctf.net -p 51299 -U postgres pico
Password for user postgres: 
psql (14.5 (Ubuntu 14.5-0ubuntu0.22.04.1), server 15.2 (Debian 15.2-1.pgdg110+1))
WARNING: psql major version 14, server major version 15.
         Some psql features might not work.
Type "help" for help.

pico=# select * from flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)

pico=# ^C
pico=# 
```

## Bandera
picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}

## Notas adicionales

## Referencias

