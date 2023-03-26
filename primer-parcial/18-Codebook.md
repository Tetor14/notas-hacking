# Codebook

## Descripcion
Run the Python script `code.py` in the same directory as `codebook.txt`.

-   [Download code.py](https://artifacts.picoctf.net/c/2/code.py)
-   [Download codebook.txt](https://artifacts.picoctf.net/c/2/codebook.txt)


## Pistas
- On the webshell, use `ls` to see if both files are in the directory you are in
- The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución

```
eltetor14-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/2/codebook.txt
--2023-03-26 05:33:27--  https://artifacts.picoctf.net/c/2/codebook.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.6, 108.156.172.74, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.6|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: 'codebook.txt'

codebook.txt                                    100%[======================================================================================================>]      27  --.-KB/s    in 0s      

2023-03-26 05:33:28 (16.8 MB/s) - 'codebook.txt' saved [27/27]

eltetor14-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/2/code.py
--2023-03-26 05:33:42--  https://artifacts.picoctf.net/c/2/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.74, 108.156.172.120, 108.156.172.6, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: 'code.py'

code.py                                         100%[======================================================================================================>]   1.25K  --.-KB/s    in 0.001s  

2023-03-26 05:33:43 (844 KB/s) - 'code.py' saved [1278/1278]

eltetor14-picoctf@webshell:~$ python code.py
picoCTF{c0d3b00k_455157_7d102d7a}
eltetor14-picoctf@webshell:~$ 

```

## Bandera
picoCTF{c0d3b00k_455157_7d102d7a}

## Notas adicionales

## Referencias