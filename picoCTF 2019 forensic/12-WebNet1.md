# WebNet1

## Descripcion
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.

## Pistas
-  Try using a tool like Wireshark.
-  How can you decrypt the TLS stream?

## Solución

```
Descarga el archivo y la llave y corre el siguiente comando para obtener la bandera:
-r capture.pcap -k picopico.key -d | grep pico -A 2
```

## Bandera
picoCTF{honey.roasted.peanuts}

## Notas adicionales

## Referencias