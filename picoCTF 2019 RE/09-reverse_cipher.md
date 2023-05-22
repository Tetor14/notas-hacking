# reverse_cipher

## Descripcion
We have recovered a [binary](https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev) and a [text file](https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev_this). Can you reverse the flag.

## Pistas
- objdump and Gihdra are some tools that could assist with this

## Solución

```
eltetor14-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev
--2023-05-21 23:42:03--  https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16856 (16K) [application/octet-stream]
Saving to: 'rev'

rev                                             100%[======================================================================================================>]  16.46K  --.-KB/s    in 0s      

2023-05-21 23:42:03 (275 MB/s) - 'rev' saved [16856/16856]

eltetor14-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev_this
--2023-05-21 23:42:17--  https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev_this
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 24 [application/octet-stream]
Saving to: 'rev_this'

rev_this                                        100%[======================================================================================================>]      24  --.-KB/s    in 0s      

2023-05-21 23:42:17 (10.9 MB/s) - 'rev_this' saved [24/24]

eltetor14-picoctf@webshell:~$ cat rev
rev       rev_this  
eltetor14-picoctf@webshell:~$ cat rev_this 
picoCTF{w1{1wq85jc=2i0<}
eltetor14-picoctf@webshell:~$ nano exp.py
eltetor14-picoctf@webshell:~$ exp.py
r3v3rs37ee84d27
```

## Codigo

```
c = open('rev_this','r').read()

flag = ''

for i in range(8, len(c)-1):
	if i & 1 == 0:
		flag += chr( ord(c[i]) - 5 )
	else:
		flag += chr( ord(c[i]) + 2 )
print(flag)
```

## Bandera
picoCTF{r3v3rs37ee84d27}

## Notas adicionales

## Referencias