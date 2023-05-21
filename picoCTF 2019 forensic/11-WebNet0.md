# WebNet0

## Descripcion
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.

## Pistas
- Try using a tool like Wireshark.
- How can you decrypt the TLS stream?
## Solución

```
Descarga el archivo y la llave y corre el siguiente comando para obtener la bandera:
-r capture.pcap -k picopico.key -d | grep pico -A 2
```

## Bandera
picoCTF{nongshim.shrimp.crackers}

## Notas adicionales

## Referencias