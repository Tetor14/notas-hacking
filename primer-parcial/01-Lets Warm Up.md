## Lets Warm Up

## Descripcion
If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?

## Pistas
- Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{hello}' as the flag


## Solución

```
>>> int(0x70)
112
>>> chr(112)
'p'
>>> chr(0x70)
'p'
>>> 
```

## Bandera
picoCTF{p}

## Notas adicionales
chr

## Referencias