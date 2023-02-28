## Objetivo
The password for the next level is stored in the file **data.txt** next to the word **millionth**

## Datos de acceso al nivel
bandit7
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

## Solución

```
bandit7@bandit:~$ ls  
data.txt  
bandit7@bandit:~$ wc data.txt  
98567 197133 4184396 data.txt  
bandit7@bandit:~$ grep millionth data.txt  
millionth TESKZC0XvTetK0S9xNwm25STk5iWrBvP  
bandit7@bandit:~$ cat data.txt | grep millionth  
millionth TESKZC0XvTetK0S9xNwm25STk5iWrBvP  
bandit7@bandit:~$
```

## Notas adicionales
man, grep, sort, uniq

## Referencias
https://overthewire.org/wargames/bandit/bandit8.html