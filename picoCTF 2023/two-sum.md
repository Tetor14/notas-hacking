# two-sum
## Descripción
Can you solve this? What two positive numbers can make this possible: `n1 > n1 + n2 OR n2 > n1 + n2` Enter them here `nc saturn.picoctf.net 63002`. [Source](https://artifacts.picoctf.net/c/453/flag.c)

## Pistas
- Not necessarily a math problem
- Integer overflow
## Solución
```bash
heligarcia-picoctf@webshell:~$ nc saturn.picoctf.net 62774
n1 > n1 + n2 OR n2 > n1 + n2 
What two positive numbers can make this possible: 
2147483647
1
You entered 2147483647 and 1
You have an integer overflow
YOUR FLAG IS: picoCTF{Tw0_Sum_Integer_Bu773R_0v3rfl0w_482d8fc4}
```

## Bandera
picoCTF{Tw0_Sum_Integer_Bu773R_0v3rfl0w_482d8fc4}

## Notas adicionales
El número 2147483647 al sumarle 1, se convierte en un número negativo.

## Referencias
None
