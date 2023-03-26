# plumbing

## Descripcion
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 7480`.

## Pistas
- Remember the flag format is picoCTF{XXXX}
- What's a pipe? No not that kind of pipe... This [kind](http://www.linfo.org/pipes.html)

## Solución

```
eltetor14-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 7480 > flag.txt
eltetor14-picoctf@webshell:~$ cat flag.txt | grep picoCTF
picoCTF{digital_plumb3r_06e9d954}
```

## Bandera
picoCTF{digital_plumb3r_06e9d954}

## Notas adicionales
Debes guardar lo que hay dentro de la conexion en un archivo txt y hacer un grep buscando la bandera.

## Referencias
