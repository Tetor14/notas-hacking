## Objetivo
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

## Datos de acceso al nivel
bandit11
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

## Solución

```
bandit11@bandit:~$ ls  
data.txt  
bandit11@bandit:~$ cat data.txt  
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi  
bandit11@bandit:~$ cat data.txt | tr [a-zA-Z] [n-za-mN-ZA-M]  
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv  
bandit11@bandit:~$
```

## Notas adicionales
grep, sort, uniq, strings

## Referencias
https://en.wikipedia.org/wiki/ROT13