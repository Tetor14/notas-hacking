## Descripcion
The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://artifacts.picoctf.net/c/261/flag.png).
## Pistas 
****** 
## Solucion
```
xxd flag.png
0000a750: 2a0b 0000 c70b 0000 0f00 1800 0000 0000  *...............
0000a760: 0000 0000 a481 4100 0000 7365 6372 6574  ......A...secret
0000a770: 2f66 6c61 672e 706e 6755 5405 0003 9378  /flag.pngUT....x
0000a780: 1264 7578 0b00 0104 0000 0000 0400 0000  .dux............
0000a790: 0050 4b05 0600 0000 0002 0002 00a2 0000  .PK.............
0000a7a0: 00b4 0b00 0000 00                        .......
jt@jt-VirtualBox:~/Downloads$ unzip flag.png
```
## bandera
picoCTF{Hiddinng_An_imag3_within_@n_ima9e_96539bea}

## Notas adicionales 

## Referencias