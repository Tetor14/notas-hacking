# PW Crack 1

## Descripcion
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/12/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/12/level1.flag.txt.enc) in the same directory too.

## Pistas
- To view the file in the webshell, do: `$ nano level1.py`
- To exit `nano`, press Ctrl and x and follow the on-screen prompts.
- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución

```
eltetor14-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/12/level1.py
--2023-03-26 05:53:52--  https://artifacts.picoctf.net/c/12/level1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.6, 108.156.172.120, 108.156.172.74, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.6|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 876 [application/octet-stream]
Saving to: 'level1.py'

level1.py                                       100%[======================================================================================================>]     876  --.-KB/s    in 0s      

2023-03-26 05:53:52 (953 MB/s) - 'level1.py' saved [876/876]

eltetor14-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/12/level1.flag.txt.enc
--2023-03-26 05:54:04--  https://artifacts.picoctf.net/c/12/level1.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.6, 108.156.172.74, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 30 [application/octet-stream]
Saving to: 'level1.flag.txt.enc'

level1.flag.txt.enc                             100%[======================================================================================================>]      30  --.-KB/s    in 0s      

2023-03-26 05:54:04 (32.7 MB/s) - 'level1.flag.txt.enc' saved [30/30]

eltetor14-picoctf@webshell:~$ nano level1.py
eltetor14-picoctf@webshell:~$ python level1.py
Please enter correct password for flag: 8713
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_1b2fd683}
eltetor14-picoctf@webshell:~$ 
```

## Bandera
picoCTF{545h_r1ng1ng_1b2fd683}

## Notas adicionales
Abre el codigo para ver la clave.

## Referencias

