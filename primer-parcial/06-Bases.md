# Bases

## Descripcion
What does this `bDNhcm5fdGgzX3IwcDM1` mean? I think it has something to do with bases.

## Pistas
- Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{hello}' as the flag.

## Solución

```
eltetor14-picoctf@webshell:~$ python
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import base64
>>> base64.b64decode("bDNhcm5fdGgzX3IwcDM1")
b'l3arn_th3_r0p35'
>>> 
```

## Bandera
picoCTF{l3arn_th3_r0p35}

## Notas adicionales
Se debe importar la libreria base64.

## Referencias
