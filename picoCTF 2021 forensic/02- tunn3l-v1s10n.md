# tunn3l v1s10n

## Descripcion
We found this [file](https://mercury.picoctf.net/static/01be2b38ba97802285a451b94505ea75/tunn3l_v1s10n). Recover the flag.

## Pistas
- Weird that it won't display right...

## Solución

```
eltetor14-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/21c07c9dd20cd9f2459a0ae75d99af6e/tunn3l_v1s10n
--2023-05-21 18:52:37--  https://mercury.picoctf.net/static/21c07c9dd20cd9f2459a0ae75d99af6e/tunn3l_v1s10n
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2893454 (2.8M) [application/octet-stream]
Saving to: 'tunn3l_v1s10n'

tunn3l_v1s10n                                   100%[======================================================================================================>]   2.76M  1.81MB/s    in 1.5s    

2023-05-21 18:52:39 (1.81 MB/s) - 'tunn3l_v1s10n' saved [2893454/2893454]
eltetor14-picoctf@webshell:~$ cp tunn3l_v1s10n tunn3l_v1s10n.bmp
eltetor14-picoctf@webshell:~$ exiftool tunn3l_v1s10n.bmp
ExifTool Version Number         : 12.40
File Name                       : tunn3l_v1s10n.bmp
Directory                       : .
File Size                       : 2.8 MiB
File Modification Date/Time     : 2023:03:29 23:35:05+00:00
File Access Date/Time           : 2023:03:29 23:35:05+00:00
File Inode Change Date/Time     : 2023:03:29 23:35:05+00:00
File Permissions                : -rw-rw-r--
File Type                       : BMP
File Type Extension             : bmp
MIME Type                       : image/bmp
BMP Version                     : Unknown (53434)
Image Width                     : 1134
Image Height                    : 306
Planes                          : 1
Bit Depth                       : 24
Compression                     : None
Image Length                    : 2893400
Pixels Per Meter X              : 5669
Pixels Per Meter Y              : 5669
Num Colors                      : Use BitDepth
Num Important Colors            : All
Red Mask                        : 0x27171a23
Green Mask                      : 0x20291b1e
Blue Mask                       : 0x1e212a1d
Alpha Mask                      : 0x311a1d26
Color Space                     : Unknown (,5%()
Rendering Intent                : Unknown (826103054)
Image Size                      : 1134x306
Megapixels                      : 0.347
eltetor14-picoctf@webshell:~$ stat tunn3l_v1s10n.bmp | grep Size
  Size: 2893454         Blocks: 5656       IO Block: 4096   regular file

eltetor14-picoctf@webshell:~$ xxd -g 1 tunn3l_v1s10n.bmp | head -1
00000000: 42 4d 8e 26 2c 00 00 00 00 00 36 00 00 00 28 00  BM.&,.....6...(.

eltetor14-picoctf@webshell:~$ xxd -g 1 tunn3l_v1s10n.bmp | head -2
00000000: 42 4d 8e 26 2c 00 00 00 00 00 36 00 00 00 28 00  BM.&,.....6...(.
00000010: 00 00 6e 04 00 00 52 03 00 00 01 00 18 00 00 00  ..n...R.........
```

## Bandera
picoCTF{qu1t3_a_v13w_2020}

## Notas adicionales

## Referencias