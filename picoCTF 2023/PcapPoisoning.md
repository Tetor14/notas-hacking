## Descripcion
How about some hide and seek heh? Download this [file](https://artifacts.picoctf.net/c/376/trace.pcap) and find the flag.

## Pistas 
****** 
## Solucion

```
wireshark trace.pcap
```
follow tcp stream
then
tcp.stream eq 1
```
507	0.101285	172.16.0.2	10.253.0.6	TCP	82	[TCP Retransmission] [TCP Port numbers reused] 20 → 21 [SYN] Seq=0 Win=8192 Len=42

0000   45 00 00 52 00 01 00 00 40 06 c3 90 ac 10 00 02   E..R....@.......
0010   0a fd 00 06 00 14 00 15 00 00 00 00 00 00 00 00   ................
0020   50 02 20 00 b0 19 00 00 70 69 63 6f 43 54 46 7b   P. .....picoCTF{
0030   50 36 34 50 5f 34 4e 34 4c 37 53 31 53 5f 53 55   P64P_4N4L7S1S_SU
0040   35 35 33 35 35 46 55 4c 5f 66 36 32 31 66 61 33   55355FUL_f621fa3
0050   37 7d                                             7}

```
## bandera
picoCTF{P64P_4N4L7S1S_SU55355FUL_f621fa37}

## Notas adicionales 

## Referencias