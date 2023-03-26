# Nice netcat

## Descripcion
There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 49039`, but it doesn't speak English...

## Pistas
- You can practice using netcat with this picoGym problem: [what's a netcat?](https://play.picoctf.org/practice/challenge/34)
- You can practice reading and writing ASCII with this picoGym problem: [Let's Warm Up](https://play.picoctf.org/practice/challenge/22)

## Solución

```
eltetor14-picoctf@webshell:~$ nc mercury.picoctf.net 49039 > flag.txt
eltetor14-picoctf@webshell:~$ python
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> x=open('flag.txt','r')
>>> for i in x:
...     print(chr(int(i)),end="")
... 
picoCTF{g00d_k1tty!_n1c3_k1tty!_3d84edc8}
>>> 
eltetor14-picoctf@webshell:~$ 
```

## Bandera
picoCTF{g00d_k1tty!_n1c3_k1tty!_3d84edc8}

## Notas adicionales

## Referencias