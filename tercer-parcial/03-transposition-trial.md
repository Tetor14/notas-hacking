# transposition-trial

## Descripción
Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message. Download the corrupted message [here](https://artifacts.picoctf.net/c/193/message.txt).

## Pistas
- Split the message up into blocks of 3 and see how the first block is scrambled

## Solución

```
eltetor14-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/193/message.txt
--2023-05-30 19:49:56--  https://artifacts.picoctf.net/c/193/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.74, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 54 [application/octet-stream]
Saving to: 'message.txt'

message.txt                                     100%[======================================================================================================>]      54  --.-KB/s    in 0s      

2023-05-30 19:49:56 (19.5 MB/s) - 'message.txt' saved [54/54]

eltetor14-picoctf@webshell:~$ cat message.txt
heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V9AAB1F8}7
eltetor14-picoctf@webshell:~$ 

Usamos el siguiente codigo para obtener la bandera
```

```
file = open("message.txt", "r", encoding="UTF-8")
txt = file.read()
n=3
anagrama = [txt[i:i+n] for i in range(0, len(txt), n)]
decode = []
for i in range(len(anagrama)):
        decode.append(anagrama[i][2]+anagrama[i][0]+anagrama[i][1])
        print(''.join(decode))
```

## Bandera
picoCTF{7R4N5P051N6_15_3XP3N51V3_A9AFB178}

## Notas adicionales

## Referencias
