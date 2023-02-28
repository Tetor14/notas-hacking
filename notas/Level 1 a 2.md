## Objetivo
The password for the next level is stored in a file called **-** located in the home directory

## Datos de acceso al nivel
bandit1  
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

## Solución
```
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat -
^C
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$ pwd
/home/bandit1
bandit1@bandit:~$ cat /home/bandit1/-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$
```

## Notas adicionales
ls
cd
cat

## Referencias
https://www.webservertalk.com/dashed-filename
https://tldp.org/LDP/abs/html/special-chars.html
