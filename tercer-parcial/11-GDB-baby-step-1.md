# GDB baby step 1

## Descripción
Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Disassemble [this](https://artifacts.picoctf.net/c/512/debugger0_a).

## Pistas
- gdb is a very good debugger to use for this problem and many others!
- `main` is actually a recognized symbol that can be used with gdb commands.

## Solución

```
eltetor14-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/512/debugger0_a
--2023-05-30 22:49:38--  https://artifacts.picoctf.net/c/512/debugger0_a
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.6, 108.156.172.74, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16472 (16K) [application/octet-stream]
Saving to: 'debugger0_a'

debugger0_a                                     100%[======================================================================================================>]  16.09K  --.-KB/s    in 0.006s  

2023-05-30 22:49:38 (2.54 MB/s) - 'debugger0_a' saved [16472/16472]

eltetor14-picoctf@webshell:~$ chmod +x debugger0_a
eltetor14-picoctf@webshell:~$ gdb ./debugger0_a
GNU gdb (Ubuntu 12.0.90-0ubuntu1) 12.0.90
Copyright (C) 2022 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from ./debugger0_a...
(No debugging symbols found in ./debugger0_a)
(gdb) run
Starting program: /home/eltetor14-picoctf/debugger0_a 
warning: Error disabling address space randomization: Operation not permitted
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".
[Inferior 1 (process 300) exited with code 0102]
(gdb) break *main+48
Breakpoint 1 at 0x55ece5992159
(gdb) continue
The program is not being run.
(gdb) print $eax
No registers.
(gdb) run
Starting program: /home/eltetor14-picoctf/debugger0_a 
warning: Error disabling address space randomization: Operation not permitted
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x0000556c4e2ee159 in __libc_csu_init ()
(gdb) continue
Continuing.
[Inferior 1 (process 303) exited with code 0102]
(gdb) print $eax
No registers.
(gdb) run
Starting program: /home/eltetor14-picoctf/debugger0_a 
warning: Error disabling address space randomization: Operation not permitted
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x00005598f1903159 in __libc_csu_init ()
(gdb) print $eax
$1 = -753475072
(gdb) continue
Continuing.
[Inferior 1 (process 304) exited with code 0102]
(gdb) disassemble main
Dump of assembler code for function main:
   0x00005598f1903129 <+0>:     endbr64 
   0x00005598f190312d <+4>:     push   %rbp
   0x00005598f190312e <+5>:     mov    %rsp,%rbp
   0x00005598f1903131 <+8>:     mov    %edi,-0x4(%rbp)
   0x00005598f1903134 <+11>:    mov    %rsi,-0x10(%rbp)
   0x00005598f1903138 <+15>:    mov    $0x86342,%eax
   0x00005598f190313d <+20>:    pop    %rbp
   0x00005598f190313e <+21>:    ret    
End of assembler dump.
(gdb) break *main+21
Breakpoint 2 at 0x5598f190313e
(gdb) run
Starting program: /home/eltetor14-picoctf/debugger0_a 
warning: Error disabling address space randomization: Operation not permitted
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x000055e4dece4159 in __libc_csu_init ()
(gdb) continue
Continuing.

Breakpoint 2, 0x000055e4dece413e in main ()
(gdb) print $eax
$2 = 549698
(gdb) q
A debugging session is active.

        Inferior 1 [process 305] will be killed.

Quit anyway? (y or n) y
```

## Bandera
picoCTF{549698}

## Notas adicionales

## Referencias
