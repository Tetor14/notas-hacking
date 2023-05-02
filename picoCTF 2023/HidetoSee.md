# HideToSee

## Descripcion
How about some hide and seek heh? Look at this image [here](https://artifacts.picoctf.net/c/240/atbash.jpg).

## Pistas
- Download the image and try to extract it.

## Solución

```
eltetor14-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/240/atbash.jpg
--2023-05-02 00:33:21--  https://artifacts.picoctf.net/c/240/atbash.jpg
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.74, 108.156.172.42, 108.156.172.6, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 51508 (50K) [application/octet-stream]
Saving to: 'atbash.jpg'

atbash.jpg              100%[============================>]  50.30K  --.-KB/s    in 0.02s   

2023-05-02 00:33:22 (2.22 MB/s) - 'atbash.jpg' saved [51508/51508]

eltetor14-picoctf@webshell:~$ steghide extract -sf atbash.jpg
Enter passphrase: 
wrote extracted data to "encrypted.txt".
eltetor14-picoctf@webshell:~$ cat encrypted.txt
krxlXGU{zgyzhs_xizxp_xz00558y}
eltetor14-picoctf@webshell:~$ 
```

## Bandera
picoCTF{atbash_crack_ca00558b}

## Notas adicionales
La palabra esta encriptada en AtBash

## Referencias