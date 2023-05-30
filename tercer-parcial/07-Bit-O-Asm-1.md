# Bit-O-Asm-1

## Descripción
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Download the assembly dump [here](https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt).

## Pistas
- As with most assembly, there is a lot of noise in the instruction dump. Find the one line that pertains to this question and don't second guess yourself!

## Solución

```
eltetor14-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt
--2023-05-30 21:22:20--  https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.74, 108.156.172.42, 108.156.172.120, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 209 [application/octet-stream]
Saving to: 'disassembler-dump0_a.txt'

disassembler-dump0_a.txt                        100%[======================================================================================================>]     209  --.-KB/s    in 0s      

2023-05-30 21:22:20 (9.88 MB/s) - 'disassembler-dump0_a.txt' saved [209/209]

eltetor14-picoctf@webshell:~$ cat disassembler-dump0_a.txt
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x4],edi
<+11>:    mov    QWORD PTR [rbp-0x10],rsi
<+15>:    mov    eax,0x30
<+20>:    pop    rbp
<+21>:    ret
eltetor14-picoctf@webshell:~$ python
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> hex = '30'
>>> int(hex, 16)
48
>>> exit()
eltetor14-picoctf@webshell:~$ 
```

## Bandera
picoCTF{48}

## Notas adicionales

## Referencias
