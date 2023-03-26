# fixme1.py

## Descripcion
Fix the syntax error in this Python script to print the flag. [Download Python script](https://artifacts.picoctf.net/c/25/fixme1.py)

## Pistas
- Indentation is very meaningful in Python
- To view the file in the webshell, do: `$ nano fixme1.py`
- To exit `nano`, press Ctrl and x and follow the on-screen prompts.
- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución

```
eltetor14-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/25/fixme1.py
--2023-03-26 05:36:34--  https://artifacts.picoctf.net/c/25/fixme1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.6, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 837 [application/octet-stream]
Saving to: 'fixme1.py'

fixme1.py                                       100%[======================================================================================================>]     837  --.-KB/s    in 0s      

2023-03-26 05:36:34 (654 MB/s) - 'fixme1.py' saved [837/837]

eltetor14-picoctf@webshell:~$ python fixme1.py
  File "/home/eltetor14-picoctf/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
eltetor14-picoctf@webshell:~$ nano fixme1.py
eltetor14-picoctf@webshell:~$ python fixme1.py
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_6a476c8f}
eltetor14-picoctf@webshell:~$ 
```

## Bandera
picoCTF{1nd3nt1ty_cr1515_6a476c8f}

## Notas adicionales
En la ultima linea del codigo debes quitar la identación ya que no esta dentro de ningun ciclo o función.

## Referencias