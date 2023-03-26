# Wave a flag

## Descripcion
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/fc1d77192c544314efece5dd309092e3/warm) has extraordinarily helpful information...

## Pistas
- This program will only work in the webshell or another Linux computer.
- To get the file accessible in your shell, enter the following in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/fc1d77192c544314efece5dd309092e3/warm`
- Run this program by entering the following in the Terminal prompt: `$ ./warm`, but you'll first have to make it executable with `$ chmod +x warm`
- -h and --help are the most common arguments to give to programs to get more information from them!
- Not every program implements help features like -h and --help.

## Solución

```
eltetor14-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/fc1d77192c544314efece5dd309092e3/warm
--2023-03-25 06:56:05--  https://mercury.picoctf.net/static/fc1d77192c544314efece5dd309092e3/warm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 10936 (11K) [application/octet-stream]
Saving to: 'warm'

warm                                            100%[======================================================================================================>]  10.68K  --.-KB/s    in 0s      

2023-03-25 06:56:06 (246 MB/s) - 'warm' saved [10936/10936]

eltetor14-picoctf@webshell:~$ chmod +x warm
eltetor14-picoctf@webshell:~$ ./warm
Hello user! Pass me a -h to learn what I can do!
eltetor14-picoctf@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_6635aa47}
eltetor14-picoctf@webshell:~$
```

## Bandera
picoCTF{b1scu1ts_4nd_gr4vy_6635aa47}

## Notas adicionales

## Referencias
