# Static ain't always noise

## Descripcion
- Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/static)? This [BASH script](https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/ltdis.sh) might help!

## Pistas

## Solución

```
eltetor14-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/static
--2023-03-25 07:45:35--  https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/static
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8376 (8.2K) [application/octet-stream]
Saving to: 'static'

static                                          100%[======================================================================================================>]   8.18K  --.-KB/s    in 0s      

2023-03-25 07:45:35 (224 MB/s) - 'static' saved [8376/8376]

eltetor14-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/ltdis.sh
--2023-03-25 07:45:50--  https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/ltdis.sh
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 785 [application/octet-stream]
Saving to: 'ltdis.sh'

ltdis.sh                                        100%[======================================================================================================>]     785  --.-KB/s    in 0s      

2023-03-25 07:45:50 (508 MB/s) - 'ltdis.sh' saved [785/785]

eltetor14-picoctf@webshell:~$ ./ltdis.sh static
-bash: ./ltdis.sh: Permission denied
eltetor14-picoctf@webshell:~$ chmod +x ltdis.sh
eltetor14-picoctf@webshell:~$ ./ltdis.sh static
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
eltetor14-picoctf@webshell:~$ cat static.ltdis.strings.txt | grep pico
   1020 picoCTF{d15a5m_t34s3r_ae0b3ef2}
eltetor14-picoctf@webshell:~$ 
```

## Bandera
picoCTF{d15a5m_t34s3r_ae0b3ef2}

## Notas adicionales
Descarga los archivos necesarios para el desafio wget, para obtener los enlaces de los archivos copia el enlace de cada uno en la ventana del ejercicio.

## Referencias