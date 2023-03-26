# Based

## Descripcion
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29221`

## Pistas
- I hear python can convert things.
- It might help to have multiple windows open.

## Solución

```
eltetor14-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 29221
Let us see how data is stored
street
Please give the 01110011 01110100 01110010 01100101 01100101 01110100 as a word.
...
you have 45 seconds.....

Input:
street
Please give me the  164 141 142 154 145 as a word.
Input:
table
Please give me the 6e75727365 as a word.
Input:
nurse
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_00a975ff}
```

## Bandera
picoCTF{learning_about_converting_values_00a975ff}

## Notas adicionales
El problema te da varios valores para convertir, el primero es en binario pero ahi mismo te da la respuesta, el segundo es en octal y el tercero en hexadecimal, puedes hacer uso de herramientas en linea.

## Referencias
- https://www.rapidtables.com/convert/number/hex-to-ascii.html
- https://photo333.com/octal-to-text-es.php
- https://gchq.github.io/CyberChef/
