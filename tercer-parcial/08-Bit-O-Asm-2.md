# Bit-O-Asm-2

## Descripción
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Download the assembly dump [here](https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt).

## Pistas
- `PTR`'s or 'pointers', reference a location in memory where values can be stored.

## Solución

```
eltetor14-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt
--2023-05-30 21:30:04--  https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.42, 108.156.172.6, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: 'disassembler-dump0_b.txt'

disassembler-dump0_b.txt                        100%[======================================================================================================>]     270  --.-KB/s    in 0s      

2023-05-30 21:30:04 (131 MB/s) - 'disassembler-dump0_b.txt' saved [270/270]

eltetor14-picoctf@webshell:~$ cat disassembler-dump0_a.txt
cat: disassembler-dump0_a.txt: No such file or directory
eltetor14-picoctf@webshell:~$ cat disassembler-dump0_b.txt
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    mov    eax,DWORD PTR [rbp-0x4]
<+25>:    pop    rbp
<+26>:    ret
eltetor14-picoctf@webshell:~$ 


┌──(kali㉿kali)-[~/SegRedySis]
└─$ grep 'mov.*eax' disassembler-dump0_b.txt                    
<+22>:    mov    eax,DWORD PTR [rbp-0x4]
 
┌──(kali㉿kali)-[~/SegRedySis]
└─$ grep '\[rbp-0x4\]' disassembler-dump0_b.txt
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    mov    eax,DWORD PTR [rbp-0x4]

┌──(kali㉿kali)-[~/SegRedySis]
└─$ grep "eax" disassembler-dump0_b.txt
<+22>:    mov    eax,DWORD PTR [rbp-0x4]

┌──(kali㉿kali)-[~/SegRedySis]
└─$ grep '\[rbp-0x4\]' disassembler-dump0_b.txt

<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    mov    eax,DWORD PTR [rbp-0x4]

┌──(kali㉿kali)-[~/SegRedySis]
└─$ echo $((0x9fe1a))
654874

```

## Bandera
picoCTF{654874}

## Notas adicionales

## Referencias
